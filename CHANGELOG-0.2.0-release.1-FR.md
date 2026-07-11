# Servant 0.2.0-release.1

Minecraft 1.21.1 - NeoForge

`0.2.0-release.1` est la première version stable de la nouvelle expérience Servant. Ces notes regroupent les changements apportés par `0.2.0-beta.2`, `0.2.0-beta.3` et les dernières finitions de la version stable.

Servant s'articule désormais autour de compagnons rares, trouvés dans le monde, libérés, recrutés, équipés puis orientés vers un rôle. Leur travail se déroule réellement dans Minecraft : ils se déplacent, utilisent des outils, transportent des objets, mangent, combattent et interagissent avec les lieux construits pour eux.

## Release.1 - Dernières finitions

- Les accessoires permettant de marcher sur l'eau influencent désormais le pathfinding en plus des déplacements. Tant que l'effet est actif, la surface de l'eau est considérée comme un sol solide.
- Lorsqu'un effet de marche sur l'eau expire ou que son équipement est retiré, un Servant déjà dans l'eau se met à nager vers son propriétaire.
- Les décisions de chemin liées à Aqua Walker tiennent maintenant compte de sa charge réellement disponible, au lieu de seulement vérifier si la relique est équipée.
- Les barres de santé et de faim de l'inventaire ont été légèrement réduites et séparées pour améliorer leur lisibilité.
- Les indications de saturation et d'épuisement d'AppleSkin restent correctement alignées avec la nouvelle taille de la barre de faim.
- La description publique du mod a été réécrite autour du véritable parcours du joueur et du contenu actuel de la version.
- Le wiki public complet a été mis à jour pour couvrir le recrutement, les commandes, l'inventaire, la faim, la résurrection, les zones de travail, la compatibilité et le dépannage.

## Beta.3 - Un compagnon plus proche du joueur

### Actions, outils et enchantements

- Le minage, les attaques, la pose de blocs, l'utilisation des seaux, les repas, les récoltes et la replantation de l'Assistant utilisent désormais des animations visibles des mains.
- La destruction d'un bloc prend du temps et suit la vitesse de casse du joueur au lieu de se terminer instantanément.
- Le type d'outil, Efficacité, Célérité, Fatigue de minage, le minage dans les airs ou sous l'eau et les attributs d'équipement influencent la vitesse de travail.
- Fortune, Toucher de soie, Solidité, les butins modifiés, l'expérience des blocs et la durabilité sont pris en compte.
- Les attaques de mêlée respectent l'arme sélectionnée, sa vitesse d'attaque, ses dégâts, son recul, ses attaques balayées, ses enchantements et sa durabilité.
- Les travailleurs profitent également des outils adaptés, des bonus de minage, des enchantements, des butins, de l'expérience et de l'usure de l'équipement.
- Les Fermiers et Bûcherons portent visiblement leur outil dans la main principale et l'objet qu'ils souhaitent replanter dans l'autre main.

### Inventaire et barre d'action de l'Assistant

- L'inventaire de l'Assistant a été reconstruit autour de la disposition familière de celui du joueur.
- Un modèle de joueur est maintenant affiché avec l'armure, les objets tenus dans les deux mains et les accessoires équipés.
- Un inventaire persistant de 36 emplacements et une barre d'action sélectionnable de neuf emplacements ont été ajoutés.
- L'emplacement d'arme séparé et invisible a été supprimé. L'Assistant change maintenant d'emplacement dans sa barre d'action pour choisir ses armes, outils, blocs, aliments et seaux.
- L'Assistant organise automatiquement sa barre d'action lorsque son propriétaire lui lance des objets utiles.
- Les infobulles ordinaires au survol, le glisser-déposer, Maj-clic, les échanges avec la barre d'action et le jet d'objets ont été rétablis.
- Un fond d'inventaire proche de celui de Minecraft, accompagné d'un fond assorti pour le panneau Curios, a été ajouté.
- Curios se présente maintenant dans un panneau vertical à gauche, ouvert grâce au bouton placé à côté du modèle de l'Assistant.

