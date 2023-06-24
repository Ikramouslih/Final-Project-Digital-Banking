# Compte Rendu
Final Project - Spring Angular JWT, Digital Banking

## Introduction ##
Ce compte rendu présente une étude approfondie de l'application de gestion des opérations bancaires développée en utilisant les frameworks Spring Boot et Angular. L'objectif principal de cette application est de fournir une plateforme pour gérer les clients, leurs comptes et leurs opérations bancaires, telles que les dépôts, les retraits, les transferts.

L'application repose sur deux technologies majeures : Spring Boot, un framework Java populaire pour le développement d'applications d'entreprise, et Angular, un framework JavaScript utilisé pour la création d'interfaces utilisateur dynamiques et interactives.

L'utilisation de Spring Boot offre plusieurs avantages significatifs pour le développement de l'application bancaire. Il fournit un environnement prêt à l'emploi pour la configuration et la gestion des composants d'entreprise, tels que la sécurité, la persistance des données et la gestion des transactions. De plus, Spring Boot facilite le développement rapide et la création d'applications modulaires grâce à son système de configuration automatique et à sa prise en charge native des conteneurs d'application.

D'autre part, Angular est utilisé pour créer une interface utilisateur réactive et intuitive. Il offre une architecture basée sur les composants, permettant de créer des interfaces modulaires et réutilisables. Avec Angular, il est possible de développer des fonctionnalités riches, telles que la validation des formulaires, la gestion des états, l'interfaçage avec des services backend et bien d'autres encore.

Dans ce compte rendu, nous examinerons en détail les fonctionnalités clés de l'application de gestion des opérations bancaires, y compris la création des clients et de comptes, la consultation des listes, l'exécution d'opérations bancaires, ainsi que l'historique des opérations et la recherche des clients selon un mot clé. 

### Présentation du Spring Boot ###  

