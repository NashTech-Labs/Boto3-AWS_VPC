### Prerequisites

1. Create IAM User
2. Install AWS CLI and configure
3. python3
4. boto3

### Check Python Version 

```
which python

/usr/bin/python --version

OR

python --version
```

### Update the local repo , install pip & check version

```
sudo apt update

sudo apt install python-pip

pip --version
```

### Install Boto3 & check version

```
pip3 install boto3

pip show boto3
```

### To create an VPC and its dependent components we will use this methods.

* create_vpc
* create_route_table
* create_internet_gateway
* create_subnet
* associate_with_subnet


### Syntax of  create_vpc method-


```
response = client.create_vpc(
    CidrBlock='string',
    AmazonProvidedIpv6CidrBlock=True|False,
    Ipv6Pool='string',
    Ipv6CidrBlock='string',
    DryRun=True|False,
    InstanceTenancy='default'|'dedicated'|'host',
    Ipv6CidrBlockNetworkBorderGroup='string'
)
```


### Syntax of create_route_table method-

```
route_table = ec2.create_route_table(
    DryRun=True|False,
    VpcId='string'
)
```

### Syntax of create_internet_gateway method

```
response = client.create_internet_gateway(
    DryRun=True|False
)
```

### Syntax of create_subnet method

```
subnet = ec2.create_subnet(
    AvailabilityZone='string',
    AvailabilityZoneId='string',
    CidrBlock='string',
    Ipv6CidrBlock='string',
    OutpostArn='string',
    VpcId='string',
    DryRun=True|False
)
```

### Syntax of associate_with_subnet method

```
route_table_association = route_table.associate_with_subnet(
    DryRun=True|False,
    SubnetId='string',
    GatewayId='string'
)
```





### If you want to change the  values of CidrBlock for “create_vpc” and “create_subnet” you can do this by :

```
vim boto.py
```

### To create vpc run the python script as:

```
python3 boto.py
```

Go to you AWS Console and select vpc , you can see your vpc created.
