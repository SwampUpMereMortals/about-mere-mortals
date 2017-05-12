# About Mere Mortals - SwampUP 2017 Talk

![mere mortal quote][quote]

Find setup instructions, slides, and wiki/notes here on the Mere
Mortals Architecture.  We detail everything needed to get mere mortals
up and running with Artifactory, Kubernetes, Travis CI, and a very
basic pipeline to deploy your software.


## Slides

TBD.


## Artifactory Setup

We used the SaaS Artifactory Online offering, hosted on GCP.  Since we
are running a Kubernetes instance in GKE, this made the most sense.
_Protip_: Host your Artifactory GCP instance in the same region as
your GKE instance.  For us, this was `us-central1`.  This cuts down on
bandwidth costs to/from GKE and Artifactory when pulling Docker
images.


## Travis CI Setup

CI setup is fairly straight forward.  There are a few rules however,
to be a mortal:
  * Use a dedicated CI account.
  * Use encrypted variables to setup the credentials.
  *


## Kubernetes on GKE/GCP Setup

TBD.


## Github / Software Setup

We separate concerns between the software (a repo that has your
service/microservice, along with a Docker/`Dockerfile`), and the
*kubernetes deployment* configuration.  We see these as two separate
concerns: Software & Deployment.  Therefore, repos here are broken
into their separate entities.

- `crispy-barnacle`: The Service.  Builds a Java Servlet WAR and
  Docker image.  Both of these are then pushed into Artifactory. Once
  completed, CI makes a commit to a _separate repo_ to update the
  version of this service's Kubernetes deployment yaml configuration.
- `crispy-kube-deployment`: The kubernetes deployment.
- `common-ci`: TBD.


[quote]: http://wist.info/wp/wp-content/uploads/2015/12/Lewis-ordinary-people-wist_info-quote.jpg
