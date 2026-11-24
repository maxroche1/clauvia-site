# Clauvia — site vitrine

Site statique (HTML/CSS/JS, aucune dépendance, aucun build). Il suffit de modifier les fichiers et de les pousser.

## Structure

| Fichier | Rôle |
|---|---|
| `index.html` | Accueil |
| `services.html` | Formules (Ponctuel / Sérénité / Complète), pack de lancement, comparatif |
| `clauvia.html` | Qui je suis |
| `contact.html` | Formulaire de devis (ouvre le client mail, aucun serveur) |
| `style.css` | Toute la charte (couleurs, typo, mise en page, menu mobile) |
| `logo-clauvia.svg` | Le C-clé, en-tête et pied de page |
| `favicon.svg` | Icône d'onglet |

## Règles à ne pas casser

- **Les textes viennent de l'offre validée.** Les tarifs, les pourcentages et ce qui est inclus sont décidés dans le coffre Obsidian (`1 - Pro/Clauvia/Offre Clauvia.md`). Ne pas inventer de prix.
- **Sérénité 12,5 % → 15 %, Complète 15 % → 18 %** : taux de la première année, barré + taux plein annoncé. Ne jamais présenter le taux bas sans la mention « offre de la première année ».
- **Commission sur les revenus nets**, jamais bruts.
- **Le ménage est facturé aux locataires.** Le linge est lavé et changé, jamais fourni.
- **Le pack de lancement est à 150 €**, une seule fois.
- **Zone : « Les Combrailles et alentours »**, sans rayon chiffré : rester vague pour ne décourager aucun propriétaire un peu plus loin.
- **Pas de « haut de gamme », pas de « terrain »** : formulations écartées volontairement.
- Aucune formule n'est engageante : ne pas remettre « sans engagement » sur une seule carte, ça laisserait croire que les autres le sont.

## Remarques techniques

- Le CSS est un fichier unique, sans préprocesseur. Les variables de couleur sont en haut (`:root`).
- Une seule requête externe : Google Fonts (Cormorant Garamond + Jost). Le reste est local.
- Le menu ne se déplie qu'en dessous de 860 px (classe `.burger` + `.nav.ouvert`, script en bas de chaque page).
- Le formulaire de contact n'envoie rien à un serveur : il compose un mail vers `contact.clauvia@gmail.com`.

## Mise en ligne

GitHub Pages, branche `main`, dossier racine. À chaque `push`, le site se met à jour en une minute environ.

## Visuels provisoires (`images/`)

Le site utilise cinq illustrations SVG provisoires, dessinées dans la palette de `style.css`. Chacune est marquée par un commentaire `<!-- VISUEL PROVISOIRE -->` dans le HTML.

| Fichier | Où | Ratio | Taille d'origine |
|---|---|---|---|
| `images/hero-conciergerie.svg` | Accueil, à côté du titre | 16:10 | 1600 × 1000 |
| `images/formule-ponctuel.svg` | Services, carte Ponctuel | 3:2 | 1200 × 800 |
| `images/formule-serenite.svg` | Services, carte Sérénité | 3:2 | 1200 × 800 |
| `images/formule-complete.svg` | Services, carte Complète | 3:2 | 1200 × 800 |
| `images/parcours.svg` | Page Clauvia, section « Trois ans à gérer mes logements, cinq biens » | 16:10 | 1600 × 1000 |

### Remplacer un visuel par une vraie photo

1. Recadrer la photo au **même ratio** que le visuel remplacé (16:10 ou 3:2).
2. L'exporter en `.jpg` ou `.webp`, **1600 px de large** pour le hero et le parcours, **1200 px** pour les formules, idéalement sous 250 Ko.
3. La déposer dans `images/` avec **le même nom** que le SVG, en changeant l'extension (par exemple `hero-conciergerie.jpg`), puis modifier le `src` dans le HTML (`index.html`, `services.html` ou `clauvia.html`). Garder `width` et `height` (1600 × 1000 ou 1200 × 800).
4. Réécrire l'`alt` pour décrire la vraie photo, et supprimer le commentaire `<!-- VISUEL PROVISOIRE -->`.
5. Ne rien changer dans `style.css` : le ratio est imposé par la classe (`.visuel--hero`, `.visuel--formule`, `.visuel--parcours`) et `object-fit: cover` recadre la photo sans la déformer.

Garder `loading="eager"` et `fetchpriority="high"` sur l'image du hero (première image visible), `loading="lazy"` sur toutes les autres.
