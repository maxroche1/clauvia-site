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
- **Zone : « Les Combrailles et alentours »**. Le rayon de 10 km reste sur la page Clauvia.
- **Pas de « haut de gamme », pas de « terrain »** : formulations écartées volontairement.
- Aucune formule n'est engageante : ne pas remettre « sans engagement » sur une seule carte, ça laisserait croire que les autres le sont.

## Remarques techniques

- Le CSS est un fichier unique, sans préprocesseur. Les variables de couleur sont en haut (`:root`).
- Une seule requête externe : Google Fonts (Cormorant Garamond + Jost). Le reste est local.
- Le menu ne se déplie qu'en dessous de 860 px (classe `.burger` + `.nav.ouvert`, script en bas de chaque page).
- Le formulaire de contact n'envoie rien à un serveur : il compose un mail vers `contact.clauvia@gmail.com`.

## Mise en ligne

GitHub Pages, branche `main`, dossier racine. À chaque `push`, le site se met à jour en une minute environ.
