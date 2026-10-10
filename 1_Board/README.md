Les fichiers de fabrication des deux cartes v1.1, tels que les sort l'outil de CAO : la carte logique dans `Logic-board/`, la carte d'alimentation dans `Power-board/`, chacune avec sa fiche `_0-README.txt`.

## Nommage des fichiers de carte

Les fichiers de `1_Board/` suivent le schéma :

```
Maelstrom-<Carte>-v<version>_<n>-<Nature>.<ext>
```

- `<Carte>` : `Logic-board` ou `Power-board`, le nom du sous-dossier ;
- `<version>` : la version de la carte, `1.1` ;
- `<n>-<Nature>` : la nature du fichier.

| n | fichier |
|---|---|
| 0 | `0-README.txt` : la fiche de la carte |
| 1 | `1-Schematics.pdf`, `1-Schematics.png` : le schéma |
| 2 | `2-view_top.png`, `2-view_bot.png` : vues du dessus et du dessous ; `2-view_3D.png`, `2-view_3D-bot.png`, `2-view_3D.step` : vues 3D du dessus et du dessous, et modèle 3D |
| 3 | `3-Gerber.zip` : Gerber RS-274X et perçages Excellon |
| 4 | `4-BoM.xlsx` : la nomenclature, références LCSC |
| 5 | `5-PnP.xlsx` : le placement, coordonnées en mm |

Exemple : `Maelstrom-Logic-board-v1.1_3-Gerber.zip`.

Les autres fichiers gardent leur nom : ceux de `2_Hardware/` (`Maelstrom_<Pièce>.<ext>`), et les
fichiers de tiers (datasheets, documents de référence, firmware, MProg, viewer).
