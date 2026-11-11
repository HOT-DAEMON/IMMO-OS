# IMMO-OS

> **Vision : construire une plateforme ConTech et PropTech de référence pour concevoir, réaliser et exploiter l’environnement bâti — du territoire jusqu’au composant, et de la première esquisse à la fin de vie.**

IMMO-OS vise un chef-d’œuvre d’ingénierie logicielle : un système où les disciplines du bâtiment et de la ville peuvent travailler ensemble à partir de modèles cohérents, détaillés, vérifiables et réutilisables.

**Important :** cette vision décrit une ambition, pas des fonctionnalités déjà livrées. Le dépôt est au début de son développement. Les calculs et documents produits à l’avenir devront être vérifiés par des professionnels qualifiés et conformes aux réglementations applicables. IMMO-OS ne se substitue ni à leur jugement ni aux autorités compétentes.

## La vision

Aujourd’hui, un projet immobilier mobilise des outils, des modèles et des équipes souvent cloisonnés. IMMO-OS ambitionne de relier ces informations dans un environnement commun, traçable et extensible, à l’image des grands systèmes d’ingénierie qui coordonnent des milliers de composants et de contributeurs.

L’ambition est de pouvoir décrire un projet à toutes ses échelles — territoire, site, bâtiment, système, assemblage, pièce et matériau — et d’en suivre les exigences, hypothèses, décisions, coûts, risques, performances et changements tout au long de son cycle de vie.

À terme, la plateforme vise à assister la conception, la coordination, l’exécution et l’exploitation de nombreux types d’ouvrages : logements, hôtels, bureaux, équipements publics, aéroports, gares, réseaux de transport, ponts et infrastructures. Chaque type d’ouvrage nécessitera des modèles métiers, des règles, des données et des validations adaptés à son contexte.

## Domaines que la plateforme ambitionne de relier

### Territoire, architecture et conception

- Cartographie, topographie, géographie, données de site et contexte urbain
- Urbanisme, contraintes foncières, réseaux et règles locales
- Référentiel de styles, typologies, techniques et précédents architecturaux de différentes périodes et cultures, avec sources et droits d’utilisation documentés
- Conception architecturale, programmation, espaces, circulations et accessibilité
- Design d’intérieur, matériaux, équipements, éclairage, acoustique et finitions
- Études de variantes, exigences du maître d’ouvrage et arbitrages de conception

### Ingénierie et systèmes du bâtiment

- Génie civil, géotechnique et ingénierie des structures
- Fondations, béton, maçonnerie, coffrage, ferraillage et charpentes
- Électricité, plomberie, chauffage, ventilation, climatisation et protection incendie
- Enveloppe, menuiserie, isolation, étanchéité et gestion des eaux
- Chimie et caractérisation des matériaux, durabilité et compatibilité des composants
- Coordination spatiale et détection de conflits entre disciplines

### Chantier, contrats et coûts

- Phasage des travaux, méthodes d’exécution, quantités et approvisionnements
- Estimation documentée des matériaux, des équipements, des pertes et des coûts
- Contrats, responsabilités, livrables, jalons, modifications et réserves
- Suivi d’avancement, contrôles qualité, inspections, incidents et traçabilité
- Coordination des intervenants et comparaison entre conception, chantier et ouvrage réalisé

### Exploitation et gestion immobilière

- Gestion des bâtiments, espaces, équipements, parkings et accès
- Entretien préventif, interventions, garanties, consommations et historique des actifs
- Gestion locative : annonces, candidatures, baux, paiements, états des lieux et clés
- Relations avec les occupants, demandes de service et suivi des prestataires
- Parcours de sélection des candidats fondé sur des critères pertinents, transparents et conformes au droit applicable ; aucune décision ne doit reposer sur des caractéristiques protégées ou des inférences sensibles

## Un modèle numérique relié, du site au composant

Le cœur du produit sera un modèle de données commun capable de représenter les éléments d’un ouvrage et leurs relations. Un composant pourra être décrit par son identité, sa géométrie, ses matériaux, ses propriétés, ses interfaces, ses exigences, son fabricant éventuel, ses coûts, sa durée de vie estimée, ses opérations de maintenance et ses preuves documentaires.