### Faim et santé

- Les Servants recrutés utilisent désormais la faim, la saturation, l'épuisement, la régénération naturelle et la famine.
- Manger prend du temps et applique les valeurs nutritives, les effets et l'éventuel contenant restant de l'aliment.
- Des barres de santé et de faim ont été ajoutées à l'inventaire, avec leurs valeurs exactes au survol.
- Jade peut maintenant afficher la santé et la faim des Servants.
- AppleSkin peut afficher la saturation et l'épuisement dans l'inventaire du Servant.

### Déplacements et pathfinding

- Les déplacements vers les objectifs de travail, les blocs en hauteur, les marches étroites et les terrains difficiles ont été améliorés.
- Les Assistants visent maintenant le centre stable d'un bloc au lieu de sauter indéfiniment depuis son bord.
- Des vérifications de saut plus sûres, la gestion du manque d'espace au-dessus de la tête, la destruction des obstacles, la récupération après une chute et l'abandon des chemins impossibles ont été ajoutés.
- Les chemins normaux et non destructifs sont privilégiés avant toute destruction d'obstacle.
- L'Assistant ne pose plus de blocs de terrain lorsqu'il suit son propriétaire, ce qui l'empêche de refermer les tunnels derrière lui.
- La pose de supports temporaires est réservée aux trajets de travail qui en ont réellement besoin.
- Le travail de l'Assistant s'arrête au-delà de 12 blocs et le retour vers son propriétaire devient prioritaire.
- Sa vitesse de suivi s'adapte aux déplacements, aux sprints et aux sauts répétés de son propriétaire.
- Les boucles de suivi à longue distance, qui faisaient tourner l'Assistant sans lui permettre de rejoindre son propriétaire, ont été corrigées.
- L'Assistant évite mieux la lave et tente de s'en échapper en urgence lorsqu'il y tombe.
- Un affichage de débogage de l'IA a été ajouté en haut à gauche. Il peut être activé avec la touche `B`, configurable dans les contrôles.

### MLG et récupération après une chute

- L'Assistant peut désormais tenter visiblement un MLG au seau d'eau pendant une chute dangereuse.
- Il sélectionne le seau d'eau dans sa barre d'action avant de l'utiliser.
- L'eau est récupérée après un délai aléatoire de 24 à 56 ticks, et non plus instantanément.
- Des tentatives de retour par MLG ont été ajoutées lorsqu'une chute peut aider l'Assistant à rejoindre son propriétaire situé plus bas.

### Combat et sécurité du propriétaire

- L'Assistant peut rejoindre immédiatement un combat commencé par son propriétaire, y compris contre une cible passive ou neutre.
- Les joueurs, leurs familiers, leurs projectiles, les Servants du même propriétaire et les attaques invoquées dont l'origine peut être retrouvée ne peuvent plus blesser leurs Servants alliés.
- La protection contre les dégâts alliés empêche également les Servants de blesser leur propriétaire ou les alliés de celui-ci.
- La sélection des armes a été améliorée afin que l'Assistant n'attaque plus avec un outil inadapté lorsqu'une meilleure arme est disponible.
- Les gardes de mêlée et les Assistants adoptent un comportement plus prudent face aux Creepers.
- L'Assistant peut protéger les objets tombés à proximité lorsque son propriétaire meurt, en donnant la priorité aux outils, armes, armures et sacs à dos.

### Mort, sceaux et récupération

- Les Servants recrutés et les Assistants morts peuvent désormais être restaurés grâce à leur Sceau d'asservissement lié.
- La récupération conserve le nom, le rôle, l'inventaire, l'équipement, les Curios, la faim, le propriétaire et la barre d'action de l'Assistant.
- Le sceau de récupération est consommé en mode Survie et conservé en mode Créatif.
- Un enregistrement valide de la mort est nécessaire, ce qui empêche un sceau de dupliquer un Servant simplement déchargé.
- Un joueur peut créer un nouvel Assistant après la mort du précédent.
- La création d'un remplaçant invalide la récupération de l'ancien Assistant et empêche ainsi de restaurer plusieurs Assistants.

