Per a una pràctica d'aula o un entorn de laboratori virtual, **no cal un disc enorme**.

La mida depèn de si vols que les quotes saltin *ràpid* o *lent*. Aquí tens les recomanacions segons el teu objectiu:

### Opció 1: Mida Estàndard de Pràctica (Recomanada)
**Mida del Disc: 5 GB - 10 GB**

- **Per què?**
    - Ocupa poc espai al teu disc dur real.
    - És prou gran per instal·lar el rol FSRM i tenir sistema operatiu (si és C:), però prou petit perquè les quotes es notin.
    - **Conseqüència per a les proves:** Hauràs de crear fitxers grans artificialment per superar els límits de 200 MB o 500 MB (explicat més avall).

### Opció 2: Mida Mínima Absoluta (Per a màquines virtuals justes d'espai)
**Mida del Disc: 2 GB**

- Amb **2 GB** tens espai suficient per a les carpetes buides i uns quants fitxers de prova.
- *Avís:* Si actives la quota per volum a 500 MB, el mateix servidor pot començar a donar errors d'espai si el disc és de només 2GB i el Windows hi instal·la actualitzacions.

---

### IMPORTANT: Com simular que "omples" 500 MB en un disc petit?

Com que la quota està posada a **500 MB per usuari**, si el disc total fa només 5 GB, no podràs copiar fitxers de veritat que ocupin tant sense esborrar coses.

Per fer la **Captura de Pantalla de l'error de Quota NTFS** (Fita 4) sense haver de copiar 500 MB reals, fes servir aquest truc de **PowerShell** des del client:

```powershell
# Executa això al CLIENT (Windows 10) amb l'usuari u_trans
# Això crea un fitxer buit de 600 MB a la unitat mapejada X: (o al recurs compartit)
fsutil file createnew \\SERVIDOR\Public\fitxer_prova.tmp 629145600
```

Això crearà un fitxer que ocupa espai lògic però sense haver de buscar arxius reals (ISOs, vídeos) per copiar.

### Resum ràpid per a la creació de la MV:
- **Disc C: (SO):** 40-60 GB (Estàndard Windows Server)
- **Disc D: (Dades/Pràctica):** **5 GB** (Amb això vas sobrat i el laboratori va fluid).
