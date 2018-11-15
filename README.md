# Welcome! Hack along with OpenShift@symbioticon 2018

Hi! We're extremely proud offering you a fully-fledged OpenShift cluster for your development and demoing needs at the **symbioticon 2018** in Frankfurt.

To get you started quickly, we collected information we think is most needed for the hackathon. 

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
* Use any docker container (not demanding root priviliges - won't work).

## How can we get a Cluster

Just come around to our table. Look for red hats. Talk to us ;)

## How to Develop With OpenShift

With OpenShift, true dev support comes into Kubernetes.

### Basic Flow

Though you can tweak OpenShift - as every Kubernetes distribution - to hell, there's also a built-in opinionated path:

1. Create a project in OpenShift (basically a fixed Kubernetes namespace).
2. Set up a Git repo (e.g. on GitHub/GitLab/BitBucket). Or know its repo URL.
3. Add a source-to-image based technology/stack to your project that suits your repo (e.g. Node.js repo -> Node.js s2i. Not Python :D).
4. Enter some parameters (mainly the repo URL) and confirm.
5. That's it - based on the repo a build will automatically be created, put into a container an instantiated. Based on the app template even routes are created automatically.
6. New commits trigger new background builds automatically - ready for testing by the other team members.

### Eclipse Che

If you want to get a super boost, skip local IDE adjustments and eliminate "runs on my computer" problems: Use Eclipse Che, an IDE that runs in the browser. It comes with some functionality that is extra handy for the hackathon:

1. Code collaboration: Multiple hackers can code in the same workspace simultaneously.
2. Syntax highlighting and intelligent proposal support for many languages.
3. Git integration -> OpenShift flow supported.
4. Run and access your app in the browser (automatic route exposure).

### Useful Tools to be Installed
With the OpenShift web console and Che you could basically run the hackathon without and IDE and without the terminal. To have more finegrained control or just keep up with your IDE and CLI workflow, there are some handy tools supporting your interaction with OpenShift.

#### oc
`oc` is the general-purpose CLI for OpenShift. It wraps its entire REST API and, thus, supports both ops and dev workflows. You need it for the other tools, so make sure installing it in any case!

You can get it from here: [https://github.com/openshift/origin/releases/tag/v3.11.0](https://github.com/openshift/origin/releases/tag/v3.11.0) (extract the `oc` executable from the archive and put, make it executable and put it under a $PATH-included directory).

Basic overview:  `oc --help`

Cookbook: [https://github.com/openshift-evangelists/openshift-cookbook](https://github.com/openshift-evangelists/openshift-cookbook)

#### odo
`odo` ("OpenShift Do") is a developer-centric CLI on top of `oc` to support common OpenShift interaction when developing applications. It can save you a good amount of time at a hackathon.

You can get it from here: [https://github.com/redhat-developer/odo/releases](https://github.com/redhat-developer/odo/releases)

Basic overview here: [odo.md](odo.md) or `odo`
 
Interactive tutorial here (Katacoda, needs sign-up, takes around ~10 minutes): [https://www.katacoda.com/mjelen/courses/introduction/developing-with-odo](https://www.katacoda.com/mjelen/courses/introduction/developing-with-odo)

#### nodeshift

Specialized OpenShift tooling for node.js developers. Deeply integrates the node ecosystem and tooling with OpenShift. Useful if you already know OpenShift very well and want to finetune configuration.

You can get it from here: `npm install -g nodeshift`

Basic information:  [https://nodeshift.github.io/nodeshift/](https://nodeshift.github.io/nodeshift/)

#### Eclipse/DevStudio

When using Eclipse, there's built-in OpenShift support available.
Either use the Red Hat Dev Studio (with Eclipse) or the Dev Studio Tooling Eclipse plugin.
If you have Eclipse (Photon) installed, we recommend using the plugin.

You can get it from here: +++TODO

 Basic overview here:  +++TODO

#### JetBrains IDEs (IDEA, WebStorm, pycharm et al.)

https://plugins.jetbrains.com/plugin/9354-kubernetes-and-openshift-resource-support

https://plugins.jetbrains.com/plugin/10485-kubernetes







## Survival Guide

### Support at the Hackathon (Onsite Team!)

There's a dedicated Red Hat team for you at the hackathon. Look out for our table and talk to the middleware and infrastructure specialist there to get support. Don't be shy - there are no dumb questions and we do all we can to get your project winning!

Save time, be more relaxed - just talk to us. We're happy to help!

### CLI Ninja

+++ TODO move CLI stuff to separate page!

Summary of most basic commands to keep you productive on the platform.

#### Create a Project

oc
`oc new-project <project-name>`

odo
`odo project create <project-name>`

#### List Available Projects
oc
`oc get project` (=> w/ status)
OR
`oc projects` (with hints)

odo
`odo project list`



#### Delete a Project

oc

odo

#### Delete All Stuff Within a Project
E.g. if you want to proceed working, but delete all apps, pods, configs etc.

`oc delete all --all`


#### Manually Trigger a Build

oc

odo

#### Manually Trigger a Deployment

oc

odo

nodeshift

#### Expose Your App

oc

odo

nodeshift

### Ramp up for Node Devs

+++TODO

#### Interactive Tutorial (On Live Platform)
[https://learn.openshift.com/middleware/rhoar-getting-started-nodejs/](https://learn.openshift.com/middleware/rhoar-getting-started-nodejs/)


### Ramp up for Java Devs

+++TODO

#### Interactive Learning at Katacoda (Live Environments)
Contains tracks for various topics (usually around ~15 min each):

* **Getting Started with Spring**<br>Basic Introduction to Spring on Red Hat OpenShift
* **Spring MVC**<br>Model/View/Controller pattern with Spring's MVC framework.
* **Spring REST**<br>RESTful applications using Spring Rest
* **Spring Data with JPA/Hibernate**<br>Database Integration in Spring Boot on OpenShift
* **Spring Messaging with Red Hat AMQ**<br>Modern Distributed microservices using Red Hat messaging
* **Testing Spring Applications with Arquillian Cube**<br>Integration testing in a containerized environment
* **Externalized Configuration**<br>Externalized Configuration and Health Checks
* **Service Discovery and Load Balancing**<br>Service Discovery and Load Balancing
* **Fault Tolerance and Resiliency**<br>Circuit Breaking
* **Monitoring Spring Applications on OpenShift**

[https://learn.openshift.com/middleware/courses/middleware-spring-boot/](https://learn.openshift.com/middleware/courses/middleware-spring-boot/)

### Ramp up for Mobile Devs

+++TODO

### Ramp up for ML Folks

+++TODO

### Further Documentation/Learning Tools

#### Katacoda: Interactive Tutorials on a Live Platform


+++TODO

#### OpenShift Documentation

#### Red Hat Developer Network

+++TODO

## symbiotishift: An _Inofficial_ Name :)

First a disclaimer: Red Hat is not affiliated with the symbioticon or the Sparkassen Gruppe at all, but one of many great sponsors.

We used the name in the tradition of other OpenShift related tools (minishift, nodeshift) and just found it funny. Relax.
