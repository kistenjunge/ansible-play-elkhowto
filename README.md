ansible-play-elkhowto
=====================

Ansible Play based on the HowTo available at [Digitalocean](https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-4-on-ubuntu-14-04) by [Mitchell Anicas] (https://twitter.com/thisismitch).

The Vagrantfile requires a debian78 box which can be added like this:

```bash
$ vagrant box add deb/wheezy-amd64
```

After fetching the image simply start up the machines and start the provisioning

```bash
$ vagrant up
$ ansible-playbook -i staging playbook.yml -v
```

You should then be able to access your fresh Kibana dashboard on the [ELK](http://192.168.60.6/) machine. 
