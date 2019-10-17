# Decentralize your application

Decentralizing your application permits users to buy your application on a pay-per-use basis.
This is a two steps workflow.

#### 1. Initialization

Pre-requesite: Your app needs to be dockerized and publicly available on the [Docker hub](https://hub.docker.com/)

Let's initialize an app:

`iexec app init`{{execute}}

Application initialization has some default value:

* `name` : your application name (default is _VanityEth_)
* `multiaddr` : Dockerimage public URL (default is _registry.hub.docker.com/iexechub/vanityeth:1.1.1_).

But you can also set your own environment by editing `iexec.json` file to customize your app.

`vi iexec.json`{{execute}}

#### 2. Deployment

You can now deploy your app on Ethereum 
(here, please note we keep output to ease the tutorial) :

`iexec app deploy 2>&1 | tee deploy.out`{{execute}}

Let's show the details of your freshly deployed app:

`iexec app show`{{execute}}

Congratulations, your application is now decentralized for anyone to use when running a work on iExec network. 

Finaly, let's check your deployed apps:

`iexec app count`{{execute}}


# Monetize your application

Decentralizing your application is a unic chance to monetize it by earning RLC.
This is a four steps workflow.


#### 1. Order initialization
You must first initialize a sell order for your application.

`iexec order init --app`{{execute}}

Application order initialization has some default value:

* `price` : order price (default is _0_): that's how many nRLC you will earn each time someone use your app.
* `volume` : order volume (default is _1000000_).

You should set your own environment by editing `iexec.json` file to customize your order.

`vi iexec.json`{{execute}}


#### 2. Order signature

You must sign your order with your wallet.

`iexec order sign --app`{{execute}}


#### 3. Order publication

You can publish your signed order.
(here, please note we keep output to ease the tutorial) :

`iexec order publish --app  2>&1 | tee publish.out`{{execute}}

#### 4. Order check

You can see your order.

`cat publish.out | grep orderHash| cut -d ' ' -f 7 | xargs iexec order show --app`{{execute}}

#### 5. Optional: application orderbook

You can check your application orderbook

`cat deploy.out | grep Deployed | cut -d ' ' -f 7| xargs iexec orderbook app` {{execute}}

## Conclusion

Your application is ready for renting.

Next section will introduce application buyers workflow.