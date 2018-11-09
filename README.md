# Welcome! Hack along with OpenShift@symbioticon 2018

Hi! We're so proud offering you a fully-fledged OpenShift server for your development and demoing needs at the **symbioticon 2018** in Frankfurt.

To get you started quickly, we the collected information we think is most needed for the hackathon. 

## What is OpenShift
OpenShift is a developer-centric enterprise Kubernetes distribution orchestrating an OCI compatible container runtime like docker naka moby. 
It covers the entire lifecycle from code commit to running your containerized application in production with built-in functionality.

All the functionality that either needs to be manually configured for Kubernetes or doesn't exist at all in it is available via UI and a developer API ready to use in CLI tools and IDEs.

## Why Should the Team use OpenShift
We have set up an individual OpenShift cluster *each* for up to eight teams.

This cluster is ready to use and brings you the following advantages:

  * Run apps in docker containers and make them available on the internet.
  * Use source-to-image (s2i) containers and benefit from the integrated build pipeline. s2i + GitHub repo -> commit -> new container. Completely automatically!
  * Select, mix and match your technology stack from the broad service catalogue offering available, e.g.
      * Java (with Spring Boot, Spring Applications, Wildlfy/JBoss EAP, Tomcat, Vert.x, Wildfly Swarm)
      * Node.js
      * Python
      * Ruby
      * PHP
      * .NET
      * C (sic!)
      * Middleware (e.g. Infinispan/JBoss Data Grid Cache, Apache Camel/JBoss FUSE, Apache ActiveMQ Artemis/AMQ)
      * Databases (MariaDB, MySQL, PostgreSQL, Mongo, Redis)
      * ML (Spark cluster and running in two minutes, Jupiter Notebooks, JDG Computing Grid)
      * Mobile (Push Notifications, Security)
      * API Management (if needed) with 3scale
  * Skip IDE fiddling overhead, save precious hackathon time and use Eclipse Che or FUSE ignite (Camel routes and mappings) in the browser.
  * Use up-to-date technologies such as Serverless and the integrated Istio Service Mesh.
 

## How can we get a Cluster
Just come around to our table. Look for red hats. Talk to us ;)

## How to Develop With OpenShift
With OpenShift, true dev support comes into Kubernetes.

### Basic Flow
Though you can tweak OpenShift - as every Kubernetes distribution - to hell, there's also a built-in opinionated path:

  1. Create a project in OpenShift (basically a fixed Kubernetes namespace).
  1. Set up a Git repo (Git(Hub|Lab)/BitBucket). Or know its repo URL.
  1. Add a source-to-image based technology/stack to your project that suits your repo (e.g. Node.js repo -> Node.js s2i. Not Python :D).
  1. Enter some parameters (mainly the repo URL) and confirm.
  1. That's it - based on the repo a build will automatically be created, put into a container an instantiated. Based on the app template even routes are created automatically.
  1. New commits trigger new background builds automatically - ready for testing by the other team members.

### Eclipse Che
If you want to get a super boost, skip local IDE adjustments and eliminate "runs on my computer" problems: Use Eclipse Che, an IDE that runs in the browser. It comes with some functionality that is extra handy for the hackathon:
  1. Code collaboration: Multiple users can code in the same workspace simultaneously.
  1. Syntax highlighting and intelligent proposal support for many languages.
  1. Git integration -> OpenShift flow supported.
  1. NN
  
 


### Useful Tools to be Installed


#### oc


#### odo


#### nodeshift


#### Eclipse/DevStudio


## Survival Guide


### Support at the Hackathon (Onsite Team!)


### CLI Ninja


#### Create a Project


#### Delete a Project


#### Manually Trigger a Build


#### Manually Trigger a Deployment


#### Expose Your App


### Ramp up for Node Devs


### Ramp up for Java Devs


### Ramp up for Mobile Devs


### Ramp up for ML Folks



## symbiotishift: Just an Inofficial Name :)
First a disclaimer: Red Hat is not affiliated with the symbioticon or the Sparkassen Gruppe at all, but on of many sponsors. 
We used the name in the tradition of other OpenShift related tools (minishift, nodeshift) and just found it funny. Relax.



