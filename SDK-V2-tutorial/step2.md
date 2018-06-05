# Deploy your app

Pre-requesite: Your app needs to be dockerized and publicly available on the [Docker hub](https://hub.docker.com/)

Now let's check if you have already deployed apps:

`iexec app count`{{execute}}

Let's initialize an app:

`iexec app count`{{execute}}

Now go ahead and edit `iexec.json` file to customize your app, especially you should set the:

* price field (that's how many nRLC you will earn when someone use your app).
* Dockerimage name (that should be the dockerhub public image name).

`vi iexec.json`{{execute}}

You can now deploy your app on Ethereum:

`iexec app deploy`{{execute}}

Let's show the details of your freshly deployed app:

`iexec app show`{{execute}}

Congrats, your app is available for anyone to use when running a work on iExec network. Let's see in the next section how to use this app.
