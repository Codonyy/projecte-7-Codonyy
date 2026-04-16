
# T03: Servidor de fitxers

## Breu descripció

Implementació d’un servidor de fitxers per a **FoodLogístic S.A.** amb l’objectiu de centralitzar la informació, millorar la seguretat i controlar l’ús de l’emmagatzematge.

---

## Introducció

Amb el creixement de l’empresa, la gestió de dades s’ha tornat desorganitzada, amb informació dispersa en diferents equips.

Per solucionar-ho, es desplega una infraestructura de fitxers basada en:

- Permisos NTFS i SMB
- Recursos compartits
- Control d’espai (quotes)
- Filtrat de fitxers (FSRM)

---

## 1. Preparació i Seguretat de Grups (Active Directory)

S’han creat els següents grups de seguretat al domini:

```
Administracio
Transport
Direccio
```

### Funcions

- **Administracio** → Gestió de documents i factures  
- **Transport** → Operacions logístiques  
- **Direccio** → Informació confidencial  

---

## 2. Implementació de Recursos Compartits

### A. Carpeta Public (Explorador)

- Accés: Tots els usuaris  
- Permisos SMB: Lectura  
- Permisos NTFS: Modificació  

📌 Permís efectiu: limitat per SMB (Lectura)

---

### B. Carpeta Operacions (Server Manager)

- Nom del recurs: `Operacions`
- Accés: només grup `Transport`
- Access-Based Enumeration activat

---

### C. Carpeta Direccio (PowerShell avançat)

Creació del recurs compartit:

```powershell
New-SmbShare -Name "Direccio" -Path "C:\Dades\Direccio" -FullAccess "Direccio"
Set-SmbShare -Name "Direccio" -FolderEnumerationMode AccessBased
```

- Accés exclusiu: grup `Direccio`
- Visibilitat restringida (ABE)

---

### Mapatge amb GPO

Assignació de la unitat de xarxa:

```
Z: → \\Servidor\Direccio
```

Només per usuaris del grup `Direccio`.

---

## 3. Control d'Emmagatzematge

### Quotes NTFS

- Límite per usuari: **500 MB**
- Aplicat a nivell de volum

---

### FSRM

#### Quota de carpeta

- Carpeta: `Public`
- Límite: **200 MB (Hard Quota)**
- Avís al 90%:

```
Compte! FoodLogístic t'informa que estàs a punt d'esgotar l'espai compartit.
```

---

#### Filtrat de fitxers

A la carpeta `Operacions`:

Fitxers bloquejats:

```
.exe
.msi
.mp3
.mp4
.avi
```

---

## 4. Verificació i proves

### Accés per grups

- Administracio → només Public  
- Transport → Public + Operacions  
- Direccio → accés total  

---

### Proves realitzades

- ❌ Intent copiar `.exe` a Operacions → BLOQUEJAT  
- ⚠️ Canvi extensió `.exe` a `.txt` → POSSIBLE (limitació del filtre)

---

## Resum de configuració

| Carpeta     | Ruta UNC                  | Grup accés   | Mètode              |
|------------|--------------------------|--------------|---------------------|
| Public     | \\Servidor\Public        | Tots         | Explorador          |
| Operacions | \\Servidor\Operacions    | Transport    | Server Manager      |
| Direccio   | \\Servidor\Direccio      | Direccio     | PowerShell avançat  |

---

## Conclusions

- S’ha aconseguit centralitzar la informació de l’empresa  
- S’han aplicat controls d’accés per grups  
- S’ha limitat l’ús indegut de l’emmagatzematge  
- S’ha millorat la seguretat de les dades  

El sistema és escalable i permet futures ampliacions segons les necessitats del client.

---

## Material de suport

```
0224 SOX — UD8
AA2
```
