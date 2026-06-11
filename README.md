# Diagramme de Gantt Droit

Un petit site pour obtenir une frise chronologique (diagramme de Gantt) en PNG à partir d'un fichier Excel.

## 📋 Caractéristiques

- **Upload Excel simple** : Glissez-déposez votre fichier `.xlsx`, `.xls` ou `.csv`
- **Configuration intuitive** : Sélectionnez les colonnes contenant les dates, noms et métadonnées
- **Affichage politique** : Codage couleur selon l'orientation politique (gauche/centre/droite/extrême droite)
- **Contexte gouvernemental** : Visualisez les faits majoritaires et les situations politiques
- **Export multi-formats** : Téléchargez en PNG (pour Word/impression) ou SVG (pour édition)
- **Pas d'upload serveur** : Tout se passe dans votre navigateur — vos données restent privées

## 🚀 Utilisation

### Étape 1 : Préparer votre fichier Excel

Votre fichier doit contenir une en-tête avec les noms de colonnes. Exemples de colonnes reconnaissables automatiquement :

| Colonne | Alias reconnus |
|---------|---|
| **Nom** | nom, catégorie, règne, ligne, groupe, titre, tâche |
| **Commentaire** | commentaire, comment, label, étiquette, détail, événement, libellé |
| **Date de début** | début, début, départ, date_début |
| **Date de fin** | fin, end, date_fin, échéance |
| **Ponctuel** | ponctuel, instantané, jalon, milestone |
| **Orientation** | orientation, bord, tendance, couleur politique, camp, parti |
| **Position gouvernementale** | position gouvernementale, gouvernement, situation |
| **Réussi** | réussi, succès |
| **Fait majoritaire** | majoritaire, majorité, fait_majoritaire |
| **Ordre** | ordre, rang, position |

### Étape 2 : Télécharger le fichier

1. Ouvrez `gantt-excel.html` dans un navigateur
2. Glissez-déposez votre fichier Excel ou cliquez pour le sélectionner
3. L'outil détecte automatiquement les colonnes correspondantes

### Étape 3 : Vérifier et générer

Vérifiez les correspondances de colonnes (l'outil en devine la plupart), puis cliquez sur **"Générer la frise"**.

### Étape 4 : Télécharger

- **PNG** : Pour intégrer dans Word, PowerPoint ou une présentation (résolution 2x pour impression)
- **SVG** : Format vectoriel pour édition ultérieure dans Inkscape, Adobe Illustrator, etc.

## 📊 Format des dates

L'outil accepte automatiquement plusieurs formats :

- Dates françaises : `jj/mm/aaaa` ou `jj-mm-aaaa`
- Format ISO : `aaaa-mm-jj`
- Années seules : `1789`, `1989` (interprétées comme 1er janvier de l'année)
- Dates Excel : conversions automatiques des numéros de série
- Objets Date natifs (si importé depuis un vrai tableur)

## 🎨 Codage couleur

### Par orientation politique (si la colonne est renseignée)

- **Bleu** : Droite
- **Rouge** : Gauche
- **Orange** : Centre
- **Noir** : Extrême droite

### Par réussite (priorité absolue)

- **Vert** : Réussi (oui)
- **Rouge foncé** : Non réussi (non)

### Autres

- **Hachures blanches** : Fait majoritaire
- **Couleurs par défaut** : Un événement par ligne (si pas de colonne orientation)

## ⚙️ Options de configuration

| Option | Obligatoire | Description |
|--------|---|---|
| Nom | ✅ | Chaque valeur unique crée une ligne de la frise |
| Date de début | ✅ | Date du début de l'événement (ou la seule date pour ponctuel) |
| Date de fin | ❌ | Date de fin de l'événement (vide si ponctuel) |
| Commentaire | ❌ | Label affichée sur la barre ou en externe |
| Ponctuel | ❌ | oui/non - Si oui, affichée comme un losange |
| Orientation | ❌ | gauche/centre/droite/extrême droite |
| Position gouvernementale | ❌ | gouvernement, cohabitation, minoritaire, coalition, etc. |
| Réussi | ❌ | oui/non - Override les couleurs d'orientation |
| Fait majoritaire | ❌ | oui/non - Ajoute des hachures blanches |
| Ordre | ❌ | Nombre pour forcer l'ordre des lignes (tri manual) |

## 📐 Adaptatif et intelligent

- **Zoopage temporel** : Les graduations (jours/mois/années) s'ajustent automatiquement à la portée
- **Empilage des étiquettes** : Si une étiquette ne rentre pas dans sa barre, elle bascule en externe avec un trait
- **Multi-bandes** : Pour les frises très longues, découpage intelligent en bandes horizontales empilées
- **Résolution intelligente** : La largeur se règle pour que les étiquettes tiennent (jusqu'à 3000px max)

## 🛡️ Confidentialité

**Aucun fichier n'est envoyé sur internet.** Tout le traitement se fait en JavaScript dans votre navigateur, côté client. Vos données Excel restent sur votre ordinateur.

## 💻 Technologies utilisées

- **XLSX.js** : Lecture des fichiers Excel
- **SVG** : Rendu du diagramme
- **Canvas** : Conversion SVG → PNG
- **Google Fonts** : Typographie (Hanken Grotesk, Fraunces)

## 📝 Auteur

Créé par **Arnaud BUREL**

## 📄 Licence

Libre d'utilisation — aucune restriction.

---

**Besoin d'aide ?** Vérifiez que :
- ✅ Votre fichier a une en-tête
- ✅ Les dates sont dans un format reconnu
- ✅ La colonne "Nom" contient des valeurs non vides
- ✅ La colonne "Date de début" n'est pas vide
