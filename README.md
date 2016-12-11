Role Name
=========

Launch a new ec2 instance

Requirements
------------

python >= 2.6
boto

Role Variables
--------------

Almost every entry in ec2 module is defined via a variable to make the role as broad as possible. defaults/main.yml contains the variable:

	ec2_launch_image_type: "t2.micro"

With this type of instance you can launch free tier eligible instances.

Dependencies
------------

N/A

Example Playbook
----------------

When calling the role you should specify variables in the playbook or a different vars file or via the interactive 'vars_prompt'

    - hosts: localhost
      roles:
         - role: ec2-launch
	   ec2_launch_count: 1
	   ec2_launch_ami_id: ami-e4c63e8b
	   ....


Author Information
------------------

https://github.com/ichundu
