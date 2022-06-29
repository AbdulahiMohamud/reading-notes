#### Serverless Overview

* **Serverless** systems run by externalizing some of the backend infrastructure of an application to a centralized platform run by a third party. Computing resources are divided up between (VERY) many clients on the basis of discrete processes rather than portioned per application. ("Functions as a Service")

  * Major providers include: AWS (Amazon); Azure Functions (Microsoft); Google Cloud Functions

#### Pros & Cons

* Advantages:

  * Low cost for relatively less computationally-intense applications (relative to traditionally maintained servers)

  * Uniform development environment (vs. dev, production, etc)

  * Allows for scaling without fundamental change in infrastructure/design

* Disadvantages:

  * Cannot route as directly to hosted content(needs to be accessed through provider's API)

  * Must support libraries of code for functionality that may be irrelevant to your app for the purposes of serverless dependencies

  * Ill-suited to longer, more complex functions

  * Cannot address scaling in any way other than service provider products

### AWS Amplify

* *Amplify* is Amazon's popular (not yet ubiquitous) framework and suite of tools for use with their Amazon Web Services cloud hosting. Amplify has command-line and UI-based functionality to integrate databasing, auth, and other backend features.


- citted Rob M Alxander