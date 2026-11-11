# Sky Pilot (Horizon)

Simulateur de vol 3D dans le navigateur : F-35B et PV-40 à aile basculante, relief, météo, vol libre.

**▶ Démo en ligne : [https://yoannservices.github.io/sky-pilot/](https://yoannservices.github.io/sky-pilot/)**

## Fonctionnalités

- Deux appareils : F-35B (tuyères orientables) et PV-40 à aile basculante (couleur personnalisable)
- Quatre pistes, départ sur la piste, au décollage vertical ou en vol
- Heure au choix : jour, coucher de soleil, nuit
- Pilotage assisté optionnel, train, volets, parachute, rampe arrière, carte

## Commandes

| Touche | Action |
|---|---|
| Z / ↓ | Cabrer |
| S / ↑ | Piquer |
| Q ← / D → | Rouler à gauche / droite |
| A / E | Palonnier |
| Maj / Ctrl | Poussée + / − (à 100 %, rappuyer sur Maj = boost) |
| Espace | Freinage d'urgence |
| J | Larguer le parachute |
| T / Y | Tuyères (F-35) · basculer / rabaisser l'aile (PV-40) |
| B | Freins VTOL (PV-40) |
| O | Portes et rampe arrière (PV-40) |
| G | Train d'atterrissage |
| F | Volets |
| C | Changer de vue |
| Clic + glisser | Tourner la caméra autour de l'avion (vues extérieures) |

## Lancer en local

Aucune installation : ouvrez `index.html` dans un navigateur, ou servez le dossier :

```bash
python -m http.server 8000
```

puis allez sur http://localhost:8000 (dans le dossier `web/` de Mes Projets : http://localhost:8000/loisirs/sky-pilot/).

## Structure

- `index.html`, `style.css`
- `js/main.js` : le simulateur

## Technologies

HTML, CSS et JavaScript ; rendu 3D avec [Three.js](https://threejs.org/) r186 (chargé depuis un CDN par `assets/three-compat.js`). Sans étape de build.

---

Fait partie de [Mes Projets](https://yoannservices.github.io/) · [Portfolio](https://yoannservices.github.io/portfolio/) · par [@yoannservices](https://github.com/yoannservices)

## Fiche technique

Résumé de ce que fait le code, tenu à jour à chaque modification : le lire suffit pour vérifier une information sans relire tout le jeu.

- **Code** : `js/main.js` (script classique).
- **Avions** : `f35.glb` (andertan, longueur 15,5, yaw π) et `v22-osprey-tilt.glb` (PV-40, longueur 33) cadrés par `fitGLB(..., keepAxes)` ; train et tuyère découpés dans le modèle et animés.
- **Caméras (C)** : 0 poursuite ; 1 cockpit (F-35 (0 ; 0,92 ; −3,55), PV-40 (−0,62 ; −0,25 ; −10,6)) ; 2 vue de côté (8 ; 2,6 ; 15) × échelle ; PV-40 seulement : 3 cabine (0,15 ; 0,1 ; −7,5) et 4 soute.
- **Sauvegarde** : `horizon:aircraft`, `horizon:pvColor`.

## Crédits des modèles 3D

Véhicules réels sous licence CC-BY (Sketchfab) : auteurs et licences dans `assets/models/CREDITS.md`.
