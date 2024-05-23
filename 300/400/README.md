# 400 - Configure the Server on Hetzner

 After having created a server (here: ```agility-game-1```), connect to it with SSH as shown below, using its public IP address (here: ```116.203.36.60```) as **root**. Don't forget to append the command with ``` -i ~/.ssh/id_ed25519_hetzner``` which is required when using a non-default name for your key pair.

![Screenshot 2024-05-14 at 16 54 52](https://github.com/agility-game/dokploy/assets/1499433/225a3eb6-90ec-4905-a38b-c6ecaef5b42a)

**NOTE**: You may run into the below error:

```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the ED25519 key sent by the remote host is
SHA256:Pea9K3FjgtrY9XAshx3KUvzpZJ/n21YB94a/7N+CkSA.
Please contact your system administrator.
Add correct host key in /Users/willemvanheemstra/.ssh/known_hosts to get rid of this message.
Offending ECDSA key in /Users/willemvanheemstra/.ssh/known_hosts:9
Host key for 116.203.36.60 has changed and you have requested strict checking.
Host key verification failed.
```

In that case, visit [Updating host keys](https://help.dreamhost.com/hc/en-us/articles/217239087-Updating-host-keys). It will recommend to remove the old key from your know hosts file on your client (here: Mac Mini) as follows:

```
$ ssh-keygen -R 116.203.36.60
# Host 116.203.36.60 found: line 7
# Host 116.203.36.60 found: line 8
# Host 116.203.36.60 found: line 9
/Users/willemvanheemstra/.ssh/known_hosts updated.
Original contents retained as /Users/willemvanheemstra/.ssh/known_hosts.old
```

After this re-ssh into your server.

```
$ ssh root@116.203.36.60 -i ~/.ssh/id_ed25519_hetzner
```

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

In a separate browser window, browse to your domain hosting service (here: versio.nl) and setup an A record for your domain (here: agility-game.com) and for the IP address choose the public IP address (here: 116.203.36.60) of the server on Hetzner. We choose "dokploy" as the subdomain, but this can be anything else.

== IMAGE GOES HERE ==

The A record is now setup.

![Screenshot 2024-05-21 at 15 35 53](https://github.com/agility-game/dokploy/assets/1499433/87289317-52d4-4bfe-a472-dbe3f391c205)

Based on what was set as the A record, complete the form on the Dokploy Settings page as follows:

== IMAGE GOES HERE ==

And click **Save**

...

Based on "Dokploy Introduction" at https://youtu.be/mznYKPvhcfw?t=268

Copy the Domain as set in the Settings page in the previous step (here: ```dokploy.agility-game.com```). Paste it in a browser window, and wait a few seconds for LetsEncrypt to have picked up the change. Your browser should show the following page:

**TIP**: Here is how to fix a possible error, [How to Fix DNS_PROBE_FINISHED_NXDOMAIN in Chrome](https://www.youtube.com/watch?v=AgeJhUvEezo).

MORE

...

Click **+ Create Project**.

MORE ...
