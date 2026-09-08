# IMC Aruba Ops · Architecture

## Fonti autoritative

- MySQL Aruba = fonte dati autoritativa.
- GitHub = fonte autoritativa di codice e deploy.
- Supabase = ponte tecnico verso MySQL Aruba quando previsto.

## Database

- CORE: Sql1956795_1
- GOLD / MULTI: Sql1956795_2
- CUSTOM / SINGLE: Sql1956795_3

## Principio operativo

Questo repository ospita esclusivamente asset operativi GitHub ↔ Aruba approvati e verificati. Ogni migrazione di componenti produttivi deve preservare la continuità operativa e deve essere eseguita in modo sequenziale: audit → autorizzazione → modifica → deploy → verifica reale.
