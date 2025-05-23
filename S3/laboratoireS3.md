# Laboratoire S3

## Installation et configuration du CLI

* [Installer le client git](https://git-scm.com/)
  * Git bash vous embarque de nombreuses commandes Linux utiles pour s'entrainer avec S3 (cat, grep, touch, ls)
* [Installation du CLI - v2](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
* [Configuration du CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-quickstart.html#getting-started-quickstart-existing)
  * Les clés vous ont été partagées par oneDrive
* [Gestion des profiles](https://docs.aws.amazon.com/cli/v1/userguide/cli-configure-files.html#cli-configure-files-format-profile)
  * Vous devez créer un profile du nom de votre équipe et l'utiliser pour toute les futures commandes
  ```
  aws s3 <la commande> --profile devopsteam<xx>
  ```

## IAM Policy

Voici la "policy" qui vous a été attribuée:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "s3:ListAllMyBuckets",
            "Resource": "arn:aws:s3:::*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:PutObject",
                "s3:GetObject",
                "s3:DeleteObject",
            ],
            "Resource": "arn:aws:s3:::devopsteam<XX>-i346/*" //XX -> devopsteam number
        }
    ]
}
```

## Exploiter un S3

Attention:
* Vous devez utiliser la v2 du CLI
* Le client offre soit la commande s3, soit s3api. En priorité vous devez essayer "s3".

### Créer un bucket

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* Le bucket existe-t-il ?

```bash
aws s3 ls --profile devopsteam99-i346 | grep "devopsteam*"
```

```
[OUTPUT]
2025-01-27 22:23:30 devopsteam01-i346
2025-01-27 22:28:03 devopsteam02-i346
2025-01-27 22:28:05 devopsteam03-i346
2025-01-27 22:28:06 devopsteam04-i346
2025-01-27 22:28:08 devopsteam05-i346
2025-01-27 22:28:09 devopsteam06-i346
2025-01-27 22:28:11 devopsteam07-i346
2025-01-27 22:28:13 devopsteam08-i346
2025-01-27 22:28:14 devopsteam09-i346
2025-01-27 22:28:16 devopsteam10-i346
2025-02-03 19:32:33 devopsteam99-i346
```

* Créer un bucket (via un compte admin)

```bash
aws s3 mb s3://devopsteam99-i346 ^
--region eu-central-1 ^
--profile s3-admin
```

```
[OUTPUT]
make_bucket: devopsteam99-i346
```


### Uploader un fichier

//TODO en suivant le modèle livré sous "Créer un bucket"

* https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/cp.html 

* [Vérifier l'état du bucket avant votre commande]

```bash
aws s3 ls s3://devopsteam09-i346 ^
--profile devopsteam09
```

```
[OUTPUT]
                           PRE path/
                           PRE repertoire1/
                           PRE test/
2025-02-12 12:20:33          0 test1.txt
2025-02-05 18:56:19          5 test1_upload.txt
2025-02-05 18:56:19          5 test2_upload.txt
2025-02-11 13:40:00          0 texte.txt
2025-02-05 18:09:17          0 upload_file.txt
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
$ aws s3 cp ./cloud/test1.txt s3://devopsteam09-i346/ \
--profile devopsteam09
```

```
upload: .\test1.txt to s3://devopsteam09-i346/test1.txt
```

### Uploader un répertoire

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)
* https://www.geeksforgeeks.org/how-to-upload-files-to-aws-s3-using-cli/

* [Vérifier l'état du bucket avant votre commande]

```bash
aws s3 ls s3://devopsteam09-i346 \
--profile devopsteam09
```

```
[OUTPUT]
                           PRE path/
                           PRE repertoire1/
                           PRE test/
2025-02-12 12:20:33          0 test1.txt
2025-02-05 18:56:19          5 test1_upload.txt
2025-02-05 18:56:19          5 test2_upload.txt
2025-02-11 13:40:00          0 texte.txt
2025-02-05 18:09:17          0 upload_file.txt
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
$ aws s3 cp ./Cours/cloud/synchronisation s3://devopsteam09-i346/repertoire1 \
--recursive \
--profile devopsteam09
```

```
[OUTPUT]
upload: Cours\cloud\synchronisation\test1.2.txt to s3://devopsteam09-i346/repertoire1/test1.2.txt
upload: Cours\cloud\synchronisation\test1.1.txt to s3://devopsteam09-i346/repertoire1/test1.1.txt
```

### Lister le contenu d'un "repertoire"

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Repertori upload]([https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/cp.html))

* [Vérifier l'état du bucket avant votre commande]

```bash
$ aws s3 ls s3://devopsteam09-i346 \
--recursive \
--profile devopsteam09
```

```
[OUTPUT]
                           PRE path/
                           PRE repertoire1/
                           PRE test/
