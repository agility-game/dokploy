# 600 - Create a Home Project in Dokploy on Server on Hetzner

Login to the Dokploy page at https://dokploy.agility-game.com and you'll be directed to the projects page:

![Screenshot 2024-05-23 at 16 48 34](https://github.com/agility-game/dokploy/assets/1499433/1cac5520-694c-4e31-8c9d-13bd460d0872)

We are going to upload a ```home``` application, which can be found at https://github.com/agility-game/home

Copy the below URL:

```
https://github.com/agility-game/home.git
```

On the Projects page of Dokploy click **+ Create Project** button. Give it a name (here: ```Home```) and a description (here: ```Home application```) and click **Create** button.

![add_project_home-001](https://github.com/agility-game/dokploy/assets/1499433/3576ff0b-f88d-4bf4-8c58-6d48192aef35)

Once the project has been created, inside the project click **+ Create Service** and from the Actions choose **Application** (not Database):

![create_service_in_home-001](https://github.com/agility-game/dokploy/assets/1499433/e5e63c6a-9578-4f52-bd94-b66a6adc5da0)

For the name of the Application Service let's use ```Frontend``` and for the Description ```Frontend of Home App```, like so:

MORE