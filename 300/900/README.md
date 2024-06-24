# 900 - Create an Api Project in Dokploy on Server on Hetzner

Login to the Dokploy page at https://dokploy.agility-game.com and you'll be directed to the projects page:

![create_a_new_project-001](https://github.com/agility-game/dokploy/assets/1499433/8cd7133a-8ddc-4d1c-b643-7806c63a7d97)

We are going to upload an api application, which can be found at https://github.com/agility-game/dokploy-api

Copy the below URL:

```
https://github.com/agility-game/dokploy-api.git
```

On the [Projects page of Dokploy](https://dokploy.agility-game.com/dashboard/projects) click **+ Create Project** button. Give it a name (here: ```Api```) and a description (here: ```Api application```) and click **Create** button.

![create_a_new_project_api-001](https://github.com/agility-game/dokploy/assets/1499433/49a4432c-f48d-4d42-9846-87f0760dd1bc)

Once the project has been created, inside the project click **+ Create Service** and from the Actions choose **Compose** (not Application):

**NOTE**: If the option ```Compose``` is not showing, consider upgrading your Dokploy instance. This is a newer feature, not found in older versions of Dokploy. You can upgrade your Dokploy server from within Dokploy.

![create_a_new_api_service-001](https://github.com/agility-game/dokploy/assets/1499433/1c87bf74-b94f-4847-a774-12bf9571d394)

For the name of the Compose Service let's use ```Frontend``` and for the Description ```Frontend of App```, like so:



MORE
