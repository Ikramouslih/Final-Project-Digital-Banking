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
![angular-spring-boot-mysql-removebg-preview](https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/45789190-e687-48c5-99ca-4309ec1c45d0)

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

<img width="350" alt="global project front and back" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/1a49161b-e968-45f6-a2de-ad340ae5a893">

## 1. Backend ##

<img width="262" alt="backend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/f6d0d393-e1b0-41c6-8f52-ce46f5200cbf">
<br/>
<br/>
=> 1.1. Les dependences utilisés (Le fichier "pom.xml"):

* Spring DATA JPA : Pour conserver les données dans ‘SQL stores‘ avec Java Persistance API à l’aide de Spring Data et Hibernate. C'est un module qui facilite le ORM basé sur JPA. Il est utilisé avec les bases de données relationnelles.
  <p align="center">
    <img width="144" alt="2 jpa depend graphe" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/5206b14e-72fe-4193-9105-a2cf62af3d02">
    <img width="393" alt="1 jpa depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/af0c3d27-9e80-4033-9043-cb8dd39f5183">
  </p>

* Spring Web : pour créer des applications Web, y compris RESTful, à l'aide de Spring MVC. Utilise Apache Tomcat comme conteneur intégré par défaut.
  <p align="center">
    <img width="319" alt="1 jpa depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/840dc311-0351-48b5-9851-6b62a297754d">
  </p>

* Spring-boot-devtools : une dépendance Spring Boot qui fournit des outils de développement pratiques pour le développement de vos applications Spring Boot. Cette dépendance a été utilisé dans cette activité pour :
  - Le mécanisme de rechargement automatique des classes en mode développement;
  - Le serveur embarqué qui permet de redémarrer l'application automatiquement lorsqu'un changement est détecté.
  <p align="center">
    <img width="319" alt="3 dev tools depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/6673418e-43ef-40aa-a9d5-99e10f7beecf">
  </p>

* H2 Database : Une base de données intégrée, open source et en mémoire. C'est un système de gestion de base de données relationnelle écrit en Java. C'est une application client/serveur et elle est généralement utilisée dans les tests unitaires (Remplacé après par MySQL).
  <p align="center">
    <img width="319" alt="4 h2 database depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/7ef65595-602f-4809-bc71-6628d36b4dc1">
  </p>

* MySQL est l'un des systèmes de bases de données relationnelles les plus populaires et il est souvent utilisé dans les applications Spring Boot.
  <p align="center">
    <img width="319" alt="4 h2 database depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/deee9e81-87a4-497e-bb67-e56f28843573">
  </p>

* Lombok : Un outil de bibliothèque Java qui génère du code pour minimiser le code ‘boilerplate’. La bibliothèque remplace le code ‘boilerplate’ par des annotations faciles à utiliser (Exemples : @NoArgsConstructor, @Getter, @Setter…).
  <p align="center">
    <img width="319" alt="4 h2 database depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/11e6a1d2-74c3-49fe-b36e-e036a7a9097d">
  </p>  

* Spring-boot-starter-test : facilite les tests unitaires et d'intégration dans les applications Spring Boot. Il fournit un ensemble de bibliothèques et d'outils utiles pour écrire et exécuter des tests de manière efficace.
  <p align="center">
    <img width="319" alt="4 h2 database depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/30df7833-dd14-4d86-8960-51c0fdf674d3">
  </p>  

* Springdoc-openapi-starter-webmvc-ui : facilite la documentation et la visualisation de l'API REST de votre application à l'aide de l'interface utilisateur Swagger UI pour le test des points d'extrémité, l'affichage les modèles de données et l'obtention des exemples de requêtes et de réponses.
  <p align="center">
    <img width="319" alt="4 h2 database depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/f14bef6b-3a07-4d12-a29d-f2f17a862fa8">
    <img width="350" alt="4 h2 database depend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/09eeab4f-31c6-4e7c-a2c1-786bd2c17a0f">
  </p> 

