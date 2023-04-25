
# Learning Objectives

There are lots of learning objectives so don't tackle them all at once! The objectives are self-contained and designed to be addressed one at a time. Pick one at a time and have a flexible roadmap. You should aim to finish all Level 3 objectives before tackling any level 4 objectives.

Higher levels of learning objectives build on lower levels. However, you should be free to jump around different areas to best suit your desired learning path. Some objectives require you to have completed other specific objectives - when this is the case it is explicitly mentioned in the description.

The descriptions include specific technologies that are most commonly used in MYOB. These are the recommended default choices, however, you and your mentors are free to choose any other technologies should they better suit your needs.

You should complete up to Level 3 of each learning area. The 4th levels are optional stretch goals.

## API Design

### Level 1

> <i>Can describe what an API is and what can help make it successful. Has built something that responds to a request locally. Some form of documentation exists.</i>

It's important to understand that to build a successful API we need to go beyond just the technical implementation. We need to offer something useful, stable, secure, and easy to use. We need to treat users as customers, and our API as a product.

We will be leveraging industry-standard tools to quickly create a usable API. At MYOB the most common server-side technology is C#/ASP.NET Core. The first iteration can be anything that can be accessed locally, such as a GET endpoint that returns "Hello World".

Make sure that this endpoint has some form of documentation. This could be some simple instructions in your README.

Resources:
* https://www.thoughtworks.com/radar/techniques/apis-as-a-product
* https://docs.microsoft.com/en-us/aspnet/core/
* https://www.linkedin.com/learning/building-web-apis-with-asp-dot-net-core-3

#### Considerations
- [ ] I know what an API is and why we use them
- [ ] I can explain what a GET request does and when I’d use it
- [ ] I can explain what a POST request does and when I’d use it
- [ ] I can explain what a PUT or PATCH request does, when I’d use it and the difference between the two
- [ ] I can explain what a DELETE request does and when I’d use it
- [ ] I have created an API that can be run locally
- [ ] I have documented what my API does

### Level 2

> <i>Can describe the basics of JSON and REST. Understands standard best practices for RESTful API design. The project supports basic operations and this is documented.</i>

At MYOB we most commonly see REST over HTTPS using JSON. 

By following industry standard best practices we can take big steps towards making our APIs easier to use for our consumers.

Your project should support Create/Read/Update/Delete operations. We strongly suggest using REST with JSON as this is widely used across MYOB. The operations should be documented.

* https://en.wikipedia.org/wiki/JSON
* https://en.wikipedia.org/wiki/Representational_state_transfer
* https://www.linkedin.com/learning/learning-rest-apis/
* https://code.tutsplus.com/tutorials/a-beginners-guide-to-http-and-rest--net-16340

#### Considerations
- [ ] I know what REST is in regards to APIs
- [ ] I have created a GET endpoint in my API to retrieve a group of entries
- [ ] I have created a GET endpoint in my API to retrieve a single entry
- [ ] I have created a POST endpoint in my API to add a new entry
- [ ] I have created a PUT/PATCH endpoint in my API to update an existing entry
- [ ] I have created a DELETE endpoint in my API to delete an existing entry
- [ ] I have documentation for all of my endpoints that include what parameters they accept and all expected return responses
- [ ] Every endpoint has appropriate testing
- [ ] I can explain the different ways of sending data to an API (URL parameters vs request body content) and why each one is useful/why you’d use one over the other

### Level 3

> <i>Can articulate the benefits of following industry standards for documentation. The project handles all common use-cases including errors. These are documented following industry standards.</i>

Handling and providing good experiences around errors is also an important part of a good API. You should make sure that error cases are handled in a way consumers expect and also included documentation.

At MYOB the most common REST specification is OpenAPI, and Swagger is the tool typically used to help build documentation. You should use a tool such as Swagger to build the API documentation. 

* https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
* https://http.cat
* https://httpstatusdogs.com
* https://www.openapis.org/faq
* https://swagger.io/
* https://docs.microsoft.com/en-us/aspnet/core/tutorials/web-api-help-pages-using-swagger?view=aspnetcore-5.0

#### Considerations
- [ ] All of my endpoints have error handling
- [ ] All of my endpoints return appropriate HTTP codes
- [ ] My API has automated documentation with Swagger
- [ ] I know the most common HTTP codes (200, 201, 204, 400, 401, 403, 404, 500, 502) and can explain when/why they’d be used

### Level 4

> <i> Can describe strategies for evolving APIs while minimising customer impact. Has updated project API in such a manner. </i> 

