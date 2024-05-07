# Node Hello World

Simple node.js app that servers "hello world"

Great for testing simple deployments to the cloud
Run It
`npm start`
# webhooks
### by running on cli 
Step 1: Deploy the app into local and serve<br>
Step 2: Create a hooks.json file and mention the stages that to be done and also update the secert & change the value as main or master<br>
Step 3: Create a redeploy.sh and run the dependencies that need and git pull \n create the <br>
Step 4: Run command- webhook -hooks hooks.json -hotreload -verbose -http-methods post<br>
Step 5: Create the webhook in post url: http://your-server-ip:9000/hooks/{id}(that is mentioned in your id inside the hook.json file) and application/json. Check webhook by changing the local and pushing to the github.<br>
Step 6: Run your in the port number 3000.

### by running as service 
Step 1: Deploy the app into local and serve<br>
Step 2: Create a hooks.json file and mention the stages that to be done and also update the secert & change the value as main or master<br>
Step 3: Create a redeploy.sh and run the dependencies that need and git pull \n create the <br>
Step 4: sudo nano /etc/systemd/system/webhook.service<br>
and paste this<br>

[Unit]<br>
Description= Github Webhook<br>
Documentation=https://github.com/adnanh/webhook<br>
After=network.target<br>
StartLimitIntervalSec=0<br>

[Service]<br>
Type=simple<br>
User=ubuntu<br>
Restart=on-failure<br>
RestartSec=5<br>
ExecStart=/usr/local/bin/webhook -verbose -hotreload -hooks /var/www/html/webhooks/hooks.json -port 9000 -ip 0.0.0.0 -http-methods POST<br>

[Install]<br>
WantedBy=multi-user.target<br>

Step 5: sudo systemctl enable webhook.service<br>
sudo systemctl start webhook.service<br>
sudo systemctl status webhook.service<br>

Step 6: Create webhook in github and in post url: http://your-ip:9000(or)domain/hooks/{id} (that is mentioned in your hooks.json file)<br>
