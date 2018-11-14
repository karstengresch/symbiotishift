# odo - "OpenShift Do"
## Quickstart for Symbioticon

### Installation


### Getting Started

We will be developing and deploying a Node.JS application to an OpenShift cluster in this guide.

We'll be going over the following steps:

**Your first application**

 1. [Create an application](#1-create-an-application)
 1. [Create a component](#2-create-a-component)
 1. [Accessing the component](#3-accessing-the-component)
 1. [Pushing new changes to the component](#4-pushing-new-changes-to-the-component)
 1. [Adding storage to the component](#5-adding-storage-to-the-component)

**Extra documentation:**

* [Service Catalog](#service-catalog)


## Your first application

Log in to the OpenShift cluster:

```sh
$ oc login --token "YOUR_TOKEN_AS_GIVEN_FROM_US_HERE"
Login successful.

You have one project on this server: "myproject"

Using project "myproject".
```

Now we can move on to creating our application using `odo`.

### 1. Create an application

An application is an umbrella that will comprise all the components (microservices) you will build.

Let's create an application:

```console
$ odo app create nodeapp
Creating application: nodeapp
Switched to application: nodeapp
```

### 2. Create a component

First, we'll download the our test application: 

```console
$ git clone https://github.com/openshift/nodejs-ex
Cloning into 'nodejs-ex'...
remote: Counting objects: 568, done.
remote: Total 568 (delta 0), reused 0 (delta 0), pack-reused 568
Receiving objects: 100% (568/568), 174.63 KiB | 1.53 MiB/s, done.
Resolving deltas: 100% (224/224), done.

$ cd nodejs-ex 
~/nodejs-ex  master
```

Now that you've created an application, add a component of type _nodejs_ to the application, from the current directory where our code lies:

```console
$ odo create nodejs
Component 'nodejs-ex-nodejs-xfru' was created and port 8080/TCP was opened
To push source code to the component run 'odo push'

Component 'nodejs-ex-nodejs-xfru' is now set as active component.
```

*Note:* You can explicitly supply a namespace by using: `odo create openshift/nodejs:8`. Otherwise, the `latest` image is used.

Now that a component is running we'll go ahead and push our initial source code!

```sh
odo push
Pushing changes to component: nodejs-ex-nodejs-xfru
Please wait, building component....
+ set -eo pipefail
+ '[' -f /opt/app-root/src/.s2i/bin/assemble ']'
+ '[' -f /usr/local/s2i/assemble ']'
+ /usr/libexec/s2i/assemble
---> Installing application source
---> Building your Node application from source
---> Installing dependencies
---> Using 'npm install -s --only=production'
---> Pruning the development dependencies
---> Cleaning up npm cache
---> Fix permissions on app-root
+ /var/lib/supervisord/bin/supervisord ctl stop run
run: stopped
+ /var/lib/supervisord/bin/supervisord ctl start run
run: started
changes successfully pushed to component: nodejs-ex-nodejs-xfru
```

Great news! Your component has been deployed to OpenShift! Now we'll connect to the component.

### 3. Accessing the component

To access the component, we'll need to create an OpenShift route:

```console
$ odo url create
Adding URL to component: nodejs-ex-nodejs-xfru
URL created for component: nodejs-ex-nodejs-xfru

nodejs-ex-nodejs-xfru - http://nodejs-ex-nodejs-xfru-foo-myproject.192.168.42.208.nip.io
```

Now simply access the URL `nodejs-myproject.192.168.42.147.nip.io` in the browser and you will be able to view your deployed application.

### 4. Pushing new changes to the component

Let's make some changes to the code and push them.

Edit one of the layout files within the Node.JS directory.

```sh
$ vim views/index.html
```

Now let's push the changes:

```console
$ odo push
Pushing changes to component: nodejs
sending incremental file list
...
changes successfully pushed to component: nodejs
```

Refresh your application in the browser, and you'll be able to see the changes.

After each change, you can continue updating your component by using: `odo push nodejs`.

### 5. Adding storage to the component

Now that you've got your component running, how do you add persistent any data between restarts?

If you wish to add storage to your component, `odo` makes it very easy for you to do this:

```console
$ odo storage create nodestorage --path=/opt/app-root/src/storage/ --size=1Gi 
Added storage nodestorage to nodejs
```

That's it! Storage has been added your component with an allocated size of 1 Gb.

### Service Catalog

You can list available services via `odo catalog list services` and service catalog related operations via `odo service <verb> <servicename>`.
