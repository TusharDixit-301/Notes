# Installation 
- `npm i -g @nestjs/cli` use to install the nest cli globally; if you're having this, you don't need to run it again.
- `nest new <app_name>`  use to create a new nest app.

# Setting up the controllers
- *app.controller.ts* file contains the logic for controllers, and in controllers, we set up the API routes or Endpoints.
- `:<variable>` It is used for dynamic end points.
-  `@Param("<variable>")` It is used to extract the dynamic args passed in the url, **Example**
```ts
 @Get()
	// type is giving whether it is of income or expense
  getAllReports(@Param('type') type: string) {
    const reportType =
      type === 'income' ? ReportType.INCOME : ReportType.EXPENSE;
    return data.report.filter((item) => item.type === reportType);
  }
```
- Controller is just for creating endpoints and receiving body , we should not put our business logic in it.
-  For validating our input we use **Pipes**. Example: `ParseUUIDPipe`
-  Setup different controllers:
	-  `nest g module <module name>`
	-   `nest g controller <controller name>`
## Pipes: 
- Enum pipes are used as this :  `new ParseEnumPipe(<EnumType>)`
- `$ npm i class-validator class-transformer`


# Setting up the services
- *app.service.ts*  file contains the logic for services, and in services file we write all our business logic.