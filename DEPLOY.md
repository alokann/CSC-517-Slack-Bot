# Milestone: DEPLOYMENT


### Deployment

We have used Ansible as a configuration management tool to automate the deployment of our bot. In order to deploy the bot, we made use of the Amazon EC2 instance. The playbook creates an EC2 instance on Amazon AWS and adds the public IP to the inventory file. 

After which the Ansible playbook is used to configure the EC2 instance by configuring the environment variables and running the bot.

The link of our deployment folder is: https://github.ncsu.edu/csc510-fall2019/CSC510-17/tree/master/Deployment

The link to our deployment screencast is: https://drive.google.com/open?id=1V4kGGOE33DD-a-McVVWd5

### Acceptance Testing

We have sent an invite to join our Slack team with workspace name 'GitHubApi help' on ffahid@ncsu.edu and yshi26@ncsu.edu.

Preconditions:
The Bot already has a GitHub Token stored in it.

The user will send a direct message to Bot for all the API help needed.

#### 1) Example to Search Topics:

In order for the user to get help on Searching topic, he can start the conversation with Bot as "Example on Searching".  To which the Bot will list all the actions supported by GitHub endpoints for searching. To enhance the user experience of the Bot, we can either provide the number from the list or type the name of action without any errors.

This reply will trigger the bot to pull up all the required parameters for the particular endpoint and then will keep continuing the conversation to build the personalized curl command.

Once this command is ready it will ask the user to either run the command on his behalf by saying 'yes' or 'sure'.  Users can even opt-out from this feature in order to run the command on his own by saying 'no'. If the bot is asked to run the command, the bot will be able to detect from the response status code whether the curl command executed successfully or not.

The user commands will be of the following form:

"Example on Searching" --> "7" --> "Python" 

This flow will generate the curl command for the user. And give the user an option to run the command or opt-out.


#### 2) Example to Edit an Issues:

The conversation between bot and user will be initialized when the user sends "Need help on issues". The bot will reply to a list of actions that can be performed on issues. Users can choose the action to be performed by replying with a number or typing the name of the action.

The bot then generates customized commands by gathering the values for the required parameters. And will create a curl command based on the inputs. 

The user commands will be of the following form:

"Need help on issues" --> "36" --> "<issue_number>(integer)" --> "<Owner>(String)" --> "<Repo name>(String)" 

This flow will generate the curl command for the user. And give the user and option to run the command or opt out.

#### 3) Example to Create a Repository

User can get help on creating a repository by sending a direct message to bot "Stuck on repository need help". The bot replies user for the list of actions that can be performed on a repository. 

User can choose one of the actions and bot will develop and user-defined curl command

The user commands will be of the following form:

"Stuck on repository need help" --> "18" --> "<Name of Repo>(String)".

This flow will generate the curl command for the user. And give the user an option to run the command or opt-out.


Note: The bot will wait 30 seconds for a reply from the user to either run the curl command or skip it.
