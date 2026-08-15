LoaderDiag runtime fixtures
===========================

Diese 14 Artefakte sind ausschliesslich modulnahe Testressourcen fuer
LOADERD.R4X. Sie sind keine eigenstaendigen Produktkomponenten und erhalten
keine eigenen Repositories.

Der normale LoaderDiag-Build erzeugt gemeinsam mit LOADERD:

- EXTMATH sowie acht Resolver-/Runtime-R4L-Fixtures,
- BADSTART als ungueltigen R4XStart-Container,
- LSTRX, LSTRL, LSTRD und LSTRP als grosse Loader-Stresscontainer.

Die Manifeste unter Manifests dokumentieren Ziel und IMAGE_SCOPE. Der Build
nutzt bewusst rohe, deterministische Payloads aus Fixtures/build.zig und den
gepinnten R4M021-Binaerfixtures des SDK.
