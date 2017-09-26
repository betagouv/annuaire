FORMAT: 1A
HOST: http://etablissements-publics.api.gouv.fr/v1

# Annuaire des établissements publics de l'administration

Cette API recense plus de 60 000 guichets publics locaux (mairies, organismes sociaux, services de l'état, etc.). Elle fournit leurs coordonnées (adresses, téléphones, site internet, horaires d'ouverture, coordonnées de géolocalisation).
> Le contenu de cet annuaire est généré automatiquement à partir des données de [Service-public.fr - Annuaire de l’administration - Base de données locales](https://www.data.gouv.fr/fr/datasets/53699fe4a3a729239d206227),
> par le script d'import disponible sur [github.com/sgmap/annuaire-import](https://github.com/sgmap/annuaire-import)

## Lancement de l'API sur docker

[Docker](https://www.docker.com/) est un logiciel libre qui automatise le déploiement d'applications dans des conteneurs logiciels.

1. Construire le conteneur docker de l'API
```bash
  docker build -t annuaire .
```

2. Lancer le conteneur
```bash
  docker run -p 4000:80 annuaire  
```

3. La documentation de l'API est alors disponible sur `http://localhost:4000`  `http://localhost:4000/v1/organismes/13/maison_handicapees`

## Liste des organismes [/organismes/{departement}/{type}]

### Trouver des organismes par département et par type [GET]

+ Parameters

    + departement: `14` (number) - Code departement sur deux caractères.

    + type: `maison_handicapees` (enum[string]) - Code du type de l'organisme.
        + Members
            + `adil` - Information sur le logement (agenceAgence départementale pour l’information sur le logement (ADIL) départementale, Adil)
            + `anah` - Agence nationale de l’habitat (ANAH), réseau local
            + `ars` - Agence régionale de santé (ARS)
            + `afpa` - "Association nationale pour la formation professionnelle des adultes (AFPA), réseau local"
            + `apec` - Association pour l’emploi des cadres (APEC)
            + `apecita` - "Association pour l'emploi des cadres, ingénieurs et techniciens de l'agriculture et de l'agroalimentaire (APECITA), réseau local"
            + `banque_de_france` - "Banque de France, succursale"
            + `gendarmerie` - Brigade de gendarmerie
            + `bav` - Bureau d'aide aux victimes
            + `bsn` - Bureau ou centre du service national
            + `caf` - Caisse d’allocations familiales (CAF)
            + `carsat` - Caisse d'assurance retraite et de la santé au travail (CARSAT)
            + `cpam` - Caisse primaire d’assurance maladie (CPAM)
            + `cicas` - Centre d’information de conseil et d'accueil des salariés (CICAS)
            + `cio` - Centre d’information et d’orientation (CIO)
            + `cidf` - "Centre d’information sur les droits des femmes et des familles (CIDFF)"
            + `centre_detention` - Centre de détention
            + `cdg` - Centre de gestion de la fonction publique territoriale
            + `pmi` - Centre de protection maternelle et infantile (PMI)
            + `crib` - Centre de ressources et d'information des bénévoles (CRIB)
            + `csl` - Centre de semi-liberté
            + `cddp` - Centre départemental de documentation pédagogique
            + `centre_impots_fonciers` - Centre des impôts foncier et cadastre
            + `cnra` - Centre en route de la navigation aérienne
            + `cnfpt` - "Centre national de la fonction publique territoriale (CNFPT), réseau local"
            + `crfpn` - "Centre ou délégation régionale de recrutement et de formation de la police nationale"
            + `centre_penitentiaire` - Centre pénitentiaire
            + `creps` - Centre régional d’éducation populaire et de sports (CREPS)
            + `crdp` - Centre régional de documentation pédagogique
            + `chambre_agriculture` - Chambre d’agriculture
            + `cci` - Chambre de commerce et d’industrie (CCI)
            + `chambre_metier` - Chambre de métiers et de l’artisanat
            + `crc` - Chambre régionale ou territoriale des comptes
            + `commissariat_police` - Commissariat de police
            + `commission_conciliation` - Commission départementale de conciliation
            + `civi` - Commission d'indemnisation des victimes d'infraction
            + `conciliateur_fiscal` - Conciliateur fiscal
            + `conseil_culture` - "Conseil de la culture, de l’éducation et de l’environnement"
            + `prudhommes` - Conseil de prud’hommes
            + `cesr` - "Conseil économique, social et environnemental régional"
            + `cg` - Conseil départemental
            + `cr` - Conseil régional
            + `caa` - Cour administrative d’appel
            + `cour_appel` - Cour d’appel
            + `crous` - CROUS et ses antennes
            + `defenseur_droits` - Défenseur des droits
            + `dml` - Délégation à la mer et au littoral
            + `drrt` - Délégation régionale à la recherche et à la technologie
            + `dr_femmes` - Délégation régionale aux droits des femmes et à l’égalité
            + `dr_insee` - Délégation régionale de l’INSEE
            + `dronisep` - Délégation régionale de l’ONISEP
            + `ars_antenne` - Délégation territoriale de l'Agence régionale de santé
            + `dac` - Direction de l’aviation civile
            + `ddcs` - Direction départementale de la cohésion sociale (DDCS)
            + `ddcspp` - Direction départementale de la cohésion sociale et de la protection des populations (DDCSPP)
            + `dd_fip` - Direction départementale des finances publiques
            + `ddt` - Direction départementale des territoires -et de la mer- (DDT)
            + `ddsp` - Direction départementale ou service de la sécurité publique
            + `inspection_academique` - Direction des services départementaux de l'Éducation nationale
            + `did_routes` - Direction interdépartementale des routes
            + `drpjj` - Direction interdépartementale ou régionale de la protection judiciaire de la jeunesse
            + `dir_mer` - Direction interrégionale de la mer
            + `dir_pj` - Direction interrégionale de la police judiciaire
            + `drsp` - Direction interrégionale des services pénitentiaires
            + `drddi` - Direction interrégionale et régionale des douanes
            + `dreal` - "Direction régionale de l’environnement, de l’aménagement et du logement (DREAL)"
            + `dreal_ut` - "Unité territoriale - Direction régionale de l'environnement, de l'aménagement et du logement (DREAL)"
            + `drjscs` - "Direction régionale de la jeunesse, des sports et de la cohésion sociale"
            + `draf` - "Direction régionale de l'alimentation, de l’agriculture et de la forêt (DRAAF)"
            + `onf` - Direction régionale de l'Office national des forêts
            + `drac` - Direction régionale des affaires culturelles (DRAC)
            + `direccte` - "Direction régionale des entreprises, de la concurrence, de la consommation, du travail et de l'emploi"
            + `direccte_ut` - "Unité territoriale - Direction régionale des entreprises, de la concurrence, de la consommation, du travail et de l'emploi"
            + `dr_fip` - Direction régionale des finances publiques
            + `driee` - Direction régionale et interdépartementale de l'environnement et de l'énergie (DRIEE)
            + `driee_ut` - Unité territoriale - Direction régionale et interdépartementale de l'environnement et de l'énergie (DRIEE)
            + `driea` - Direction régionale et interdépartementale de l'équipement et de l'aménagement (DRIEA)
            + `driea_ut` - Unité territoriale - Direction régionale et interdépartementale de l'équipement et de l'aménagement (DRIEA)
            + `drihl` - Direction régionale et interdépartementale de l'hébergement et du Hébergement et logement (direction logement (DRIHL) régionale et
            + `drihl_ut` - Unité territoriale - Direction régionale et interdépartementale de l'hébergement et du logement (DRIHL)
            + `ddpjj` - Direction territoriale de la protection judiciaire de la jeunesse
            + `dz_paf` - Direction zonale de la police aux frontières
            + `dd_femmes` - "Droit des femmes et égalité, mission départementale"
            + `esm` - Etablissement spécialisé pour mineurs
            + `fdc` - Fédération départementale des chasseurs
            + `fdapp` - "Fédération départementale pour la pêche et la protection du milieu aquatique"
            + `fongecif` - Fongecif
            + `prefecture_greffe_associations` - Greffe des associations
            + `greta` - Greta
            + `cij` - "Information jeunesse, réseau local"
            + `epci` - Intercommunalité
            + `mairie` - Mairie
            + `paris_mairie` - "Mairie de Paris, Hôtel de Ville"
            + `paris_mairie_arrondissement` - "Mairie de Paris, mairie d'arrondissement"
            + `mairie_com` - Mairie des collectivités d'outre-mer
            + `maison_centrale` - Maison centrale
            + `maison_arret` - Maison d'arrêt
            + `mjd` - Maison de justice et du droit
            + `maison_handicapees` - Maison départementale des personnes handicapées (MDPH)
            + `dir_meteo` - "Météo France, direction interrégionale"
            + `maia` - Mission d’accueil et d’information des associations (MAIA)
            + `mission_locale` - "Mission locale et Permanence d’accueil, d’information et d’orientation (PAIO)"
            + `msa` - "Mutualité sociale agricole (MSA), réseau local"
            + `ofii` - "Office français de l'immigration et de l'intégration (ex ANAEM), réseau local"
            + `onac` - "Office national des anciens combattants (ONAC), réseau local"
            + `permanence_juridique` - Permanence juridique
            + `accompagnement_personnes_agees` - Plateforme d'accompagnement et de répit pour les aidants de personnes âgées
            + `pif` - Point info famille
            + `clic` - Point d'information local dédié aux personnes âgées
            + `pole_emploi` - Pôle emploi
            + `prefecture` - Préfecture
            + `paris_ppp` - Préfecture de police de Paris
            + `paris_ppp_gesvres` - Préfecture de police de Paris - Site central de Gesvres
            + `paris_ppp_antenne` - "Préfecture de police de Paris, antenne d’arrondissement"
            + `paris_ppp_certificat_immatriculation` - "Préfecture de police de Paris, certificat d'immatriculation"
            + `paris_ppp_permis_conduire` - "Préfecture de police de Paris, permis de conduire"
            + `pp_marseille` - Préfecture de police des Bouches-du-Rhône
            + `prefecture_region` - Préfecture de région
            + `ddpp` - "Protection des populations (direction départementale, DDPP)"
            + `rectorat` - Rectorat
            + `sgami` - Secrétariat pour l'administration du ministère de l'Intérieur (SGAMI)
            + `service_navigation` - Service de la navigation
            + `hypotheque` - Service de publicité foncière ex-conservation des hypothèques
            + `sie` - Service des impôts des entreprises du Centre des finances publiques
            + `sip` - Service des impôts des particuliers du Centre des finances publiques
            + `spip` - Service pénitentiaire d'insertion et de probation
            + `sdac` - Service territorial de l’architecture et du patrimoine
            + `suio` - Service universitaire d'information et d'orientation
            + `sous_pref` - Sous-préfecture
            + `tresorerie` - Trésorerie
            + `ta` - Tribunal administratif
            + `ti` - Tribunal d’instance
            + `tribunal_commerce` - Tribunal de commerce
            + `tgi` - Tribunal de grande instance
            + `te` - Tribunal pour enfants
            + `urssaf` - Urssaf

+ Response 200 (application/json)

        {
        "type": "FeatureCollection",
        "features": [
            {
                "type": "Feature",
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        -0.3576579988,
                        49.1777992249
                    ]
                },
                "properties": {
                    "id": "maison_handicapees-14118-01",
                    "codeInsee": "14118",
                    "dateMiseAJour": "2017-02-21",
                    "pivotLocal": "maison_handicapees",
                    "Nom": "Maison départementale des personnes handicapées (MDPH) - Calvados",
                    "EditeurSource": "La Direction de l'information légale et administrative (Premier ministre)",
                    "Adresse": {
                        "type": "géopostale",
                        "Ligne": "17 rue du 11-Novembre",
                        "CodePostal": "14000",
                        "NomCommune": "Caen",
                        "Localisation": {
                            "Latitude": "49.1777992249",
                            "Longitude": "-0.3576579988",
                            "Précision": "6"
                        },
                        "Accessibilité": {
                            "type": "ACC"
                        }
                    },
                    "CoordonnéesNum": {
                        "Téléphone": "02 31 78 91 75",
                        "Télécopie": "02 31 78 91 99",
                        "Email": "mdph@calvados.fr",
                        "Url": "http://www.calvados.fr"
                    },
                    "Ouverture": {
                        "PlageJ": {
                            "début": "lundi",
                            "fin": "vendredi",
                            "PlageH": [
                                {
                                    "début": "09:00:00",
                                    "fin": "12:15:00"
                                },
                                {
                                    "début": "13:30:00",
                                    "fin": "16:15:00"
                                }
                            ]
                        }
                    }
                }
            }
        ]
        }
