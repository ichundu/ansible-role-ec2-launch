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
| `ec2_access_key` | N/A | AWS access key. If not set then the value of the AWS_ACCESS_KEY_ID, AWS_ACCESS_KEY or EC2_ACCESS_KEY environment variable is used |
| `ec2_secret_key` | N/A | AWS secret key. If not set then the value of the AWS_SECRET_ACCESS_KEY, AWS_SECRET_KEY, or EC2_SECRET_KEY environment variable is used. |
| `ec2_launch_id` | N/A | Instance launch ID, used for idempotency when specifying an existing running instance. |
| `ec2_launch_count` | N/A | Number of instances to launch. |
| `ec2_launch_count_tag` | N/A | Used with 'exact_count' to determine how many nodes based on a specific tag criteria should be running. |
| `ec2_launch_exact_count` | N/A | An integer value which indicates how many instances that match the 'count_tag' parameter should be running. Instances are either created or terminated based on this value. |
| `ec2_launch_image` | N/A | Instance image code, like `ami-xxxxxxxx`. |
| `ec2_launch_groups` | N/A | Comma separated list of security groups to assign to the instance. |
| `ec2_launch_tag_name` | N/A | Name tag of the instance. |
| `ec2_launch_tag_class` | N/A | Class tag of the instance. |
| `ec2_launch_instance_type` | N/A | EC2 [instance types](https://aws.amazon.com/ec2/instance-types/). |
| `ec2_launch_key_name` | N/A | Name of existing key pair to assign to the instance. |
| `ec2_launch_region` | N/A | AWS region where the instance will be launched. |
| `ec2_launch_state` | N/A | Create or terminate instances. |


Dependencies
------------

None

Example Playbook
----------------

When calling the role you should specify variables inside the playbook, inside a vars file in `group_vars`/`host_vars` or via the interactive 'vars_prompt'.

```yaml
    - hosts: localhost
      roles:
         - role: ichundu.ec2-launch
```


Author Information
------------------

https://github.com/ichundu
