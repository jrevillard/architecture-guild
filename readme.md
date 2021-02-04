# Guilde Architecture Technique

- [Guilde Architecture Technique](#guilde-architecture-technique)
  * [Motivation](#motivation)
  * [Roles et responsabilités de la guilde](#roles-et-responsabilités-de-la-guilde)
    + [Aligner l'architecture des systèmes sur les objectifs de l'entreprise](#aligner-larchitecture-des-systèmes-sur-les-objectifs-de-lentreprise)
    + [Trouver et recommander des solutions aux problèmes partagés](#trouver-et-recommander-des-solutions-aux-problèmes-partagés)
    + [Partager les architectures et les connaissances techniques](#partager-les-architectures-et-les-connaissances-techniques)
  * [Comment la guilde travail](#comment-la-guilde-travail)
    + [Qui est responsable](#qui-est-responsable)
    + [RFC](#rfc)
    + [Prise de décision et dossier de décision d'architecture](#prise-de-décision-et-dossier-de-décision-d-architecture)
    + [Diagramme d'architecture (C4 model)](#diagramme-d-architecture--c4-model-)
  * [Comment la guilde coopère avec les autres](#comment-la-guilde-coop-re-avec-les-autres)
    + [Commercial](#commercial)
    + [Développeurs](#développeurs)
    + [Direction](#direction)
  * [Bénéfices](#bénéfices)
    + [Exemples de réalisations](#exemples-de-réalisations)
  * [Qui d'autre travail de cette manière](#qui-d-autre-travail-de-cette-manière)
  * [Contacte](#contacte)

## Motivation

Il n'y a pas si longtemps, il était courant de trouver des comités d'examen d'architecture centralisés dans les grandes organisations techniques, qui examineraient toutes les conceptions pour garantir leur cohérence avec une vision globale. Lorsque l'informatique était principalement considéré comme un centre de coûts, cela avait un sens éminent, car la normalisation et la cohérence sont un excellent moyen de contenir les coûts de maintenance. Cette centralisation était nécessaire, en raison de la nature monolithique et lente du système en développement.

Maintenant, cependant, il est plus utile de permettre aux équipes de bouger rapidement, en leur donnant plus d'options et de pouvoir de décision. La nature distribuée d'un système basé sur le cloud nous permet d'utiliser les technologies et les méthodes adaptées au problème d'une équipe, sans impacter tout le monde. Ainsi, nous suivons les principes du Manifeste Agile:

"Construisez des projets autour d'individus motivés. Donnez-leur l'environnement et le soutien dont ils ont besoin et faites-leur confiance pour faire le travail."

et:

"Les meilleures architectures, exigences et conceptions émergent d'équipes auto-organisées."

"[La loi sur l'évolutivité universelle](https://en.wikipedia.org/wiki/Neil_J._Gunther]) prédit que le débit maximal que les systèmes peuvent atteindre - y compris les systèmes organisationnels de personnes coopérantes - est limité par la quantité de conflits pour les ressources partagées et la quantité travail mise en cohérence nécessaire pour tenir tout le monde au courant de ce qui se passe. Alors que les organisations techniques et l'appétit commercial pour leurs services ont augmenté [..], il est tout à fait naturel que les comités de révision d'architecture centralisés aient été rejetés comme des goulots d'étranglement, ou que l'accent ait été mis sur la réduction de la taille de l'équipe et sur l'effort de permettre aux équipes de travailler de manière indépendante."

Nous adoptons cette approche, en introduisant la culture DevOps (les développeurs exploitant leur système en production) et les équipes basées sur les produits.

Cependant, cela nécessite encore une certaine coordination et des conseils, pour aligner les décisions prises par les équipes sur les principaux objectifs de l'entreprise.

C'est le rôle de la Guilde Architecture Technique : fournir un modèle commun d'alignement du monde du développement informatique sur l'entreprise, des conseils aux développeurs moins expérimentés et réduire le coût des solutions partagées.

## Roles et responsabilités de la guilde

La Guilde a 3 responsibilitées

### Aligner l'architecture des systèmes sur les objectifs de l'entreprise

Lorsque les architectures ne correspondent pas aux objectifs de l'entreprise, la mise en œuvre de chaque nouvelle fonctionnalité prend de plus en plus de temps, voir devient impossible. L'ancien système backend monolithique est un bon exemple d'architecture qui allait dans la mauvaise direction.
La guilde a la responsabilité de garder les architectures propres et alignées avec les besoin de l'entreprise.

### Trouver et recommander des solutions aux problèmes partagés

L'infrastructure et les préoccupations transverses sont partagées entre les équipes, il est donc logique de partager les solutions aux problèmes communs au sein de l'entreprise. La Guilde est responsable des recommandations sur les problèmes qui ont des conséquences durables ou un coût de changement élevé. Ceci est particulièrement important si une décision d'une équipe influence les autres équipes.
Exemples: utilisation d'Apache Kafka pour l'échange de messages et le traitement de flux. Créer des templates de services pour que les équipes lancent de nouveaux services plus rapidement, etc...

### Partager les architectures et les connaissances techniques

La Guilde est également chargée de s'assurer que toutes les équipes ont la vision et les connaissances nécessaires en matière d'architecture, avec une bonne visibilité sur le fonctionnement du système et son orientation.
Ceci est réalisé en fournissant des diagrammes d'architecture, en formalisant toutes les décisions qui ont été prises avec leurs conséquences, et en impliquant toute l'entreprise dans le processus d'alignement.

## Comment la guilde travail

Le Guilde se réunit régulièrement, une fois toutes les 2 semaines, mais organise également des réunions ad-hoc pour résoudre les problèmes urgents lorsqu'ils surviennent.
Lorsque la guilde se réunit, il discute des problèmes et du travail requis, invite toutes les personnes concernées (en dehors de la guilde), planifie les recherches nécessaires, crée un document RFC pour recueillir toutes les contributions possibles de personnes ayant les connaissances sur la question, choisit la personne responsable de la prise de décision.

### Qui est responsable

Toutes les 2 semaines, une personne de la Guilde est choisie comme président par intérim.
Cette personne a la responsabilité personnelle de s'assurer que la guilde prend les décisions de manière efficace.
Pour chaque problème discuté par la guilde, une personne responsable sera choisie. S'il n'y a pas de volontaires, le président de la guilde est responsable.
Le président est également en service de la guilde d'architecture, où il est chargé de répondre à toutes les questions venants de l'extérieur de la guilde.

### RFC

RFC (Request for Comments) est une technique de communication et de prise de décision efficace sans réunion. Le but est de permettre aux personnes ayant les connaissances d'exprimer leur opinion, afin que la décision finale soit bien informée.
Les auteurs proposent une solution dans un document en ligne (dans le référentiel git), où toute personne intéressée peut ajouter ses commentaires ou suggestions.

Ces documents capturent:
- Contexte: de quelles informations avons-nous tenu compte lors de cette décision?
- Alternatives envisagées: quelles options avons-nous vues
- Décision: que recommandons-nous?
- Justification: pourquoi avons-nous fait cette recommandation?
- Conséquences: quels sont les inconvénients connus?

Une fois le document créé, la guilde le publie sur la liste de diffusion et le canal de discussion de la guilde. Il faut généralement une semaine pour obtenir toutes les informations nécessaires, mais cela dépend de l'urgence du problème.
Une fois que toutes les contributions sont rassemblées, la guilde se réunit à nouveau pour prendre la recommandation / décision finale.

### Prise de décision et dossier de décision d'architecture

La décision / recommandation est prise après que tous les commentaires de RFC sont rassemblés, lors d'une réunion distincte. La guilde prend la décision ensemble. Si les participants à la réunion ne peuvent s'entendre, la décision finale appartient au Président.

Le dossier de décision d'architecture est un moyen de documenter les décisions architecturales et techniques. Ces documents sont créés après la réunion finale sur le problème et capturent:
- Contexte: de quelles informations avons-nous tenu compte lors de cette décision?
- Alternatives envisagées: quelles options avons-nous vues
- Résultats de la recherche: qu'avons-nous appris en recherchant et en discutant ce problème?
- Décision: que recommandons-nous?
- Justification: pourquoi avons-nous fait cette recommandation?
- Conséquences: quels sont les inconvénients connus?

### Diagramme d'architecture (C4 model)

Le modèle C4 (https://c4model.com) a été choisi comme notation formelle pour les diagrammes d'architecture logicielle.

La notation C4 est une approche légère pour visualiser l'architecture. Il présente une architecture à quatre niveaux différents, fournit une carte au système et permet la collaboration (les développeurs utilisent des Pull/Merge Requests pour maintenir les diagrammes à jour).

Avantages de l'approche:
 - possibilité de définir et de modifier des diagrammes sous forme de code, permettant un travail très facile de définition pour les développeurs en permettant à chaque membre de n'importe quelle équipe de le mettre à jour quand un changement a lieu
 - des niveaux spécifiques de diagrammes peuvent être utilisés par différents publics, par ex. diagramme de contexte par la direction tandis que le diagramme de code (s'il existe) est destiné aux développeurs d'une équipe spécifique
 - une notation formelle simple facilite la compréhension et la discussion du diagramme et de ses conséquences

Les diagrammes sans notation formelle ne doivent pas être utilisés car ils ne sont pas professionnels et créent de la confusion.

## Comment la guilde coopère avec les autres

### Commercial

Le Président de la guilde est disponible pendant les heures de travail sur le canal Ms Teams «Architecture logicielle [ENG]» - pas besoin de vérifier ou de se souvenir qui est en service du point de vue commercial. Elle répondra à toutes les questions et prendra toutes les mesures nécessaires en cas de problème.
La guilde a également une adresse e-mail: (expurgé)

La guilde devra également se tenir au courant des objectifs commerciaux de l'entreprise afin de pouvoir aligner l'architecture informatique avec les objectifs de l'entreprise, en utilisant des méthodes telles que Event Storming et Value-Stream mapping.

### Développeurs

Tous les développeurs sont invités à rejoindre la guilde et les réunions si leurs tâches actuelles le permettent.
La guilde est inclusive, ce qui signifie qu'elle accepte les nouveaux membres par défaut.
Tout le monde peut signaler un problème à la guilde et demander de l'aide, ou donner un aperçu du problème.
Les personnes qui rejoignent la guilde seront tenues responsables de leur contribution et peuvent être invitées à faire la recherche, la preuve de concepts, etc...

### Direction

La guilde est tenue responsable de l’architecture du système et signale tous les problèmes d’organisation aux responsables correspondants, en cas de désalignement de l’organisation et de l’architecture (composition et responsabilité de l’équipe).

## Bénéfices

Les décisions / recommandations faites par la guilde sont bien formalisées et partagées. Aucune décision n'est prise par une personne qui n'a pas les connaissances requises en architecture.
Parce que le processus de prise de décision est inclusif, aucune décision n'est prise sans la contribution des personnes qui doivent vivre avec les conséquences de cette décision.
Une seule personne ne peut pas avoir une visibilité suffisante sur un grand système distribué pour prendre une décision sensée. Parce que la guilde est composée de nombreuses personnes, de tous les côtés du système, la décision prend en compte toutes les perspectives sur le système que nous construisons.
Parce que la guilde est inclusive, elle partage les connaissances et améliore la coopération entre développeurs et avec l'entreprise.

L'avantage de cette approche est prouvée par plusieurs grandes organisations.

### Exemples de réalisations

- Les personnes incluses dans la guilde ont créé les diagrammes d'architecture représentant l'architecture actuelle et l'avenir. Approche utilisée par les développeurs et les entreprises pour mettre en œuvre d'autres changements.
- Définition d'un modèle de service personnalisé permettant la mise en place rapide de nouveaux microservices.
- La guilde a défini la feuille de route de l'évolution de l'architecture en fonction des "bouded contexts" identifiés et continue son évolution.
- La guilde a recommandé une base de données pour les applications basées sur le cloud en fonction des options possibles et en tenant compte du coût, de la maintenabilité et des performances.
- Répartition des responsabilités suggérée entre les équipes Scrum.
- Animation de deux ateliers TDD / OOP.

## Qui d'autre travail de cette manière

Il existe plusieurs organisations qui travaillent de cette façon. Quelques grands exemples:
- Comcast: https://www.infoq.com/articles/architecture-guild-800-friends/
- Internet Engineering Task Force (IETF)
- Communauté Java
- World Wide Web Consortium

## Contacte

La guilde peut être contactée sur le cannal mattermost "XXXXXXXX" , ou, par l'intermédiaire de [l'addresse mail de la guilde](mailto:example.com)
