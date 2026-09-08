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

## IMC Aruba Ops Trigger

File: `imc-aruba-ops-trigger.yml`

Scopo: meccanismo centralizzato e controllato con cui ChatGPT può avviare esclusivamente comandi OPS autorizzati tramite Issue GitHub con titolo esatto.

Mapping attuale:
- `RUN ARUBA FILESYSTEM INVENTORY` → `OPS-001 · ARUBA Filesystem Inventory`.

Il trigger non accede direttamente ad Aruba e non esegue operazioni mutative sul filesystem: si limita a lanciare il workflow OPS autorizzato.

Nuovi comandi OPS e nuovi mapping verranno introdotti esclusivamente dopo approvazione esplicita.