When evolving an API we often discover that we want to change the shape of our interfaces in an incompatible way. There are strategies around this, such as versioning or expand-contract. 

You should change your API to support new data fields. This should be done in a way that minimises customer impact.

* https://martinfowler.com/bliki/ParallelChange.html
* https://restfulapi.net/versioning/

#### Considerations
- [ ] My API includes versioning

## Continuous Integration

### Level 1

> <i>Can explain containerisation and why it's beneficial. The project can be run as a container.</i>

Containerisation allows us to build and run our software in a consistent environment on any type of machine. At MYOB, Docker is the standard container technology we use.

You should build a container image for your project and be able to run it from the image.

* https://docs.docker.com/get-started/overview/
* https://docs.docker.com/get-started/  

#### Considerations
- [ ] I can explain what a Docker image is
- [ ] I can explain what a Docker container is
- [ ] I can explain why we use containers and the benefits they provide
- [ ] I can explain how containers work (what happens when you run docker run and the meaning of its parameters?)
- [ ] I can explain the content and different steps in a Dockerfile
- [ ] I have made a Docker image for my API
- [ ] I can run my Docker image locally and interact with my API through it

### Level 2

> <i>Can explain continuous integration and why it is used. Demonstrates a working continuous integration pipeline that runs tests and builds the project.</i>

Continuous integration helps give us confidence that our software is working, provides fast feedback, and allows us to respond to problems faster. This is achieved through services that can automatically test and build our software.

The standard build tool used at MYOB is Buildkite. You should run your tests and build your project whenever you commit to your code repository.

* https://www.martinfowler.com/articles/continuousIntegration.html
* https://hello.hub.myob.com/external/auto/buildkite.html

#### Considerations
- [ ] I can explain what continuous integration means
- [ ] I can explain the problem that continuous integration solves and the benefits in how it solves it
- [ ] My pipeline automatically runs when I push code to Github
- [ ] My pipeline builds my project and runs my tests in separate steps
- [ ] I can explain what happens when I push code to Github and how it ends up in Buildkite
- [ ] I can explain what Buildkite does when it gets the code (how does it work?)

### Level 3

> <i>Can explain what artefact repositories are and their benefits. The project pushes images to an artefact repository only if the tests pass and the build succeeds.</i>

Container images are stored in artefact repositories so they can be used by other machines. The standard artefact repository we use at MYOB is Cloudsmith.

You should update your build pipeline so that it pushes your built images to an artefact repository, but only when your tests and build pass.

* https://hello.hub.myob.com/external/arts/cloudsmith.html

#### Considerations
- [ ] I can explain what an `artefact` and an `artefact repository` are
- [ ] I can explain why we use an artefact repository and the problem that it solves
- [ ] I can explain our preferred artefact repository at MYOB (and the other options)
- [ ] My pipeline can push my API image to an artefact repository
- [ ] My pipeline can push my API image to an artefact repository only if it passes all tests and successfully builds

### Level 4

> <i>Can articulate the value of having clearly defined and fast build pipelines. The project has clearly defined build steps with separated concerns and is optimised to build as quickly as possible.</i>

Having clearly defined build steps with separations of concerns allows you to quickly identify the cause of build failures.

Pipelines can be optimised through parallelisation and containers can be optimised through creating smaller images and refining container build steps.

You should improve your build process so that your pipeline has clearly defined steps with separated concerns. You should optimise your pipeline structure and container building.

* https://docs.docker.com/develop/develop-images/dockerfile_best-practices/
* https://buildkite.com/docs/pipelines

#### Considerations
- [ ] My pipeline has been optimised as per the instructions above

## Continuous Delivery/Deployment

### Level 1

> <i>Can explain the benefits of using a service to run your containers. Can get the project running in a service manually.</i>

You should complete Continuous Integration Level 1 prior to attempting this.

There are many technologies and services that can run or orchestrate containers. The default technology at MYOB is Jupiter, which is a platform composed of Kubernetes and several other technologies.

If you are using MYOB's standard technology stack, you can run a Docker container in Jupiter manually. The URL of your Docker container image can be used to manually deploy a Pod in Jupiter through the Jupiter Kubernetes dashboard.

You should deploy your project and run it in a service. It doesn't need to be accessible from the internet, but you can verify it's working via shell access to the running container.

* https://en.wikipedia.org/wiki/IT_infrastructure
* https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/
* https://docs.jupiter.myob.com/what-and-why/why.html
* https://docs.jupiter.myob.com/what-and-why/what-is-jupiter.html

