aws-vpc
=============

Manages private networks at Amazon Web Services

Requirements
------------
- AWS account and credentials



## Role Variables


##### List of Variables

    ---
    aws_secret_key: required
    aws_access_key: required
    vpc_cidr_block: optional
    vpc_region: optional
    vpc_resource_tags: optional
    vpc_subnets: optional

##### Example of Variables file
    ---
    aws_secret_key: heyHo
    aws_access_key: letsGo

    vpc_list:
      - vpc_name: Kubernetes VPC
        vpc_cidr_block: '10.1.0.0/16'
        vpc_region: 'ap-southeast-2'
        vpc_state: present
        vpc_resource_tags:
          Name: Kubernetes VPC
          Organisation: Starvisitor
          Environment: Development
          Tier: Infrastructure
        vpc_subnets:
          - cidr: "10.1.0.0/16"
            az: "ap-southeast-2b"
            resource_tags:
              Name: Kubernetes Subnet
              Organisation: Starvisitor
              Environment: Development
              Tier: Infrastructure

      - vpc_name: Sandbox VPC
        vpc_cidr_block: '10.2.0.0/16'
        vpc_region: 'ap-southeast-2'
        vpc_state: present
        vpc_resource_tags:
          Name: Sandbox VPC
          Organisation: Starvisitor
          Environment: Development
          Tier: Infrastructure
        vpc_subnets:
          - cidr: "10.2.1.0/24"
            az: "ap-southeast-2b"
            resource_tags:
              Name: Development Subnet
              Organisation: Starvisitor
              Environment: Test
              Tier: Infrastructure
          - cidr: "10.2.2.0/24"
            az: "ap-southeast-2b"
            resource_tags:
              Name: Sandbox Subneta
              Organisation: Starvisitor
              Environment: Test
              Tier: Infrastructure




Example Playbook
----------------

##### Simple

    ---
    - hosts: local
      connection: local
      sudo: no
      gather_facts: yes

     roles:
      - marcelocorreia.aws-vpc

     vars_files:
      - /path/vars.yml


License
-------

GPLv2

Author Information
------------------
Some useful stuff at:
  - [https://github.com/marcelocorreia](https://github.com/marcelocorreia)
  - [https://galaxy.ansible.com/list#/users/15516](https://galaxy.ansible.com/list#/users/15516)
  - [https://hub.docker.com/u/marcelocorreia/](https://hub.docker.com/u/marcelocorreia/)
  - Any issues, pull-request are welcome
# aws-vpc
