Checkpoint 2 - Research: Multi-Tier Architecture
1. What is a Two-Tier Architecture?
A Two-Tier Architecture is a system design that separates an application into two main parts: the Web/Application Tier and the Database Tier. Each tier has its own responsibility and communicates with the other to provide the required services to users.

2. Components of a Two-Tier Architecture
Tier	Role	Example
Web/Application Tier	Displays the user interface, handles HTTP requests, processes application logic, and communicates with the database.	Web server running PHP and Apache
Database Tier	Stores and manages persistent data, such as user accounts, passwords, products, and transactions.	MySQL database server
A. The Web/Application Tier
The Web/Application Tier is responsible for handling user interactions and processing requests from the browser. It displays web pages, executes application logic, and sends queries to the Database Tier when data needs to be retrieved or saved.

B. The Database Tier
The Database Tier is responsible for storing, organizing, and managing the application's data. It keeps information such as user accounts, product details, and transaction records so that the data remains available when needed.

3. Why Separate Them?
Separating the web server and database into two containers makes the application easier to manage, update, and maintain because each service can operate independently. It also improves security by allowing database access to be restricted and enables each tier to be scaled or restarted without necessarily affecting the other. Compared with placing both services in one container, this separation provides better organization and makes troubleshooting easier.

4. Architecture Diagram
       +----------------------+
       |         User         |
       |      Web Browser     |
       +----------+-----------+
                  |
              HTTP Request
                  |
                  v
       +----------------------+
       |  Web/Application     |
       |        Tier          |
       |   Web Server (PHP)   |
       |   Container 1        |
       +----------+-----------+
                  |
             Database Query
                  |
                  v
       +----------------------+
       |     Database Tier    |
       |    MySQL Server      |
       |    Container 2      |
       +----------------------+
                  |
                  v
          Persistent Data
5. Conclusion
A Two-Tier Architecture separates the web application from the database into two distinct components. Using separate containers improves organization, security, maintenance, and scalability while allowing both tiers to communicate to provide the application's services.
