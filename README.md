# Do Not Use

This respository has been archived.  There are known security vulnerabilities.

deploy_drupal
=============

Install Drupal web framework and all necessary components.

Vagrant
======

`vagrant up`

EC2
===

`knife ec2 server create -r 'recipe[apt],recipe[drupal]' -f t1.micro -N ec2_drupal -I  ami-3d4ff254  -x ubuntu`
