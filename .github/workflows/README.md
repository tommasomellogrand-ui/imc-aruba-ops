# Workflows

Workflow operativi approvati:

## OPS-001 · ARUBA Filesystem Inventory

File: `aruba-filesystem-inventory.yml`

Scopo: inventario READ-only del filesystem Aruba limitato a `/www.italianmastersclub.it`.

Trigger disponibili:
- manuale (`workflow_dispatch`);
- tramite `IMC Aruba Ops Trigger` con titolo Issue esatto `RUN ARUBA FILESYSTEM INVENTORY`.

Il workflow:
- usa FTPS sulla porta 21;
- legge soltanto nomi, path, tipo, dimensione e timestamp dei file/cartelle;
- non legge il contenuto dei file;
- non esegue upload, delete, rename, mkdir o altre operazioni mutative;
- produce report TXT e JSON come artifact con retention di 3 giorni;
- non accede a MySQL, Universal Gateway o importer.

## OPS-002 · ARUBA Minisite Migration

File: `aruba-minisite-migration.yml`

Scopo: migrazione controllata dei minisiti dalla struttura `/gameworldXXX/` alla nuova area `/minisite/GWXXX/`, con motore condiviso in `/minisite/shared/app-core.js`.

Trigger disponibili:
- manuale (`workflow_dispatch`) con conferma esatta `MIGRATE_MINISITES`;
- tramite `IMC Aruba Ops Trigger` con titolo Issue esatto `RUN ARUBA MINISITE MIGRATION`.

Guardrail:
- preflight completo di tutte le sorgenti prima della prima write;
- copia ricorsiva di tutto il contenuto dei GW001–GW015;
- copia del motore condiviso da `/site-assets/gameworld/app-core.js`;
- write consentite esclusivamente sotto `/www.italianmastersclub.it/minisite/`;
- nessun delete, rename o modifica degli originali;
- aggiornamento dei riferimenti al motore condiviso soltanto nelle copie sotto `/minisite/`;
- verifica SHA-256 dei file copiati e controllo HTTP dei nuovi URL;
- report TXT/JSON come artifact con retention di 7 giorni.

Regola permanente minisiti Aruba: qualunque nuovo file, cartella, asset, script, sottopagina o componente destinato ai minisiti deve vivere sotto `/minisite/`.

## IMC Aruba Ops Trigger

File: `imc-aruba-ops-trigger.yml`

Scopo: meccanismo centralizzato e controllato con cui ChatGPT può avviare esclusivamente comandi OPS autorizzati tramite Issue GitHub con titolo esatto.

Mapping attuale:
- `RUN ARUBA FILESYSTEM INVENTORY` → `OPS-001 · ARUBA Filesystem Inventory`;
- `RUN ARUBA MINISITE MIGRATION` → `OPS-002 · ARUBA Minisite Migration`.

Il trigger non accede direttamente ad Aruba: si limita a lanciare il workflow OPS autorizzato.

Nuovi comandi OPS e nuovi mapping verranno introdotti esclusivamente dopo approvazione esplicita.
