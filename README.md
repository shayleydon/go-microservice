<p align="center">
    <a href="http://kitura.io/">
        <img src="https://landscape.cncf.io/logos/ibm-cloud.svg" height="100" alt="IBM Cloud">
    </a>
</p>


<p align="center">
    <a href="https://cloud.ibm.com">
    <img src="https://img.shields.io/badge/IBM%20Cloud-powered-blue.svg" alt="IBM Cloud">
    </a>
    <img src="https://img.shields.io/badge/platform-go-lightgrey.svg?style=flat" alt="platform">
    <img src="https://img.shields.io/badge/license-Apache2-blue.svg?style=flat" alt="Apache 2">
</p>


# Create and deploy a Go microservice with Gin

> We have similar applications available for [Node.js](https://github.com/IBM/nodejs-microservice), [Java Spring](https://github.com/IBM/spring-microservice), [Python Flask](https://github.com/IBM/flask-microservice), and [Java Liberty](https://github.com/IBM/java-liberty-microservice).

In this sample microservice, you will create an application using Gin complete with standard best practices. A microservice is an individual component of an application that follows the **microservice architecture** - an architectural style that structures an application as a collection of loosely coupled services, which implement business capabilities. The microservice exposes a RESTful API matching a [OpenAPI 2.0](https://swagger.io/docs/specification/2-0/basic-structure/) definition.


## Steps

You can [deploy this application to IBM Cloud](https://cloud.ibm.com/developer/appservice/starter-kits/68fb7fbd-13de-3e22-854f-1dfe50f9101e/go-web-app-with-gin) or [build it locally](#building-locally) by cloning this repo first.  Once your app is live, you can access the `/health` endpoint to build out your cloud native application.

### Deploying to IBM Cloud

<p align="center">
    <a href="https://cloud.ibm.com/developer/appservice/starter-kits/68fb7fbd-13de-3e22-854f-1dfe50f9101e/go-web-app-with-gin">
    <img src="https://cloud.ibm.com/devops/setup/deploy/button_x2.png" alt="Deploy to IBM Cloud">
    </a>
</p>

Use the button above to deploy this same application to IBM Cloud.  This option will create a deployment pipeline, complete with a hosted Git lab project and devops toolchain.  You will have the option of deploying to either CloudFoundry or a Kubernetes cluster. [IBM Cloud DevOps](https://www.ibm.com/cloud-computing/bluemix/devops) services provides toolchains as a set of tool integrations that support development, deployment, and operations tasks inside IBM Cloud. 


This microservice comes with the following capabilities:
- [Swagger UI](http://swagger.io/swagger-ui/) running on: `/explorer`
- An OpenAPI 2.0 definition hosted on: `/swagger/api`
- A Healthcheck: `/health`

### Building Locally

To get started building this web application locally, you can either run the application natively or use the IBM Cloud Developer Tools for containerization and easy deployment to IBM Cloud.

All of your `dep` dependencies are stored inside of `Gopkg.toml`.

#### Native Application Development

- Install [Go](https://golang.org/dl/)
- Install [dep](https://github.com/golang/dep)

In order for Go applications to run locally, they must be placed in the correct file path. The application must exist in `$GOPATH/src/gostarter`

Once the Go toolchain has been installed, you can compile a Go project with:

```bash
go install
```

To run your application locally:

```bash
dep ensure
go run server.go
```

Your sources will be compiled to your `$GOPATH/bin` directory. Your application will be running at `http://localhost:8080`.

#### IBM Cloud Developer Tools

Install [IBM Cloud Developer Tools](https://cloud.ibm.com/docs/cli/index.html#overview) on your machine by using the following installation command: `curl -sL https://ibm.biz/idt-installer | bash`.

Your application will be compiled with Docker containers. To compile and run your app, run:

```bash
ibmcloud dev build
ibmcloud dev run
```

This will launch your application locally.  When you are ready to deploy to IBM Cloud on CloudFoundry or Kubernetes, run one of the commands below:

```bash
ibmcloud dev deploy -t buildpack
ibmcloud dev deploy -t container
```

You can build and debug your app locally with:

```bash
ibmcloud dev build --debug
ibmcloud dev debug
```

## Next Steps
* Learn more about augmenting your Go applications on IBM Cloud with the [Go Programming Guide](https://cloud.ibm.com/docs/go).
* Explore other [sample applications](https://cloud.ibm.com/developer/appservice/starter-kits) on IBM Cloud.

## License

This sample application is licensed under the Apache License, Version 2. Separate third-party code objects invoked within this code pattern are licensed by their respective providers pursuant to their own separate licenses. Contributions are subject to the [Developer Certificate of Origin, Version 1.1](https://developercertificate.org/) and the [Apache License, Version 2](https://www.apache.org/licenses/LICENSE-2.0.txt).

[Apache License FAQ](https://www.apache.org/foundation/license-faq.html#WhatDoesItMEAN)
