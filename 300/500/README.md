# 500 - Create a New Project in Dokploy on Server on Hetzner

Login to the Dokploy page at https://dokploy.agility-game.com and you'll be directed to the projects page:

![Screenshot 2024-05-23 at 16 48 34](https://github.com/agility-game/dokploy/assets/1499433/1cac5520-694c-4e31-8c9d-13bd460d0872)

For demonstration purpose, we are going to upload an example application, which can be found at https://github.com/Dokploy/next-todo-app

Copy the below URL:

```
https://github.com/Dokploy/next-todo-app.git
```

On the Projects page of Dokploy click **+ Create Project** button. Give it a name (here: ```Next ToDo App```) and a description (here: ```Next ToDo App for demonstration purposes```) and click **Create** button.

![add_project_next_todo_app-001](https://github.com/agility-game/dokploy/assets/1499433/d9829caf-9783-48a6-b526-4807d48dc48d)

Once the project has been created, inside the project click **+ Create Service** and from the Actions choose **Application** (not Database):

![create_service-application-001](https://github.com/agility-game/dokploy/assets/1499433/cdc4cc61-4b56-4432-8ba3-5ba4ff32ee81)

For the name of the Application Service let's use ```Frontend``` and for the Description ```Frontend of Next ToDo App```, like so:

![create_service-application-002](https://github.com/agility-game/dokploy/assets/1499433/a50e2b8d-b764-4f0c-a513-83d14eabbd06)

Click **Create** button.

Our new Application is listed as ```Frontend```.

![service_application_created-001](https://github.com/agility-game/dokploy/assets/1499433/018d0dcc-6623-4466-bc2b-0e1e39cf0ad2)

Click on the ```Frontend``` application to configure it.

In the configuration page, paste the previously copied URL into the field Repository URL under the **Git** tab:

![configure_service_application-001](https://github.com/agility-game/dokploy/assets/1499433/ba6f3c44-61de-46cc-8ce7-0efe358bc467)

As the branch type **main** and click **Save**.

Next, click on **Deploy**.

When prompted, choose **Confirm**.

![deploy_service_application-001](https://github.com/agility-game/dokploy/assets/1499433/a6821743-5822-4c1f-add2-da99eaf637ef)

The deploy process will start, as can be seen from the spinning wheel:

![deploy_service_application-002](https://github.com/agility-game/dokploy/assets/1499433/7e1e9fc7-2e5d-4d25-bfd0-30143c2906d5)

Once the deployment has completed, go to the tab **Deployments**. We can see the manual deployment listed. Click **View**.

![deployments_manual_deployment-001](https://github.com/agility-game/dokploy/assets/1499433/9a638b71-e8e6-4df4-b57c-e10d5fcad726)

You will see the log of the deployment:

![deployments_manual_deployment-002](https://github.com/agility-game/dokploy/assets/1499433/3414b3ca-0b83-46b0-9d90-a89b6e00983f)

When successful, the log will state ```Docker Deployed: tickbox```

Switch to the tab **Logs** to see any issues. Also check for the status **Ready**:

![manual_deployment_logs-001](https://github.com/agility-game/dokploy/assets/1499433/185152df-19e9-4963-9b65-f74901934f63)

Now, switch to the tab **Domains** and click **Add Domain**.

![domains_manual_deployment-001](https://github.com/agility-game/dokploy/assets/1499433/14792b9d-0bea-40b0-9a91-1a4f163cb14b)

Create an A record at your domain name provider (here: versio.nl) for this application. Use the IP address of the Server on Hetzner that hosts the NextJS application (here: 116.203.36.0):

![add_a_record_for_nextjs_on_versio-001](https://github.com/agility-game/dokploy/assets/1499433/d92d20d7-b5e7-4a1c-8ca9-c71ea7634bb4)

Click **Add record**.

**WARNING**: Make sure to click **Save changes** on the Versio page, otherwise your added A Record will not be saved.

Back in the Hetzner Dashboard, enter the sub- and domain name (here: ```nextjs.agility-game.com```), for the path stay with ```/``` as the root, for Container Port set the value of the port of our NextJS application (here: ```3000```), pick ```Letsencrypt (Default)``` as the Certificate, and set HTTPS to ```YES``` with the slider.

![domains_manual_deployment-002](https://github.com/agility-game/dokploy/assets/1499433/2a5935d4-9363-4a38-8976-64e2dc6b820a)

Click **Create**.

You will see the newly created domain ```nextjs.agility-game-com``` that is associated with our Frontend application.

![domains_manual_deployment-003](https://github.com/agility-game/dokploy/assets/1499433/7698102f-9a4c-4cca-a555-b678fe20ec04)




MORE
