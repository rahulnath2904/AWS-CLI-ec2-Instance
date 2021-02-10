# AWS-CLI-ec2-Instance
-> aws configure
    AWS Access Key ID [****************46XW]:
    AWS Secret Access Key [****************6YDK]:
    Default region name [ap-south-1]:
    Default output format [None]:
->
-> aws ec2 create-key-pair --key-name awscli
    {
        "KeyFingerprint": "59:4b:0a:a1:49:2e:88:a5:de:8f:e5:ee:c8:5f:7e:fe:7e:76:c2:39",
        "KeyMaterial": "-----BEGIN RSA PRIVATE KEY-----\nMIIEowIBAAKCAQEAufR7bOnXbXwagYQPpcCdJpgCfz5q9ADwmIT6fYrsdxTS2M1Q\n/rX8KL7gl53U9IPTFrctqqEu3WJhm+56y09967Ipq/BtDRnDi3I4J8koac1THX/z\nxSlMjh/jOqE/VlybKmbEEWKTOfZqSuVe32Kt5/MgsVxtaoIxzexCN9zAr8cvsyhp\nfTSZRMOuf4cOL8KsAR1osyTdHrNvGfsmgsaX00HeemO6kn4HYA1bOtaBYpj6RN8b\nmVUhcvNdPmV7VvHEDzuqohhUZBVqp8UFc18re6YHsdFVV0SZuZ3FjpSynrusGx7g\nMqk3FhtcQc1FjTs9llI5csH8KgaKzIVcGTvrjQIDAQABAoIBAQCJvS4vXobT8jkv\n9kIg5KuDCtXOqs1OL+QHFXj1xRGioyoKrQpxoRtGkxyJMb+r3nldOhH5carlERp8\nBgmuzxLWowF6+nvMWGkfwVsXHUlyFUSbdUt7nzu1iqklpIrlzXKh1b0lo36qUHwr\nPfsoPE/Un6J3vZ7OZeG+RmJGPp37lKscLka2ZK/QFqgy7q2jFuSyP2hBWhv9aCs6\n6sT4Lxv5JNDQAbvglPDAPwoe44FwDtIDTRROZfiF7H2GX2k4w2ZrujVNrccms4Yb\nQ9iMUYV2+6lWVOd9D7pizmcp2CS68PCtz4oPSjqER6jdAhv4AB9feVwYeDgCumVx\n1qfzdkGBAoGBAOn2RDt+EdYz5rm0nyiCe0wNGRLRqw1IxCnIiLQ23CRydLfuE74q\nY5A33MqFj6p7KNogAM2abcJ0pY3U9sjfodevYtwqBNDhE2ATz05S+lx0VoehknJo\nHHILsI7rY8rwQuEBL+uxA5U9odeOzHX/tnKE44Vitk4LzuX3Bd7Do+LLAoGBAMt4\nlK5k1ZvOK84Y6xm6avDdYdqvrk7zyD421i5F506L1FrAh0ZPCgFBQDRpGMSTUA0l\n4ryNszCF9LCZX+7r2s/xpasoaHS43l3dULzym7qQgG/v2qhzVnBQjyowx4aMGbk4\nTtmuQoWWT8RLf8A6LL/DgaCP2qeQMrT4SCvF0ygHAoGAR7LErkawSKiXKIoFzHBQ\nQLoy2OWQOf32v6dI3ZGCXVkGE+fN/RUYdfXon9fWczRTDKWKGXgd8t20boa5Kk3+\nVw7UiQwHdcvEGEl52lLrjrHIYsBNFOp67ShP7zyL1IFUvYeTm/MfWfkNQ/XrCq5W\nxzmaUCI0JC7SNP9CuUXTT4kCgYB9K8/jvRp/wATIxCGVcU4qoTZ6rwr/fQ9Z3qhC\nTTSv6GuZ7MkLYsJX5UlXNLRM8gcUH5NtxYpPtojCP4h51dSFijYNpk0kSTpa6jSq\nGGHfEthAhICykknBzH1WSi3kwrlsbYxsc7xuq/qkWoHbwq4WxnIvUXAFFztqgzb6\n3rc47wKBgHdLdWhR5eEPsOLpDPULmOxeNSx5vv0CeInS5VSpERNrAIBLhNRGdyjk\n6fVdMU/sP4wH4zQsc1AWFgtKqj9JfDUe3BJAfo1uXwbJkgjc5+NrRe3d65/a+wbU\nb2apZUNyRglq3KPKWlo/n5xyqJ0UKoMUo70PnqZMlJ17uWYE9ZRy\n-----END RSA PRIVATE KEY-----",
        "KeyName": "awscli",
        "KeyPairId": "key-0f06caabae5494805"
    }
->
-> aws ec2 create-security-group --group-name awsCLI --description AWS_using_CLI
    {
        "GroupId": "sg-0f91777a674ab547b"
    }
