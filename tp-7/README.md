# TP7 : 

## I setup des machines routeur et John 

## II SSH 

### B. Manips ! 

```
PS C:\Users\Makhov> ssh alexandre@10.7.1.11
The authenticity of host '10.7.1.11 (10.7.1.11)' can't be established.
ED25519 key fingerprint is SHA256:Q9XDaTUbyjz0otsCw0GMRa5FJoebm5UT+jfDyXVGVmM.
This host key is known by the following other names/addresses:
    C:\Users\Makhov/.ssh/known_hosts:10: 10.3.1.12
    C:\Users\Makhov/.ssh/known_hosts:13: 10.3.1.11
    C:\Users\Makhov/.ssh/known_hosts:17: 10.5.1.13
    C:\Users\Makhov/.ssh/known_hosts:18: 10.5.1.11
    C:\Users\Makhov/.ssh/known_hosts:19: 10.5.1.254
    C:\Users\Makhov/.ssh/known_hosts:20: 10.6.1.11
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '10.7.1.11' (ED25519) to the list of known hosts.
alexandre@10.7.1.11's password:
Last login: Thu Nov 23 14:45:36 2023
```
ensuite une commande pour avoir seulement la fingerprint :
```
sudo ssh-keygen -l -f /etc/ssh/ssh_host_ed25519_key
```
et la fingerprint :
```
256 SHA256:Q9XDaTUbyjz0otsCw0GMRa5FJoebm5UT+jfDyXVGVmM /etc/ssh/ssh_host_ed25519_key.pub (ED25519)
```

### 2. conf serveur ssh 

pour vérifier que le port SSH tourne sur le port 22/tcp 
on utlise la commande 

```
sudo ss -alntp
```

ce qui donne comme resultat

```
State  | Recv-Q | Send-Q | Local Address:Port | Peer Address:Port | Process
LISTEN |    0   |   128  | 0.0.0.0:22         |          0.0.0.0:*| users:(("sshd",pid=695,fd=3))
LISTEN |    0   |   128  |    [::]:22         |             [::]:*| users:(("sshd",pid=695,fd=4))
```

