# Ec2 commandes



### LIST ALL VPCS

* [AWS Official Doc - LIST ALL VPCS](https://awscli.amazonaws.com/v2/documentation/api/2.1.29/reference/ec2/describe-vpcs.html)

```bash
$ aws ec2 describe-vpcs ^
--profile devopsteam09 ^
--region eu-central-1 ^
--output table

```

```
[OUTPUT]
-----------------------------------------------------------
|                      DescribeVpcs                       |
+---------------------------------------------------------+
||                         Vpcs                          ||
|+----------------------+--------------------------------+|
||  CidrBlock           |  10.0.0.0/16                   ||
||  DhcpOptionsId       |  dopt-05854b009a610ac91        ||
||  InstanceTenancy     |  default                       ||
||  IsDefault           |  False                         ||
||  OwnerId             |  709024702237                  ||
||  State               |  available                     ||
||  VpcId               |  vpc-0a22d771f16ae549d         ||
|+----------------------+--------------------------------+|
|||               BlockPublicAccessStates               |||
||+------------------------------------------+----------+||
|||  InternetGatewayBlockMode                |  off     |||
||+------------------------------------------+----------+||
|||               CidrBlockAssociationSet               |||
||+----------------+------------------------------------+||
|||  AssociationId |  vpc-cidr-assoc-0fad6e9a11ccae331  |||
|||  CidrBlock     |  10.0.0.0/16                       |||
||+----------------+------------------------------------+||
||||                  CidrBlockState                   ||||
|||+-------------------+-------------------------------+|||
||||  State            |  associated                   ||||
|||+-------------------+-------------------------------+|||
|||                        Tags                         |||
||+----------------------+------------------------------+||
|||  Key                 |  Name                        |||
|||  Value               |  vpc-i346                    |||
||+----------------------+------------------------------+||

```


### LIST ALL SUBNETS

* [AWS Official Doc - LIST ALL SUBNETS](https://awscli.amazonaws.com/v2/documentation/api/2.1.29/reference/ec2/describe-subnets.html)

```bash
$ aws ec2 describe-subnets ^
--profile devopsteam09 ^
--region eu-central-1 ^
--output table

```

```
[OUTPUT]
------------------------------------------------------------------------------------------------------------
|                                              DescribeSubnets                                             |
+----------------------------------------------------------------------------------------------------------+
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1c                                                          ||
||  AvailabilityZoneId          |  euc1-az1                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.10.0/28                                                           ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-0c409522b892fc4bf  ||
||  SubnetId                    |  subnet-0c409522b892fc4bf                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+---------------------------+--------------------------------------------------------------------------+||
|||  Key                      |  Name                                                                    |||
|||  Value                    |  subnet-10.0.10.0/28                                                     |||
||+---------------------------+--------------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1c                                                          ||
||  AvailabilityZoneId          |  euc1-az1                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.4.0/28                                                            ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-02d0c07be4b48422c  ||
||  SubnetId                    |  subnet-02d0c07be4b48422c                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+----------------------------+-------------------------------------------------------------------------+||
|||  Key                       |  Name                                                                   |||
|||  Value                     |  subnet-10.0.4.0/28                                                     |||
||+----------------------------+-------------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1c                                                          ||
||  AvailabilityZoneId          |  euc1-az1                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.2.0/28                                                            ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-06924d9bed0d3f9fa  ||
||  SubnetId                    |  subnet-06924d9bed0d3f9fa                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+----------------------------+-------------------------------------------------------------------------+||
|||  Key                       |  Name                                                                   |||
|||  Value                     |  subnet-10.0.2.0/28                                                     |||
||+----------------------------+-------------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1a                                                          ||
||  AvailabilityZoneId          |  euc1-az2                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.8.0/28                                                            ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-04000c6ac17aa87cd  ||
||  SubnetId                    |  subnet-04000c6ac17aa87cd                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+----------------------------+-------------------------------------------------------------------------+||
|||  Key                       |  Name                                                                   |||
|||  Value                     |  subnet-10.0.8.0/28                                                     |||
||+----------------------------+-------------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1c                                                          ||
||  AvailabilityZoneId          |  euc1-az1                                                               ||
||  AvailableIpAddressCount     |  10                                                                     ||
||  CidrBlock                   |  10.0.0.0/28                                                            ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-007585998051b2c4a  ||
||  SubnetId                    |  subnet-007585998051b2c4a                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+----------------------------------+-------------------------------------------------------------------+||
|||  Key                             |  Name                                                             |||
|||  Value                           |  public-subnet                                                    |||
||+----------------------------------+-------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1a                                                          ||
||  AvailabilityZoneId          |  euc1-az2                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.6.0/28                                                            ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-0abac7e48b2a18a65  ||
||  SubnetId                    |  subnet-0abac7e48b2a18a65                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+----------------------------+-------------------------------------------------------------------------+||
|||  Key                       |  Name                                                                   |||
|||  Value                     |  subnet-10.0.6.0/28                                                     |||
||+----------------------------+-------------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1a                                                          ||
||  AvailabilityZoneId          |  euc1-az2                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.1.0/28                                                            ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-0fc3126df64eea2b9  ||
||  SubnetId                    |  subnet-0fc3126df64eea2b9                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+----------------------------+-------------------------------------------------------------------------+||
|||  Key                       |  Name                                                                   |||
|||  Value                     |  subnet-10.0.1.0/28                                                     |||
||+----------------------------+-------------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1a                                                          ||
||  AvailabilityZoneId          |  euc1-az2                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.99.0/28                                                           ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-0cfda26e6ed7eeeca  ||
||  SubnetId                    |  subnet-0cfda26e6ed7eeeca                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+---------------------------+--------------------------------------------------------------------------+||
|||  Key                      |  Name                                                                    |||
|||  Value                    |  subnet-10.0.99.0/28                                                     |||
||+---------------------------+--------------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1c                                                          ||
||  AvailabilityZoneId          |  euc1-az1                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.5.0/28                                                            ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-092ced6aa04603165  ||
||  SubnetId                    |  subnet-092ced6aa04603165                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+----------------------------+-------------------------------------------------------------------------+||
|||  Key                       |  Name                                                                   |||
|||  Value                     |  subnet-10.0.5.0/28                                                     |||
||+----------------------------+-------------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1c                                                          ||
||  AvailabilityZoneId          |  euc1-az1                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.3.0/28                                                            ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-0aaee76144e27a3dd  ||
||  SubnetId                    |  subnet-0aaee76144e27a3dd                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+----------------------------+-------------------------------------------------------------------------+||
|||  Key                       |  Name                                                                   |||
|||  Value                     |  subnet-10.0.3.0/28                                                     |||
||+----------------------------+-------------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1c                                                          ||
||  AvailabilityZoneId          |  euc1-az1                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.9.0/28                                                            ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-0ab631f69a314e92d  ||
||  SubnetId                    |  subnet-0ab631f69a314e92d                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+----------------------------+-------------------------------------------------------------------------+||
|||  Key                       |  Name                                                                   |||
|||  Value                     |  subnet-10.0.9.0/28                                                     |||
||+----------------------------+-------------------------------------------------------------------------+||
||                                                 Subnets                                                ||
|+------------------------------+-------------------------------------------------------------------------+|
||  AssignIpv6AddressOnCreation |  False                                                                  ||
||  AvailabilityZone            |  eu-central-1a                                                          ||
||  AvailabilityZoneId          |  euc1-az2                                                               ||
||  AvailableIpAddressCount     |  11                                                                     ||
||  CidrBlock                   |  10.0.7.0/28                                                            ||
||  DefaultForAz                |  False                                                                  ||
||  EnableDns64                 |  False                                                                  ||
||  Ipv6Native                  |  False                                                                  ||
||  MapCustomerOwnedIpOnLaunch  |  False                                                                  ||
||  MapPublicIpOnLaunch         |  False                                                                  ||
||  OwnerId                     |  709024702237                                                           ||
||  State                       |  available                                                              ||
||  SubnetArn                   |  arn:aws:ec2:eu-central-1:709024702237:subnet/subnet-01cfa9e1ea9fb3d90  ||
||  SubnetId                    |  subnet-01cfa9e1ea9fb3d90                                               ||
||  VpcId                       |  vpc-0a22d771f16ae549d                                                  ||
|+------------------------------+-------------------------------------------------------------------------+|
|||                                        BlockPublicAccessStates                                       |||
||+---------------------------------------------------------------------------------+--------------------+||
|||  InternetGatewayBlockMode                                                       |  off               |||
||+---------------------------------------------------------------------------------+--------------------+||
|||                                     PrivateDnsNameOptionsOnLaunch                                    |||
||+-----------------------------------------------------------------------------+------------------------+||
|||  EnableResourceNameDnsAAAARecord                                            |  False                 |||
|||  EnableResourceNameDnsARecord                                               |  False                 |||
|||  HostnameType                                                               |  ip-name               |||
||+-----------------------------------------------------------------------------+------------------------+||
|||                                                 Tags                                                 |||
||+----------------------------+-------------------------------------------------------------------------+||
|||  Key                       |  Name                                                                   |||
|||  Value                     |  subnet-10.0.7.0/28                                                     |||
||+----------------------------+-------------------------------------------------------------------------+||

```

### CREATE ROUTE TABLE

* [AWS Official Doc - Create route table](https://awscli.amazonaws.com/v2/documentation/api/2.1.21/reference/ec2/create-route-table.html)

```bash
$ aws ec2 create-route-table ^
 --profile devopsteam09 ^
 --region eu-central-1 ^
 --vpc-id vpc-0a22d771f16ae549d 
```

```
[OUTPUT]
{
    "RouteTable": {
        "Associations": [],
        "PropagatingVgws": [],
        "RouteTableId": "rtb-00b3f747f972f123a",
        "Routes": [
            {
                "DestinationCidrBlock": "10.0.0.0/16",
                "GatewayId": "local",
                "Origin": "CreateRouteTable",
                "State": "active"
            }
        ],
        "Tags": [],
        "VpcId": "vpc-0a22d771f16ae549d",
        "OwnerId": "709024702237"
    },
    "ClientToken": "d1d9c3c1-04d8-40c8-9db4-22efe7d732fa"
}
```

### ADD TAG NAME AFTER CREATION (Route table)

* [AWS Official Doc - add tag](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/ec2/create-tags.html)

```bash
$ aws ec2 create-tags ^
 --resources rtb-0a9293aaf3c30b82c
--tags Key=Name,Value=private-rte-table-devopsteam09
```

```
[OUTPUT]

```

### ADD ROUTE IN ROUTE TABLE

* [AWS Official Doc - Add route in route table](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/ec2/create-route.html)

```bash
$ aws ec2 create-route ^
--route-table-id rtb-0a9293aaf3c30b82c ^
--destination-cidr-block 0.0.0.0/0 ^
--network-interface-id eni-0e382f5c175b09ce2 ^
--region eu-central-1 ^
--profile devopsteam09
```

```
[OUTPUT]
{
    "Return": true
}
```

### ASSOCIATE ROUTE TABLE TO SUBNETS

* [AWS Official Doc - Associate route table to subnet](https://docs.aws.amazon.com/cli/latest/reference/ec2/associate-route-table.html)

```bash
$ aws ec2 associate-route-table^
--route-table-id rtb-0a9293aaf3c30b82c^
--subnet-id subnet-0ab631f69a314e92d^
--region eu-central-1^
--profile devopsteam09
```

```
[OUTPUT]
{
    "AssociationId": "rtbassoc-02be5f3b76aee3c4c",
    "AssociationState": {
        "State": "associated"
    }
}


```
### CREATE SUBNET SECURITY GROUP

* [AWS Official Doc - CREATE SUBNET SECURITY GROUP](https://docs.aws.amazon.com/cli/latest/reference/ec2/create-security-group.html)

```bash
$ aws ec2 create-security-group^
--group-name secugrp-i346-devopsteam09^
--description secugrp-i346-devopsteam09^
--vpc-id vpc-0a22d771f16ae549d^
--tag-specifications 'ResourceType=security-group,Tags=[{Key=Name,Value=SG-DEVOPSTEAM09-SUBNET}]'^
--region eu-central-1^
--profile devopsteam09^
--output table

```

```
[OUTPUT]
---------------------------------------------------------------------------------------------------
|                                       CreateSecurityGroup                                       |
+------------------+------------------------------------------------------------------------------+
|  GroupId         |  sg-06c9cb6e3625401fa                                                        |
|  SecurityGroupArn|  arn:aws:ec2:eu-central-1:709024702237:security-group/sg-06c9cb6e3625401fa   |
+------------------+------------------------------------------------------------------------------+
||                                             Tags                                              ||
|+-----------------------+-----------------------------------------------------------------------+|
||  Key                  |  Name                                                                 ||
||  Value                |  SG-DEVOPSTEAM09-SUBNET                                               ||
|+-----------------------+-----------------------------------------------------------------------+|

```
### AUTHORIZE SECURITY GROUP

* [AWS Official Doc - Authorize-Security-Group](https://awscli.amazonaws.com/v2/documentation/api/2.1.30/reference/ec2/authorize-security-group-ingress.html)

```bash
$ aws ec2 authorize-security-group-ingress ^
--group-id sg-06c9cb6e3625401fa ^
--ip-permissions "IpProtocol=tcp,FromPort=22,ToPort=22,IpRanges=[{CidrIp=10.0.0.0/28,Description=SSH-FROM-DMZ}]" ^
--region eu-central-1 ^
 --profile devopsteam09 ^
 --output table


$ aws ec2 authorize-security-group-ingress ^
 --group-id sg-06c9cb6e3625401fa ^
 --ip-permissions "IpProtocol=tcp,FromPort=3389,ToPort=3389,IpRanges=[{CidrIp=10.0.0.0/28,Description=RDP-FROM-DMZ}]" ^
--region eu-central-1 ^
--profile devopsteam09 ^
--output table
```

```
[OUTPUT]
---------------------------------------------------------------------------------------------------------------
|                                        AuthorizeSecurityGroupIngress                                        |
+------------------------------------------------------------+------------------------------------------------+
|  Return                                                    |  True                                          |
+------------------------------------------------------------+------------------------------------------------+
||                                            SecurityGroupRules                                             ||
|+----------------------+------------------------------------------------------------------------------------+|
||  CidrIpv4            |  10.0.0.0/28                                                                       ||
||  Description         |  RDP-FROM-DMZ                                                                      ||
||  FromPort            |  3389                                                                              ||
||  GroupId             |  sg-06c9cb6e3625401fa                                                              ||
||  GroupOwnerId        |  709024702237                                                                      ||
||  IpProtocol          |  tcp                                                                               ||
||  IsEgress            |  False                                                                             ||
||  SecurityGroupRuleArn|  arn:aws:ec2:eu-central-1:709024702237:security-group-rule/sgr-03f0b754fe2e4adef   ||
||  SecurityGroupRuleId |  sgr-03f0b754fe2e4adef                                                             ||
||  ToPort              |  3389                                                                              ||
|+----------------------+------------------------------------------------------------------------------------+|
```
### CREATE AND UPLOAD PRIVATE KEY PAIR

* [AWS Official Doc - Create Key pair](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/ec2/create-key-pair.html)

```bash
$ aws ec2 create-key-pair ^
--key-name KEY-I346-SUB-DEVOPSTEAM09 ^
--key-type rsa ^
--key-format pem ^
--tag-specifications 'ResourceType=key-pair,Tags=[{Key=Name,Value=KEY-I346-SUB-DEVOPSTEAM09}]' ^
--region eu-central-1 ^
--profile devopsteam09 ^
--output text > KEY.pem
```

```
[OUTPUT]
(Un fichier aura aussi été créer dans votre explorateur de fichier avec la clé)
```


### DEPLOY INSTANCE EC2 WIN

* [AWS Official Doc - Deploy Instance](https://awscli.amazonaws.com/v2/documentation/api/2.0.34/reference/ec2/run-instances.html)

```bash
$ aws ec2 run-instances ^
--image-id ami-045114d716addc65d ^
--instance-type t3.micro ^
--key-name KEY-I346-SUB-DEVOPSTEAM09 ^
--subnet-id subnet-0ab631f69a314e92d ^
--security-group-ids sg-06c9cb6e3625401fa ^
--private-ip-address 10.0.9.11 ^
--region eu-central-1 ^
--profile devopsteam09 ^
--output table
```

```
[OUTPUT]

```
### DEPLOY INSTANCE EC2 LIN

* [AWS Official Doc - Deploy Instance](https://awscli.amazonaws.com/v2/documentation/api/2.0.34/reference/ec2/run-instances.html)

```bash
$ aws ec2 run-instances ^
--image-id ami-0584590e5f0e97daa ^
--instance-type t2.micro ^
--key-name KEY-I346-SUB-DEVOPSTEAM09 ^
--subnet-id subnet-0ab631f69a314e92d ^
--security-group-ids sg-06c9cb6e3625401fa ^
--private-ip-address 10.0.9.10 ^
--region eu-central-1 ^
--profile devopsteam09 ^
--output table
```


### ATTENTION PAS OUBLIÉ LE TAG (Commande pour le rajouter après la création)
```
$ aws ec2 create-tags ^
--resources i-0505d348163787cc3 ^
--tags Key=Name,Value=EC2-DEVOPSTEAM09-LIN-SRV
```
```
[OUTPUT]
-----------------------------------------------------------------------------
|                               RunInstances                                |
+-------------------------------+-------------------------------------------+
|  OwnerId                      |  709024702237                             |
|  ReservationId                |  r-0c0c420ab77675cfe                      |
+-------------------------------+-------------------------------------------+
||                                Instances                                ||
|+--------------------------+----------------------------------------------+|
||  AmiLaunchIndex          |  0                                           ||
||  Architecture            |  x86_64                                      ||
||  ClientToken             |  e2e68681-b907-4dd7-b8e0-1cc4df82b884        ||
||  CurrentInstanceBootMode |  legacy-bios                                 ||
||  EbsOptimized            |  False                                       ||
||  EnaSupport              |  True                                        ||
||  Hypervisor              |  xen                                         ||
||  ImageId                 |  ami-0584590e5f0e97daa                       ||
||  InstanceId              |  i-0505d348163787cc3                         ||
||  InstanceType            |  t2.micro                                    ||
||  KeyName                 |  KEY-I346-SUB-DEVOPSTEAM09                   ||
||  LaunchTime              |  2025-03-18T14:41:16+00:00                   ||
||  PrivateDnsName          |  ip-10-0-9-10.eu-central-1.compute.internal  ||
||  PrivateIpAddress        |  10.0.9.10                                   ||
||  PublicDnsName           |                                              ||
||  RootDeviceName          |  /dev/xvda                                   ||
||  RootDeviceType          |  ebs                                         ||
||  SourceDestCheck         |  True                                        ||
||  StateTransitionReason   |                                              ||
||  SubnetId                |  subnet-0ab631f69a314e92d                    ||
||  VirtualizationType      |  hvm                                         ||
||  VpcId                   |  vpc-0a22d771f16ae549d                       ||
|+--------------------------+----------------------------------------------+|
|||                   CapacityReservationSpecification                    |||
||+---------------------------------------------------------+-------------+||
|||  CapacityReservationPreference                          |  open       |||
||+---------------------------------------------------------+-------------+||
|||                              CpuOptions                               |||
||+-------------------------------------------------------+---------------+||
|||  CoreCount                                            |  1            |||
|||  ThreadsPerCore                                       |  1            |||
||+-------------------------------------------------------+---------------+||
|||                            EnclaveOptions                             |||
||+--------------------------------------+--------------------------------+||
|||  Enabled                             |  False                         |||
||+--------------------------------------+--------------------------------+||
|||                          MaintenanceOptions                           |||
||+-----------------------------------------+-----------------------------+||
|||  AutoRecovery                           |  default                    |||
||+-----------------------------------------+-----------------------------+||
|||                            MetadataOptions                            |||
||+-------------------------------------------------+---------------------+||
|||  HttpEndpoint                                   |  enabled            |||
|||  HttpProtocolIpv6                               |  disabled           |||
|||  HttpPutResponseHopLimit                        |  1                  |||
|||  HttpTokens                                     |  optional           |||
|||  InstanceMetadataTags                           |  disabled           |||
|||  State                                          |  pending            |||
||+-------------------------------------------------+---------------------+||
|||                              Monitoring                               |||
||+-----------------------------+-----------------------------------------+||
|||  State                      |  disabled                               |||
||+-----------------------------+-----------------------------------------+||
|||                           NetworkInterfaces                           |||
||+------------------------------+----------------------------------------+||
|||  Description                 |                                        |||
|||  InterfaceType               |  interface                             |||
|||  MacAddress                  |  0a:d8:a3:05:ff:cd                     |||
|||  NetworkInterfaceId          |  eni-03711aa89ee9fce92                 |||
|||  OwnerId                     |  709024702237                          |||
|||  PrivateIpAddress            |  10.0.9.10                             |||
|||  SourceDestCheck             |  True                                  |||
|||  Status                      |  in-use                                |||
|||  SubnetId                    |  subnet-0ab631f69a314e92d              |||
|||  VpcId                       |  vpc-0a22d771f16ae549d                 |||
||+------------------------------+----------------------------------------+||
||||                             Attachment                              ||||
|||+----------------------------+----------------------------------------+|||
||||  AttachTime                |  2025-03-18T14:41:16+00:00             ||||
||||  AttachmentId              |  eni-attach-0f022a43986a2c207          ||||
||||  DeleteOnTermination       |  True                                  ||||
||||  DeviceIndex               |  0                                     ||||
||||  NetworkCardIndex          |  0                                     ||||
||||  Status                    |  attaching                             ||||
|||+----------------------------+----------------------------------------+|||
||||                               Groups                                ||||
|||+--------------------+------------------------------------------------+|||
||||  GroupId           |  sg-06c9cb6e3625401fa                          ||||
||||  GroupName         |  secugrp-i346-devopsteam09                     ||||
|||+--------------------+------------------------------------------------+|||
||||                              Operator                               ||||
|||+-------------------------------------+-------------------------------+|||
||||  Managed                            |  False                        ||||
|||+-------------------------------------+-------------------------------+|||
||||                         PrivateIpAddresses                          ||||
|||+-----------------------------------------+---------------------------+|||
||||  Primary                                |  True                     ||||
||||  PrivateIpAddress                       |  10.0.9.10                ||||
|||+-----------------------------------------+---------------------------+|||
|||                               Operator                                |||
||+--------------------------------------+--------------------------------+||
|||  Managed                             |  False                         |||
||+--------------------------------------+--------------------------------+||
|||                               Placement                               |||
||+-------------------------------------+---------------------------------+||
|||  AvailabilityZone                   |  eu-central-1c                  |||
|||  GroupName                          |                                 |||
|||  Tenancy                            |  default                        |||
||+-------------------------------------+---------------------------------+||
|||                         PrivateDnsNameOptions                         |||
||+------------------------------------------------------+----------------+||
|||  EnableResourceNameDnsAAAARecord                     |  False         |||
|||  EnableResourceNameDnsARecord                        |  False         |||
|||  HostnameType                                        |  ip-name       |||
||+------------------------------------------------------+----------------+||
|||                            SecurityGroups                             |||
||+---------------------+-------------------------------------------------+||
|||  GroupId            |  sg-06c9cb6e3625401fa                           |||
|||  GroupName          |  secugrp-i346-devopsteam09                      |||
||+---------------------+-------------------------------------------------+||
|||                                 State                                 |||
||+-----------------------------+-----------------------------------------+||
|||  Code                       |  0                                      |||
|||  Name                       |  pending                                |||
||+-----------------------------+-----------------------------------------+||
|||                              StateReason                              |||
||+----------------------------------+------------------------------------+||
|||  Code                            |  pending                           |||
|||  Message                         |  pending                           |||
||+----------------------------------+------------------------------------+||

```
### CONNECT SSH ACCESS

```bash
$ ssh devopsteam09@52.59.181.213 ^
   -i KEY-I346-DMZ-DEVOPSTEAM09.pem
```

```
[OUTPUT]
The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Wed Mar 19 11:34:33 2025 from 193.5.240.9
devopsteam09@ip-10-0-0-10:~$ 
```


### POUR SORTIR
```
devopsteam09@ip-10-0-0-10:~$ exit
```
```
[OUTPUT]
logout
Connection to 52.59.181.213 closed.
```
### TUNNEL TO DMZ
```bash
$ ssh devopsteam09@52.59.181.213 ^
   -i KEY-I346-DMZ-DEVOPSTEAM09.pem ^
   -L 23:10.0.9.10:22 ^
   -L 3399:10.0.9.11:3389
```

```
[OUTPUT]
Linux ip-10-0-0-10 6.1.0-31-cloud-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.128-1 (2025-02-07) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Wed Mar 19 11:36:39 2025 from 193.5.240.9
devopsteam09@ip-10-0-0-10:~$
```

### START INSTANCE 
```
$ aws ec2 start-instances ^
--instance-ids i-0505d348163787cc3 ^
--region eu-central-1 ^
--profile devopsteam09
```
```
[OUPUT]
{
    "StartingInstances": [
        {
            "InstanceId": "i-0505d348163787cc3",
            "CurrentState": {
                "Code": 0,
                "Name": "pending"
            },
            "PreviousState": {
                "Code": 80,
                "Name": "stopped"
            }
        }
    ]
}

```
### STOP INSTANCE 
```
$ aws ec2 stop-instances ^
--instance-ids i-0505d348163787cc3 ^
--region eu-central-1 ^
--profile devopsteam09
```
```
[OUPUT]
{
    "StoppingInstances": [
        {
            "InstanceId": "i-0505d348163787cc3",
            "CurrentState": {
                "Code": 64,
                "Name": "stopping"
            },
            "PreviousState": {
                "Code": 16,
                "Name": "running"
            }
        }
    ]
}

```
### TEST EC2 LIN ACCESS -INBOUND 
```
$ ssh admin@localhost ^
    -p 23
    -i KEY.pem
```
```
[OUPUT]
The authenticity of host '[localhost]:23 ([::1]:23)' can't be established.
ED25519 key fingerprint is SHA256:TdbDIJ96QG9RvccOUkTaNwLRnIcqIx00aK/vQeCH+fI.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[localhost]:23' (ED25519) to the list of known hosts.
Linux ip-10-0-9-10 6.1.0-32-cloud-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.129-1 (2025-03-06) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Fri Mar 21 14:56:05 2025 from 10.0.0.10
admin@ip-10-0-9-10:~$
```

### TEST EC2 WIN ACCESS -INBOUND 
```
Ouvrir bureau à distance
```
```
[Paramètres à rentrer]
![image](https://github.com/user-attachments/assets/caeb9069-3ebd-41c6-b0a9-1af07a485597)
```

```
Obtenir le mot de passe :
$ aws ec2 get-password-data ^
--instance-id i-0a168859ac1de6290 ^
--priv-launch-key KEY.pem ^
--region eu-central-1 ^
--profile devopsteam09
```
```
[POUTPUT]
{
    "InstanceId": "i-0a168859ac1de6290",
    "Timestamp": "2025-03-18T14:51:49+00:00",
    "PasswordData": "g=.A1zwv(Bi6hmCrzLml*&tiThu$0Bi&"
}
```

### TEST EC2 LIN - ACCESS - OUTBOUND 
```
$ ping 8.8.8.8
```
```
[OUPUT]
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=57 time=1.66 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=57 time=1.81 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=57 time=2.63 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=57 time=2.10 ms
^C
--- 8.8.8.8 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3005ms
rtt min/avg/max/mdev = 1.659/2.051/2.634/0.372 ms
```

### TEST EC2 WIN - ACCESS - OUTBOUND 
```
$ ping 8.8.8.8
```
```
[OUPUT]
Pinging 8.8.8.8 with 32 bytes of data:
Reply from 8.8.8.8: bytes=32 time=1ms TTL=57
Reply from 8.8.8.8: bytes=32 time=1ms TTL=57
Reply from 8.8.8.8: bytes=32 time=1ms TTL=57
Reply from 8.8.8.8: bytes=32 time=1ms TTL=57

Ping statistics for 8.8.8.8:
   Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
   Minimum = 1ms, Maximum = 1ms, Average = 1ms
```


### CLEAN SUBNET

* [AWS Official Doc -delete subnet](https://awscli.amazonaws.com/v2/documentation/api/2.7.25/reference/ec2/delete-subnet.html)

```
$ aws ec2 delete-subnet ^
--subnet-id subnet-0ab631f69a314e92d ^
--profile devopsteam09 ^
--region eu-central-1
```
```
[OUPUT]

```

### CLEAN KEY

* [AWS Official Doc -delete key](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/ec2/delete-key-pair.html)

```
$ aws ec2 delete-key-pair ^
--key-name KEY-I346-SUB-DEVOPSTEAM09 ^
--profile devopsteam09 ^
--region eu-central-1
```
```
[OUPUT]

```

### CLEAN INSTANCES (Exemple avec la linux)

* [AWS Official Doc -delete instance](https://awscli.amazonaws.com/v2/documentation/api/2.0.33/reference/ec2/terminate-instances.html)

```
$ aws ec2 terminate-instances ^
--instance-ids i-0505d348163787cc3 ^
--profile devopsteam09 ^
--region eu-central-1
```
```
[OUPUT]

```

### CLEAN SECURITY GROUP 

* [AWS Official Doc -delete securiity group](https://awscli.amazonaws.com/v2/documentation/api/2.3.2/reference/ec2/delete-security-group.html)

```
$ aws ec2 delete-security-group ^
--group-id sg-06c9cb6e3625401fa ^
--profile devopsteam09 ^
--region eu-central-1
```
```
[OUPUT]

```
