# MEMÒRIA TÈCNICA – PROPOSTA PER A FOODLOGÍSTIC S.A.

![](/Productes/P01/images/imatge1.png)

**Autors:** Marc Jurado i Martí Codony  
**Data:** 4 de maig de 2026  

https://docs.google.com/document/d/1hyW8ebolwct2gJBrbkYNrRjhxwXY9NqXU85z-k85kOE/edit?usp=sharing

---

## TAULA DE CONTINGUTS

| Apartat | Pàgina |
|--------|--------|
| 1. Introducció | 3 |
| 2. Anàlisi de necessitats | 5 |
| 3. Proposta de solució | 9 |
| 3.1 Infraestructura (T01) | 15 |
| 3.2 Serveis al núvol (T07) | 16 |
| 3.3 Seguretat i LOPD (T05 i T06) | 17 |
| 3.4 Presència web (T02) | 17 |
| 4. Arquitectura i disseny tècnic | 18 |
| 5. Pressupost (T10) | 24 |
| 6. Planificació (T09) | 31 |
| 7. Conclusions | 36 |

---

## 2. INTRODUCCIÓ

### Què ens ha demanat el client?

FoodLogístic S.A. és una empresa de logística de menjar que està a Mataró. Tenen 35 treballadors i han crescut molt. El problema és que els seus sistemes informàtics són vells i donen molts problemes.

1. Servidors que no fallen mai com de fitxers i de impressores que són els treballats  
2. Correu electrònic al núvol  
3. Seguretat i compliment de la llei (LOPD)  
4. Pàgina web nova i legal

---

### Qui som?

Som una empresa de Mataró que arregla ordinadors i servidors. Volem donar un servei proper, ràpid i de confiança.

---

### Tasques del projecte

- T01.Estudi competència  
- T02. Web corporativa  
- T03. Servidor de Fitxers  
- T04. Servidor d’impressió  
- T05. Vídeo formatiu LOPD empleats  
- T06. Adaptació web normativa legal  
- T07. Solució correu cloud  
- T08. Tria de la web definitiva  
- T09. Estimació temporal de projecte  
- T10. Pressupost del projecte  

---

### Productes finals

- P01. Proposta tècnica i dossier  
- P02. Web corporativa publicada  
- P03. Repositori Github  

---

## 2. ANÀLISI DE NECESSITATS