2025-02-12 12:20:33          0 test1.txt
2025-02-05 18:56:19          5 test1_upload.txt
2025-02-05 18:56:19          5 test2_upload.txt
2025-02-11 13:40:00          0 texte.txt
2025-02-05 18:09:17          0 upload_file.txt
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
 $ aws s3 ls s3://devopsteam09-i346 \
--recursive \
--profile devopsteam09
```

```
[OUTPUT]
An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
```

### Synchroniser un répertoire local de sa machine avec un bucket

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)
* https://docs.aws.amazon.com/cli/latest/userguide/cli-services-s3-commands.html

* [Vérifier l'état du bucket avant votre commande]

```bash
aws s3 ls s3://devopsteam09-i346 \
--profile devopsteam09
```

```
[OUTPUT]
                           PRE path/
                           PRE repertoire1/
                           PRE test/
2025-02-12 12:20:33          0 test1.txt
2025-02-05 18:56:19          5 test1_upload.txt
2025-02-05 18:56:19          5 test2_upload.txt
2025-02-11 13:40:00          0 texte.txt
2025-02-05 18:09:17          0 upload_file.txt
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
$ aws s3 sync C:/Cours/cloud/synchronisation s3://devopsteam09-i346 \
--profile devopsteam09
```

```
[OUTPUT]
fatal error: An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
```

### Publier un fichier présent sur un bucket en générant un lien (url) temporaire

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
$ aws s3 ls s3://devopsteam09-i346 \
--profile devopsteam09
```

```
[OUTPUT]
                           PRE path/
                           PRE repertoire1/
                           PRE test/
2025-02-12 12:20:33          0 test1.txt
2025-02-05 18:56:19          5 test1_upload.txt
2025-02-05 18:56:19          5 test2_upload.txt
2025-02-11 13:40:00          0 texte.txt
2025-02-05 18:09:17          0 upload_file.txt
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
$ aws s3 presign s3://devopsteam09-i346/test2_upload.txt \
--expires-in 60 \
--region eu-central-1 \ 
--profile devopsteam09
```

```
[OUTPUT]
https://s3.eu-central-1.amazonaws.com/devopsteam09-i346/test2_upload.txt?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIA2KFJKL4OZXZVCEH6%2F20250211%2Feu-central-1%2Fs3%2Faws4_request&X-Amz-Date=20250211T125229Z&X-Amz-Expires=604800&X-Amz-SignedHeaders=host&X-Amz-Signature=53787a1939d55582c144bef3dae6590afcce827cf34acb29ad96bf60621c5be7
```

### Supprimer un fichier

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
aws s3 ls s3://devopsteam09-i346 \
--profile devopsteam09
```

```
                           PRE path/
                           PRE repertoire1/
                           PRE test/
2025-02-12 12:20:33          0 test1.txt
2025-02-05 18:56:19          5 test1_upload.txt
2025-02-05 18:56:19          5 test2_upload.txt
2025-02-11 13:40:00          0 texte.txt
2025-02-05 18:09:17          0 upload_file.txt
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
$ aws s3 rm s3://devopsteam09-i346//test2_upload.txt \
--profile devopsteam09

```

```
delete: s3://devopsteam09-i346//test2_upload.txt
```

### Vider un "repertoire"

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
aws s3 ls s3://devopsteam09-i346 \
--profile devopsteam09
```

```
                           PRE path/
                           PRE repertoire1/
                           PRE test/
2025-02-12 12:20:33          0 test1.txt
2025-02-05 18:56:19          5 test1_upload.txt
2025-02-05 18:56:19          5 test2_upload.txt
2025-02-11 13:40:00          0 texte.txt
2025-02-05 18:09:17          0 upload_file.txt
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
$ aws s3 rm s3://devopsteam09-i346/repertoire1/ \
--recursive \
--profile devopsteam09
```

