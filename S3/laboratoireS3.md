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
aws s3 mb s3://devopsteam99-i346 --region eu-central-1 --profile s3-admin
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
aws s3 ls s3://devopsteam09-i346 \
--profile devopsteam09
```

```
[OUTPUT]
An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
$ aws s3 cp C:\texte.txt s3://devopsteam09-i346/ \
--profile devopsteam09
```

```
upload: C:\texte.txt to s3://devopsteam09-i346/texte.txt
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
An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
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
An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
 $ aws s3 ls s3://devopsteam09-i346/repertoire1 \
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
An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
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
$ aws s3 sync . s3://devopsteam09-i346 \
--profile devopsteam09
```

```
[OUTPUT]
fatal error: An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
$ aws s3 presign s3://devopsteam09-i346/test2_upload.txt \
--expires-in 604800 \
--region eu-central-1 \
--endpoint-url https://s3.eu-central-1.amazonaws.com <
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
fatal error: An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
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
fatal error: An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
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
An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action

```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
//TODO
```

```
[OUTPUT]
//TODO
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
An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
```

* [La commande à réaliser pour effecuter l'action demandée]

```bash
$ aws s3 rm s3://devopsteam09-i346 \
--recursive \
--profile devopsteam09
```

```
[OUTPUT]
fatal error: An error occurred (AccessDenied) when calling the ListObjectsV2 operation: User: arn:aws:iam::709024702237:user/devopsteam09-i346 is not authorized to perform: s3:ListBucket on resource: "arn:aws:s3:::devopsteam09-i346" because no identity-based policy allows the s3:ListBucket action
```

---

## Questions d'analyse

Consigne : répondre en utilisant des sources officielles et en vous appuyant dessus pour répondre.

### Pourquoi est-il déconseillé de détruire un bucket S3 selon AWS ?

* [Sources AWS]

Entraîne la perte permanentes des données qu'ils contient. Peut causer des interruption, ou entraîner des coûts supplémentaires pour récuperer les données.

### Quelle est la différence entre un Bucket S3 et Glacier ?

* [Sources AWS]

le bucket s3 Glacier est un service distinct qui stocke les données sous forme d'archives dans des coffres-forts. Il est déconseiller de l'utilisser pour des données à long termes.

### Reprenez l'IAM "Policy" et expliquer ce que vous pouvez en déduire au niveau des droits qui vous sont alloués

Consigne : Reprenez la "policy" et documenter chaque ligne
