# Ec2 commandes



### LIST ALL VPCS

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

```bash
aws s3 mb s3://devopsteam99-i346 ^
--region eu-central-1 ^
--profile s3-admin
```

```
[OUTPUT]
make_bucket: devopsteam99-i346
```


### LIST ALL SUBNETS

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

```bash
$ aws s3 cp ./cloud/test1.txt s3://devopsteam09-i346/ \
--profile devopsteam09
```

```
[OUTPUT]
upload: .\test1.txt to s3://devopsteam09-i346/test1.txt
```

### CREATE ROUTE TABLE

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

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

### ADD ROUTE IN ROUTE TABLE

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

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

### ASSOCIATE ROUTE TABLE TO SUBNETS

* [AWS Official Doc - Create Bucket](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/mb.html#examples)

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
