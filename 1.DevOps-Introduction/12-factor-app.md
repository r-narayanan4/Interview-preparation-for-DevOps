# What is the 12-Factor App?

The 12-factor app is a methodology for building modern software-as-a-service (SaaS) applications. It provides a set of best practices aimed at making applications more scalable, maintainable, and portable in cloud-native environments.

## Why do we need it?

Building applications that can scale seamlessly, adapt to changing requirements, and run reliably across different environments is crucial in today's fast-paced development landscape. The 12-factor app methodology helps achieve these goals by promoting standardized practices that facilitate:

- **Scalability**: Applications built following the 12 factors can easily scale horizontally to handle increased loads.
- **Portability**: They can be deployed consistently across various environments, such as development, staging, and production.
- **Maintainability**: By enforcing separation of concerns and clear configuration management, these apps are easier to maintain and update over time.

## The 12 Factors Explained:

1. **Codebase**:
   - *Explanation*: Keep one codebase tracked in version control, but with multiple deployments.
   - *Example*: Your ToDoList application's code is stored in a Git repository. This single codebase can be deployed to different environments like development, staging, and production.

2. **Dependencies**:
   - *Explanation*: Explicitly declare and isolate dependencies.
   - *Example*: Your ToDoList app relies on Express.js and MongoDB. These dependencies are declared in the package.json file, allowing for easy management using npm or yarn.

3. **Config**:
   - *Explanation*: Store configuration in the environment, not in the code.
   - *Example*: The MongoDB connection string is stored as an environment variable named `MONGODB_URI`. This allows you to configure the database connection without modifying the code.

4. **Backing Services**:
   - *Explanation*: Treat backing services (databases, queues, caches, etc.) as attached resources.
   - *Example*: Your ToDoList app uses MongoDB as a backing service. Instead of hardcoding the database connection details in the code, it connects dynamically using the `MONGODB_URI` environment variable.

5. **Build, Release, Run**:
   - *Explanation*: Strictly separate build, release, and run stages.
   - *Example*: Your CI/CD pipeline automates the process of building, testing, and deploying the ToDoList app. Changes pushed to the main branch trigger the pipeline, ensuring consistent deployments.

6. **Processes**:
   - *Explanation*: Execute the app as one or more stateless processes.
   - *Example*: The ToDoList app runs as stateless processes managed by a process manager like PM2. Each instance is independent and can be easily scaled horizontally.

7. **Port Binding**:
   - *Explanation*: Export services via port binding.
   - *Example*: The ToDoList app exports its services via port binding. It listens for HTTP requests on port 3000 in development and port 80 in production.

8. **Concurrency**:
   - *Explanation*: Scale out via the process model.
   - *Example*: Horizontal scaling is achieved by adding more instances of the ToDoList app behind a load balancer as traffic increases.

9. **Disposability**:
   - *Explanation*: Maximize robustness with fast startup and graceful shutdown.
   - *Example*: The ToDoList app is designed to start up quickly and shut down gracefully. It handles failures gracefully and terminates connections properly when shutting down.

10. **Dev/Prod Parity**:
    - *Explanation*: Keep development, staging, and production as similar as possible.
    - *Example*: Development, staging, and production environments are kept similar using Docker containers. This ensures consistency and reduces the risk of bugs.

11. **Logs**:
    - *Explanation*: Treat logs as event streams.
    - *Example*: The ToDoList app generates logs for events like user actions and errors. These logs are sent to a centralized logging service like Loggly for real-time monitoring and analysis.

12. **Admin Processes**:
    - *Explanation*: Run admin/management tasks as one-off processes.
    - *Example*: Database migrations are run as one-off processes separate from the main application. This ensures data consistency without affecting the running app.
