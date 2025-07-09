
# Schema Architecture

This spring boot application uses MVC and REST controllers. Thymeleaf templating engine is used for the Doctor and Admin
dashboards and RESTful APIs power all CRUD operations. The application leverages MySQL for its relational database
capabilities and MongoDB for unstructured data like prescriptions. All controllers route request through a common
service layer, which then delegates to the appropriate repositories. MySQL uses JPA entities while MongoDB uses document
models.

1. User accesses AdminDashboard or Appointment pages.
2. The action is routed to the appropriate Thymeleaf or REST controller.
3. The controller calls the service layer that handles business logic.
4. The service layer communicates with MySQL or MongoDB repositories.
5. The repositories perform CRUD operations on the database leveraging JPA or MongoDB drivers.
6. The results are returned to the service layer.
7. The service layer processes the results and returns them to the controller.