->
-> aws ec2 run-instances --image-id ami-052c08d70def0ac62 --instance-type t2.micro --count 1 --subnet-id subnet-e6180c8e --security-group-ids sg-0f91777a674ab547b --key-name awscli
    {
        "Groups": [],
        "Instances": [
            {
                "AmiLaunchIndex": 0,
                "ImageId": "ami-052c08d70def0ac62",
                "InstanceId": "i-0f43e45ca21071aa4",
                "InstanceType": "t2.micro",
                "KeyName": "awscli",
                "LaunchTime": "2021-02-10T10:46:20+00:00",
                "Monitoring": {
                    "State": "disabled"
                },
                "Placement": {
                    "AvailabilityZone": "ap-south-1a",
                    "GroupName": "",
                    "Tenancy": "default"
                },
                "PrivateDnsName": "ip-172-31-41-239.ap-south-1.compute.internal",
                "PrivateIpAddress": "172.31.41.239",
                "ProductCodes": [],
                "PublicDnsName": "",
                "State": {
                    "Code": 0,
                    "Name": "pending"
                },
                "StateTransitionReason": "",
                "SubnetId": "subnet-e6180c8e",
                "VpcId": "vpc-91c12efa",
                "Architecture": "x86_64",
                "BlockDeviceMappings": [],
                "ClientToken": "34e9a27a-f81b-4bb3-bd65-8fbad1ef542c",
                "EbsOptimized": false,
                "EnaSupport": true,
                "Hypervisor": "xen",
                "NetworkInterfaces": [
                    {
                        "Attachment": {
                            "AttachTime": "2021-02-10T10:46:20+00:00",
                            "AttachmentId": "eni-attach-062c022e780bd6e81",
                            "DeleteOnTermination": true,
                            "DeviceIndex": 0,
                            "Status": "attaching"
                        },
                        "Description": "",
                        "Groups": [
                            {
                                "GroupName": "awsCLI",
                                "GroupId": "sg-0f91777a674ab547b"
                            }
                        ],
                        "Ipv6Addresses": [],
                        "MacAddress": "02:0a:0a:55:5d:98",
                        "NetworkInterfaceId": "eni-02bfad21161f23a7e",
                        "OwnerId": "069199410929",
                        "PrivateDnsName": "ip-172-31-41-239.ap-south-1.compute.internal",
                        "PrivateIpAddress": "172.31.41.239",
                        "PrivateIpAddresses": [
                            {
                                "Primary": true,
                                "PrivateDnsName": "ip-172-31-41-239.ap-south-1.compute.internal",
                                "PrivateIpAddress": "172.31.41.239"
                            }
                        ],
                        "SourceDestCheck": true,
                        "Status": "in-use",
                        "SubnetId": "subnet-e6180c8e",
                        "VpcId": "vpc-91c12efa",
                        "InterfaceType": "interface"
                    }
                ],
                "RootDeviceName": "/dev/sda1",
                "RootDeviceType": "ebs",
                "SecurityGroups": [
                    {
                        "GroupName": "awsCLI",
                        "GroupId": "sg-0f91777a674ab547b"
                    }
                ],
                "SourceDestCheck": true,
                "StateReason": {
                    "Code": "pending",
                    "Message": "pending"
                },
                "VirtualizationType": "hvm",
                "CpuOptions": {
                    "CoreCount": 1,
                    "ThreadsPerCore": 1
                },
                "CapacityReservationSpecification": {
                    "CapacityReservationPreference": "open"
                },
                "MetadataOptions": {
                    "State": "pending",
                    "HttpTokens": "optional",
                    "HttpPutResponseHopLimit": 1,
                    "HttpEndpoint": "enabled"
                },
                "EnclaveOptions": {
                    "Enabled": false
                }
            }
        ],
        "OwnerId": "069199410929",
        "ReservationId": "r-0456b27884cced941"
    }
->
-> aws ec2 create-volume --volume-type gp2 --size 1 --availability-zone ap-south-1a
    {
        "AvailabilityZone": "ap-south-1a",
        "CreateTime": "2021-02-10T10:56:19+00:00",
        "Encrypted": false,
        "Size": 1,
        "SnapshotId": "",
        "State": "creating",
        "VolumeId": "vol-050148e313b8fb5af",
        "Iops": 100,
        "Tags": [],
        "VolumeType": "gp2",
        "MultiAttachEnabled": false
    }
->
-> aws ec2 attach-volume --instance-id i-0f43e45ca21071aa4  --volume-id vol-050148e313b8fb5af --device /dev/sda2
    {
        "AttachTime": "2021-02-10T11:09:34.964000+00:00",
        "Device": "/dev/sda2",
        "InstanceId": "i-0f43e45ca21071aa4",
        "State": "attaching",
        "VolumeId": "vol-050148e313b8fb5af"
    }
