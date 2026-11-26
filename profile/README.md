# La Bataille de France

Jeu vidéo open source de reconquête de la France face aux zombies, en 2030 : monde à l'échelle 1:1, temps réel, une seule partie multijoueur persistante, dans le navigateur.

Site : https://labatailledefrance.fr

| Dépôt | Rôle |
|---|---|
| `beta1-common` | Code partagé : géographie, format des tiles, protocole |
| `beta1-server` | Serveur de simulation (Bevy sans rendu) |
| `beta1-client` | Client navigateur (Bevy, WebAssembly, WebGPU) |
| `beta1-datachain` | Chaîne de données : sources IGN et INSEE vers tiles |
| `beta1-assets` | Manifeste et récupération des assets tiers |
| `beta1-helm` | Charts Helm du jeu et du socle du cluster |

Le code est sous licence AGPL-3.0-or-later. Pour contribuer : [CONTRIBUTING.md](https://github.com/labatailledefrance/.github/blob/main/CONTRIBUTING.md).
