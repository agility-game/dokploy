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

== IMAGE GOES HERE ==

MORE


Next, click on **Deploy**.

When prompted, choose **Confirm**.

== IMAGE GOES HERE ==



MORE
