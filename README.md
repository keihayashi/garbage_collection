Slackbots
---
### Description   
I am planning to move and create my slack bots here.    
I am currently deploying the bot to [GCE](https://cloud.google.com/compute/pricing), since I found that I need to be a paying member in order to use *cron* if I use Heroku.

### Usage
I explained the case of using GCP instance to deploy slackbots below.
1. Sign in into [Google Cloud Platform](https://console.cloud.google.com/home/). You need Google account to sign in.
2. Create a project and make a new instance there.
3. SSH into your instance. You can both click SSH button at your project page or [use gcutil](https://cloud.google.com/sdk/)
4. Clone or download this repository at the instance. Change the [script](https://github.com/keihayashi/home_bot/blob/master/myhubot/scripts/example.coffee) to change room, message and time.
5. Install dependencies. Here is [how to install and deploy hubot on UNIX](https://hubot.github.com/docs/deploying/unix/). You may also need [install and configure redis](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-redis-on-ubuntu-16-04)
6. Configure and deploy the slack bot. I used [systemd](https://freedesktop.org/wiki/Software/systemd/) to monitor. I also changed timezone of cron service.
```
sudo dpkg-reconfigure tzdata
sudo service cron restart
```
