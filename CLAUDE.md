# Maelstrom

Caméra astronomique APS-C refroidie, bâtie sur le CCD d'un Nikon D40 : un dépôt de matériel (cartes, mécanique) et de fichiers tiers, sans code source à construire.

## Stack

- Pas de code source, ni build ni suite de tests : la CI du dépôt n'est qu'un placeholder vert.
- `1_Board/` : deux cartes v1.1, `Logic-board/` et `Power-board/`, conçues sur OSHWLab (https://oshwlab.com/lordzurp/cam87_redux) ; le dépôt n'en porte que les exports de fabrication (schéma PDF/PNG, vues, STEP, Gerber, BoM, PnP).
- `2_Hardware/` : mécanique en Fusion 360 (`.f3d`) et STEP.
- `4_Firmware/` : binaire STM32 tiers et gabarit MProg de l'EEPROM du FT2232H ; `5_App/` : outils Windows tiers.

## Doc

La doc de chaque partie est le `README.md` de son dossier ; chaque carte a sa fiche `_0-README.txt` dans son sous-dossier de `1_Board/`.

## Conventions

- `README.md`, `9_Assets/`, `LICENSE`, `LICENSE-HARDWARE` et `.github/workflows/zurp-site.yml` sont la vitrine, rédigée par l'org zUrp-Astronomics pour tous ses produits à la fois : un ticket du projet n'y touche pas.
- L'arborescence `0_` à `9_` et le nommage des fichiers de carte sont la norme de l'org, décrite au § 5 du kit : https://github.com/zUrp-Astronomics/.github/blob/main/readme-kit/README.md — s'y référer, ne pas la recopier.

## Gotchas

- Les fichiers de `4_Firmware/` et de `5_App/` sont des tiers, gardés tels quels : ne pas les modifier, renommer ni réorganiser. Certains n'ont pas de licence connue ; la section « License » du `README.md` liste ces exceptions.
- Les dossiers de `5_App/` restent groupés : chaque exécutable charge ses DLL dans son propre dossier (`FTD2XX.dll` à côté de `MProg.exe`, `ftd2xx.dll` à côté de `viewer cam87.exe`).
- Plusieurs chemins contiennent des espaces (`4_Firmware/cam87 v1.0.bin`, `5_App/MProg 3.5 Release/`, `5_App/Viewer/viewer cam87.exe`) : les citer entre guillemets en shell.