![image](https://user-images.githubusercontent.com/60039200/232336407-9086d231-984c-4478-a695-23f39021096b.png)

Spring Boot est un framework open source pour le développement d'applications Java. Il fournit un cadre prêt à l'emploi pour créer des applications et des services Web en utilisant la configuration plutôt qu'une approche programmatique. 
Spring Boot aide à créer des applications qui ne sont pas liées à une plate-forme spécifique et qui peuvent s'exécuter localement sur un appareil sans connexion Internet ou autres services installés pour être fonctionnelles.
Voici quelques caractéristiques clés de Spring Boot :
- Configuration automatique : "Convention plutôt que configuration", ce qui signifie qu'il peut détecter automatiquement les dépendances et configurer les composants de l'application en fonction des meilleures pratiques. Cela réduit considérablement le temps et l'effort nécessaires pour configurer l'application.
- Intégration transparente : Intègre facilement les bibliothèques et les frameworks tiers, ce qui facilite l'ajout de fonctionnalités supplémentaires à votre application.
- Serveur d'application intégré : Inclut un serveur d'application embarqué (tel que Tomcat, Jetty ou Undertow) afin que vous puissiez exécuter votre application Java en tant que JAR autonome sans nécessiter de déploiement séparé d'un serveur d'application.
- Gestion des dépendances : Simplifie la gestion des dépendances en fournissant des starters préconfigurés.

### Présentation d'Angular ### 

![angular-3-logo](https://github.com/Ikramouslih/JEE-Activite-6/assets/60039200/ebef6263-bf31-4059-96b0-1e8b83434e09)

Angular est un framework JavaScript open-source basé sur TypeScript. Il permet de construire des applications web dynamiques, single-page (SPA) et multiplateformes. Il offre un ensemble complet d'outils et de fonctionnalités pour simplifier le processus de développement et améliorer l'expérience utilisateur.

Principales caractéristiques et avantages d'Angular :
- Structure MVC : Facilite la séparation des responsabilités et la maintenance du code. Cela rend le développement plus structuré et évolutif.
- Deux-way data binding : Toute modification effectuée dans l'interface utilisateur est automatiquement reflétée dans les données sous-jacentes, et vice versa. Cela permet une synchronisation fluide entre les vues et les modèles de données.
- Injection de dépendances : Facilite la gestion des dépendances entre les composants. Cela rend le code plus modulaire, réutilisable et testable.
- Routing : Permet la navigation entre différentes vues et la gestion des URL. Cela permet la création d'applications à pages multiples tout en maintenant une expérience utilisateur fluide.

### Interaction entre Backend & Frontend ###
![angular-spring-boot-mysql-removebg-preview](https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/775dcb13-e8fd-4e7c-85f7-dc2a87bd8efa)

La communication entre Spring Boot et Angular dans une application typique suit généralement une architecture client-serveur. Voici comment ces composants interagissent :

=> Angular envoie des requêtes HTTP au Spring Boot pour récupérer des données, effectuer des opérations ou envoyer des informations.
* Les requêtes sont généralement initiées par des événements déclenchés par l'utilisateur, tels que le clic d'un bouton ou la soumission d'un formulaire.
* Angular utilise le module HttpClient pour envoyer des requêtes HTTP (GET, POST, PUT, DELETE, etc.) avec les paramètres appropriés, tels que les en-têtes et le corps de la requête.
* Spring Boot expose des API RESTful en tant que points de terminaison (endpoints) pour recevoir ces requêtes. Ces endpoints sont généralement définis à l'aide d'annotations spécifiques, telles que @GetMapping, @PostMapping, etc.
* Spring Boot traite les requêtes reçues, effectue les opérations nécessaires et renvoie les réponses appropriées, généralement sous la forme de données JSON.

=> Communication entre Spring Boot et MySQL :

* Spring Boot utilise le module Spring Data JPA pour interagir avec la base de données MySQL de manière simplifiée.
* Les entités Java sont définies pour représenter les tables de la base de données MySQL. Ces entités sont annotées avec des annotations telles que @Entity, @Table, etc., pour établir la correspondance entre les objets Java et les tables de la base de données.
* Spring Data JPA fournit des interfaces de repository qui définissent les opérations courantes sur les entités, telles que la création, la récupération, la mise à jour et la suppression (CRUD).
* Le backend Spring Boot utilise ces interfaces de repository pour exécuter les requêtes nécessaires à la base de données MySQL. Les opérations de persistance, de recherche et de mise à jour sont gérées par Spring Data JPA, qui génère automatiquement les requêtes SQL correspondantes.

# L'architecture de l'application Digital Banking #
=> L'architecture globale :

<img width="350" alt="global project front and back" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/3fdff22f-e909-4005-9928-b588c0ed57ac">


## 1. Backend ##

<img width="262" alt="backend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/bf64a276-1153-4f9e-ac2f-e942b299ae11">
<br/>
<br/>
=> 1.1. Les dependences utilisés (Le fichier "pom.xml"):

* Spring DATA JPA : Pour conserver les données dans ‘SQL stores‘ avec Java Persistance API à l’aide de Spring Data et Hibernate. C'est un module qui facilite le ORM basé sur JPA. Il est utilisé avec les bases de données relationnelles.
  <p align="center">
  <img width="144" alt="2 jpa depend graphe" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/e4b128f9-73f4-4e0c-97d8-8c3bdbb5501a">
  <img width="393" alt="1 jpa depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/72ded0d2-ce62-4c09-9740-a65bcea7b8d3">
  </p>

* Spring Web : pour créer des applications Web, y compris RESTful, à l'aide de Spring MVC. Utilise Apache Tomcat comme conteneur intégré par défaut.
  <p align="center">
    <img width="350" alt="2 web depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/2d763f3b-add6-4b96-b874-af808ae0bfb9">
  </p>

* Spring-boot-devtools : une dépendance Spring Boot qui fournit des outils de développement pratiques pour le développement de vos applications Spring Boot. Cette dépendance a été utilisé dans cette activité pour :
  - Le mécanisme de rechargement automatique des classes en mode développement;
  - Le serveur embarqué qui permet de redémarrer l'application automatiquement lorsqu'un changement est détecté.
  <p align="center">
  <img width="319" alt="3 dev tools depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/669ec9c0-47a6-43f2-a365-ffbec77c1a2d">
  </p>

* H2 Database : Une base de données intégrée, open source et en mémoire. C'est un système de gestion de base de données relationnelle écrit en Java. C'est une application client/serveur et elle est généralement utilisée dans les tests unitaires (Remplacé après par MySQL).
  <p align="center">
  <img width="319" alt="h2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/4335e76d-fd97-4728-9263-331f3690ca27">
  </p>

* MySQL est l'un des systèmes de bases de données relationnelles les plus populaires et il est souvent utilisé dans les applications Spring Boot.
  <p align="center">
  <img width="319" alt="mysql" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/1ae3a72b-337d-42de-a308-77e9e49535e3">
  </p>

* Lombok : Un outil de bibliothèque Java qui génère du code pour minimiser le code ‘boilerplate’. La bibliothèque remplace le code ‘boilerplate’ par des annotations faciles à utiliser (Exemples : @NoArgsConstructor, @Getter, @Setter…).
  <p align="center">
   <img width="319" alt="lombok" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/5da5f94c-c93b-461b-8409-e7308c42c312">
  </p>  

* Spring-boot-starter-test : facilite les tests unitaires et d'intégration dans les applications Spring Boot. Il fournit un ensemble de bibliothèques et d'outils utiles pour écrire et exécuter des tests de manière efficace.
  <p align="center">
  <img width="319" alt="starter test" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/9570086f-1ca4-4d15-bcaf-3bbc328adfa5">
  </p>  

* Springdoc-openapi-starter-webmvc-ui : facilite la documentation et la visualisation de l'API REST de votre application à l'aide de l'interface utilisateur Swagger UI pour le test des points d'extrémité, l'affichage les modèles de données et l'obtention des exemples de requêtes et de réponses.
  <p align="center">
   <img width="350" alt="swagger ui" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/e1eb4863-8fcd-417f-b759-fb2a32e17711">
    <img width="370" alt="openapi" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/36a3cc0a-9fc0-448b-9abe-03f698c980cd">
  </p> 

=> 1.2. Le fichier "application.properties" :

<img width="662" alt="application properties" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/235bbb57-885d-4515-a944-90655ee35fe1">
<br/>
<br/>

=> 1.3. La couche DAO : 
  * Les entités : l'ensemble des entités JPA utilisées pour modéliser, persister et manipuler les données de l'application en utilisant la base de données.<br/>
  <img width="184" alt="entities" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/7a895635-4633-4472-bb1d-ad80308042ce"><br/>
  * Les interfaces JPA Repository basées sur Spring Data : Pour effectuer des opérations de persistance et de récupération de données dans la base de données à l'aide de la Java Persistence API (JPA) et Spring Data, et en fournissant les opérations CRUD, des requêtes personnalisées, pagination et tri, transactions ...<br/>
  <img width="178" alt="repos" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/2a56d19c-5f31-4262-b588-7f233eb8a916"><br/><br/>

=> 1.4. Les DTOs et les mappers :<br/>
  * Les DTOs : Servent à transférer des données entre les différentes couches de l'application ou entre l'application et des services externes. Ils permettent de simplifier le transfert de données, de gérer différentes représentations, de protéger les données sensibles et de définir une interface stable entre les couches de l'application.<br/>
  <img width="173" alt="dtos" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/6497c2ef-6230-48b8-907e-b02dc0b6052d"><br/>
  * Les mappers : Utilisés pour convertir des objets d'un type à un autre, faciliter la transformation des données entre différentes représentations et réduire le couplage entre les différentes couches de l'application. Ils jouent un rôle important dans l'adaptation et la manipulation des modèles de données.<br/>
  <img width="185" alt="mappers" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/5d580e93-c05d-42a5-a0f3-b690c73252a3"><br/>
  <br/>
  
=> 1.5. La couche métier : l'intermediaire entre la couche WEB et la couche DAO.<br/>
<img width="181" alt="services" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/fb9d568b-42b8-4a1c-bf85-a3b7763e91f2"><br/>
  * BankAccountService : Interface qui contient l'ensemble des fonctionnalités métier des comptes et des clients à implementer.
  * BankAccountServiceImpl : Contient l'implementation des méthodes précisées dans l'interface.
  * BankService : Contient l'implementation d'une méthode de consultation d'un compte banquaire précis.
    
=> 1.6. La couche WEB : Pour la gestion des requêtes HTTP, la coordination de la logique métier et la génération des réponses appropriées.<br/>
<img width="174" alt="web" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/c44ea761-117c-484c-ae1c-c6d794124958"><br/>
  * BankAccountRestAPI : Concerne les comptes bancaires.
  * CustomerRestController : Concerne les clients.

=> 1.7. Autres :
  * Les enums : les types possibles des operations et des status des comptes.<br/>
 <img width="180" alt="enums" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/7472ff7c-d310-40eb-bfe0-311bca5f3084"> <br/>
  * Les exceptions : Pour la gestion des exceptions.<br/>
 <img width="183" alt="exceptions" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/f550404d-455f-4a4f-b431-1be15f2b5201"><br/>
<br/>

=> 1.8. EbankingBackendApplication : Le point d'entrée principal de l'application, contient une méthode main() qui est exécutée lorsque l'application est lancée. Cette méthode initialise le contexte de l'application et démarre l'exécution de l'application.<br/>
<img width="194" alt="app" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/3a963470-5a99-47de-b58d-db6e0f686d91">

## 2. Frontend ##

On commence par créer un projet Angular avec la commande : `ng new frontend`.<br/></br>
<img width="233" alt="frontend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/8a0ccdd8-8dac-4f9f-a54d-bd1be08e8707"><br/><br/>

=> 2.1. Les dependences utilisés (Le fichier "package.json"):
<br/>
  * Bootstrap & Bootstrap-icons : Une bibliothèque open-source de développement front-end pour la conception de sites et d'applications web. Elle fournit des styles CSS prédéfinis, des composants JavaScript et des icônes pour faciliter la création d'interfaces utilisateur esthétiques et responsives.
    - Installation : `npm i bootstrap bootstrap-icon`<br/>
    - l'ajout les références du Bootstrap dans la partie 'styles' & 'scripts' dans le fichier "angular.json".
     <p align="center">
    <img width="350" alt="bootstrap 1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/34b844bd-36ce-4082-8903-7876d52735f6">
    <img width="260" alt="bootstrap ang" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/25f017ce-1914-4f8b-86ff-0364819b4de6">
    </p>
<br/>    

=> 2.2. Les modèles : <br/>
les modèles font référence aux structures de données utilisées pour représenter et manipuler les données dans l'application. Les modèles sont généralement des classes TypeScript qui définissent la structure des objets de données et les fonctionnalités associées.<br/>
<img width="200" alt="models" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/2e2b26be-22c7-4a85-a4ca-d14f3568c49b">


=> 2.3. Les composants : <br/>
Un composant Angular est généralement constitué de quatre parties principales : le template, la classe du composant, les styles associés et le fichier de test :
  - Le template définit la structure HTML de la vue du composant,
  - La classe du composant contient la logique et les données associées,
  - Les styles définissent l'apparence visuelle du composant,
  - Le fichier de test est utilisé pour écrire des tests unitaires pour le composant afin de vérifier son comportement et sa fonctionnalité attendus,
  - Création d'un composant : `ng g c componant-name`.

    * Le composant 'accounts' : Responsable de l'affichage des opérations bancaires d'un compte précis ainsi que d'effectuer des nouvelles opérations (crédit, débit, transfert).<br/>
    <img width="179" alt="accounts" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/f37f56b4-b77d-45b5-b420-3db0e362f0cf"><br/>
  
    * Le composant 'customer-accounts' : Responsable de l'affichage des comptes bancaires d'un client.<br/>
     <img width="205" alt="customer accounts" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/8446c1d2-8bdb-4610-9b4e-f79420c89d70"><br/>
  
    * Le composant 'customers' : Responsable de l'affichage de la liste des clients où on peut afficher leurs comptes, les supprimer ou rechercher un client selon un mot clé.<br/>
     <img width="213" alt="customers" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/76ac4414-8fcd-46f1-b0bd-3620d04af4a7"><br/>
  
    * Le composant 'navbar' : Responsable de l'affichage et de la logique de la barre de navigation.<br/>
    <img width="193" alt="navbar" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/89f669ca-c642-4db3-a97d-64e411c8996b"><br/>
  
    * Le composant 'new-customer' : Responsable de l'affichage et de la logique du formulaire d'ajout d'un nouveau client.<br/>
    <img width="185" alt="new costumer" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/1287a2dc-0727-4d5d-a072-cfb2f1fdf99b"><br/>

 => 2.4. Les services : <br/>
 les services sont des classes qui fournissent des fonctionnalités réutilisables et partagées au sein de l'application. Ils sont utilisés pour séparer la logique métier et les fonctionnalités communes des composants afin de favoriser la modularité, la réutilisabilité et la maintenabilité du code.
 - Création d'un service : `ng g c services/service-name` <br/><br/>
 <img width="300" alt="Screenshot 2023-06-24 171252" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/822abbd1-70a9-49fd-9d08-5ca2e59e0163"><br/>
   * accounts.service.ts : Concerne les fonctionnalités métier des comptes bancaires.<br/>
   * customer.service.ts : Concerne les fonctionnalités métier des clients.<br/>

 => 2.5. Routing (le fichier 'app-routing.module.ts'): <br/>
 Le routing dans Angular fait référence à la capacité de l'application à naviguer entre différentes vues ou composants en fonction de l'URL actuelle. Il permet de définir des règles de navigation, de gérer les paramètres d'URL et d'afficher dynamiquement les composants correspondants.<br/><br/>
 <img width="500" alt="routing" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/7cc78552-f922-42af-bf65-98c9644939bb">

## L'interface utilisateur et les fonctionnalités implémentées ## 

-L'ajout d'un client :
<img width="960" alt="add 1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/8db49d0f-a0ef-4dba-97e9-a8fe69deae78">
<img width="960" alt="add 2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/d742e544-fdb1-41e6-8906-631e095bb739">
<img width="960" alt="add 3" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/4c780c2c-aeac-4fd7-a9d6-7fc8c8bfcb44">
<img width="960" alt="add 4" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/546fa675-89dc-41b4-9f11-ce937c6a5f45">
<img width="960" alt="add 5" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/842f5bc0-8444-47bc-95c9-24ebdab3cc83">
<br/><br/>

- La liste des clients et la recherche d'un client selon un mot clé :
<img width="960" alt="1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/cf8573b5-fa22-4474-80d5-2ce512de1d22">
<img width="960" alt="2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/d97deb98-05a6-4318-a9d6-5b2852e35fff">
<img width="960" alt="3" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/d33c78f6-6ce3-4d45-b5fd-eccb25acd264">
<br/><br/>

- La suppression d'un client :
<img width="960" alt="1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/dcef1509-f908-43d6-98d6-a973c715ba6b">
<img width="960" alt="Screenshot 2023-06-24 191137" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/c6e03877-7938-45fb-97cc-9694e150514e">
<br/><br/>

- L'affichage des comptes d'un client :
<img width="960" alt="accounts 1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/ca224b50-aea6-4753-84b3-75d1f7c3571d">
<img width="960" alt="accounts 2 " src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/57341dbc-1041-413a-ba5b-3d25d0555c4a">
<br/><br/>

- L'historique des opérations d'un compte précis :
<img width="960" alt="Screenshot 2023-06-24 193546" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/9d26747c-6474-4b92-aab0-062eccf17e63">
<img width="960" alt="1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/b85424bc-72a6-4120-bde5-64f4129eca8d">
<img width="960" alt="history du compte" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/cece2d42-1f7d-439e-bfd5-d40bcd88d523">
<br/><br/>

- L'opération "DEBIT" sur un compte précis :
<img width="960" alt="debit 1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/4a2b37c7-c75c-43d9-9db3-771d5039d7f8">
<img width="960" alt="debit 2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/20291c49-2ca3-4eaa-8ace-2517a84cf2a4">
<img width="960" alt="debi 3" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/bb8521dc-f660-44c6-83d7-231e23fc6780">
<br/><br/>

- L'opération "CREDIT" sur un compte précis :
<img width="960" alt="1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/2746b805-a96e-42a7-8646-935dcfc4b038">
<img width="960" alt="2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/3f79c68a-fa12-40dd-bd5c-f7a130a7ae67">
<img width="960" alt="3" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/43e42a7e-170a-4c8a-9031-953902403144">
<br/><br/>

- L'opération "TRANSFER" sur un compte précis :
<img width="960" alt="1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/ebaf8b5f-dd50-4b24-bd3e-9f420cd5fc17">
<img width="960" alt="2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/9b32e8db-4052-46d0-bef5-9a42d73df007">
<img width="960" alt="3" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/31998ac5-a54a-40db-b964-e8ed31b77757">
<img width="960" alt="4" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/d38cf8dc-58d3-4cb6-8c2a-796c04b47af3">
<br/><br/>

## Conclustion ## 
En conclusion, grâce à la combinaison de Spring Boot et d'Angular, l'application Digital Banking offre une solution complète et performante pour répondre aux besoins de gestion bancaire. Les technologies utilisées ont permis de développer une application robuste, sécurisée et conviviale, offrant aux utilisateurs une expérience bancaire agréable et efficace.
