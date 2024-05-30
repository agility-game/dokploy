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

Hooray, you have deployed your application on Dokploy!

From the ```Monitoring``` tab on Dokploy you can see the performance of the Frontend application. Try refreshing the Frontend page several times to generate traffic.

![monitor_frontend_application_in_home-001](https://github.com/agility-game/dokploy/assets/1499433/8d75c982-d6e7-4247-a589-243ddd223cff)

## In Addition

Now automate the deployment process by means of Dokploy's webhook, see [Autodeploy](https://docs.dokploy.com/application/overview)

Under the tab **Deployments** of the Frontend application in the Home project, copy the Webhook URL (here: https://dokploy.agility-game.com/api/deploy/84vv_PIWLe4lCOjGJTkxE).

![webhook_url_frontend_application_in_home-001](https://github.com/agility-game/dokploy/assets/1499433/34647a34-0884-4aaf-9518-8a249935a68b)

Now go to the repository in Github (here: https://github.com/agility-game/dokploy-home) and open the tab **Settings**, choose **Webhooks** from the sidebar menu.

![github_dokploy_home_webhook-001](https://github.com/agility-game/dokploy/assets/1499433/ffd138fa-4f48-4fc6-bcf5-bd90abed184a)

Click on the **Add webhook** button.

![github_dokploy_home_webhook-002](https://github.com/agility-game/dokploy/assets/1499433/7cd92811-56b4-4880-bd46-fb63131c3117)

Paste the previously copied Webhook URL in the **Payload URL** field. Set **Content type** to ```application/json```. Leave **Secret** blank. Check **Enable SSL verification**. For now, check **Just the ```push``` event**. And set the webhook to **Active**. 

Finally click **Add webhook**.

![github_dokploy_home_webhook-003](https://github.com/agility-game/dokploy/assets/1499433/95bcb71e-4dbd-4e3f-85eb-0f95d20e1f56)

Go back to the webhook settings and under the tab **Recent Deliveries** verify if an initial ping command for this webhook has a tick in front of it for being successful.

![github_dokploy_home_webhook-004](https://github.com/agility-game/dokploy/assets/1499433/84d4646b-a586-4183-8434-1fadfa227d68)

Here, we have been successful so when can continue.

Let's create a new test branch in the Github repository (here: https://github.com/agility-game/dokploy-home), name it ```test/no-ref/testing-webhook``` for testing purpose following the [naming convention for branches and commits in Git](https://dev.to/varbsan/a-simplified-convention-for-naming-branches-and-commits-in-git-il4).

![github_dokploy_home_webhook-005](https://github.com/agility-game/dokploy/assets/1499433/aa7078fe-02fe-4462-b653-c1468d3d3bd6)

Click on the **Create branch test/no-ref/testing-webhook from main** text so the branch gets created.

You will have been switched to the newly created branch automatically.

![github_dokploy_home_webhook-006](https://github.com/agility-game/dokploy/assets/1499433/1981d75b-b309-44f2-b703-bac9652fcf7a)

Next, make a change to the ```index.html``` by adding a version number:

![github_dokploy_home_webhook-007](https://github.com/agility-game/dokploy/assets/1499433/303ab913-3da8-4add-b20c-00a6a1322aac)

Now commit your change.

![github_dokploy_home_webhook-008](https://github.com/agility-game/dokploy/assets/1499433/22cb7e9d-4c10-4080-8c30-d668972db93b)

You'll be notified that your branch had recent pushes, so click the **Compare & pull request** button.

![github_dokploy_home_webhook-009](https://github.com/agility-game/dokploy/assets/1499433/29cf286e-08e7-465c-b17a-7b5f816db2ae)

Add a title and optionally a description, then click **Create pull request**.

![github_dokploy_home_webhook-010](https://github.com/agility-game/dokploy/assets/1499433/f75ff816-4646-4b83-b12f-ee56c885609b)

Click on **Merge pull request**.

![github_dokploy_home_webhook-011](https://github.com/agility-game/dokploy/assets/1499433/06686570-1ff6-4a06-8e25-bf98357436d3)

Click on **Confirm merge**.

![github_dokploy_home_webhook-012](https://github.com/agility-game/dokploy/assets/1499433/9ee35054-c4bf-4955-a48e-3b66520aacc1)

You will see a confirmation that the pull request was successfully merged and closed.

![github_dokploy_home_webhook-013](https://github.com/agility-game/dokploy/assets/1499433/62828064-bce4-48e4-b277-5ed093e1a93a)

The ```pull``` event will have triggered the webhook. Let's see if it has been successful.

![github_dokploy_home_webhook-014](https://github.com/agility-game/dokploy/assets/1499433/f66556d5-6f10-4d82-8791-794bd13a6fb8)

From the green tick it shows a **successful** delivery.

Click on the blue text next to the green check to inspect what has happened.

![github_dokploy_home_webhook-015](https://github.com/agility-game/dokploy/assets/1499433/3f626f7e-0d82-44cc-b0f2-3d891e02c975)

The response states ```{"message":"App Deployed Successfully"}```.

Hooray!!

Now check in dokploy if we have indeed triggered a new deployment.

![github_dokploy_home_webhook-016](https://github.com/agility-game/dokploy/assets/1499433/a71019ae-1947-4806-be70-c7932fd1d5f3)

Indeed, the application was deployed based on the webhook being triggered from Github.

Finally, check the web page if we can see the change, in this case the addition of ```(v1)```.

![github_dokploy_home_webhook-017](https://github.com/agility-game/dokploy/assets/1499433/76362a03-5b76-478f-9f4f-37bc011d0e53)

All good.