### Interface de l'Établi de Servitude

- L'écran de l'Établi de Servitude a été reconstruit avec une disposition plus claire et plus aérée.
- Le curseur du rayon a été remplacé par de simples boutons `-` et `+`.
- Un bouton **Centrer** permet de replacer la zone de travail sur l'établi.
- Des commandes nord, sud, est et ouest permettent de déplacer la zone autour de l'établi.
- Un aperçu persistant des limites a été ajouté dans le monde et reste visible après la fermeture de l'écran.
- Les décalages sont limités afin que l'établi reste toujours à l'intérieur de sa propre zone de travail.
- L'ancienne action `Assign nearest` a été supprimée.

### Curios, Artifacts et Relics

- L'attribution Curios intégrée à Servant se limite désormais à l'emplacement de dos, au lieu d'exposer tous les emplacements enregistrés.
- Les familles d'emplacements fournies par Artifacts, Relics et les extensions de compatibilité prises en charge sont ajoutées lorsque ces mods sont installés.
- Les 49 objets d'Artifacts et les 28 objets de Relics ont été examinés pour leur utilisation par les Servants.
- Les effets automatiques compatibles liés à la santé, aux dégâts, à la défense, à la riposte, à la nourriture, aux déplacements, aux activités sous-marines, à la marche sur les fluides et à l'équipement ont été activés.
- Les raccourcis, sorts, changements de mode, clics droits et actions spéciales d'inventaire restent sous le contrôle du joueur.
- Les charges passives, délais de récupération, gains d'expérience, déplacements, respirations, réflexions de dégâts, rages, dissimulations et neutralités de Relics compatibles sont pris en charge.
- Les délais de récupération, attaques automatiques, ripostes, effets de nourriture et protections contre la mort compatibles d'Artifacts sont pris en charge.
- Les objets Curios et leur état restent attachés au véritable Servant sans être dupliqués ou déplacés pendant les effets passifs compatibles.

### Autres corrections

- Les 36 emplacements de l'Assistant sont conservés après une sauvegarde, sa mort et sa résurrection.
- La perte de durabilité des armures et des casques a été rétablie.
- Les modèles épuisés des gisements miniers ont été corrigés pour Minecraft 1.21.1.
- Le modèle manquant de l'œuf d'apparition de Servant a été ajouté.

## Beta.2 - Progression et rôles reconstruits

### Trouver et recruter des Servants

- Des Servants peuvent apparaître comme prisonniers dans les avant-postes de pillards.
- Les cages des avant-postes contiennent au maximum un Servant prisonnier.
- Lorsqu'ils sont libérés, les prisonniers fuient l'avant-poste, évitent les créatures hostiles et errent dans les environs jusqu'à leur recrutement.
- Les noms traduits `Prisoner` et `Prisonnier` ont été ajoutés.
- Les Sceaux d'asservissement sont devenus les principaux objets de recrutement et se trouvent en explorant des lieux dangereux au lieu d'être fabriqués.
- Le recrutement crée un sceau lié à ce Servant précis.
- Les sceaux liés brillent comme des objets enchantés et affichent le nom du Servant ainsi que son UUID dans les infobulles avancées.

### Propriété et progression

- Retirer le sceau lié suspend le suivi, la garde, le travail, la production et les ordres ordinaires.
- Remettre le bon sceau en place réactive le Servant.
- Les sceaux liés peuvent transférer un Servant chargé à un autre joueur.
- Le Sceau d'asservissement renforcé a été ajouté comme seul moyen normal d'obtenir un Assistant.
- Chaque joueur est limité à un seul Assistant.
- Les commandes d'ordre ordinaires et les actions réseau ne peuvent pas transformer directement un Servant en Assistant ni changer un Assistant en garde ordinaire.