```
[OUTPUT]
//TODO
```

### Extraire uniquement les metadonnées d'un objet

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
aws s3 ls s3://devopsteam09-i346 \
--profile devopsteam09
```

```
                           PRE path/
                           PRE repertoire1/
                           PRE test/
2025-02-12 12:20:33          0 test1.txt
2025-02-05 18:56:19          5 test1_upload.txt
2025-02-05 18:56:19          5 test2_upload.txt
2025-02-11 13:40:00          0 texte.txt
2025-02-05 18:09:17          0 upload_file.txt
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
aws s3api get-object-attributes ^
--bucket devopsteam09-i346 ^
--key test2.jpg ^
--object-attributes ObjectSize ^
--profile devopsteam99-i346
```

```
[OUTPUT]
[OUTPUT]
{
{
    "LastModified": "2025-02-23T08:32:02+00:00",
    "ObjectSize": 17010
}
```

### Vider le bucket

//TODO en suivant le modèle livré sous "Créer un bucket"

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

* [Vérifier l'état du bucket avant votre commande]

```bash
aws s3 ls s3://devopsteam09-i346 \
--profile devopsteam09
```

```
                           PRE path/
                           PRE repertoire1/
                           PRE test/
2025-02-12 12:20:33          0 test1.txt
2025-02-05 18:56:19          5 test1_upload.txt
2025-02-05 18:56:19          5 test2_upload.txt
2025-02-11 13:40:00          0 texte.txt
2025-02-05 18:09:17          0 upload_file.txt
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
$ aws s3 rm s3://devopsteam09-i346/ \
--recursive \
--profile devopsteam09   
```

```
[OUTPUT]
delete: s3://devopsteam09-i346/path/test1_upload.txt
delete: s3://devopsteam09-i346/test1_upload.txt
delete: s3://devopsteam09-i346/upload_file.txt
delete: s3://devopsteam09-i346/path/test2_upload.txt
delete: s3://devopsteam09-i346/test2_upload.txt
delete: s3://devopsteam09-i346/repertoire1/test1.1.txt
delete: s3://devopsteam09-i346/test1.txt
delete: s3://devopsteam09-i346/texte.txt
delete: s3://devopsteam09-i346/repertoire1/test1.2.txt
delete: s3://devopsteam09-i346/test/test2_upload.txt
delete: s3://devopsteam09-i346/test/test1_upload.txt
```

---

## Questions d'analyse

Consigne : répondre en utilisant des sources officielles et en vous appuyant dessus pour répondre.

### Pourquoi est-il déconseillé de détruire un bucket S3 selon AWS ?

* [Sources AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/delete-bucket.html)

AWS déconseille de supprimer un bucket. Le nom étant unique est impactant les DNS, une suppression/recréation (par exemple lors de tests automatique) risque de rendre l'état des DNS instables. En supprimant un Bucket, vous permettez à un autre utilisateur de le créer et vous risquez ainsi de ne plus pouvoir l'utiliser ce nom. Le coût d'un Bucket vide est nul. Autrement dit si vous désirez utiliser ce Bucket dans un avenir proche, laissez-le en place.

### Quelle est la différence entre un Bucket S3 et Glacier ?

* [Sources AWS](https://aws.amazon.com/s3/storage-classes/glacier/)

Glacier est un produit utilisant les mêmes concepts d'"Object Storage" que S3. La différence majeure est la nécessité d'accéder aux données stockées. En effet Glacier est prévu pour de l'archivage. Le temps de récupération peut être de plusieurs heures (max 12 heures). Cette lenteur qui n'est pas acceptable pour l'hébergement de fichier dont nous avons régulièrement besoin et cependant très intéressante pour des archives. Le coût de stockage devient dérisoire sur Glacier.

Rapide comparatif
|Produit|Temps de récupération|Coût ($/Gb|
|:--|:--|:--|
|S3 Standard|Immédiat|Entre 0.0021-0.0023|
|Glacier Deep Archive|Jusqu'à 12 heures|0.00099|

[Source](https://aws.amazon.com/s3/pricing/)

### Reprenez l'IAM "Policy" et expliquer ce que vous pouvez en déduire au niveau des droits qui vous sont alloués

Consigne : Reprenez la "policy" et documenter chaque ligne
