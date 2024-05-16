# 400 - Configure the Server on Hetzner

 After having created a server (here: ```agility-game-1```), connect to it with SSH as shown below, using its public IP address (here: ```116.203.36.60```) as **root**. Don't forget to append the command with ``` -i ~/.ssh/id_ed25519_hetzner``` which is required when using a non-default name for your key pair.

![Screenshot 2024-05-14 at 16 54 52](https://github.com/agility-game/dokploy/assets/1499433/225a3eb6-90ec-4905-a38b-c6ecaef5b42a)

Now visit the landing page of [Dokploy](dokploy.com) and copy the line of text presented there:




```
curl -sSL https://dokploy.com/install.sh | sh
```

Paste the above code in your SSH terminal and run it. It will install Dokploy on your new server.



MORE ...
