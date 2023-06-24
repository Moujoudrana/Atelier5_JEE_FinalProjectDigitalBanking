JEE-Activite-5
-
On souhaite créer une application qui permet de gérer des comptes bancaires. Chaque compte appartient à un client. 
Un compte peut subir plusieurs opérations de type DEBIT ou CREDIT. Il existe deux types de comptes : Comptes courants et comptes épargnes.

L'application repose sur deux technologies majeures : Spring Boot, un framework Java populaire pour le développement d'applications d'entreprise, et Angular, un framework JavaScript utilisé pour la création d'interfaces utilisateur dynamiques et interactives.

Travail à faire
-
Partie Backend
-
1. Créer un projet Spring Boot
2. Créer les entités JPA : Customer, BankAccount, Saving Account, CurrentAccount, AccountOperation
3. Créer les interfaces JPA Repository basées sur Spring Data
4. Créer la couche service, DTOs et RestController

Partie Frontend
-
1. Créer un projet Angular avec la commande ng new DigitalBanking
2. Créer le modele 'Customer' et 'Account'
3. Créer les composants et services


![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/9a8bf6c6-cde8-4833-9c9f-a637eb89d7da)

Spring Boot est un framework open source pour le développement d'applications Java.
Il est basé sur le framework Spring et vise à simplifier le processus de configuration, de déploiement et de développement d'applications Java.

Parmi ses caractéristiques:
-
  -Spring Boot intègre un serveur web embarqué, tel que Tomcat.
  
  -Spring Boot propose des dépendances prédéfinies pour de nombreux frameworks et bibliothèques couramment utilisés, tels que Spring MVC, Spring Data, Hibernate, JPA, JDBC, etc.
  
  -Spring Boot s'appuie sur le framework Spring et profite de ses fonctionnalités, telles que l'injection de dépendances.

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/9d7f0aba-f5d3-4d2f-a058-5bb5b20633d1)

Angular est un framework open-source développé par Google. Il est utilisé pour créer des applications web dynamiques et interactives. Angular est basé sur le langage TypeScript, qui est une extension de JavaScript.
Angular est largement utilisé pour développer des applications web d'entreprise, des applications de gestion, des tableaux de bord, des applications mobiles, etc. Il est apprécié pour sa performance, sa robustesse et sa capacité à créer des applications complexes et évolutives.

Parmi ses caractéristiques:
-
  -Angular utilise une architecture basée sur des composants. Les composants sont des éléments autonomes de l'application qui encapsulent à la fois le HTML, le CSS et le comportement de l'interface utilisateur.
  
  -Les services dans Angular sont des classes réutilisables qui fournissent des fonctionnalités spécifiques à travers l'application.
  
  -Angular propose une liaison de données bidirectionnelle entre les composants et les vues.
  
Concernant le projet:
-
*Backend:
-
SDK : 1.8 Oracle OpenJDK version 18.0.2

Java : 17

Type : Maven

Les dépendances utilisées:

    -Spring Web : pour créer des applications Web, y compris RESTful, à l'aide de Spring MVC. Utilise Apache Tomcat comme conteneur intégré par défaut.

    -Spring DATA JPA : Pour conserver les données dans ‘SQL stores‘ avec Java Persistance API à l’aide de Spring Data et Hibernate. C'est un module qui facilite le ORM basé sur JPA. Il est utilisé avec les bases de données relationnelles.

    -MySQL : MySQL est l'un des systèmes de bases de données relationnelles les plus populaires et il est souvent utilisé dans les applications Spring Boot.

    -Lombok : Un outil de bibliothèque Java qui génère du code pour minimiser le code ‘boilerplate’. La bibliothèque remplace le code ‘boilerplate’ par des annotations faciles à utiliser (Exemples : @NoArgsConstructor, @Getter, @Setter…).

    -Spring-boot-devtools : une dépendance Spring Boot qui fournit des outils de développement pratiques pour le développement de vos applications Spring Boot. Cette dépendance a été utilisé dans cette activité pour :
    
      Le mécanisme de rechargement automatique des classes en mode développement;
      
      Le serveur embarqué qui permet de redémarrer l'application automatiquement lorsqu'un changement est détecté.

*Frontend
-
Angular CLI version 16.0.1

Installation :

    Bootstrap & Bootstrap-icons : Une bibliothèque open-source de développement front-end pour la conception de sites et d'applications web. Elle fournit des styles CSS prédéfinis, des composants JavaScript et des icônes pour faciliter la création d'interfaces utilisateur esthétiques et responsives.

    npm i bootstrap bootstrap-icon
    
Architecture de l'application
-

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/8d81c06f-487d-4289-8b6e-db47bcb494df)

*Backend*
-

-La couche web joue un rôle essentiel dans la gestion des interactions entre les utilisateurs et l'application. Elle est responsable de la réception des requêtes HTTP, du traitement de ces requêtes et de la génération des réponses correspondantes.

      BankAccountRestAPI : Concerne les comptes bancaires.
      
      CustomerRestController : Concerne les clients.