### Rôles et apparences

- Des apparences spécifiques ont été ajoutées pour les Prisonniers, Servants, Assistants, Fermiers, Mineurs, gardes de mêlée et gardes à distance.
- Les Servants utilisent désormais un modèle humanoïde fin, proche de celui du joueur.
- Les armures, outils, armes et équipements de rôle sont visibles.
- Les gardes de mêlée et à distance disposent de variantes visuelles stables et distinctes.
- Des identifiants d'invocation dédiés ont été ajoutés pour les formes Prisonnier, Servant et Assistant.

### Travailleurs et Établis de Servitude

- Les Établis de Servitude basique, avancé et ultime ont été ajoutés.
- L'établi basique accepte 1 travailleur dans un rayon maximal de 16 blocs.
- L'établi avancé accepte 2 travailleurs dans un rayon maximal de 32 blocs.
- L'établi ultime accepte 5 travailleurs dans un rayon maximal de 64 blocs.
- Chaque emplacement de travailleur possède sa propre affectation de Servant et de métier.
- Les métiers de Fermier, Bûcheron et Mineur ont été ajoutés.
- Détruire proprement un établi détache ses travailleurs.
- Réassigner un travailleur chargé libère son ancien emplacement d'établi.
- Les recettes de tous les niveaux d'établi et de la Baguette de Servitude ont été ajoutées.

### Gisements miniers et équilibrage

- Des gisements miniers contrôlés ont été ajoutés pour les Mineurs.
- Leurs recettes utilisent maintenant les blocs de ressources correspondants au lieu de blocs de minerai.
- Les gisements de diamant et d'émeraude nécessitent leur bloc de stockage complet.
- Les gisements de débris antiques nécessitent un Bloc de Netherite.
- Le format des recettes a été corrigé pour Minecraft 1.21.1 afin que les visualiseurs comme JEI puissent les afficher.
- L'équilibrage des Servants, Assistants, établis et gisements miniers repose désormais sur une exploration rare et un investissement de fin de progression.

### Compatibilité de l'équipement

- La gestion et le rendu de l'inventaire Curios ont été ajoutés.
- Le rendu de Sophisticated Backpacks, l'emplacement Curios de dos et l'accès direct aux sacs à dos sont pris en charge.
- Les Servants et Assistants qui suivent leur propriétaire peuvent maintenant voyager entre les dimensions.

## Compatibilité

- Minecraft `1.21.1`
- NeoForge `21.1.235` ou une version plus récente pour Minecraft 1.21.1
- Facultatif : Curios
- Facultatif : Sophisticated Backpacks et Sophisticated Core
- Facultatif : Artifacts
- Facultatif : Relics
- Facultatif : Jade
- Facultatif : AppleSkin
- Facultatif : un visualiseur de recettes comme JEI

Les versions d'accessoires testées sont indiquées dans le wiki public. Les intégrations facultatives ne sont pas nécessaires au fonctionnement de Servant.

## Limitations connues

- Les Établis de Servitude avancé et ultime partagent actuellement l'apparence du bloc de l'établi basique.
- L'imitation de l'Assistant se concentre sur le minage des minerais visibles, la coupe du bois voisin, la gestion de l'équipement, le soutien au combat et le retour vers son propriétaire.
- Les accessoires nécessitant un raccourci, un sort manuel, un mode sélectionné, un clic droit ou une action spéciale dans l'inventaire ne sont pas activés par l'IA des Servants.
- D'autres métiers sont prévus avant l'arrivée de Servants issus de créatures, comme les pillards soumis ou les ravageurs alliés.

## Avant la mise à jour

Sauvegardez vos mondes importants, retirez l'ancien fichier jar de Servant et vérifiez que le serveur et chaque client utilisent la même version. Retirez les accessoires tiers de vos Servants avant de désinstaller le mod auquel ils appartiennent dans une sauvegarde existante.
