# Schéma de données Dessertes en forêt : Transport de bois et DFCI

Ce dépôt contient les schémas de données relatifs aux dessertes forestières pour le transport de bois et la Défense des Forêts Contre l'Incendie (DFCI), conformes au standard CNIG v2.0 publié en juin 2026.

## Contexte

Ce standard permet de décrire :
- Les **tronçons de route** en forêt utilisables pour le transport de bois et/ou la DFCI
- Les **itinéraires bois ronds** (ITBR) autorisés par arrêté préfectoral
- Les **équipements** (aires de retournement, places de dépôt, etc.)
- Les **points de contrainte** (ponts, pentes fortes, obstacles, etc.)
- Les **ressources en eau** mobilisables pour la lutte contre l'incendie

## Cadre réglementaire

Ce standard s'inscrit dans le cadre de la **Loi Incendie n° 2023-580 du 10/07/2023** qui exige que les informations relatives aux dessertes forestières, points d'eau et pistes DFCI soient mises à disposition gratuitement et librement sous forme dématérialisée.

## Schémas disponibles

### Schéma racine
- **`schema.json`** : Schéma principal regroupant tous les objets

### Schémas par classe d'objets
- **`troncon-route.json`** : Tronçons de route en forêt (classe générique)
- **`itineraire-bois-rond.json`** : Itinéraires autorisés pour le transport de bois ronds (hérite de troncon-route)
- **`equipement.json`** : Équipements forestiers
- **`point-contrainte.json`** : Points de contrainte de circulation
- **`ressource-en-eau.json`** : Points d'eau et ressources hydriques

## Utilisation

### Validation des données

Les données peuvent être validées avec l'outil [Validata](https://validata.fr/) ou via le portail [NaviForest](https://naviforest.ign.fr/).

### Format de diffusion

Les données peuvent être diffusées dans les formats suivants :
- GeoJSON
- GeoPackage (recommandé)
- Shapefile
- CSV (pour les données attributaires uniquement)

### Système de coordonnées

**Obligatoire** : Lambert-93 (EPSG:2154) pour la France métropolitaine

## Documentation

- [Standard complet CNIG v2.0](https://cnig.gouv.fr/gt-dessertes-pour-les-transports-de-bois-a18535.html)
- [Page du schéma sur schema.data.gouv.fr](https://schema.data.gouv.fr/cnigfr/schema-desserte-transport-bois/)
- [Registre des mesures de qualité](https://data.geocatalogue.fr/ncl/mesuresQuaDoGeo)

## Exemples de données

### Exemple de tronçon de route
```json
{
  "identifiant": "TRONROUT0000002008897356",
  "code_insee_commune_droite": "45234",
  "sens_circulation": "Double sens",
  "position_sol": "0",
  "nature": "Route à 1 chaussée",
  "reseau_bois": "Desserte forestière",
  "reseau_dfci": "Voie DFCI",
  "largeur_chaussee": 5.5,
  "methode_acquisition": "GPS"
}
```

### Exemple d'itinéraire bois rond
```json
{
  "identifiant": "TRONROUT0000002008897357",
  "sens_circulation": "Double sens",
  "position_sol": "0",
  "nature": "Route à 1 chaussée",
  "reseau_bois": "Itinéraire Bois Rond",
  "autorisation_itbr": "Sans restriction",
  "ptra_max_5_essieux": "44",
  "ptra_max_6_essieux": "57",
  "interdiction_horaire": "Non concerné",
  "itbr_temporaire": "Non",
  "arrete_a_bord": "Oui",
  "date_arrete": "2024-03-15",
  "methode_acquisition": "GPS"
}
```

### Exemple d'équipement
```json
{
  "identifiant": "EQU_DESS0000002008897356",
  "code_insee_commune": "45234",
  "nature": "Place de dépôt",
  "gestionnaire": "ONF",
  "nom": "Place de dépôt des Chênes",
  "longueur": 35.0,
  "largeur": 12.0
}
```

### Exemple de ressource en eau
```json
{
  "identifiant": "RESS_EAU0000002008897356",
  "code_insee_commune": "45234",
  "numero_pei": "SDIS45-PI-00342",
  "type_pei": "Point d'aspiration aménagé",
  "type_pei_precis": "Bâche à eau",
  "statut_pei": "Public",
  "volume": 120,
  "accessibilite_hbe": "Lourd",
  "persistance": "Permanent",
  "date_creation": "2023-06-15T10:00:00"
}
```

## Producteurs de données

Les producteurs de données concernés sont :
- **DDT/DDTM** : Directions Départementales des Territoires
- **SDIS** : Services Départementaux d'Incendie et de Secours
- **ONF** : Office National des Forêts
- **CNPF** : Centre National de la Propriété Forestière
- **Collectivités territoriales**
- **Transporteurs forestiers**

## Contribution

Les évolutions du standard sont pilotées par le [groupe de travail Dessertes en forêt du CNIG](https://cnig.gouv.fr/gt-dessertes-pour-les-transports-de-bois-a18535.html).

Pour toute question ou suggestion :
- [Formulaire de contact du CNIG](https://cnig.gouv.fr/spip.php?page=contact)
- GitHub du projet : [cnigfr/schema-dessertes-transport-de-bois](https://github.com/cnigfr/schema-dessertes-transport-de-bois)

## Licence

Les schémas et la documentation sont publiés sous **Licence Ouverte v2.0 (Etalab)**.

## Versions

- **v2.0.0** (juin 2026) : Intégration de la thématique DFCI et mise à jour suite à la Loi Incendie
- **v1.0.0** (mars 2019) : Version initiale "Dessertes pour le transport de bois"

## Contact

**Pilotage** : 
- Isabelle BERTRAND (MASA)
- Vincent MORILLON (FCBA)

**Animation** : 
- Marion LACROIX (IGN)
```