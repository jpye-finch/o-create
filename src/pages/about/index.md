---
templateKey: about-page
title: About our values
---
# Our solution

##### Why is OpenCRVS required?

Even though civil registration is critical to citizen participation and effective governance, 44% of countries do not have functioning CRVS systems. Countries are currently stuck with inefficient paper-based systems or expensive and poorly designed information systems that are not flexible enough to adapt to changing operational environments. These existing systems do not meet the needs and capacities of the civil registration staff, leaving large parts of the population unregistered, unrecognised, and unprotected.

##### Product overview

Plan International is challenging the current gap in the market for a user-centric and rights-based CRVS system by leading the development of OpenCRVS, an open-source digital CRVS solution that is free to use, adaptable to the country context, interoperable with other government systems (e.g. health and ID systems), and rights-based to ensure it protects and provides for those most vulnerable.



OpenCRVS has the potential to go well beyond the scope of traditional CRVS systems. We see OpenCRVS as a foundational identity and population data system which will support and maintain the integrity of many other service delivery, statistical and identity management functions. In particular, OpenCRVS will ensure that these functions are above all inclusive, providing a digital response to the global call to “Leave No One Behind”.

To create OpenCRVS we have partnered with registration authorities, leading health system providers, expert software developers, and communities to design and build a global digital product that will serve the needs of end users and those being registered. We have achieved this by following international standards, digital principles for development, human-centred design and agile methodologies.

From the outset we have been committed to the creation of a digital public good that is:

* Freely available with no license fees or ties to software vendors.
* Safe and secure using best-practice security features.
* Fully interoperable with other government systems.
* Data enabled for fast decision-making.
* Based on international CRVS standards.
* Easily configured and deployed in all country contexts.
* Rights-based, empowering all individuals to access their basic human rights.
* User friendly, designed by and for the people it serves.
* Accessible and inclusive, extending registration coverage to the hard to reach and marginalised.



## Our development principles

Modularity

Designed around “microservice” components, OpenCRVS suits every country’s scale, customisation and configuration needs by being modular, configurable & independent across the full stack.



Security by design

