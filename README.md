# Node Hello World

Simple node.js app that servers "hello world"

Great for testing simple deployments to the cloud

## Run It

`npm start`
# webhooks


Step 1: Deploy the app into local and serve<br>
Step 2: Create a hooks.json file and mention the stages that to be done and also update the secert & change the value as main or master<br>
Step 3: Create a redeploy.sh and run the dependencies that need and git pull \n create the <br>
Step 4: Run command- webhook -hooks hooks.json -hotreload -verbose -http-methods post<br>
Step 5: Create the webhook in post url: http://your-server-ip:9000/hooks/{id(that is mentioned in your id inside the hook.json file)} and application/json. Check webhook by changing the local and pushing to the github  