┌─────────────────────────────────────────────────────────────────────────────┐
│                    PROBLEMES DETECTATS A FOODLOGÍSTIC                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│      ABANS                                     DESPRÉS                   │
│                                                                             │
│   ┌─────────────────────┐                   ┌─────────────────────┐       │
│   │ Fitxers perduts     │                   │ Tot centralitzat    │       │
│   │ per tots cantons    │      ──────►      │ al servidor         │       │
│   └─────────────────────┘                   └─────────────────────┘       │
│                                                                             │
│   ┌─────────────────────┐                   ┌─────────────────────┐       │
│   │ Impressora es penja  │                   │ 2 impressores       │       │
│   │ i no imprimeix      │      ──────►      │ treballant juntes   │       │
│   └─────────────────────┘                   └─────────────────────┘       │
│                                                                             │
│   ┌─────────────────────┐                   ┌─────────────────────┐       │
│   │ Correu antic        │                   │ Correu al núvol     │       │
│   │ i inestable         │      ──────►      │ (sempre funciona)   │       │
│   └─────────────────────┘                   └─────────────────────┘       │
│                                                                             │
│   ┌─────────────────────┐                   ┌─────────────────────┐       │
│   │ Web sense legal     │                   │ Web 100% legal      │       │
│   │ (poden tenir multa) │      ──────►      │ (avís legal, cookies│       │
│   └─────────────────────┘                   └─────────────────────┘       │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

---


### Quins problemes té FoodLogístic ara mateix?

1. Fitxers perduts  
2. Impressores que fallen  
3. Correu electrònic dolent  
4. No compleixen la llei

---

### Detall problemes

1. Fitxers perduts  
Cada treballador guarda els documents al seu ordinador  
Si es trenca l'ordinador, es perden els albarans  

2. Impressores que fallen  
Quan una impressora es trenca, no poden imprimir etiquetes  
Els camions no poden sortir  

3. Correu electrònic dolent  
El servidor de correu es penja sovint  
Perden correus importants  

4. No compleixen la llei  
La web no té avís legal ni política de cookies  
Poden tenir una multa  

---

### Què ens ha demanat exactament el client?

- Servidor de fitxers en alta disponibilitat  
- Servidor d’impressió en alta disponibilitat  
- Correu al núvol  
- Web legal  

---

### Competència

Informàtic Mataró  
Sisticat  
JSM Consultoria  

---

### Organigrama d'una empresa del sector:

Direcció General
├── Departament Tècnic
│   ├── Sistemes (servidors, xarxes)
│   └── Helpdesk (suport)
├── Departament Comercial
└── Administració

---

### Quina és la nostra estratègia?

Volem ser millors que la competència amb:
Resposta ràpida (menys de 4 hores)
Preu clar (sense sorpreses)
Servei personalitzat (tracte directe)

---

### Quanta gent necessitem?

Tècnic de Sistemes 1 persona servidor i xarxes
Tècnic Helpdesk 1 persona suport  i tambe incidències
Comercial 0.5 persones buscant clients
i finalment Administració 0.25 mitja de persones amb factures

Conclusió: Amb 2 persones podem començar. Amb 3 donem un bon servei.

---

## 3. PROPOSTA DE SOLUCIÓ


### TASQUES T03:

Estructura de carpetes i permisos:

┌─────────────────────────────────────────────────────────────────────────────┐
│                         SERVIDOR DE FITXERS                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐             │
│  │     Public      │  │   Operacions    │  │   Direcció$     │             │
│  │                 │  │                 │  │   (oculta)      │             │
│  ├─────────────────┤  ├─────────────────┤  ├─────────────────┤             │
│  │ UNC:            │  │ UNC:            │  │ UNC:            │             │
│  │ \\servidor\     │  │ \\servidor\     │  │ \\servidor\     │             │
│  │ Public          │  │ Operacions      │  │ Direcció$       │             │
│  ├─────────────────┤  ├─────────────────┤  ├─────────────────┤             │
│  │ Grups:          │  │ Grups:          │  │ Grups:          │             │
│  │ Tothom          │  │ Transport       │  │ Direccio        │             │
│  ├─────────────────┤  ├─────────────────┤  ├─────────────────┤             │
│  │ Permisos:       │  │ Permisos:       │  │ Permisos:       │             │
│  │ Lectura/Escript │  │ Lectura/Escript │  │ Lectura/Escript │             │
│  ├─────────────────┤  ├─────────────────┤  ├─────────────────┤             │
│  │ Mètode:         │  │ Mètode:         │  │ Mètode:         │             │
│  │ Explorador      │  │ Server Manager  │  │ PowerShell      │             │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘             │
│                                                                             │

---


![](/Productes/P01/images/imatge2.png)

---

![](/Productes/P01/images/imatge3.png)

---

![](/Productes/P01/images/imatge4.png)

---

![](/Productes/P01/images/imatge5.png)

---


![](/Productes/P01/images/imatge6.png)

---

![](/Productes/P01/images/imatge7.png)

---

![](/Productes/P01/images/imatge40.png)

### 3.1 Infraestructura (relatiu a la T01)

Aquesta secció explica com està organitzada la nostra empresa per poder donar servei a FoodLogístic.

Hem creat una estructura clara per repartir la feina:
Direcció General
├── Departament Tècnic
│   ├── Sistemes (servidors, xarxes, seguretat)
│   └── Helpdesk / Suport (atenció a incidències)
├── Departament Comercial
└── Administració

---

### Què fa cada departament?

Departament             Funcions

Direcció General Gestionar l'empresa, prendre decisions
Departamen               Tècnic I Coordinar projectes IT
Sistemes               Servidors, xarxes, còpies de seguretat
Helpdesk               Atendre incidències i suport remot
Comercial               Buscar clients, fer pressupostos
Administració Facturació, comptabilitat, RRHH

---

### Quanta gent necessitem?

Tècnic de Sistemes 1 persona servidor i xarxes
Tècnic Helpdesk 1 persona suport  i tambe incidències
Comercial 0.5 persones buscant clients
i finalment Administració 0.25 mitja de persones amb factures

Conclusió: Amb 2 persones podem començar. Amb 3 donem un bon servei.

---

### 3.2 Serveis al núvol (T07)

Què hem de fer?
Canviar el correu antic per un de nou al núvol.

Quines opcions hem mirat?

![](/Productes/P01/images/imatge8.png)

---

![](/Productes/P01/images/imatge9.png)

---

### Seguretat i LOPD (T05 i T06)

Hem fet dos vídeos de 5 minuts.

### Vídeo 1 (per a tothom):
Bloquejar l'ordinador amb Windows + L
No guardar dades al núvol personal
No connectar USBs desconeguts
Triturar documents importants

### Vídeo 2 (per a RRHH):

Guardar currículums legalment
Què és un responsable de dades
Drets ARSULIPO

---

### 3.4 Presència web

Hem creat una web en local, amb dues carpetes on ens demanava codi de docs amb index.html i css i algun que altre js de java, ens demanava que creesim una web per foodlogistic, ho hem fet, despres haviem de implementar la web amb Avís legal, Política de privacitat, Política de cookies, Banner de cookies, Checkbox d'acceptació, Checkbox de newsletter.


---

## 4. ARQUITECTURA I DISSENY TÈCNIC

![](/Productes/P01/images/imatge10.png)

---

## Quines pàgines té la web?

index.html     Pàgina principal (landing page)
avis-legal.html    Avís legal (obligatori per llei)
politica-privacitat.html  Política de privacitat
politica-cookies.html      Política de cookies
dades.html                            Informació de protecció de dades

---

![](/Productes/P01/images/imatge11.png)

---

![](/Productes/P01/images/imatge12.png)

---

![](/Productes/P01/images/imatge13.png)

---

![](/Productes/P01/images/imatge14.png)

---

![](/Productes/P01/images/imatge15.png)

---

### Com vam triar aquesta web? (T08)

Nosaltres per decidir quina web presentàvem al client vam fer:

Reflexió individual – cadascú va escriure què li agradava de la seva web
Debat en equip – vam compartir idees
Negociació – vam votar les millors parts
Web final – vam la millor de cada un i vam implementar alguna cosa del altre

La web final està publicada aquí:

marcjurado983.github.io/web-corporativa/

---

### Estadístiques (StatCounter)

![](/Productes/P01/images/imatge16.png)

---

![](/Productes/P01/images/imatge17.png)

---

## PRESSUPOST (T10)

A continuació presentem la proposta econòmica per a la modernització dels sistemes de FoodLogístic S.A. , una empresa de 35 treballadors situada a Mataró.

El pressupost es divideix en:
-Implantació (pagament únic)
-Manteniment recurrent (pagament mensual)

Els preus per hora estan basats en una investigació de mercat real a la zona del Maresme.

---

### Cost d'Implantació (Pagament únic)


### Maquinari i Programari

Domini.com  Registre de foodlogistic.com per 1 any EL TOTAL 12,50 €
Certificat SSL Inclòs amb GitHub Pages EL TOTAL  0 €
Llicències Windows Server Ja les tenen (Directori Actiu existent) EL TOTAL  0 €
PDF24 Programari gratuït per a impressió EL TOTAL 0 €

---

### HONORARIS - Àrea 1: Infraestructura

Servidor de fitxers Crear carpetes, permisos NTFS/SMB, quotes, FSRM, proves
Servidor d'impressió Instal·lar PDF24, Printer Pooling, GPO, proves de càrrega

6 h i 4h de preus els dos 45 € preu/hora  total de fitxers 270 € i de impressió 180 €

---

### HONORARIS - Àrea 2: Serveis al núvol

Estudi de mercat cloud  2 h
Comparar Microsoft 365, Google Workspace, Zoho 50 € preu/hora que serien en TOTAL 100 €

Migració a Microsoft 365 5 h
Crear 35 usuaris, configurar domini, migrar correus 50 € preu/hora ue serien en TOTAL 250€

---

### HONORARIS - Àrea 3: Seguretat i LOPD

Vídeo formatiu LOPD (general) 3 h
Guió, gravació, edició, pujada a YouTube 40 € preu/hora que serien en TOTAL 120€

Vídeo formatiu LOPD (RRHH) 3 h
Guió, gravació, edició, pujada a YouTube 40 € preu/hora que serien en TOTAL 120€

Adaptació web legal 2 h
Afegir avís legal, política privacitat, política cookies preu/hora que serien 40 € i en TOTAL 80€

Banner de cookies i checkboxes 2 h
Programar banner, dos checkboxes al formulari preu/hora que serien 40 € i en TOTAL 80€

---

### HONORARIS - Àrea 4: Presència web


Disseny web (landing page) 5 h
HTML, CSS, JavaScript, formulari de contacte, responsive preu/hora que serien 40 € i en TOTAL 200€

Desplegament GitHub Pages 1 h
Configurar repositori, /docs, StatCounter preu/hora que serien 40 € i en TOTAL 40€

---

### COORDINACIÓ DEL PROJECTE

Cap de projecte 4 h
Reunions amb client, planificació, documentació, seguiment preu/hora que serien 60 € i en TOTAL 240€

TOTAL MAQUINARI I PROGRAMARI 12,50 €
TOTAL HONORARIS 1.680 €
TOTAL IMPLANTACIÓ 1.692,50 €

---

### Costos Recurrents (Manteniment mensual)

### PLATAFORMA SaaS

Llicència Microsoft 365 Business Standard
Per usuari: 10,90 €/mes (facturació anual)
35 × 10,90 €   TOTAL: 381,50 €

### ALLOTJAMENT I DOMINI

Hosting (GitHub Pages) Gratuït

Domini .com (foodlogistic.com) Renovació anual (12,50 € l'any)
12,50 € ÷ 12 TOTAL: 1,04 €

### SUPORT I MANTENIMENT PREVENTIU

Manteniment web
Actualitzacions de seguretat, còpies de seguretat, revisions TOTAL: 50 €

Suport IT
Resolució d'incidències, assessorament, gestió de llicències, còpies de seguretat SaaS
8 h × 45 € TOTAL:360 €

### TOTAL MENSUAL 792,54 €
### TOTAL ANUAL 9.510,48 €
---

### Justificació de la proposta

D'on hem tret els preus per hora?

Hem investigat els preus de mercat a Mataró i rodalies consultant tres empreses competidores:

Informàtic Mataró Preu tècnic/hora 50 euros i de preu consultor/hora 60 euros
Sisticat Preu tècnic/hora 55 euros i de preu consultor/hora 70 euros
JSM Consultoria Preu tècnic/hora 60 euros i de preu consultor/hora 75 euros

Preu mitjà del sector seria de 55 euros i 68 euros

---

### Els nostres preus ajustats:

Tècnic de sistemes
Amb preu de mercat de 50 a 60 euros El nostre preu seria 45 euros hora perque empresa nova, preu competitiu

Tècnic web
Amb preu de mercat de 40 a 55 euros El nostre preu seria 40 euros hora perque Preu ajustat per a PIME

Cap de projecte
Amb preu de mercat de 60 a 80 euros El nostre preu seria 60 euros hora perque Preu estàndard de mercat

---

### Per què hem triat Microsoft 365 Business Standard?

Després de comparar Microsoft 365, Google Workspace i Zoho, hem triat Microsoft 365 Business Standard per aquests motius:

Microsoft Teams
Poden fer videotrucades, xat i reunions sense programes extres

OneDrive (1 TB)
Emmagatzematge al núvol per a cada usuari

SharePoint
Per compartir documents entre departaments

Suport 24/7
Microsoft dona suport tècnic directe

Integració
Ja fan servir Windows, tot funciona millor

Word, Excel, Outlook online
Poden treballar des de qualsevol lloc

### Alternatives que vam descartar:

Google Workspace i Zoho Workplace tenient Menys implantat a empreses catalanes, sense Teams i Massa bàsic, poca capacitat d'emmagatzematge de 30 gb

### Per què no comprem servidor físic per a l'Àrea 1?

Ja tenen un servidor amb Directori Actiu funcionant
No necessiten maquinari addicional
Estalviem 1.500-2.000 € en servidor nou
Estalviem electricitat i manteniment

### Resum econòmic per al client

Implantació inicial (única pagament)  1.692,50 €
Manteniment mensual 792,54 €
Manteniment anual 9.510,50 €

### Forma de pagament proposada

A la signatura del contracte de un 30 per cent un import de 507,75 €
En finalitzar la implantació de un 40 per cent 677 €
Als 30 dies de la posada en marxa de 30 per cent 507,75 €

Els costos recurrents (792,54 €/mes) es facturaran mensualment per domiciliació bancària.

## PLANIFICACIÓ

Per garantir que el projecte es lliura a temps, hem fet una planificació detallada de totes les tasques de la T01 a la T08. El projecte dura 4 setmanes (1 mes) i hem repartit la feina entre els 2 membres de l'equip: Marc Jurado i Martí Codony.

---

### Anàlisi de tasques i dependències

### Aquestes tasques es poden fer alhora perquè no depenen les unes de les altres:

T01 Estudi de la competència
T02 Web corporativa
T03 Servidor de fitxers
T05 Vídeo formatiu LOPD
T07 Solució de correu cloud

---

### Tasques amb dependències

T04 (Servidor impressió) T03 (Servidor fitxers)
T06 (Web legal) T02 (Web corporativa)
T08 (Tria web definitiva) T06 (Web legal)

---

### tasques que no poden retardar-se perquè si es retarden, tot el projecte es retarda

T02 (Web corporativa) → T06 (Web legal) → T08 (Tria web definitiva)

### Tasques amb marge

T01 – Estudi competència
T03 – Servidor fitxers
T04 – Servidor impressió
T05 – Vídeos LOPD
T07 – Solució cloud


![](/Productes/P01/images/imatge18.png)

---

![](/Productes/P01/images/imatge19.png)

### Diagrama de Gantt

![](/Productes/P01/images/imatge20.png)

---

![](/Productes/P01/images/imatge21.png)

---
### Pla de contingència


Retard en la web (T02 o T06)

Problemes en servidors (T03, T04 )

### Preguntes

Quina és la tasca més crítica del projecte?
La T02 (web corporativa) perquè sense ella no podem fer la web legal ni triar la web definitiva.

On pot haver-hi un coll d'ampolla?
A la T06 (web legal) perquè depèn de la T02 i és llarga (5 hores).

Quin risc podria fer fracassar el projecte?
Que la T02 es retardi massa i no tinguem temps per fer la T06 i la T08.

Si tinguéssim una setmana més, què canviaríem?
Faríem més proves als servidors i un vídeo LOPD més complert.

---

## CONCLUSIONS

Hem treballat en totes les àrees que ens va demanar el client:

Resum del que hem fet
Hem treballat en infraestructura (servidor fitxers i despres una mica de la T01), serveis al núvol (Microsoft 365), seguretat LOPD (vídeos i web legal) i presència web (landing page a GitHub Pages).

Què millora?
Fitxers: abans perduts, ara al servidor
Correu: abans inestable, ara al núvol amb Teams
Web: abans sense legal i lletja, ara legal i moderna

Per què triar-nos?
Som de Mataró, preus competitius 45 € la hora i donem servei complet.

 Resum econòmic
Implantació: 1.692,50 €
Manteniment mensual: 792,54 €
Manteniment anual: 9.510,48 €

---
