# IMC · Responsibility Map

## Database Manager

L'IMC Database Manager Aruba è il control plane amministrativo di MySQL Aruba.

Baseline consolidata:

- health;
- schema;
- read_query / query READ-only;
- plan_migration;
- execute_migration;
- history;
- data migration / backfill espliciti tramite `data_migration=true`.

Non svolge CRUD applicativo ordinario e non espone `clear_repository`.

## Universal Gateway

Il perimetro definitivo del Gateway non viene definito in questo documento finché non sarà completato l'audit preventivo delle dipendenze degli importer correnti.
