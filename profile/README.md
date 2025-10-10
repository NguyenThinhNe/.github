# 📑 Warranty Management System

We'll cover the following
+ [Project Overview & Goals](#)
+ [System Requirement](#system-requirement)
+ [Team Roles & Responsibilities](#-team-roles--responsibilities)
+ [Technology Stack](#technology-stack)
+ [System Architecture]()
+ [Database Design](#database-design)
+ [Document References](#document-references)

## 🎯 Project Overview & Goals
ELV Warranty Management System helps local service staff handle warranty requests efficiently and transparently. It allows them to record customer issues, verify warranty eligibility, and submit claims directly to the manufacturer. The system tracks the status of each request—from submission and inspection to approval and replacement—ensuring quick resolution and accurate documentation. By digitizing the entire process, local staff can reduce paperwork, improve communication with the manufacturer, and deliver faster, more reliable service to customers.

<img src="./Resources/logo.png" alt="logo">

## 🔍 System Requirement
We will focus on the following set of requirements while designing:
#### Main Function
##### For SC Technican:
1. SC Technican should be able to login into system.
2. SC Technican should be able to reset password by send a  request password change to admin
3. SC Technican should be able to create a claim request.
4. SC Technican should be able to see list of created claim request.
5. SC Technican should be able to edit a created claim request (can edit if the status is pending).
6. SC Technican should be able to see all work orders.
7. SC Technican should be able to list work orders by status (Pending, In Progress, Completed, Overdue). 
8. SC Techincian should be able to list work by by priority (High, Medium, Low).
9. SC Technician should be able to search work orders by orderID/VehicleName
10. SC Techician should be able to see no result model if no search result found
11. SC Technicican should be able to see details of a work order (Vehicle information, Customer information, Issue Details, Work Details, Schedule, Actions)
12. SC Technician should be able to set action of an work detail (Start working, Complete work)
13. SC Techician should be able to see their basic profile information

##### For SC Staff:
1. SC Staff should be able to login into system.
2. SC Staff should be able to reset password by sending a request password change to admin
3. SC Staff should be able to view all claim requests.
4. SC Staff should be able to view detail of a claim requests.
5. Sc Staff should be able to accept or reject a claim request.
6. Sc Staff should be able to assign a technician worker for an order.
7. SC Staff should be able to list work orders by status (Pending, Assigned, In Progress, Completed).
8. Sc Staff should be able to list all work orders by priority (High, Medium, Low).
9. Sc Staff should be able to search work orders by orderID/VehicleName.
10. Sc Staff should be able to see no result model if no search result found.  
11. Sc Staff should be able to see warranty report (status).
12. Sc Staff should be able to see work reports by status (Pending, In-Progress, Completed, Overdue).
13. Sc Staff should be able to list all work reports by priority (High, Medium, Low).
14. Sc Staff should be able to search work reports by orderID/VehicleName.
15. Sc Staff should be able to see no result model if no search result found.
16. Sc Staff should be able to list all work history/revenue by OrderId/VehicleName
17. Sc Staff should be able to see warranty cost detail of an order.
18. Sc Staff should be able to approved and export report cost of an completed work order.
19. Sc Staff should be able to see their basic profile information.

##### For EVM Staff:
1. EVM Staff should be able to login into system.
2. EVM Staff should be able to reset password by sending a request password change to admin.
3. EVM Staff should be able to view monthly revenue for the services in the center.

## 🧑‍💻 Team Roles & Responsibilities
### Team Structure
| Role              | Name / Placeholder |
| ------------------|:------------------:|
| Back-End Dev      | Nguyễn Phước Thịnh |
| Back-End Dev      | Trương Minh Nhật   |
| Front-End Dev     | Nguyễn Việt Hùng   |
| Front-End Dev     | Phạm Minh Ánh      |
| Front-End Dev     | Hồ Tú Minh Triều   |

### Github Workflow
<img src="./Resources/Github_Workflow.png" alt="Github workflow">

<!-- ## Flow Diagram -->
<!-- <img src="./Resources/Main_Flow.png" alt="Main_Flow">
<img src="./Resources/Detail_Flow.png" alt="Detail_Flow"> -->

## 🛠️ Technology Stack
### Backend
+ .NET 8.0 - Main Framework
+ ASP.NET Core - Web API framework
+ Entity Framework Core - ORM
+ Postgres - Database
+ JWT Authentication - Security
+ Postman - API documentation

### Frontend
+ React 19 - UI library
+ Vite - Build tool
+ Phosphoricons - Icons library

### DevOps
+ Docker - Containerization
+ Kubernetes - Container Orchestration
+ Nginx Proxy Manager - Reverse proxy
+ Jenkins - Continuous Integration
+ ArgoCD - Continuous Delivery

## System Architecture
```
[ Frontend (React) ]
   ↓ REST API calls
[ Backend (ASP.NET Core WebAPI) ]
   ↓
[ Database (PostgreSQL) ]
   ↓
[ File Storage (Local / S3 / MinIO) ]
```

## 🎨 Database Design
Our system will have total 15 Entities:

+ Users: User management and authorization
+ Customer: Customer information
+ CustomerVehicle: Customer vehicle information
+ Campaign: 
+ CampaignType: 
+ ServiceCenter: 
+ WarrantyPolicy: Warranty policy for each part
+ WarrantyClaim: 
+ Report: 
+ ReportType: Type of warranty report
+ WorkOrder: Tasks information for SC Technician
+ VehicleParts: 
+ PartItem: Parts detail information
+ Parts: Parts information
+ Inventory: Parts management

## 📚 Document References
### DevOps & Deployment
+ [🚀 CI/CD Pipeline](CICD.md)
### Project Documentation
+ [⚙️ Project Main Flow](MAIN_FLOW.md)
+ [🗄️ Database Overview](DATABASE.md)