#### Considerations
- [ ] I can explain what continuous delivery/deployment is, the problem that it solves and the difference between the two terms
- [ ] I can explain what Kubernetes is and how it works at a high level
- [ ] I can explain what MYOB’s Jupiter platform is and what it does
- [ ] I have manually deployed my API to Jupiter
- [ ] I can get shell access to my running API in Jupiter and interact with the API

### Level 2

> <i>Can articulate what the various components of your infrastructure achieve. The project can be deployed from a configuration file via the command line.</i>

Infrastructure is the backbone that runs all the software we make. You should understand what the various components of your project achieve. 

For Jupiter, you can create configuration files for your infrastructure that can be deployed via the command line. 

You should document what you are using the various components of your infrastructure for, and be able to deploy your project via the command line.

* https://docs.jupiter.myob.com/basics/getting-started.html

#### Considerations
- [ ] I can explain the difference between pods, nodes, clusters and replica sets
- [ ] I can use `kubectl` to deploy my API via the command line
- [ ] I have a configuration file in my codebase to help automate the deployment
- [ ] I have made a diagram of the architecture of my infrastructure

### Level 3

> <i>Can articulate the benefits of having infrastructure as code. The project is deployed from a build pipeline using infrastructure as code concepts.</i>

Having as much as possible of your infrastructure in version control allows you to easily recreate your current or any previous state of your infrastructure with ease. This allows us to deliver our software and its environment quickly and with confidence.

Your project should be deployed as part of your build pipeline.

This learning objective requires Continuous Integration Level 2.

* https://docs.jupiter.myob.com/basics/deployment-with-buildkite.html

#### Considerations
- [ ] I can explain the problem that infrastructure as code solves
- [ ] I can use the configuration file in my codebase to automate my deployment using my build pipeline

### Level 4

> <i>Articulates the full continuous integration, continuous deployment, and continuous delivery concepts and how it impacts the customer. Has implemented automation to deploy software to multiple environments (eg “sit” and “prod”) and can explain the processes used.</i>

Ultimately CI/CD is about giving us the ability to deliver quality software to our customers quickly and with more confidence. 

Supporting multiple environments gives us the flexibility to test things that we wouldn't be able to in a production environment.

At MYOB we commonly use ktmpl to support multiple environments without duplicating all of our configuration files.

* https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment
* https://docs.jupiter.myob.com/basics/templating.html

#### Considerations
- [ ] I have used `ktmpl` to deploy to multiple environments (dev/preprod/sit and prod)

## Security

### Level 1

> <i>Can articulate the importance of security and how it can impact the safety and livelihood of our customers and employees.
Can explain the concepts of threats, vulnerabilities, and risks. Can describe how risks are reduced by improving our application security as well as our ability to respond to security incidents.</i>

A security breach may expose the personal data of our customers to attackers. As a business platform, MYOB holds a large quantity of sensitive personal and business information. In the wrong hands, such information can have material impacts on our customers' financial, physical, and mental wellbeing. It can also cause irreversible damage to the MYOB brand.

Understanding the concepts of threats, vulnerabilities and risks help us have objective discussions about how to identify, prioritise and remediate security issues. 

At MYOB our Appsec team helps us build secure systems, and our Secops team helps us respond to security incidents. We also have a GRC (Governance, Risk and Compliance) team to help us manage risks and meet our various obligations.

* https://en.wikipedia.org/wiki/Application_security
* https://myobconfluence.atlassian.net/wiki/spaces/security/overview

#### Considerations
- [ ] I can explain the effects on MYOB and it’s customers if there was a security breach of our products
- [ ] I can explain the importance of the CIA triad (confidentiality, integrity and availability) in security
- [ ] I can explain the difference between a threat, a risk and a vulnerability
- [ ] I can explain the types of preventative security that can help avoid security breaches (code scanning, code reviews, secret management, encrypting data)

### Level 2

> <i>Knows resources (such as OWASP) that describe common security concerns applicable to developers. Has checked top risks against the project and documented any concerns.
Can describe risks associated with handling secrets and ways of mitigating them.</i>

There are many resources available to help us build secure systems. OWASP is one commonly referenced security resource that has a multitude of beneficial information, most famously the OWASP Top 10.

You should review your application against common security risks, such as those outlined in the OWASP Top 10 and document any issues.

Safely handling "secrets" is critical to system security. Cloud providers typically provide secret management services, and the MYOB Jupiter platform (Kubernetes) also has secret management capabilities.

