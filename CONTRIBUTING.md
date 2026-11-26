# Contribuer à La Bataille de France

Merci de votre intérêt. Ce guide vaut pour tous les dépôts de l'organisation, sauf s'ils ont le leur.

## Langue

Le projet est français : issues, PR, documentation et commentaires du code en **français**.

Dans le code, les **termes techniques restent en anglais** : `handshake`, `encode`, `Reader`, `hash`, `broadcast`, `queue`, `--listen`… Les traduire les rend méconnaissables et les éloigne de la documentation des bibliothèques. Le vocabulaire du jeu (tile, zombie, unité, ravitaillement, commune) et les textes affichés au joueur sont en français.

## Licence et DCO

Le code est sous **AGPL-3.0-or-later**. En contribuant, vous certifiez le [Developer Certificate of Origin](https://developercertificate.org/) : vous avez le droit de soumettre ce code sous cette licence. Chaque commit porte la ligne :

```
Signed-off-by: Prénom Nom <adresse@exemple.fr>
```

`git commit -s` l'ajoute. La CI refuse une PR dont un commit n'en a pas, ou dont la ligne ne correspond pas à l'auteur.

## Commits signés

La branche `main` n'accepte que des **commits signés** (GPG, SSH ou S/MIME) et vérifiés par GitHub. Voir [la documentation de GitHub](https://docs.github.com/fr/authentication/managing-commit-signature-verification). Un commit : `git commit -s -S`.

## Proposer une modification

1. Forkez le dépôt et créez une branche.
2. Faites passer localement : `cargo fmt --check`, `cargo clippy --all-targets --locked -- -D warnings`, `cargo nextest run --locked` (ou `cargo test --locked`).
3. Ouvrez une PR vers `main`. Toutes les vérifications de la CI doivent passer ; l'historique reste linéaire (rebase, pas de commit de fusion).

## Règles du code

- **Rust**, édition 2024, version de la chaîne fixée par `rust-toolchain.toml`.
- **Pas de code `unsafe`** : les crates le refusent (`unsafe_code = "forbid"`). Une exception se justifie dans la PR et dans le code.
- **Dépendances** : versions exactes (`=x.y.z`), publiées depuis au moins deux semaines, sous une licence compatible AGPL (vérifié par `cargo deny`).
- **Déterminisme** : la simulation donne le même résultat quel que soit le nombre de threads ; un calcul en tâche de fond rend son résultat à un tick fixé à son lancement.

## Assets

Aucun asset tiers (modèle, texture, son, police) n'est versionné. Pour en ajouter un, inscrivez-le au manifeste de `beta1-assets` (URL, empreinte, licence, auteur). Licences acceptées : CC0-1.0, CC-BY-4.0, OFL-1.1. Pas de modèles 3D générés par IA.

## Sécurité

Ne signalez pas une vulnérabilité dans une issue publique : voir [SECURITY.md](SECURITY.md).
