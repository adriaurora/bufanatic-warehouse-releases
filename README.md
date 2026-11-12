# Bufanatic Warehouse — Releases

Este repositorio contiene **solo** los APK firmados de la app Android de almacén de Bufanatic. Los publica automáticamente el CI desde un repositorio privado; el código fuente no está aquí.

## Cómo funciona la actualización

La app consulta el fichero `releases/latest/download/release.json` de este repositorio para saber si hay una versión nueva y descargar el APK correspondiente. Cada release se publica como un tag `v*` con sus APK y sus ficheros de verificación.

## Verificar un APK

Descarga el APK y el fichero `SHA256SUMS` de la release y ejecuta:

```sh
# 1. Comprobar la integridad del fichero descargado
sha256sum -c SHA256SUMS

# 2. Comprobar la firma y el certificado
apksigner verify --print-certs bufanatic-warehouse.apk
```

El certificado de firma debe tener el SHA-256:

```
e9dabbb906f70d08125b8c4f3e95491f7c315fb9d26c2f1769986ab4a9e36afb
```

Si el hash del certificado no coincide, no instales el APK.
