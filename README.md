# DataTags Recommendation Service

##### EOSC-Hub 

EOSC-hub is the largest implementation project of the European Open Science Cloud (EOSC) initiative. It is a central contact point for European researchers and innovators 
to discover, access, use and reuse a broad spectrum of resources for advanced data-driven research. 

The consortium of 100 partners from more than 50 countries will develop the vision of the Hub as the integration and 
management system of the future European Open Science Cloud. EOSC-hub is the largest implementation project of the European Open Science Cloud (EOSC) initiative. 
It is a central contact point for European researchers and innovators 
to discover, access, use and reuse a broad spectrum of resources for advanced data-driven research. 

#### WP2

The EOSC-Hub WP2 concerns development of DataTags as a service for data support to the EOSC-hub.

## Overview

The service is developed in a generic way; therefore it can be used by any applications that support REST API.

In the sections below more details are provided about:

*	[Architecture](#datatags-architecture)
*   [Open API 3.0 Spec](#datatags-openapi)
*   [Frameworks]()
    *   [swagger-codegen](https://github.com/swagger-api/swagger-codegen)
    *   [Spring Boot](https://spring.io/projects/spring-boot)
    *   [Spring WebFlow](https://docs.spring.io/spring-webflow/docs/current/reference/htmlsingle/)
*   [DataTags Schema](#datatags-schema)
    *   [DANS DataTags Schema](#datatags-schema-dans)
*   [DataTags Schema Creator(GUI)](#datatags-schema-creator)
    *   [Creating DataTags Schema using Zinktree](https://zingtree.com/)
    *   [Creating DataTags Schema using yEd Graph Editor](https://www.yworks.com/products/yed)
*   [Push Plugins]()
*   [Dockerizing the DataTags Service](#datatags-service-docker)
*   [Deploying, Running and Using DataTags Service on Kubernetes](#datatags-kubernetes)
*   [Connecting to DataTags Service](#datatags-connection)
    *   [Dataverse](#datatags-dataverse)
    *   [B2Share](#datatags-b2share)
    *	[Your own application](#datatags-apps)
*   [iRODS Rules Output](https://irods.org/)

### <a name="datatags-architecture"></a>Architecture
The design of the Data Tags Recommendation Service is based on OpenAPI 3.0 specification, Plugins-based architecture and in a generic and reusable way.
![DataTagse-Architecture](readme-imgs/Datatags-Architecture.png "DataTags Service")
The service uses [Spring Boot](https://spring.io/projects/spring-boot) framework that is generated from Open API 3.0 specification by using the [swagger-codegen](https://github.com/swagger-api/swagger-codegen). 
The plugins mechanism is based on the [Java reflection API](https://docs.oracle.com/javase/tutorial/reflect/) that allows [runtime type introspections](https://en.wikipedia.org/wiki/Type_introspection). This increase the flexibility and the application can be dynamically extended to include new features.

### <a name="datatags-openapi"></a>Open API 3.0 Spec
[Open API](https://github.com/swagger-api/swagger-core) is an API Specification framework of the OpenAPI initiative. 
It is an open-source format and initiative for designing and creating machine-readable interface files that are utilized in producing, describing, consuming, and visualizing RESTful APIs and web services. 
With OAS 3.0, both humans and machines can find, view and process the dataset attributes of a REST API without access to the software and without additional documentation.<br/>
The DataTags Recommendation Tool uses OpenAPI-Spec and the server stub is generated by the [swagger-codegen](https://github.com/swagger-api/swagger-codegen) project. 
### Frameworks
The Daatags Recommendation Service uses the following frameworks and technology:
- [Spring Boot](https://spring.io/projects/spring-boot) <br/>
  It is an open source Java-based framework used to create a micro Service. 
- [Spring Web Flow](https://projects.spring.io/spring-webflow/) <br/>
  It is a web framework implemented on top of Spring CoreFramework, which includes Spring MVC. 
  It is a powerful controller for the management of web application page flow.
  
- XSLT
- [iRODS](https://irods.org/)

### <a name="datatags-schema-dans"></a>DANS DataTags Recommendation Schema
![DANS DataTags Schema](readme-imgs/Datatags-2nd-prototype.jpg "DANS DataTags Schema")
![DANS DataTags UI](readme-imgs/DANS-DataTags-Schema.png "DANS DataTags UI")



### <a name="datatags-schema-creator-zinktree"></a>Zinktree Visual Designer

![Zinktree DataTags Schema](readme-imgs/zinktree-visual-designer.png "Zingtree DataTags Schema Creator")

### <a name="datatags-schema-creator-yed"></a>yEd Graph Editor

![Zinktree DataTags Schema](readme-imgs/yed-designer.png "Zingtree DataTags Schema Creator")

### <a name="datatags-service-docker"></a>Dockerizing the DataTags Service
DataTags Recommendation Service Tool has a simple ["Dockerfile"](https://docs.docker.com/reference/builder/) file format that it uses to specify the "layers" of the DataTags Recommendation Service Tool image. 
Although this Dockerfile is very simple, it is all you need to run the DataTags Recommendation Service Toolwithout garnish: just Java and a JAR file.

### <a name="datatags-connection"></a>Connection to DataTag Service

### <a name="datatags-dataverse"></a>Connection to DataTag Service
        {
            "dataTagServiceUrl": "http://localhost:8888/dans/v1", 
            "encryptKey": "@km1-10Dec04",
            "validity-duration": 600   
        }
 
 dataTagServiceUrl = is the        