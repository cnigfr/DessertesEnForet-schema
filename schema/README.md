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
	"code_insee_commune_droite": "60300",
	"code_insee_commune_gauche": "63000",
	"numero_route": "D330",
	"nom_ban_voie_droite": "Avenue de Creil",
	"nom_ban_voie_gauche": "Avenue de Creil",
	"nom_usuel_voie_droite": "",
	"nom_usuel_voie_gauche": "",
	"gestionnaire": "Conseil départemental de l'Oise",
	"importance": "5",
	"sens_circulation": "Double",
	"position_sol": "0",
	"largeur_chaussee": 6.0,
	"ptra_max": 44,
	"largeur_max_autorisee": 3.5,
	"hauteur_max_autorisee": 4.5,
	"longueur_max_autorisee": 18.0,
	"praticabilite": "Tout temps",
	"methode_acquisition": "Fichier numérique non métrique",
	"sources": "DDT60",
	"date_modification": "2023-05-10T08:30:00",
	"nature": "Route à deux chaussées",
	"reseau_bois": "Desserte forestière",
	"accessibilite_bois": "Grumier sans timon",
	"reseau_dfci": "Voie DFCI",
	"servitude_dfci": "Oui",
	"beneficiaire_servitude_dfci": "État",
	"gabarit_dfci": "Poids lourd",
	"fosses_dfci": "Fossés à droite et à gauche",
	"vitesse_moyenne_dfci": 40,
	"categorie_dfci": "1re catégorie",
	"acces_vehicule_leger": "Libre",
	"acces_pieton": "Libre"
}
```

### Exemple d'itinéraire bois rond
```json
{
	"identifiant": "TRONROUT0000002008897356",
	"code_insee_commune_droite": "60300",
	"code_insee_commune_gauche": "63000",
	"numero_route": "D330",
	"nom_ban_voie_droite": "Avenue de Creil",
	"nom_ban_voie_gauche": "Avenue de Creil",
	"nom_usuel_voie_droite": "",
	"nom_usuel_voie_gauche": "",
	"gestionnaire": "Conseil départemental de l'Oise",
	"importance": "5",
	"sens_circulation": "Double",
	"position_sol": "0",
	"largeur_chaussee": 6.0,
	"ptra_max": 44,
	"largeur_max_autorisee": 3.5,
	"hauteur_max_autorisee": 4.5,
	"longueur_max_autorisee": 18.0,
	"praticabilite": "Tout temps",
	"methode_acquisition": "Fichier numérique non métrique",
	"sources": "DDT60",
	"date_modification": "2023-05-10T08:30:00",
	"nature": "Route à deux chaussées",
	"reseau_bois": "Desserte forestière",
	"accessibilite_bois": "Grumier sans timon",
	"reseau_dfci": "Voie DFCI",
	"servitude_dfci": "Oui",
	"beneficiaire_servitude_dfci": "État",
	"gabarit_dfci": "Poids lourd",
	"fosses_dfci": "Fossés à droite et à gauche",
	"vitesse_moyenne_dfci": 40,
	"categorie_dfci": "1re catégorie",
	"acces_vehicule_leger": "Libre",
	"acces_pieton": "Libre"
	"autorisation_itbr": "Transit",
	"raccordement_itbr": "10 km max",
	"raccordement_au_plus_court": "Oui",
	"autorisation_raccordement_itbr": "Selon configuration", 
	"configuration_raccordement_itbr": "Tonnage > 48 T à 6 essieux minimum",
	"equipement_raccordement_itbr": "6 essieux max",
	"ptra_max_5_essieux": 44,
	"ptra_max_6_essieux": 48,
	"charge_essieu_max": 12,
	"interdiction_horaire": "Plage horaire",
	"itbr_temporaire": "Non"
	"debut_periode_itbr": "",
	"fin_periode_itbr": "",
	"arrete_a_bord": "Non",
	"date_arrete": "2024-05-20"
}
```

### Exemple d'équipement
```json
{
  "identifiant": "EQU_DESS0000002008897356",
  "code_insee_commune": "45234",
  "nature": "Place de dépôt",
  "gestionnaire": "Office National des Forêts",
  "nature_troncon": "Route empierrée",
  "nom": "Place de dépôt du Grand Duc",
  "commentaire: "Accès difficile en période hivernale",
  "contributeur": "Crige",
  "longueur": 35.0,
  "largeur": 12.0
}
```

### Exemple de contrainte
```json
{
	"identifiant": "CONTDESS0000002008897356",
	"code_insee_commune": "27098",
	"nature": "Pont",
	"gestionnaire": "Conseil Départemental de l'Eure",
	"nature_troncon": "Route à 1 chaussée",
	"nom": "Pont du Grand-Duc",
	"commentaire": "Travaux prévus en 2027",
	"contributeur": "Crige",
	"restriction_itbr": "Restriction",
	"ptra": 44,
	"franchissement": "Franchie",
	"hauteur_max": 5.0,
	"largeur_max": 3.5,
	"longueur_max": 25.0,
	"charge_essieu_max": 13.0
}
```

### Exemple de ressource en eau
```json
{
	"identifiant": "RESS_EAU0000002008897356",
	"code_insee_commune": "27098",
	"numero_pei": "SDIS27-PI-00342",
	"numero_gestionnaire": "83027_PI_0254",
	"nom_gestionnaire": "Mairie de Bouchevilliers",
	"numero_terrain": "PI-27-0042",
	"type_pei": "Poteau d'incendie",
	"type_pei_precis": "",
	"statut_pei": "Public",
	"pression_dynamique": 1.0,
	"pression_statique": 8.5,
	"debit": 60,
	"volume": 9999,
	"date_creation": "2018-07-12T10:00:17",
	"date_modification": "2023-03-01T09:00:00",
	"methode_acquisition": "Photogrammétrie",
	"accessibilite_hbe": "Non accessible",
	"persistance": "Permanent"
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