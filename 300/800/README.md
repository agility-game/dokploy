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

For the name of the Application Service let's use ```Frontend``` and for the Description ```Frontend of App```, like so:

== IMAGE GOES HERE ==

MORE
