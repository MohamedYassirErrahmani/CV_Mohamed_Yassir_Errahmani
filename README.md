# CV en ligne — Mohamed Yassir Errahmani

Site Quarto bilingue (français / anglais) publié sur GitHub Pages :
<https://mohamedyassirerrahmani.github.io/cv/>

## Structure

| Fichier | Rôle |
|---|---|
| `index.qmd` | Version française (page d'accueil, `/cv/`) |
| `en/index.qmd` | Version anglaise (`/cv/en/`) |
| `styles.css` | Mise en forme (couleurs dans `:root` : `--navy` #1B3A6B, `--sky` #2E86C1) |
| `_quarto.yml` | Configuration du site |
| `_head.html`, `_scripts.html` | Polices et script de navigation / bascule FR-EN |
| `docs/` | Site généré (c'est ce dossier que GitHub Pages publie) |

Les deux versions utilisent les mêmes identifiants de section (`{#profile}`, `{#research}`, …) :
la bascule FR/EN ramène ainsi sur la même section. Ne pas les renommer dans une seule langue.

## Première publication

1. Sur GitHub : créer un dépôt **public** nommé exactement `cv` (sans README ni .gitignore).
2. Dans le Terminal de RStudio (onglet *Terminal*), depuis ce dossier :

   ```bash
   quarto render
   git init -b main
   git add .
   git commit -m "CV en ligne"
   git remote add origin https://github.com/MohamedYassirErrahmani/cv.git
   git push -u origin main
   ```

3. Sur GitHub : **Settings → Pages → Build and deployment**
   - Source : *Deploy from a branch*
   - Branch : `main`, dossier `/docs` → **Save**
4. Après 1 à 2 minutes, le site est en ligne à l'adresse ci-dessus.

## Mise à jour du CV

1. Modifier `index.qmd` (français) et `en/index.qmd` (anglais).
2. Aperçu local : `quarto preview`
3. Publier :

   ```bash
   quarto render
   git add .
   git commit -m "Mise à jour du CV"
   git push
   ```

Penser à mettre à jour les chiffres clés (bloc `stats` en haut de chaque page) et la date
« Dernière mise à jour » (en-tête YAML de chaque page) lorsqu'une publication est ajoutée.