OpenCRVS is critical government infrastructure that safeguards the personal data of its citizens. We took care to follow best practices and have it independently penetration tested to[UK government security standards](https://www.ncsc.gov.uk/).



Standards driven

The use of open interoperability and data standards such as[Health Level 7 FHIR v4 (ANSI Accredited, Fast Healthcare Interoperability Resources)](https://www.hl7.org/fhir/)provide vendor neutrality.



Cost effectiveness

In low resource settings, system administration and technical support needs to be cheap. OpenCRVS is deployable on either public or private cloud (following globally established frameworks and standards) reduce the Total Cost of Ownership.



Design for poor connectivity

Architected by designers, researchers and engineers used to field work, OpenCRVS supports low mobile reception & offline use.



Scalability

Schema-less & document-orientated, containerised & distributed by[Docker Swarm](https://docs.docker.com/engine/swarm/). Architected for flexibility, huge populations and continuous high traffic.



Performance

Integrated with external monitoring, automated load balancing, an industry standard search engine and using GraphQL to reduce requests, OpenCRVS is super fast and resilient.



Use of automation

Deploying OpenCRVS is a breeze. Development / QA and production environments, code testing coverage, networking, scaling and integration testing, all provision automatically using our[CI/CD](https://en.wikipedia.org/wiki/Continuous_delivery)pipeline. We use[Ansible](https://www.ansible.com/),[Travis](https://travis-ci.org/),[Jest](https://github.com/facebook/jest),[Cypress](https://www.cypress.io/),[Traefik](https://traefik.io/)&[Dockerhub](https://hub.docker.com/).



Big data insights

OpenCRVS uses time-series databases to generate visualisations and perform calculations on real-time civil registration analytics, helping policy makers make more informed decisions.

---
## System Architecture

OpenCRVS is configurable, interoperable and scalable to any country’s needs and makes best use of limited resources. In combination with[Docker](https://www.docker.com/)containers and[Docker Swarm](https://docs.docker.com/engine/swarm/), all services in all architectural layers can be distributed across a public or private cloud.

##### Database Layer

![FHIR_Foundation.png](<>)

Hearth

Massively scalable and extensible, an OpenSource NoSQL database server using interoperable[Health Level 7 FHIR v4 (ANSI Accredited, Fast Healthcare Interoperability Resources)](<>)as JSON.

[![Elasticsearch-Logo-Color-V.png](<>)](http://www.wix.com/)

[ElasticSearch](https://www.elastic.co/products/elasticsearch)

An industry standard, document orientated, real-time de-duplication / search engine. Lightning fast, intelligent civil registration record return, even with imprecise, “fuzzy” search parameters.

![influxdata-2.jpg](<>)

[InfluxData](https://www.influxdata.com/)

Hyper efficient and optimised, time series database for big data insights. Millisecond level query times over months of data, disaggregated by gender, location and configurable operational and statistical parameters.

##### Business Layer

![hapi-logo.png](<>)

![node.png](<>)

![typescript.png](<>)

[Microservices](https://en.wikipedia.org/wiki/Microservices)

OpenCRVS’ microservice architecture enables continuous delivery & deployment, facilitating endless scalability and evolution of its business requirements. The microservices are written in[TypeScript](https://www.typescriptlang.org/)(a strictly typed superset of JavaScript that compiles to JavaScript) and[NodeJS](https://nodejs.org/en/)using the fully documented[HapiJS](https://hapijs.com/)framework.

​

Each microservice in OpenCRVS has no knowledge of other services or business requirements in the application, and exposes it’s capabilities via secure APIs.

##### Interoperability Layer

![openhim-logo-green.png](<>)

[OpenHIM](http://openhim.org/)

The OpenHIM (Health Information Mediator) is an[enterprise service bus](https://en.wikipedia.org/wiki/Enterprise_service_bus)designed to ease interoperability between OpenCRVS and external systems such as Health, National ID. It provides access to the system via secure APIs, and governs transactions, routing, orchestrating and translating requests into[FHIR v4](https://www.hl7.org/fhir/).

![graphql.png](<>)

[GraphQL Gateway](https://graphql.org/)

Using GraphQL allows OpenCRVS to perform much faster and more responsively in remote areas by drastically reducing the number of HTTP requests that are required to render a view in the presentation layer.



The OpenCRVS GraphQL Gateway is a[JWT](https://jwt.io/)protected[Apollo](https://www.apollographql.com/)server that requests and resolves FHIR resources from OpenHIM into GraphQL schema, for easy consumption in the client applications.

##### Presentation Layer

![PWA-Progressive-Web-App-Logo.png](<>)

[Progressive Web Application](https://developers.google.com/web/progressive-web-apps/)

Using an Android Progressive Web Application for our mobile registration app means that we can take advantage of offline functionality and native push notifications, without the overhead of maintaining native code and App Store deployments. In remote areas, registrars can save a configurable number of registrations offline on their mobile phone using a locally encrypted database.

![OAuth.svg.png](<>)

[Secure single sign-on](https://graphql.org/)

Our applications are protected by[2-Factor Authentication](https://en.wikipedia.org/wiki/Multi-factor_authentication)with easy configuration for[OpenIDConnect](https://openid.net/connect/)or extensions for[ActiveDIrectory](https://auth0.com/docs/connections/enterprise/active-directory). Our apps and microservices utilise[OAuth best practices](https://auth0.com/blog/a-look-at-the-latest-draft-for-jwt-bcp/)for JWT authentication tokens. User permissions and roles are centrally managed, supporting IT organisations that conform to[ISO27001](https://en.wikipedia.org/wiki/ISO/IEC_27001)certification.

![react.png](<>)

[React](https://graphql.org/)

Modularity extends to the user interface using the React framework. All multi-lingual, civil registration form field components are generated and configured for validation using JSON so that they can be easily configured to suit legal requirements. Our full-stack javascript application makes it easy to allocate local system administration resources.