=> 1.2. Le fichier "application.properties" :

<img width="662" alt="application properties" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/66f37a9c-0652-42ab-b846-8a0d991532bc">
<br/>
<br/>

=> 1.3. La couche DAO : 
  * Les entités : l'ensemble des entités JPA utilisées pour modéliser, persister et manipuler les données de l'application en utilisant la base de données.<br/>
  <img width="184" alt="entities" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/82baf4be-0d4f-4adf-95a5-506405f6f3a2"><br/>
  * Les interfaces JPA Repository basées sur Spring Data : Pour effectuer des opérations de persistance et de récupération de données dans la base de données à l'aide de la Java Persistence API (JPA) et Spring Data, et en fournissant les opérations CRUD, des requêtes personnalisées, pagination et tri, transactions ...<br/>
  <img width="178" alt="repos" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/a581b7cf-0835-4116-8a38-77be7d66d5b5"><br/>
<br/>

=> 1.4. Les DTOs et les mappers :<br/>
  * Les DTOs : Servent à transférer des données entre les différentes couches de l'application ou entre l'application et des services externes. Ils permettent de simplifier le transfert de données, de gérer différentes représentations, de protéger les données sensibles et de définir une interface stable entre les couches de l'application.<br/>
  <img width="173" alt="dtos" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/81449d7a-6a84-49a3-931c-d6c64cc8d2d5"><br/>
  * Les mappers : Utilisés pour convertir des objets d'un type à un autre, faciliter la transformation des données entre différentes représentations et réduire le couplage entre les différentes couches de l'application. Ils jouent un rôle important dans l'adaptation et la manipulation des modèles de données.<br/>
  <img width="185" alt="mappers" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/e664da4e-633f-4486-b71d-a4cf21ac7c0b"><br/>
  <br/>
  
=> 1.5. La couche métier : l'intermediaire entre la couche WEB et la couche DAO.<br/>
<img width="181" alt="services" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/d8cc8286-f52d-48b6-a368-981010c7a9d5"><br/>
  * BankAccountService : Interface qui contient l'ensemble des fonctionnalités métier des comptes et des clients à implementer.
  * BankAccountServiceImpl : Contient l'implementation des méthodes précisées dans l'interface.
  * BankService : Contient l'implementation d'une méthode de consultation d'un compte banquaire précis.
    
=> 1.6. La couche WEB : Pour la gestion des requêtes HTTP, la coordination de la logique métier et la génération des réponses appropriées.<br/>
<img width="174" alt="web" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/89ccab89-915d-49e9-9f61-b52f5085b537"><br/>
  * BankAccountRestAPI : Concerne les comptes bancaires.
  * CustomerRestController : Concerne les clients.

=> 1.7. Autres :
  * Les enums : les types possibles des operations et des status des comptes.<br/>
  <img width="180" alt="enums" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/f7026ba5-befc-4676-bbf2-e810563ef3da"><br/>
  * Les exceptions : Pour la gestion des exceptions.<br/>
  <img width="183" alt="exceptions" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/35efadfc-3fa2-4610-948f-ac3dc3b51ce6"><br/>
<br/>

=> 1.8. EbankingBackendApplication : Le point d'entrée principal de l'application, contient une méthode main() qui est exécutée lorsque l'application est lancée. Cette méthode initialise le contexte de l'application et démarre l'exécution de l'application.


## 2. Frontend ##

