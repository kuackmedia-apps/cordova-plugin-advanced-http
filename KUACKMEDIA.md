# Fork de kuackmedia

Fork de [silkimen/cordova-plugin-advanced-http](https://github.com/silkimen/cordova-plugin-advanced-http) en la versión `3.3.1` publicada en npm (MIT, ver `LICENSE`). Lo usan las apps Cordova de
Kuack Media para el HTTP nativo de todo el API (`APIKuack.js`, `TrackUrlLoader`, `NativePlayback`, `PodcastOffline`, `MandatoryUpdate`, `embed/NetworkConditions.js`): sin CORS, porque el origen del WebView no es el del API.

Base: `320ed35` (upstream no tiene tag de esa versión), idéntico al paquete `cordova-plugin-advanced-http@3.3.1` de npm que las apps instalaban hasta noviembre de 2026.

**Lo publicado es el commit fijado en `_common/configTemplates/config-app*.xml`** del repo de las apps
(`github:kuackmedia-apps/cordova-plugin-advanced-http#<sha>`), no la punta de una branch: un push a este repo no llega a ningún
binario hasta que se mueve ese pin, y mover el pin es un diff que se revisa. La branch `kuack` es la línea de
Kuack; `master` queda como el de upstream.

## Cambios respecto de upstream

Ninguno en el código: el fork existe para que el app dependa sólo de Apache Cordova y de repos de Kuack (fila A18 del RFP de Claro, CM-RFP-001).

## Para actualizar desde upstream

`git fetch upstream --tags`, en una branch merge (o rebase) de la versión nueva sobre `kuack`, revisar los
cambios de arriba, probarlo en un app con `config-app-local.xml` (path local del checkout), llevarlo a `kuack` y
mover el pin en los `config-app*.xml`. Nunca cambiar el `id` del plugin ni sus `clobbers`: el bundle remoto lo
comparten los binarios publicados.
