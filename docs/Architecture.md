# CivicSync - Architecture Document

## 1. High-Level Architecture

CivicSync follows a three-tier architecture:

Citizen / Officer / Admin
↓
React Frontend
↓
Spring Boot REST API
↓
MySQL Database

The frontend communicates with the backend using REST APIs. The backend handles business logic, authentication, complaint management, officer assignment, notifications, and analytics. Data is stored in MySQL.

---

## 2. Backend Architecture

Technology Stack:

* Java 21
* Spring Boot
* Spring Security
* JWT Authentication
* Spring Data JPA
* MySQL

Layers:

Controller Layer

* Receives HTTP requests
* Returns API responses

Service Layer

* Contains business logic
* Complaint processing
* Assignment logic
* Analytics calculations

Repository Layer

* Database access using JPA

Database Layer

* Stores users, complaints, departments, assignments, and notifications

---

## 3. Frontend Architecture

Technology Stack:

* React
* React Router
* Axios
* Bootstrap

Modules:

* Authentication
* Citizen Dashboard
* Officer Dashboard
* Admin Dashboard
* Analytics Dashboard

Frontend communicates with backend APIs using Axios.

---

## 4. User Roles

### Citizen

* Register/Login
* Create Complaint
* Track Complaint
* Edit Complaint (before assignment)
* View Notifications

### Officer

* View Assigned Complaints
* Update Complaint Status
* Add Resolution Notes

### Admin

* Manage Officers
* Manage Departments
* Assign Complaints
* Monitor Analytics
* Generate Reports

---

## 5. Complaint Lifecycle

SUBMITTED
↓
ASSIGNED
↓
IN_PROGRESS
↓
RESOLVED
↓
CLOSED

Lifecycle Description:

SUBMITTED

* Complaint created by citizen.

ASSIGNED

* Complaint assigned to officer.

IN_PROGRESS

* Officer is working on complaint.

RESOLVED

* Officer marks complaint as resolved.

CLOSED

* Citizen/Admin confirms resolution and closes complaint.
