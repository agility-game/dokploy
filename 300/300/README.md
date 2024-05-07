# 300 - Create a server on Hetzner

Choose **+ CREATE SERVER** for our newly created project ```Agility Game```:

![Create_server-001](https://github.com/agility-game/dokploy/assets/1499433/f054c866-6bc4-493c-a772-6888be1493e7)

For the **location** of the server, choose a location nearby your office or home. Here we choose Nuremberg in Germany:

![Create_server-002](https://github.com/agility-game/dokploy/assets/1499433/d54d6891-d744-4ac3-a22a-b7e0e2fd95ee)

For the **type of operating system (os)**, choose an operating system similar to where you do your development. Here we choose Debian as on our Virtual Machine on our Mac we also use Debian:

![Create_server-003](https://github.com/agility-game/dokploy/assets/1499433/8101926e-a404-40be-be69-36913178722e)

For the **type of CPU**, choose a low-cost option. Here we use the lowest in cost option:

![Create_server-004](https://github.com/agility-game/dokploy/assets/1499433/f54dc7e5-56f7-4a16-894b-adba63aa5c28)

For the **networking**, choose both public IPv4 and IPv6 (comes at no additional cost) so our applications will be reachable from the Internet:

![Create_server-005](https://github.com/agility-game/dokploy/assets/1499433/b1bed9e1-133b-4a22-9500-bad93a860515)

For help with creating an **SSH Key**, see https://community.hetzner.com/tutorials/howto-ssh-key

**NOTE**: The RSA SHA-1 hash algorithm is rapidly being deprecated by many operating systems and SSH clients. This is due to various security vulnerabilities, with many of these technologies now outright rejecting the use of this algorithm. It appears that this has happened for the ssh client in Ubuntu 22.04. The public-private RSA key pair is no longer considered secure.

We recommend in such a case to use a more modern and secure type of key such as **ed25519**. Generate a new key pair in your Ubuntu 22.04 computer (or Mac OS) with this command:

```
$ ssh-keygen -t ed25519
```

Copy the content of the **Public Key** from your workstation (here we use our Mac Mini) from the default directory ```~/.ssh/id_ed25519.pub``` and paste it in the textfield show below:

![Create_server-006](https://github.com/agility-game/dokploy/assets/1499433/04d5a58b-dbe6-4734-a85e-1f2894600cde)

![Create_server-007](https://github.com/agility-game/dokploy/assets/1499433/3c292e55-28ca-4c7c-8fce-ef6eaef07fb7)

Click **Add SSH Key** to commit.

Skip the option to create **Volumes**, as we will not need them here.

![Create_server-008](https://github.com/agility-game/dokploy/assets/1499433/16d6dfc9-74b8-4906-bdc4-4e978f54b132)

Also, skip the option to create **Firewalls**, as we will not need them here.

![Create_server-009](https://github.com/agility-game/dokploy/assets/1499433/21655827-36f5-472a-932b-87c86e77f314)

Likewise, skip the option to create **Backups**, as we will not need them here.

![Create_server-010](https://github.com/agility-game/dokploy/assets/1499433/97b14852-30fb-431f-8cbb-e1d42550d431)

In addition, skip the option to create **Placement groups**, as we will not need them here.

![Create_server-011](https://github.com/agility-game/dokploy/assets/1499433/ce2fe445-64f1-454f-beca-e9b3280463d0)

Moreover, skip the option to create **Labels**, we will not need them here.

![Create_server-012](https://github.com/agility-game/dokploy/assets/1499433/9871b2a4-8f93-400f-ae60-45ed69bf1b3c)

Finally, skip the option to create **Cloud config**, as we will not need them here.

![Create_server-013](https://github.com/agility-game/dokploy/assets/1499433/703b00f3-92bc-4009-9b63-be54de3bd71c)

For **Naming** our server, use an appropriate name (here: ```agility-game-1```):

![Create_server-014](https://github.com/agility-game/dokploy/assets/1499433/ae605fc6-f123-42aa-aa41-9f3784115af1)

Now click on **Create & Buy now**.

![Create_server-015](https://github.com/agility-game/dokploy/assets/1499433/212fc610-f06c-47bf-ad59-257c4a43b831)

![Screenshot 2024-05-04 at 10 52 28](https://github.com/agility-game/dokploy/assets/1499433/49e6173b-d219-449b-8d24-bdee352dc330)
