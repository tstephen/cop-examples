# Example repo for public BPMN models and FormIO Forms

Test admin user is admin@example.com with the password ThisIsASimplePassword!

## File layout 

```
  README.md
  forms       <- form.io models
  Models      <- process, decision models to execute in process engine
  postman     <- test resources to exercise the process engine via REST API
```

## Exercising the processes alone

The simplest way is to use the Camunda Modeler to deploy the processes in this project to the all in one docker container. Then use Postman to test them.

1. Download modeler from [Camunda](https://camunda.com/download/modeler/)
2. Start the server
   - `docker pull camunda/camunda-bpm-platform:latest`
   - `docker run -d --name camunda -p 8080:8080 camunda/camunda-bpm-platform:latest`
   - open browser with url: http://localhost:8080/camunda-welcome/index.html
3. Install Postman for REST API testing
4. Import the test harness from the `postman` folder into the Postman app

This now allows you to test the process in isolation because all service tasks are encapsulated in their own non-startable process and these are currently stubbed out. 
