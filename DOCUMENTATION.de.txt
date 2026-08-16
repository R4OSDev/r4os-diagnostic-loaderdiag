LOADERD.R4X
===========

LOADERD.R4X ist die Loader- und R4M0-Moduldiagnose. Seit 0.53.47 prueft es
zusaetzlich den R4DEV-v141-Loader-Performance-Snapshot: R4L/R4D/R4P-
Kandidaten, geladene/aktive/blockierte Module, `CONFIG.R4S`-Bytes,
Service-Manager-Bootstatus und Lazy-Load-Audit-Marker.

Seit 0.54.7 prueft LOADERD auch grosse synthetische Stressmodule:
`LSTRX.R4X`, `LSTRL.R4L`, `LSTRD.R4D` und `LSTRP.R4P`. Die Diagnose liest
Header, Tabellen, Import-/Export-Strings und Section-Ranges per `fileReadAt`,
startet `LSTRX.R4X` parallel und prueft, dass Range-Reads steigen, ohne den
alten Voll-Datei-Zaehler zu erhoehen.

Projektstruktur seit 0.51.21:
- `build.zig` baut die Diagnose samt 14 modulnahen Loader-Fixtures als
  eigenes SDK-Projekt.
- `build.zig.zon` bindet `r4os_sdk` als Paket.
- `module.R4MF` beschreibt Artefakt, Zielpfad, R4L-Imports und Contract.
- `Fixtures/` besitzt Generator, Zielmanifeste und Referenzhashes der
  EXTMATH-, Resolver-, BADSTART- und Loader-Stresscontainer.

Build:

    Build.bat

Ergebnis:

    Der in Settings.R4S konfigurierte ARTIFACTS_ROOT enthaelt LOADERD.R4X
    und seine 14 Testfixtures.

Contract:
- Build-Profil: `Zig/R4XStart`
- R4XStart-Entry: `loaderd_main`
- App-Klasse: `console`
- R4L-Imports: `R4SYS`, `R4DEV`, `R4AUDIO`, `R4DESK`, `R4DRAW`, `R4NET`,
  `EXTMATH`
- Zielpfad im Image: `C:\R4OS\SOFTWARE\TERMINAL\DIAG\LOADERD.R4X`
