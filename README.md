# EuroMaroc Travel — Site public & CRM frontend

Projet de démonstration réalisé en HTML5, CSS3 et JavaScript Vanilla. Aucun backend, serveur applicatif, API métier ou base de données n'est requis.

## Lancer le projet

1. Décompresser le dossier `euromaroc-travel`.
2. Ouvrir `index.html` dans un navigateur récent.
3. Pour accéder au CRM, cliquer sur « Espace entreprise » dans le pied de page ou ouvrir `crm/index.html`.

Un serveur statique local (par exemple l'extension Live Server de VS Code) est conseillé pour une navigation plus régulière entre fichiers, mais aucun build n'est nécessaire.

## Fonctionnalités

### Site public
- Accueil, présentation de l'agence, destinations, catalogue de voyages/circuits et contact.
- Fiches détaillées de chaque offre du catalogue.
- Recherche et filtre par catégorie.
- Demande de réservation préremplie avec le voyage choisi ; le formulaire ouvre un brouillon e-mail via `mailto:`.
- Navigation responsive.

### CRM de démonstration
- Tableau de bord et indicateurs calculés à partir des données locales.
- Réservations : recherche, filtre, ajout, consultation, modification et suppression.
- Clients : ajout, consultation, modification et suppression.
- Voyages et circuits : catalogue, recherche, filtre, consultation et modification/ajout.
- Persistance locale via `localStorage` (`euromaroc_demo_v1`).

## Contenu et limites de la reprise

Le catalogue initial reprend les 13 offres identifiées sur la page d'accueil du site source au moment de l'audit. Les descriptions affichées sont les éléments accessibles dans les pages consultées. Les programmes jour par jour, dates, conditions et prestations non disponibles dans les données récupérées ne sont pas inventés ; ils sont signalés comme à confirmer.

Les réservations et clients du CRM sont des données fictives de démonstration. Les prix absents du site source restent « à confirmer ». Les prix 100 € et 145 € sont conservés pour les deux offres où ils étaient affichés.

## Images

Les visuels du site utilisent actuellement des images Unsplash chargées par URL. L'environnement de génération ne disposait pas d'accès réseau pour télécharger les fichiers images localement. Les références sont centralisées dans `js/data.js` et `js/main.js` et pourront être remplacées par des fichiers dans `assets/images/` dès que le téléchargement est possible.

## Structure

```text
euromaroc-travel/
├── index.html
├── css/
│   ├── style.css
│   └── crm.css
├── js/
│   ├── data.js
│   └── main.js
├── crm/
│   ├── index.html
│   └── crm.js
├── assets/
│   └── images/
└── README.md
```

## Préparation backend future

Les données et fonctions CRM sont isolées dans `js/data.js` et `crm/crm.js`. Le stockage est encapsulé dans `save()` et l'initialisation de `store`, ce qui facilitera le remplacement futur de `localStorage` par des appels à une API REST Spring Boot et une base MySQL/PostgreSQL.

## Avertissement

Ce livrable est un prototype frontend. Il ne réalise aucune réservation réelle, aucun envoi serveur, aucune authentification ni synchronisation entre appareils. `localStorage` est propre au navigateur et à l'appareil utilisé.


### Mise à jour de la page À propos
La page « À propos » reprend les informations fournies par le client : histoire de l'agence, fondation à Tanger, présentation de Saïd Mejdoubi, langues des circuits, accompagnement des groupes et voyageurs à mobilité réduite, moyens de transport et destinations marocaines citées. Deux photos ont été extraites de la capture d'écran fournie et placées dans `assets/images/`.

## Pages ajoutées

- **Hajj et Omra** (`#hajj-umrah`) : présentation du pèlerinage, brochures fournies par le client et formulaire de demande.
- **Autres destinations** (`#other-destinations`) : présentation des voyages sur mesure, visuels de destinations et brochures fournies.

Les brochures et images recadrées proviennent des captures d'écran transmises pour le projet. Les dates, tarifs, disponibilités et conditions des forfaits doivent être confirmés auprès de l'agence.