On commence par créer un projet Angular avec la commande : `ng new frontend`.<br/></br>
<img width="233" alt="frontend" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/e81d51c7-279e-4c48-97a2-d6d95c2c4aa3">
<br/>
<br/>
=> 2.1. Les dependences utilisés (Le fichier "package.json"):
<br/>
  * Bootstrap & Bootstrap-icons : Une bibliothèque open-source de développement front-end pour la conception de sites et d'applications web. Elle fournit des styles CSS prédéfinis, des composants JavaScript et des icônes pour faciliter la création d'interfaces utilisateur esthétiques et responsives.
    - Installation : `npm i bootstrap bootstrap-icon`<br/>
    - l'ajout les références du Bootstrap dans la partie 'styles' & 'scripts' dans le fichier "angular.json".
     <p align="center">
    <img width="319" alt="bootstrap" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/c0de24dc-7845-4629-a40b-079b7476a1f8">
    <img width="319" alt="bootstrap" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/27117b3b-e333-4bb8-bcbd-9173df3e1787">
    </p>
<br/>    

=> 2.2. Les modèles : <br/>
les modèles font référence aux structures de données utilisées pour représenter et manipuler les données dans l'application. Les modèles sont généralement des classes TypeScript qui définissent la structure des objets de données et les fonctionnalités associées.<br/>
<img width="185" alt="models" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/3a6efc27-d90e-477e-ac60-18b5c1efb442">


=> 2.3. Les composants : <br/>
Un composant Angular est généralement constitué de quatre parties principales : le template, la classe du composant, les styles associés et le fichier de test :
  - Le template définit la structure HTML de la vue du composant,
  - La classe du composant contient la logique et les données associées,
  - Les styles définissent l'apparence visuelle du composant,
  - Le fichier de test est utilisé pour écrire des tests unitaires pour le composant afin de vérifier son comportement et sa fonctionnalité attendus,
  - Création d'un composant : `ng g c componant-name`.

    * Le composant 'accounts' : Responsable de l'affichage des opérations bancaires d'un compte précis ainsi que d'effectuer des nouvelles opérations (crédit, débit, transfert).<br/>
      <img width="179" alt="accounts" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/68683d41-7a8f-4e6e-84e3-d5896a7b4fb4"><br/>
  
    * Le composant 'customer-accounts' : Responsable de l'affichage des comptes bancaires d'un client.<br/>
      <img width="205" alt="customer accounts" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/23d20f8d-091f-4b0d-91a9-30c0eeeeda98"><br/>
  
    * Le composant 'customers' : Responsable de l'affichage de la liste des clients où on peut afficher leurs comptes, les supprimer ou rechercher un client selon un mot clé.<br/>
      <img width="213" alt="customers" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/a4603f4c-9f9e-4978-9a5f-836e9735a3af"><br/>
  
    * Le composant 'navbar' : Responsable de l'affichage et de la logique de la barre de navigation.<br/>
      <img width="193" alt="navbar" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/0d5f6cba-94e5-4642-959e-f11bc474af2c"><br/>
  
    * Le composant 'new-customer' : Responsable de l'affichage et de la logique du formulaire d'ajout d'un nouveau client.<br/>
      <img width="185" alt="new costumer" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/49032e4a-7b8d-4403-b3c6-02cd2a6e3043"><br/>

 => 2.4. Les services : <br/>
 les services sont des classes qui fournissent des fonctionnalités réutilisables et partagées au sein de l'application. Ils sont utilisés pour séparer la logique métier et les fonctionnalités communes des composants afin de favoriser la modularité, la réutilisabilité et la maintenabilité du code.
 - Création d'un service : `ng g c services/service-name` <br/><br/>
 <img width="179" padding="20" alt="Screenshot 2023-06-24 171252" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/1bffac38-8ffb-4dc6-a1b3-3e5b8425739e"><br/>
   * accounts.service.ts : Concerne les fonctionnalités métier des comptes bancaires.<br/>
   * customer.service.ts : Concerne les fonctionnalités métier des clients.<br/>

 => 2.5. Routing (le fichier 'app-routing.module.ts'): <br/>
 Le routing dans Angular fait référence à la capacité de l'application à naviguer entre différentes vues ou composants en fonction de l'URL actuelle. Il permet de définir des règles de navigation, de gérer les paramètres d'URL et d'afficher dynamiquement les composants correspondants.<br/><br/>
 <img width="500" alt="Screenshot 2023-06-24 171252" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/10551e66-fdbd-4f40-95fb-aea631fd18f9">

