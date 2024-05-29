# 600 - Create a Home Project in Dokploy on Server on Hetzner

Login to the Dokploy page at https://dokploy.agility-game.com and you'll be directed to the projects page:

![Screenshot 2024-05-23 at 16 48 34](https://github.com/agility-game/dokploy/assets/1499433/1cac5520-694c-4e31-8c9d-13bd460d0872)

We are going to upload a ```home``` application, which can be found at https://github.com/agility-game/home

Copy the below URL:

```
https://github.com/agility-game/dokploy-home.git
```

On the Projects page of Dokploy click **+ Create Project** button. Give it a name (here: ```Home```) and a description (here: ```Home application```) and click **Create** button.

![add_project_home-001](https://github.com/agility-game/dokploy/assets/1499433/3576ff0b-f88d-4bf4-8c58-6d48192aef35)

Once the project has been created, inside the project click **+ Create Service** and from the Actions choose **Application** (not Database):

![create_service_in_home-001](https://github.com/agility-game/dokploy/assets/1499433/e5e63c6a-9578-4f52-bd94-b66a6adc5da0)

For the name of the Application Service let's use ```Frontend``` and for the Description ```Frontend of Home App```, like so:

![create_service-application-frontend-in-home-001](https://github.com/agility-game/dokploy/assets/1499433/12b590ba-555b-45ff-abad-b578d1dc7b98)

Click **Create** button.

Our new Application is listed as ```Frontend```.

![service_application_frontend_in_home_created-001](https://github.com/agility-game/dokploy/assets/1499433/6e08b427-5d07-4cc3-a9b9-b9d8d6d60138)

Click on the ```Frontend``` application to configure it.

In the configuration page, paste the previously copied URL into the field Repository URL under the **Git** tab:

![configure_service_application_frontend_in_home-001](https://github.com/agility-game/dokploy/assets/1499433/9d5c4f71-ee13-487b-8e88-0d257b368140)

As the branch type **main** and click **Save**.

Next, click on **Deploy**.

When prompted, choose **Confirm**.

![deploy_service_application-001](https://github.com/agility-game/dokploy/assets/1499433/a6821743-5822-4c1f-add2-da99eaf637ef)

The deploy process will start, as can be seen from the spinning wheel:

![deploy_service_application-002](https://github.com/agility-game/dokploy/assets/1499433/7e1e9fc7-2e5d-4d25-bfd0-30143c2906d5)

Once the deployment has completed, go to the tab **Deployments**. We can see the manual deployment listed. Click **View**.



MORE