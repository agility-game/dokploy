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

You will land on the projects page of Dokploy:

![Create_dokploy_project_001](https://github.com/agility-game/dokploy/assets/1499433/2e026822-ad48-42bd-8374-eb6a5001114a)

Now instead of creating a new project straight away, we click **Settings** to setup the domain.

![Setup_server_domain-001](https://github.com/agility-game/dokploy/assets/1499433/282b8439-7a58-49de-bf1c-fcc56bc998ee)

In a separate browser window, browse to your domain hosting service (here: versio.nl) and setup an A record for your domain (here: agility-game.com) and for the IP address choose the public IP address (here: 116.203.36.60) of the server on Hetzner. We choose "dokploy" as the subdomain,but this can be anything else.

![Setup_a_record_for_dokploy_server_on_versio](https://github.com/agility-game/dokploy/assets/1499433/f607a957-5f23-4e95-9d7a-28decd127d65)

The A name is now setup.

![Setup_a_record_for_dokploy_server_on_versio-002](https://github.com/agility-game/dokploy/assets/1499433/e40ccfd1-60b4-40d0-a382-fb3d47c3c326)


...

Click **+ Create Project**.

MORE ...