## L'interface utilisateur et les fonctionnalités implémentées ## 

-L'ajout d'un client :
<img width="960" alt="add 1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/2ae666b1-f65b-474a-b6e2-be25999a1798">
<img width="960" alt="add 2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/b3714018-b70f-4521-965a-f4321470dfd9">
<img width="960" alt="add 3" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/e6c1f138-fd7f-41ae-87bd-280937c7e74f">
<img width="960" alt="add 4" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/0f1646cf-9be0-43b0-a527-49eb68bc2014">
<img width="960" alt="add 5" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/d5e14bff-137a-43b8-9cff-963e5d9ff3c4">
<br/><br/>

- La liste des clients et la recherche d'un client selon un mot clé :
<img width="960" alt="1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/088441ec-7a49-4a56-899b-d6a3964e3c33">
<img width="960" alt="2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/0db33031-416c-4fc6-9626-6b1d12ec82c5">
<img width="960" alt="3" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/cd17b3b7-1696-4dc7-8984-1c59d7f38787">
<br/><br/>

- La suppression d'un client :
<img width="960" alt="1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/832afdcf-f4a8-4f5b-9a4e-d60caf414b96">
<img width="960" alt="Screenshot 2023-06-24 191137" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/bbb3a93d-df47-4493-9032-6ba9f70c80f3">
<br/><br/>

- L'affichage des comptes d'un client :
<img width="960" alt="accounts 1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/31f9c9f4-7474-4b72-b969-986fbbc124db">
<img width="960" alt="accounts 2 " src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/f56ef0d4-b1f3-492e-92da-3a39c272d9fd">
<br/><br/>

- L'historique des opérations d'un compte précis :
<img width="960" alt="Screenshot 2023-06-24 193546" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/e4b44a89-027e-4f72-81c5-09804cdc8427">
<img width="960" alt="1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/1e897cf5-d3c6-4ad0-a6cf-a3f6e2e30153">
<img width="960" alt="history du compte" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/5eca0455-ea72-4a31-afce-b197d32958b3">
<br/><br/>

- L'opération "DEBIT" sur un compte précis :
<img width="960" alt="debit 1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/da2887ce-7f5f-41a9-a012-3f55fec8b72b">
<img width="960" alt="debit 2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/e89adaef-80be-4e6a-9f30-d442c680cdca">
<img width="960" alt="debi 3" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/1bcceef0-ac84-4d4a-87c0-c4e8dc4f0244">
<br/><br/>

- L'opération "CREDIT" sur un compte précis :
<img width="960" alt="1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/549684b1-3630-4e44-9aac-65b29eaade07">
<img width="960" alt="2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/1f8619b9-2837-4ed7-b8f7-a6045ff2e86f">
<img width="960" alt="3" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/fb636040-6929-4c12-81ed-1d1e19c11c5e">
<br/><br/>

- L'opération "TRANSFER" sur un compte précis :
<img width="960" alt="1" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/41154788-4e8d-4c27-a666-fc67cd520f6c">
<img width="960" alt="2" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/06ad302a-f088-49cd-8436-966bc830c5c1">
<img width="960" alt="3" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/c0bdcefa-aada-4962-9201-76385c7d63f6">
<img width="960" alt="4" src="https://github.com/Ikramouslih/Final-Project-Digital-Banking/assets/60039200/8d89ad5f-f25e-4ffd-8b8b-446dd918c89b">
<br/><br/>

## Conclustion ## 
En conclusion, grâce à la combinaison de Spring Boot et d'Angular, l'application Digital Banking offre une solution complète et performante pour répondre aux besoins de gestion bancaire. Les technologies utilisées ont permis de développer une application robuste, sécurisée et conviviale, offrant aux utilisateurs une expérience bancaire agréable et efficace.
