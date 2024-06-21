# 800 - Create an App Project in Dokploy on Server on Hetzner

Login to the Dokploy page at https://dokploy.agility-game.com and you'll be directed to the projects page:

![create_a_new_project-001](https://github.com/agility-game/dokploy/assets/1499433/8cd7133a-8ddc-4d1c-b643-7806c63a7d97)

We are going to upload an app application, which can be found at https://github.com/agility-game/dokploy-app

Copy the below URL:

```
https://github.com/agility-game/dokploy-app.git
```

On the Projects page of Dokploy click **+ Create Project** button. Give it a name (here: ```App```) and a description (here: ```App application```) and click **Create** button.

![create_a_new_project_app-001](https://github.com/agility-game/dokploy/assets/1499433/62f5ee76-9ee7-4d19-879b-ce98b988dddf)

Once the project has been created, inside the project click **+ Create Service** and from the Actions choose **Compose** (not Application):

**NOTE**: If the option ```Compose``` is not showing, consider upgrading your Dokploy instance. This is a newer feature, not found in older versions of Dokploy. You can upgrade your Dokploy server from within Dokploy.

![create_a_new_app_service-001](https://github.com/agility-game/dokploy/assets/1499433/856e550b-8e03-4a87-812f-7cf5721e714e)

For the name of the Compose Service let's use ```Frontend``` and for the Description ```Frontend of App```, like so:

![create_a_new_app_service_compose-001](https://github.com/agility-game/dokploy/assets/1499433/63a58cc9-7a90-443f-8d91-d87f217a0a6e)

**NOTE**: The default entry for AppName uses the ```app-[Name]``` format, where the ```Name``` is capitalized. However, this causes an error. We follow the convention to keep all lowercase (here: ```app-frontend```).

For Compose Type, we choose ```Docker Compose```!

Click the **Create** button. 

*NOTE*: You may have to click outside of the dialogue to come back to the main page.

Our new Docker Compose service is listed as ```Frontend```.

![create_a_new_app_service_frontend-001](https://github.com/agility-game/dokploy/assets/1499433/47016366-5886-4ceb-aa59-123b1349f3fc)

Click on the ```Frontend``` application to configure it.

In the configuration page, paste the previously copied URL into the field Repository URL under the **Git** tab:

![configure_app_service_frontend-001](https://github.com/agility-game/dokploy/assets/1499433/bfbc76dc-7648-4772-914d-a5839c014251)

As the branch type **main**, for compose path type **./docker-compose.yml** and click **Save**.

Next, click on the tab **Advanced**.

![configure_app_service_frontend-002](https://github.com/agility-game/dokploy/assets/1499433/86ca85f3-9db1-4aab-a102-f6387674b52c)

Click on **Add Volume**.

![configure_app_service_frontend-003](https://github.com/agility-game/dokploy/assets/1499433/baad7ff0-fd77-4dbb-99bb-98ee3889815e)

For readability, see the **Content** below:

```
events {}

http {
    server {
        listen 80;
        server_name localhost;
        location / {
            proxy_pass http://whoami:80;
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header X-Forwarded-Proto $scheme;
        }
    }
}
```

And the **Mount Path**:

```
./nginx.conf
```

Click **Create**.

MORE


Next, click on **Deploy**.

When prompted, choose **Confirm**.

![configure_app_service_frontend-004](https://github.com/agility-game/dokploy/assets/1499433/c6523a69-0621-4fa5-8135-b948fcdabfbe)

We are being reminded: ```Please remeber to click Redeploy after adding, editing, or deleting a mount to apply the changes```. Follow up on this advice.

Go back to the tab **General** and click on **Deploy**.

![deploy_app_service_frontend-001](https://github.com/agility-game/dokploy/assets/1499433/a89b629f-145e-44dc-b89c-dca14f1d8ab2)

When prompted, choose **Confirm**.

The deploy process will start, as can be seen from the spinning wheel.

Once the deployment has completed, go to the tab **Deployments**. We can see the manual deployment listed. Click **View**.

![deploy_app_service_frontend-002](https://github.com/agility-game/dokploy/assets/1499433/ac271a48-db64-4366-88df-a881aaaa1a91)

You will see the log of the deployment:

![deploy_app_service_frontend-003](https://github.com/agility-game/dokploy/assets/1499433/20c55f54-40a5-42a1-ab36-4cbe72a162e8)

When successful, the log will state ```Docker Compose Deployed: tickbox```

Switch to the tab **Logs** to see any issues.

![deploy_app_service_frontend-004](https://github.com/agility-game/dokploy/assets/1499433/1b0ebcab-f20f-4182-89d5-2458e90d2f15)


If you go back to the Dokploy Dashboard and open the tab **Docker**, you should see the Docker containers as **Running**:

![deploy_app_service_frontend-005](https://github.com/agility-game/dokploy/assets/1499433/f33ae2ee-cb89-4607-a6a8-d746bf27de3e)

MORE

