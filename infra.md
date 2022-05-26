### Device:Asus laptop

<details>
  <summary>Hardware:</summary>

#### OS: `Ubuntu20.0.4`
#### Static ip add: `185.219.177.93`

</details>

### Packages:


<details>
  <summary>Opennebula Minione:</summary>

### Perequisite

  Opennebula repo and key:
  
  ```
  apt-get update
  apt-get -y install gnupg wget apt-transport-https
  wget -q -O- https://downloads.opennebula.io/repo/repo.key | apt-key add -
  echo "deb https://downloads.opennebula.io/repo/6.2/Ubuntu/20.04 stable opennebula" > /etc/apt/sources.list.d/opennebula.list
  apt-get update
  ```


  Installation:

  ```bash
  git clone https://github.com/OpenNebula/minione.git
  sudo bash minione --marketapp-name debian 11 --force
  ```

change minione MARKET_APP_NAME

```
vim minione
+ MARKET_APP_NAME='Debian 11'
```


Resualt:
```
### Installation
Updating APT cache  OK
Creating bridge interface minionebr  OK
Bring bridge interfaces up  OK
Configuring NAT using iptables  OK
Saving iptables changes  OK
Installing DNSMasq  OK
Starting DNSMasq  OK
Configuring repositories  OK
Updating APT cache  OK
Installing OpenNebula packages  OK
Installing opennebula-provision package   OK
Installing OpenNebula kvm node packages  OK
Updating AppArmor  OK
Disable default libvirtd networking  OK
Restart libvirtd  OK

### Configuration
Generating ssh keypair in /root/.ssh-oneprovision/id_rsa  OK
Add oneadmin to docker group  OK
Update network hooks  OK
Switching OneGate endpoint in oned.conf  OK
Switching OneGate endpoint in onegate-server.conf  OK
Switching keep_empty_bridge on in OpenNebulaNetwork.conf  OK
Switching scheduler interval in oned.conf  OK
Setting initial password for current user and oneadmin  OK
Changing WebUI to listen on port 80  OK
Switching FireEdge public endpoint  OK
Starting OpenNebula services  OK
Enabling OpenNebula services  OK
Add ssh key to oneadmin user  OK
Update ssh configs to allow VM addresses reusing  OK
Ensure own hostname is resolvable  OK
Checking OpenNebula is working  OK
Disabling ssh from virtual network  OK
Adding localhost ssh key to known_hosts  OK
Testing ssh connection to localhost  OK
Updating datastores template  OK
Creating KVM host  OK
Restarting OpenNebula  OK
Creating virtual network  OK
Exporting [Alpine Linux 3.14] from Marketplace to local datastore  OK
Waiting until the image is ready  OK
Updating VM template  OK

### Report
OpenNebula 6.4 was installed
Sunstone is running on:
  http://192.168.1.106/
FireEdge is running on:
  http://192.168.1.106:2616/
Use following to login:
  user: oneadmin
  password: G4jZgF7jwE


```


uninstall:

```
sudo bash minione --purge --force
```


vnet
172.16.100.1
  
</details>
