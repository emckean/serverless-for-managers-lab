# serverless-for-managers-lab
Lab instructions for serverless lab (originally THINK 2018 Lab 5790A)

Looking for the PDF of the talk itself? It's [here](/ServerlessForManagers-THINK2018-McKean.pdf).

## Goal
In this lab, you will:
	
	* Create a serverless function
	* Check your function's logs
	* Delete or suspend your function

### Prerequisites

You need an IBM Cloud account! Sign up for one with this link [https://ibm.biz/BdZTG4](https://ibm.biz/BdZTG4).


### Instructions

#### Signing in: 

1. Visit [https://www.ibm.com/cloud/](https://www.ibm.com/cloud/) in your browser.

2. Click on the "person" icon in the upper-right-hand corner:
![person icon](./images/login.png)

3. Choose "sign in" from the drop-down menu: ![sign in](./images/signin.png)

4. Enter the IBM Student Cloud login email and click 'Continue'. ![enter email](./images/email.png)
5. Enter the password that you were given when you entered the lab and click "Sign in".  
![enter password](./images/password.png)
6. Click on "My cloud console" and choose "Dashboard": ![dashboard](./images/dashboard.png)

#### Creating a Function

1. Find the menu in the upper left-hand corner: ![menu](./images/menu.png)
2. Click on the menu and choose "Functions": ![functions](./images/functions-menu.png)
3. Click the "Start Creating" button: ![actions](./images/actions.png)
4. Choose "Create Action": ![create action](./images/create-action.png)
5. Give your action a name: ![name action](./images/create-action-name.png) and click the "Create" button.
6. See your code! ![your code](./images/see-your-code.png)
7. Invoke your code by clicking the "Invoke" buttom: ![invoke](./images/invoke.png)
*NOTE: if you get a "Not found" message, add a blank line at the end of your code block, save, and invoke again.*
8. Check out the results of your activation! ![activation results](./images/activation-results.png)

#### Using an Input Parameter

Cloud functions accept a single parameter, a JSON object called `params` in our function here. 

Update your function code to say "Hello " and your name by changing line 11 to read: 

`return { message: 'Hello, ' + params.name}`

Then click on "Change Input" in the function header: 

![change input](./images/change-input.png)

And enter your name as a parameter called `name`:

````json
{"name": "Erin"}
````
![params](./images/params.png)

Click "Apply".

Click "Invoke" again and you should see an output that looks like this: 

![params example results](./images/params-results.png)


#### Adding Logs

You can add logging statements to your function very simply. To test this, add `console.log("This is a log message.")` to your function: 

![console.log](./images/console-log.png)

Save and Invoke your function and you should see this output: 

![console log output](./images/console-log-output.png)

Note that the timestamp and the type of log (`stdout`) are included automatically.

You can see full Kibana logs for all your function invocations by clicking "Logs" in the sidebar: 

![logs menu](./images/logs-menu.png)

This will take you to a full Kibana dashboard (it make take a minute or so to load): 

![kibana dashboard](./images/kibana.png)

#### Adding a Web Endpoint

It's very simple to make your function a public web endpoint! 

From the Action sidebar, click on Endpoints: 

![endpoints](./images/endpoints.png)

Click "Enable as Web Action" and Save: 

![enable web action](./images/web-action.png)

Copy and paste the string under "URL" by clicking on the copy icon:

![public url](./images/public-url.png)

Open a new tab in your browser, and paste in your url. You should see something like this: 

![hello undefined](./images/hello-undefined.png)

You won't see your name, because you didn't pass a parameter called `name` to your function. 

Add `?name=Erin` (or your name, of course) to the end of your URL and refresh. Your output should now include your name: 

![web output with name](./images/web-output-name.png)

#### Deleting Your Function

Navigate to the Actions overview dashboard and choose 'Delete Action' from the dropdown menu: 

![delete action](./images/delete-action.png)






