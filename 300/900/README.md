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

For the name of the Compose Service let's use ```Frontend``` and for the Description ```Frontend of Api```, like so:

![create_a_new_api_service_compose-001](https://github.com/agility-game/dokploy/assets/1499433/2d146f9f-9ada-4831-bfa6-a161dbd7948e)

**NOTE**: The default entry for AppName uses the ```api-[Name]``` format, where the ```Name``` is capitalized. However, this causes an error. We follow the convention to keep all lowercase (here: ```api-frontend```).

For Compose Type, we choose ```Docker Compose```!

Click the **Create** button. 

*NOTE*: You may have to click outside of the dialogue or the X in the right top corner to come back to the main page.

Our new Docker Compose service is listed as ```Frontend```.

![create_a_new_api_service_frontend-001](https://github.com/agility-game/dokploy/assets/1499433/7f6eafbb-aa43-48cf-bf83-78f7d7fd7e3c)

Click on the ```Frontend``` application to configure it.

In the configuration page, paste the previously copied URL into the field Repository URL under the **Git** tab:


MORE
