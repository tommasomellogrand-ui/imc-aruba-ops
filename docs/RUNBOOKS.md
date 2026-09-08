# IMC Aruba Ops · Runbooks

## Regola generale

Ogni intervento operativo deve seguire il ciclo:

AUDIT → AUTORIZZAZIONE → ESECUZIONE → VERIFICA → NUOVA BASELINE

## Deploy

Prima di ogni modifica leggere sempre il file corrente dalla fonte GitHub autoritativa.

Dopo ogni modifica:

1. commit;
2. GitHub Actions quando previsto;
3. verifica del deploy;
4. verifica live positiva.

Non dichiarare un componente online sulla sola base del commit o della Action.

## Sicurezza

- Nessuna credenziale nei file del repository.
- Secrets solo tramite GitHub Secrets quando verranno introdotti workflow operativi.
- WRITE, DELETE, ALTER e DROP solo su autorizzazione esplicita.
