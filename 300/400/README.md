# 400 - Configure the Server on Hetzner

 After having created a server (here: ```agility-game-1```), connect to it with SSH as shown below, using its public IP address (here: ```116.203.36.60```) as **root**. Don't forget to append the command with ``` -i ~/.ssh/id_ed25519_hetzner``` which is required when using a non-default name for your key pair.

![Screenshot 2024-05-14 at 16 54 52](https://github.com/agility-game/dokploy/assets/1499433/225a3eb6-90ec-4905-a38b-c6ecaef5b42a)

Now visit the landing page of [Dokploy](dokploy.com) and copy the line of text presented there:


![install-dokploy-001](https://github.com/agility-game/dokploy/assets/1499433/43f9a1b6-6a99-4f97-8a3e-36faeb39910a)

```
curl -sSL https://dokploy.com/install.sh | sh
```

Paste the above code in your SSH terminal and run it. It will install Dokploy on your new server.

![Screenshot 2024-05-16 at 16 19 46](https://github.com/agility-game/dokploy/assets/1499433/7e7b0642-ae68-4d49-994f-49a9cb2e7a93)

Now follow the advice from the prompt and in a browser go to the start page of Deploy here at http://116.203.36.60:3000

**NOTE**: The above URL is http, not https!

This will bring you to the registration page of Dokploy to setup the server.

![register-dokploy-001](https://github.com/agility-game/dokploy/assets/1499433/326f41b7-d51f-496a-b8bd-4800802203bb)

Fill in the above form with your details as the adminstrator of this Dokploy server and click **Register**

![register-dokploy-002](https://github.com/agility-game/dokploy/assets/1499433/4eceda92-ea2f-4b38-9079-8fed7b4aefd0)



MORE ...