-La couche de service joue un rôle clé dans la gestion de la logique métier de l'application. Elle est responsable de la mise en œuvre des fonctionnalités métier, de la coordination des opérations et de l'interaction avec la couche de persistance et la couche web.

      BankAccountService : Interface qui contient l'ensemble des fonctionnalités métier des comptes et des clients à implementer.
      
      BankAccountServiceImpl : Contient l'implementation des méthodes précisées dans l'interface.

-La couche DAO (Data Access Object) est responsable de l'accès aux données et de l'interaction avec la couche de persistance de l'application. Son objectif principal est d'abstraire les détails de l'accès aux données et de fournir une interface cohérente pour effectuer des opérations CRUD (Create, Read, Update, Delete) sur les entités persistantes.

      AccountOperationRepository:Pour effectuer des opérations de persistance sur les operations bancaires.

      BankAccountRepository:Pour effectuer des opérations de persistance sur les comptes bancaires.

      CustomerRepository: Pour effectuer des opérations de persistance sur les clients.
      

-DTO (Data Transfer Object) est un objet utilisé pour transférer des données entre les différentes couches de l'application, entre la couche de présentation (couche web) et la couche de service.

      AccountHistoryDTO

      AccountOperationDTO

      bankAccountDTO

      CreditDTO

      CurrentBankAccountDTO

      CustomerDTO

      DebitDTO

      SavingBankAccountDTO

      TransferRequestDTO

-Les mappers sont des composants responsables de la conversion et de la transformation des données entre différents formats ou structures.(Entité vers DTO ou l'inverse)

      BankAccountMapperImpl:Pour convertir les objets.    

-Les entités font référence à des objets qui représentent des concepts métier ou des données persistantes dans une base de données.

      AccountOperation:Pour les operations de debit,credit ou transfer.

      BankAccount:Pour les comptes bancaires.

      CurrentAccount:Pour les comptes courants.

      Customer:Pour les clients de la banque.

      SavingAccount:Pour les comptes epargnes.

*Frontend*
-

-Les modèles font référence aux structures de données utilisées pour représenter et manipuler les données dans l'application. Les modèles sont généralement des classes TypeScript qui définissent la structure des objets de données et les fonctionnalités associées.

        Account

        Customer

-Les composants sont les éléments de base pour construire une application. Un composant est une combinaison de code HTML, CSS et TypeScript qui définit la logique, l'apparence et le comportement d'une partie spécifique de l'interface utilisateur de l'application.

        accounts:Responsable de l'affichage des opérations bancaires d'un compte précis ainsi que d'effectuer des nouvelles opérations (crédit, débit, transfert).

        customer-accounts: Responsable de l'affichage des comptes bancaires d'un client.

        customers: Responsable de l'affichage de la liste des clients existant, supprimer ou rechercher un client a partir de son nom.

        navbar: Responsable de l'affichage et de la logique de la barre de navigation.

        new-customer: Responsable de l'affichage du formulaire d'ajout d'un nouveau client.

-Les services sont des classes qui fournissent des fonctionnalités réutilisables et partagées au sein de l'application. Ils sont utilisés pour séparer la logique métier et les fonctionnalités communes des composants afin de favoriser la modularité, la réutilisabilité et la maintenabilité du code.

        accounts: Concerne les fonctionnalités métier des comptes bancaires.
        
        customer: Concerne les fonctionnalités métier des clients.


L'interface de l'Output et les fonctionnalités implémentées
-

  .La page accounts nous donne la possibilité de chercher un client grace à son ID et de visualiser toutes les opérations faites par ce client:

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/2521776a-57dd-44ef-b310-7a6554c4abea)


![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/6caac281-77e4-480d-9bdc-90b5b3ca4649)

  .La possibilité d'effectuer une transfer,debit,credit est aussi possible

  DEBIT:

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/25eebd2e-9d52-41b7-8e09-d70679c2e461)

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/33500a57-e15a-4f50-9f60-4e4604c2c987)

  TRANSFER:

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/62b2c55a-2455-4a66-9392-39392a20996d)

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/806d16ca-0257-47f5-aaca-888c08239c70)


  .La page customers nous donne la possibilité de visualiser tout les clients:

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/f6677905-112a-4901-bdea-5d1d5dccbc3e)

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/5eaee961-d3be-419d-8616-76f490a538e6)

  .Il est possible de chercher un client par son nom:

  ![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/15503986-95b9-48cd-b072-8c37e53f35ad)

  .Il est aussi possible de créer un nouveau client, de visualiser ses données ou meme de le supprimer:

  CREATION:

  ![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/82e3a291-5356-43ca-8f41-6eec1fc0cfd0)

  ![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/faa717c8-78ed-4ebe-8a16-faa8c4d146f3)

  ![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/d7252bf1-a2ac-43ef-9dc7-9b4c48f89fc0)

  VISUALISATION:

  ![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/84b417d1-44aa-44c9-9ae8-626fefe9ed05)

  ![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/47ba752d-d558-47b4-9f07-1e7b8b6968e9)

  SUPPRESSION:

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/fa8693da-e1ba-4f4d-a843-64021f4a5b1b)

![image](https://github.com/Moujoudrana/Atelier5_JEE_FinalProjectDigitalBanking/assets/93864104/66cef9b0-57b1-497a-80d3-27823e43f4f3)


  















