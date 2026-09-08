# Workflows

Workflow operativi approvati:

## ARUBA Filesystem Inventory

File: `aruba-filesystem-inventory.yml`

Scopo: inventario READ-only del filesystem Aruba limitato a `/www.italianmastersclub.it`.

Trigger: esclusivamente manuale (`workflow_dispatch`).

Il workflow:
- usa FTPS sulla porta 21;
- legge soltanto nomi, path, tipo, dimensione e timestamp dei file/cartelle;
- non legge il contenuto dei file;
- non esegue upload, delete, rename, mkdir o altre operazioni mutative;
- produce report TXT e JSON come artifact con retention di 3 giorni;
- non accede a MySQL, Universal Gateway o importer.

Nuovi workflow Aruba verranno introdotti esclusivamente dopo approvazione esplicita, con trigger e permessi minimi.
