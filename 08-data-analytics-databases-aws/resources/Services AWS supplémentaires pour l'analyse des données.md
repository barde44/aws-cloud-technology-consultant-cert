# Traitement des données pour l'analyse : ETL et ELT

Ce cours présente deux approches principales pour le traitement des données dans le cadre de l'analyse :  

- **ETL (Extract, Transform, Load)** : Extraction, Transformation et Chargement.  
- **ELT (Extract, Load, Transform)** : Extraction, Chargement et Transformation.  

---

## 1. Extraction des données

Les deux approches commencent par l'extraction des données. Sur AWS, vous pouvez utiliser plusieurs services pour capturer des données à partir d'applications, de capteurs, d'infrastructures informatiques et de sources tierces.  

### Services AWS pour l'extraction des données

- **Amazon API Gateway**  
  Permet de créer, publier et maintenir des API RESTful et WebSocket pour accéder aux données et aux fonctionnalités des services dorsaux.  
  Pour plus d'informations : [Amazon API Gateway](https://aws.amazon.com/api-gateway/)

- **AWS Transfer Family**  
  Permet de transférer des fichiers entre AWS et vos centres de données sur site.  
  Pour plus d'informations : [AWS Transfer Family](https://aws.amazon.com/aws-transfer-family/)

- **Amazon Kinesis**  
  Capture de grands volumes de données en temps réel (vidéos, sons, journaux, flux IoT). Les données sont ensuite ingérées pour traitement et analyse.  
  Pour plus d'informations : [Amazon Kinesis](https://aws.amazon.com/kinesis/)

- **AWS Batch**  
  Permet de traiter de gros volumes de données par lots (facturation, traitement des stocks, cycles d'abonnement).  
  Pour plus d'informations : [Architecture par lots](https://docs.aws.amazon.com/batch/latest/userguide/what-is-batch.html)

- **AWS Database Migration Service (DMS)**  
  Facilite la migration de bases de données sur site vers le cloud, même entre différents moteurs.  
  Pour plus d'informations : [Fonctionnement du service de migration des bases de données AWS](https://docs.aws.amazon.com/dms/latest/userguide/Welcome.html)

---

## 2. Approche ETL

### 2.1 Transformation des données

La deuxième étape de l'ETL consiste à transformer les données pour répondre aux exigences du système cible.  

#### Services AWS pour la transformation

- **AWS Lambda**  
  Exécute du code en réponse à des déclencheurs et permet de collecter, transformer et charger des données ou d'invoquer des prédictions ML.  
  Pour plus d'informations : [AWS Lambda](https://aws.amazon.com/lambda/)

- **AWS Glue**  
  Transforme et nettoie des flux de données en continu provenant de Kinesis ou Kafka, et charge les résultats dans S3, lacs de données ou entrepôts.  
  Pour plus d'informations : [AWS Glue](https://aws.amazon.com/glue/)

### 2.2 Chargement des données

Après transformation, les données sont chargées dans le système cible. Selon le type de données :  

#### Données structurées

- **Amazon RDS** : Bases de données relationnelles gérées (MySQL, PostgreSQL, SQL Server, Oracle, etc.).  
  Pour plus d'informations : [Amazon RDS](https://aws.amazon.com/rds/)

- **Amazon Redshift** : Entrepôt de données pour analyses sur de grands ensembles de données avec stockage en colonnes.  
  Pour plus d'informations : [Amazon Redshift](https://aws.amazon.com/redshift/)

#### Données semi-structurées ou non structurées

- **Amazon DynamoDB** : Base NoSQL entièrement gérée pour applications hautes performances.  
  Pour plus d'informations : [Amazon DynamoDB](https://aws.amazon.com/dynamodb/)  
  Concepts associés : [NoSQL](https://aws.amazon.com/nosql/)

- **Amazon OpenSearch Service** : Recherche et analyse de données volumineuses en temps réel.  
  Pour plus d'informations : [Amazon OpenSearch Service](https://aws.amazon.com/opensearch-service/)

---

## 3. Approche ELT

### 3.1 Chargement des données brutes

Les données sont chargées telles quelles dans un lac de données ou un service capable de gérer des schémas flexibles.  

- **Amazon S3** : Service de stockage d’objets pour lacs de données, applications natives cloud et mobiles.  
  Pour plus d'informations : [Amazon S3](https://aws.amazon.com/s3/) et [Data Lakes and Analytics sur AWS](https://aws.amazon.com/big-data/datalakes-and-analytics/)

### 3.2 Transformation des données

La transformation des données brutes s'effectue en fonction des besoins, après nettoyage et structuration, pour les rendre compatibles avec le format souhaité et les ingérer dans le service approprié.

---

## 4. Analyse des données

Après le processus ETL ou ELT, vous pouvez effectuer des analyses sur les données transformées.  

- De nombreux services AWS offrent des fonctions pour obtenir des insights.  
- Pour visualiser les données : **Amazon QuickSight**.  
- Pour plus de détails sur l'analyse sur AWS, consultez le livre blanc : [Analytics in the Overview of Amazon Web Services](https://d1.awsstatic.com/whitepapers/aws-overview.pdf)