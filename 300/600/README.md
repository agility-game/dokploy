# 600 - Create a Home Project in Dokploy on Server on Hetzner

Login to the Dokploy page at https://dokploy.agility-game.com and you'll be directed to the projects page:

![Screenshot 2024-05-23 at 16 48 34](https://github.com/agility-game/dokploy/assets/1499433/1cac5520-694c-4e31-8c9d-13bd460d0872)

We are going to upload a ```home``` application, which can be found at https://github.com/agility-game/dokploy-home

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

![deployments_manual_deployment_frontend_in_home-001](https://github.com/agility-game/dokploy/assets/1499433/e102f92c-5b67-456c-8f40-3788a751a192)

You will see the log of the deployment:

![deployments_manual_deployment_frontend_in_home-002](https://github.com/agility-game/dokploy/assets/1499433/416d9998-e46c-4537-93f8-03f0b19c519e)

When successful, the log will state ```Docker Deployed: tickbox```

Switch to the tab **Logs** to see any issues. Also check for the status **start worker process**:

![manual_deployment_frontend_in_home_logs-001](https://github.com/agility-game/dokploy/assets/1499433/c2124f4f-fc36-419d-8c0e-afdfb695a4a3)

Now, switch to the tab **Domains** and click **Add Domain**.

![domains_manual_deployment_frontend_in_home-001](https://github.com/agility-game/dokploy/assets/1499433/78f65b6c-1ac0-4dc6-8cf0-85048c5f64c4)

Create an A record at your domain name provider (here: versio.nl) for this application. Use the IP address of the Server on Hetzner that hosts the Frontend application in Home (here: 116.203.36.0):

![add_a_record_for_app_on_versio-001](https://github.com/agility-game/dokploy/assets/1499433/c2265470-bd25-403e-a21b-597ddc4e7be7)

Click **Add record**.

**WARNING**: Make sure to click **Save changes** on the Versio page, otherwise your added A Record will not be saved.

Back in the Hetzner Dashboard, enter the sub- and domain name (here: ```app.agility-game.com```), for the path stay with ```/``` as the root, for Container Port set the value of the port of our Frontend application in Home (here: ```80```), pick ```Letsencrypt (Default)``` as the Certificate, and set HTTPS to ```YES``` with the slider.

![domains_manual_deployment_frontend_in_home-002](https://github.com/agility-game/dokploy/assets/1499433/cfd8ea5d-8c17-423d-af33-ea5a175198ea)

Click **Create**.

You will see the newly created domain ```app.agility-game-com``` that is associated with our Frontend application.

![domains_manual_deployment_frontend_in_home-003](https://github.com/agility-game/dokploy/assets/1499433/15e3c5dd-f1af-4227-a6b6-bb449f7eadfe)

Allow some time for the Certificate to be processed (about 10 minutes), after which you can click the link to ```app.agility-game.com```. It will show the landing page of the Frontend application.

![frontend_application_in_home_live-001](https://github.com/agility-game/dokploy/assets/1499433/14415c26-d5f5-48a0-8acd-7865c4e200d4)

MORE