Les composants devront pouvoir être assemblés et recombinés, sous réserve de contraintes explicites : dimensions, tolérances, charges, compatibilité, réglementation, disponibilité, performances et méthodes d’exécution. Les choix devront rester traçables : quelle version du modèle, quelles données d’entrée, quelles hypothèses, quelle règle ou source, quel calcul et quelle validation ont conduit à un résultat ?

Le modèle doit permettre de naviguer entre les vues pertinentes — plans, coupes, détails, vues 3D, tableaux, réseaux et séquences de chantier — sans perdre le lien avec les exigences et les données sous-jacentes.

## Calculs, simulations et scénarios

À terme, IMMO-OS souhaite orchestrer des outils de calcul et de simulation, selon les disciplines et les données disponibles, notamment pour :

- quantités et nomenclatures : béton, ciment, granulats, eau, mortier, acier, bois et équipements ;
- vérifications de conception structurelle et dimensionnement, selon les normes, les matériaux et les conditions du projet ;
- analyses de site et simulations d’ensoleillement, d’ombres, de vent, d’énergie, d’acoustique et de confort ;
- coordination des réseaux, détection de collisions et planification de séquences ;
- suivi de l’état des matériaux, des risques de fuite, de corrosion, de dégradation et des besoins de maintenance ;
- scénarios de performance et de vieillissement à différents horizons, par exemple 10, 100 ou 1 000 ans, en explicitant les limites, les hypothèses, les incertitudes et les scénarios d’entretien ou de remplacement.

Un résultat ne devra jamais être présenté comme « juste » sans contexte. Chaque calcul devra pouvoir exposer ses unités, entrées, hypothèses, méthode ou moteur utilisé, version, domaine de validité, incertitude et statut de vérification. La composition des matériaux, le dimensionnement et la sécurité d’un ouvrage dépendent notamment du site, des normes en vigueur, des produits réellement employés et de l’expertise professionnelle.

## Principes d’architecture logicielle

L’architecture recherchée s’inspire des pratiques des systèmes d’ingénierie à grande échelle — interfaces explicites, composants réutilisables, automatisation, tests, données traçables et évolutions compatibles — sans prétendre reproduire une architecture interne de Google. Elle devra permettre à une petite équipe de démarrer simplement, puis d’évoluer sans enfermer le produit dans un monolithe indifférencié ni imposer trop tôt une infrastructure distribuée complexe.

### 1. Noyau de domaine et modules métier

Un noyau partagé définit les identifiants, unités, géométries, versions, relations, événements et règles de validation transverses. Les domaines restent des modules délimités : conception, structure, matériaux, chantier, coûts, contrats, actifs, maintenance et gestion locative. Chaque module possède des responsabilités et des interfaces documentées.

### 2. Contrats et composants recombinables

Les API, schémas de données et contrats d’exécution sont versionnés. Ils décrivent les entrées, sorties, préconditions, responsabilités, tolérances, règles de compatibilité et résultats attendus. Les modules échangent par des contrats explicites plutôt que par des dépendances cachées.

### 3. Modèle de projet et référentiel de données

Les données géospatiales, documentaires, géométriques, tabulaires et temporelles doivent rester reliées par des identifiants stables et une provenance consultable. Le choix des stockages sera guidé par les besoins réels de chaque type de donnée, sans imposer une technologie unique à tous les usages.

### 4. Moteurs spécialisés et orchestration

Les calculs structurels, énergétiques, géospatiaux ou de simulation pourront être fournis par des moteurs spécialisés, intégrés derrière des interfaces communes. L’orchestrateur gère les versions, tâches, dépendances, résultats, erreurs et preuves de validation. Un modèle de langage, s’il est utilisé, pourra aider à rechercher, expliquer ou préparer des tâches, mais ne sera pas considéré comme une autorité de calcul ou de validation.

### 5. Applications adaptées aux métiers

Des interfaces distinctes pourront servir les architectes, ingénieurs, entreprises de travaux, gestionnaires, propriétaires et occupants, tout en travaillant sur les mêmes données gouvernées. Les vues et autorisations dépendront du rôle et du projet.

