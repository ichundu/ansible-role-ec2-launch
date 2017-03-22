Role Name: ec2-launch
=====================

This role launches Amazon EC2 instances

Requirements
------------

- python >= 2.6
- boto

Role Variables
--------------

Almost every entry in ec2 module is defined via a variable to make the role as broad as possible. `defaults/main.yml` contains these variables, which are undefined and commented out. It is up to the playbook runner to decide what variables to include.

|	Variable name	|	Default value	|	Description	|
|-------------------|-------------------|---------------|
| `ec2_launch_id` | `[]` | Instance launch ID, used for idempotency when specifying an existing running instance |
| `ec2_launch_count` | `[]` | Number of instances to launch |
| `ec2_launch_count_tag` | `[]` | Used with 'exact_count' to determine how many nodes based on a specific tag criteria should be running |
| `ec2_launch_exact_count` | `[]` | An integer value which indicates how many instances that match the 'count_tag' parameter should be running. Instances are either created or terminated based on this value |
| `ec2_launch_image` | `[]` | Instance image code, like `ami-xxxxxxxx` |
| `ec2_launch_groups` | `[]` | Comma separated list of security groups to assign to the instance |
| `ec2_launch_name_tag` | `[]` | Name tag of the instance |
| `ec2_launch_class_tag` | `[]` | Class tag of the instance |
| `ec2_launch_instance_type` | `[]` | EC2 [instance types](https://aws.amazon.com/ec2/instance-types/) |
| `ec2_launch_key_name` | `[]` | Name of existing key pair to assign to the instance |
| `ec2_launch_region` | `[]` | AWS region where the instance will be launched |
| `ec2_launch_state` | `[]` | Create or terminate instances |


Dependencies
------------

None

Example Playbook
----------------

When calling the role you should specify variables inside the playbook, inside a vars file in `group_vars`/`host_vars` or via the interactive 'vars_prompt'.

    - hosts: localhost
      roles:
         - role: ichundu.ec2-launch


Author Information
------------------

https://github.com/ichundu
