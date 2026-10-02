# Learn@Home — cadrage d'une plateforme de tutorat scolaire

Dossier de cadrage réalisé dans le cadre de ma formation de développeur full stack
(OpenClassrooms, 2026). Mise en situation professionnelle : une association de
tutorat bénévole à distance souhaite remplacer son fonctionnement par bouche-à-oreille
et SMS par un site web complet.

Ce dépôt ne contient pas de code : il rassemble les livrables de la phase d'analyse
et de conception, en amont du développement.

## Le besoin

L'association met en relation des enfants en difficulté scolaire avec des tuteurs
bénévoles, pour des rendez-vous hebdomadaires courts consacrés aux devoirs et à
l'organisation du travail. Le site doit couvrir cinq domaines fonctionnels :

| Module | Contenu |
| --- | --- |
| Connexion | Inscription élève et bénévole, authentification, mot de passe oublié, pages protégées |
| Messagerie | Échanges instantanés, historique, gestion des contacts, accusés de lecture |
| Calendrier | Rendez-vous et événements par utilisateur |
| Gestion des tâches | L'élève crée ses tâches, le bénévole en crée pour les élèves qu'il suit |
| Tableau de bord | Récapitulatif des tâches, prochains rendez-vous, messages non lus |

Contrainte transversale : le service s'adresse à des mineurs. Le RGPD, le consentement
parental, la traçabilité des échanges et la modération ont été traités dès l'analyse,
et non comme une note de bas de page.

## Les livrables

| Document | Description |
| --- | --- |
| [Veille marché et outils](./veille-marché-outils.pdf) | Analyse de cinq acteurs du marché et choix techniques argumentés |
| [Diagrammes de cas d'usage](./diagrammes-usecase.pdf) | Acteurs et interactions, en UML |
| [User stories](./user-stories.pdf) | Besoins exprimés du point de vue des utilisateurs |
| [Maquettes](./figma-maquettes.pdf) | Écrans des cinq pages, versions desktop et mobile |
| [Kanban](https://app.notion.com/p/3c59ed7662a380bfb3def7c50741a81a?v=3c59ed7662a38081ba80000c14e249b5) | Découpage et suivi des tâches |

## La démarche

**Veille concurrentielle.** Cinq acteurs analysés : ZUPdeCO, AideEducation, Acadomia,
Superprof et Yoopies. L'étude a porté sur leur positionnement, leurs fonctionnalités
et leur stack technique, afin de situer le projet et d'éviter de reproduire leurs
erreurs d'ergonomie.

**Choix techniques.** Architecture monolithique retenue : Symfony, Twig, MySQL et
JavaScript natif. Écartés en cours d'analyse : WordPress (trop rigide pour les
fonctionnalités attendues), Laravel (pas d'avantage décisif sur Symfony dans ce
contexte) et une architecture découplée Symfony + Vue.js (complexité et budget
disproportionnés). La messagerie fonctionne par rafraîchissement, sans temps réel :
un délai de trois secondes a été jugé acceptable au regard du coût d'une solution
WebSocket.

**Conception des interfaces.** Maquettes réalisées sous Figma à partir d'un UI kit
Bootstrap 5. Parti pris : interfaces épurées, responsive mobile et tablette,
accessibilité WCAG 2.1 AA, thème sombre. Palette définie et documentée.

## Ce que ce projet m'a appris

**Tenir la cohérence d'un dossier vivant.** Chaque ajout ou modification obligeait à
reprendre les autres documents : une fonctionnalité précisée dans le cahier des charges
se répercutait sur les user stories, les maquettes et le Kanban. J'ai appris à faire ces
allers-retours sans les subir, et à vérifier la cohérence de l'ensemble à chaque
itération plutôt qu'à la fin.

**Choisir une technologie que je ne maîtrise pas encore.** C'est ce qui m'a le plus
coûté. N'ayant pratiqué qu'une partie des langages et frameworks existants, j'ai dû
m'appuyer sur la veille, les retours d'expérience et les contraintes du projet — budget,
délais, compétences disponibles — plutôt que sur mon seul ressenti. Un choix technique
se défend par le contexte, pas par la préférence.

**Expliquer mes décisions du point de vue du client.** Justifier un choix entre
développeurs est une chose ; le replacer dans le besoin de l'association, avec ses
contraintes de moyens et son public mineur, en est une autre. C'est l'exercice qui m'a
le plus fait progresser, et celui que je retiens pour la suite.

## Auteur

Christophe Anger — [GitHub](https://github.com/ChrisAnger59) ·
[LinkedIn](https://www.linkedin.com/in/christophe-anger)