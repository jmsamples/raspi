# raspi
provisioning a raspi

![](https://raw.github.com/motdotla/ansible-pi/master/ansible-pi.jpg)



Run on the raspi
```bash
ssh -R myalias:22:localhost:22 serveo.net
```

Connect to raspi with VNC a forward
```bash
ssh -N -L15900:localhost:5900 -J serveo.net pi@myalias
```

SSH into raspi
```bash
ssh -J serveo.net pi@myalias
```

Copy private key to raspi
```bash
cat ~/.ssh/raspi_id_rsa.pub | ssh -J serveo.net pi@myalias "mkdir ~/.ssh; cat >> ~/.ssh/authorized_keys"
```

SSH into raspi using private key (passwordless)
```bash
ssh -i ~/.ssh/raspi_id_rsa -J serveo.net pi@myalias
```



Run ansible
```
ansible-playbook playbook.yml -i hosts
```

Retrieve facts
```
ansible all -m setup -i hosts > facts.json
```
