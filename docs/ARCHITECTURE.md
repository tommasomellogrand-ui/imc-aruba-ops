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

## Perimetro minisiti Aruba

La root applicativa riservata ai minisiti è `/www.italianmastersclub.it/minisite/`.

Qualunque nuovo file, cartella, asset, script, sottopagina o componente destinato ai minisiti deve essere creato esclusivamente sotto `/minisite/`. Le operazioni OPS dedicate ai minisiti devono impedire write al di fuori di questo perimetro.
