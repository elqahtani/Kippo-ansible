Kippo Ansible Playbook
----------------------

This project fork from https://github.com/Erethon/Kippo-ansible 

And I add Kippo-Graph ansible role to display results from kippo. 

This is an Ansible playbook to install [Kippo](
https://github.com/desaster/kippo) on Debian hosts.

The playbook will setup a node as a database server for Kippo hosts to log
incoming attacks and will also setup multiple Kippo hosts.

Process:
* setup a database server so all kippo hosts log to that server
* create a `kippouser` account to run kippo
* download the latest Kippo version from a git repo (desaster's by default)
* configure Kippo
* change sshd port to 22422 (it's a variable, so it's easy to change)
* add an iptable rule to forward traffic from port 2222 to 22
* run kippo
* install dependecies for kippo-graph : libapache2-mod-php5 php5-mysql php5-gd php5-curl
* Add Kippo-graph https://github.com/ikoniaris/kippo-graph

This is a very basic skeleton, feel free to mess around with it. I've only
tested it with Debian Wheezy and Ubuntu 14.04, and it seems to work. Keep in mind this is a proof
of concept playbook, so some stuff could be improved (e.g. mysql security).

How to use
----------

Edit the vars `db_host` and `db_password` in `group_vars/all` to reflect your
setup and run the playbook.

Screenshots
----------
Here's how kippo-graph looks like:

![kippo-home1](https://cloud.githubusercontent.com/assets/8499688/20463622/1fd9a744-af6a-11e6-9489-2c13bcc64d4f.png)