### 6. Qualité, sûreté et gouvernance

La sécurité, la confidentialité, les permissions, l’auditabilité, les sauvegardes, l’accessibilité et la conformité devront être conçues dès le départ. Les modifications importantes seront historisées. Les décisions à conséquences réglementaires, financières ou de sécurité devront être contrôlées par des personnes autorisées.

## Architecture logique envisagée

Cette organisation est indicative : elle sera affinée avec l’évolution du code et les besoins vérifiés.

```text
IMMO-OS/
├── apps/                 # Applications web et interfaces par métier
├── modules/              # Domaines : conception, chantier, actifs, location…
├── core/                 # Identités, unités, géométrie, événements, versions
├── contracts/            # API, schémas, contrats et compatibilité
├── engines/              # Adaptateurs vers calculs et simulations spécialisés
├── data/                 # Modèles, migrations, référentiels et imports
├── integrations/         # Formats, logiciels et services externes
├── platform/             # Authentification, permissions, observabilité, CI/CD
├── docs/                 # Documentation produit, technique et décisions
└── tests/                # Tests unitaires, intégration et validation métier
```

## Développement par étapes

L’objectif est immense ; le réaliser de façon responsable suppose de livrer des fondations vérifiables avant de promettre une automatisation totale.

1. **Fondations** — définir le périmètre initial, les utilisateurs, les termes métier, les unités, les identifiants, les contrats et les règles de qualité.
2. **Modèle numérique du bâtiment** — représenter un projet, ses espaces, éléments, documents, exigences et versions ; fournir une navigation et des exports utiles.
3. **Coordination de conception** — gérer les disciplines, les composants, leurs interfaces, les variantes et la détection de conflits.
4. **Quantités et chantier** — relier les éléments du modèle aux métrés, estimations, contrats, planning, contrôles et changements.
5. **Calculs et simulations** — intégrer progressivement des moteurs qualifiés, avec résultats reproductibles, sources, tests et limites explicites.
6. **Exploitation immobilière** — gérer les actifs, équipements, maintenance, espaces, occupants et flux locatifs dans un cadre respectueux des droits et de la vie privée.
7. **Interopérabilité et échelle** — développer les imports/exports, intégrations, gestion de portefeuille et collaboration multi-projets sur la base de besoins démontrés.

## État du projet

IMMO-OS est actuellement au stade de la vision et de la structuration initiale. La description ci-dessus présente une direction cible ; elle ne signifie pas que les modules, calculs, simulations, intégrations ou fonctions de gestion locative sont déjà implémentés. Les fonctionnalités réellement disponibles devront être documentées au fur et à mesure dans ce dépôt.

## Démarrage et contribution

Le dépôt ne définit pas encore de procédure d’installation ou de commande de lancement stable. Ces instructions seront ajoutées quand la première base logicielle et sa pile technique seront établies.

Les contributions sont les bienvenues. Pour toute proposition :

1. Ouvrir ou consulter une issue pour préciser le besoin et son contexte.
2. Décrire les hypothèses, les utilisateurs concernés et les critères de réussite.
3. Pour les règles ou calculs métiers, fournir les références, unités, limites et moyens de validation.
4. Proposer une modification limitée, testée et documentée.

## Sécurité et usage responsable

Ne pas utiliser une sortie expérimentale comme plan d’exécution, avis professionnel, certification ou garantie de sécurité. Les plans, calculs et décisions concernant un ouvrage réel doivent être examinés et approuvés par les professionnels qualifiés compétents, selon la juridiction, le site et les normes applicables. Toute donnée personnelle ou locative devra être traitée avec une base légale, une finalité claire, une durée de conservation appropriée et des protections contre les décisions discriminatoires.

## Licence

Aucune licence n’est actuellement définie. Les droits de réutilisation et de contribution devront être clarifiés avant toute diffusion ou adoption externe.

## Contact

Pour discuter de la vision, signaler un problème ou proposer une amélioration, utilisez les [issues du dépôt](https://github.com/HOT-DAEMON/IMMO-OS/issues).
