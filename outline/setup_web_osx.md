OS X Setup
==========
* Get Heroku installed (includes Git)
* Test installation

## Getting setup with Heroku

Heroku is the tool we will use in order to put your application online where others can see it.

First, we need to create an account. Go to [Heroku](http://heroku.com) and click the "Sign up" link.

![Heroku step 1](img/heroku-step1.png)

You will be taken to a form where you need to enter your email address in order to sign up. Fill out that form, and you will be sent an email with a link to click to continue the signup process.

![Heroku step 2](img/heroku-step2.png)

After clicking on the link, you will be taken to another form where you will need to choose a password. Choose one and enter it twice.

![Heroku step 3](img/heroku-step3.png)

After all that, you should be at your Heroku dashboard. There will be a link on the dashboard to download the Heroku Toolbelt. Download it now.

![Heroku dashboard](img/heroku-dashboard.png)

If you do not see this link on your dashboard, you can download the toolbelt from [toolbelt.heroku.com](https://toolbelt.heroku.com/).

This will download a .pkg file. Double-click it to install the Heroku Toolbelt and follow all prompts from the installation wizard. You will need your OS X account password to complete installation. If you are prompted to create an SSH key, say yes. It may also prompt you to install git. Once the Heroku Toolbelt is installed, go to your terminal and run the command `heroku login`. You will be prompted for your email and password on Heroku. If you enter them and the command ends successfully, congratulations!

![Heroku login](img/os_x/heroku_login.png)

To make your computer automatically communicate securely with Heroku, you will need to set up SSH. First, go to your terminal and run the command `ssh-keygen`. When prompted for inputs, simply press Return until the process has finished.

![Heroku SSH setup](img/os_x/heroku_ssh_setup.png)

Finally, complete your SSH setup with Heroku by running the command `heroku keys:add`.

![Heroku key-add](img/os_x/heroku_key_add.png)

## Testing your setup

You have set up Java, Leiningen, Light Table, Git, and Heroku on your computer--all the tools you will need for this course. Before starting, we need to test them out.

Go to your terminal and run the following command:

```
git clone https://github.com/heroku/clojure-sample.git
```

This will check out a sample Clojure application from GitHub, a central repository for lots of source code. Your terminal should look similar to this picture:

![Testing git clone](img/os_x/testing-step1.png)

Then run the command:

```
cd clojure-sample
```

We only have one more thing to test, Heroku.

Go back to your terminal. You should still be in the `clojure-sample` directory.

Run this command:

`heroku create`

There should be output about something being created. A URL will be displayed. Look at the following example:

![Testing heroku create](img/os_x/testing-step5.png)

Next, run the following commands:

```
git push heroku master
heroku open
```

Enter "yes" if you are asked if you are sure you want to connect, like in the following image:

![Connecting via SSH](img/os_x/testing-step6.png)

Your browser should open (and take a long time to load), and you should see a website like the following:

![Testing heroku working](img/os_x/testing-step7.png)

If your browser does not open after running `heroku open`, start a browser and go to the URL displayed after you ran `heroku create`.

Congratulations! That website is running code you have on your computer that you have uploaded. You have actually made a very simple Clojure app, and your computer is all set up to make more.