* https://owasp.org/www-project-top-ten/
* https://kubernetes.io/docs/concepts/configuration/secret/
* https://github.com/MYOB-Technology/General_Developer/blob/main/things-we-value/technical/security/managing-secrets.md

#### Considerations
- [ ] I can explain the importance of handling secrets safely and the risks if they are not handled correctly
- [ ] I know how secrets and stored and handled in Jupiter
- [ ] I know how to access my secrets in Jupiter
- [ ] I can explain the OWASP Top 10 vulnerabilities
- [ ] I have manually reviewed my codebase against the OWASP Top 10 and documented any vulnerabilities

### Level 3

> <i>Has applied some form of security analysis in build pipeline and is aware of other techniques to actively identify vulnerabilities.
Has implemented proper secret management in the project.</i>

Static security analysis is an easy way to identify common security vulnerabilities by analysing our codebases. At MYOB we use SonarQube as our recommended static security analysis tool.

You should implement SonarQube as part of your build pipeline and implement proper secret management.

This learning objective requires Continuous Deployment/Delivery Level 2.

* https://myobconfluence.atlassian.net/wiki/spaces/security/pages/1008635265/SonarQube

#### Considerations
- [ ] I have appropriately managed any secrets in my codebase using the secret management available in Jupiter
- [ ] I can scan my codebase with Sonarqube as a part of my automated build process (as a separate step)
- [ ] I have looked at the Sonarqube UI and identified any issues that it has found
- [ ] Bonus: I’ve taken a screenshot of the identified issues and can talk about how I’d resolve them (or if you have time, actually resolve them)

### Level 4

> <i>Understands where security lives at each stage of the SDLC and how/when most teams interact with it. Has retroactively completed a threat model for the project.</i>

Security needs to be incorporated throughout our software delivery lifecycle. Appsec services and tools should be leveraged from the planning stages through to after deployment.

You should run a threat modelling exercise on your project.

* https://myobconfluence.atlassian.net/wiki/spaces/security/pages/854327774/Security+Services

#### Considerations
- [ ] I have run a Threat Modelling session with Appsec to identify issues in my project

## Summary

### API Design
Level | Attributes
----- | ----------
L1 | Can describe what an API is and what can help make it successful. Has built something that responds to a request locally. Some form of documentation exists.
L2 | Can describe the basics of JSON and REST. Understands standard best practices for RESTful API design. The project supports basic operations and this is documented.
L3 | Can articulate benefits of following industry standards for documentation. The project handles all common use-cases including errors. These are documented following industry standards.
L4 | Can describe strategies for evolving APIs while minimising customer impact. Has updated project API in such a manner.

### Continuous Integration
Level | Attributes
----- | ----------
L1 | Can explain containerisation and why it's beneficial. The project can be run as a container.
L2 | Can explain continuous integration and why it is used. Demonstrates a working continuous integration pipeline that runs tests and builds the project.
L3 | Can explain what artefact repositories are and their benefits. The project pushes images to an artefact repository only if the tests pass and the build succeeds.
L4 | Can articulate the value of having clearly defined and fast build pipelines. The project has clearly defined build steps with separated concerns and is optimised to build as quickly as possible.

### Continuous Delivery/Deployment
Level | Attributes
----- | ----------
L1 | Can explain the benefits of using a service to run your containers. Can get the project running in a service manually.
L2 | Can articulate what the various components of your infrastructure achieve. The project can be deployed from a configuration file via the command line.
L3 | Can articulate the benefits of having infrastructure as code. The project is deployed from a build pipeline using infrastructure as code concepts.
L4 | Articulates the full continuous integration, continuous deployment, and continuous delivery concepts and how it impacts the customer. Has implemented automation to deploy software to multiple environments (eg “sit” and “prod”) and can explain the processes used.

### Security
Level | Attributes
----- | ----------
L1 | Can articulate the importance of security and how it can impact the safety and livelihood of our customers and employees. Can explain the concepts of threats, vulnerabilities, and risks. Can describe how risks are reduced by improving our application security as well as our ability to respond to security incidents.
L2 | Knows resources (such as OWASP) that describe common security concerns applicable to developers. Has checked top risks against the project and documented any concerns. Can describe risks associated with handling secrets and ways of mitigating them.
L3 | Has applied some form of security analysis in build pipeline and is aware of other techniques to actively identify vulnerabilities. Has implemented proper secret management in the project.
L4 | Understands where security lives at each stage of the SDLC and how/when most teams interact with it. Has retroactively completed a threat model for the project.


