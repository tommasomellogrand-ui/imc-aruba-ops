# imc-aruba-ops

Italian Masters Club · control plane operativo GitHub ↔ Aruba per deploy, amministrazione e infrastruttura.

## Scopo

Questo repository è la sede dedicata agli asset operativi GitHub ↔ Aruba dell'Italian Masters Club.

Perimetro iniziale:

- documentazione architetturale;
- responsibility map;
- runbook operativi;
- futura sede autoritativa dell'IMC Database Manager Aruba;
- workflow di deploy Aruba introdotti solo quando approvati esplicitamente.

## Regole operative

- MySQL Aruba resta la fonte dati autoritativa.
- GitHub resta la fonte autoritativa di codice e deploy.
- Nessun asset production-critical viene migrato senza audit, autorizzazione, esecuzione e verifica reale.
- IMC Universal Gateway resta fuori da questo repository finché non verrà completato l'audit preventivo delle dipendenze degli importer correnti.
- Nessun workflow automatico viene introdotto nella baseline iniziale.
