# **Functional Requirement**

## **Author:** Divya Bagora

---

## **Overview**

This document outlines the **Functional Requirements** for the **Employee Management System (EMS)**.  
The EMS is a role-based web application that allows organizations to efficiently manage employee details, departmental structures, project management, and user permissions.

It ensures **secure access control** — only authorized users (like HR or Admin) can modify sensitive data such as employee records or department configurations.

---

## **Features**

### **In Scope**

- **User Login & Profile Management**  
  Enables secure authentication using JWT and allows users to view and update their personal profiles.

- **Employee Management**  
  Admin and HR can add, update, or deactivate employee records with role-based permissions.

- **Department Management**  
  Supports creation and assignment of employees under specific departments for structured hierarchy.

- **Project Management**  
  Allows creation, tracking, and assignment of projects to employees, including project status monitoring.

- **Role-Based Access Control (RBAC)**  
  Restricts and manages user actions based on assigned roles such as Admin, HR, or Employee.

---

### **Future Scope**

1. **Leave Management**  
   Employees can submit leave requests which will be reviewed and approved or rejected by HR or Admin.

2. **Salary Details**  
   Automate salary calculation and manage payroll data based on attendance, leaves, and performance metrics.

3. **Feedback System**  
   Implement a structured feedback mechanism for performance reviews and peer evaluations.

4. **Enhanced Project Management with Time Tracking & Cost Estimation**  
   Introduce an advanced **module-based time and cost tracking system**, where:  
   - The **Project Manager** assigns specific working hours for each project module to the respective developers.  
   - Developers must log their work hours through a **timesheet** within the assigned limits.  
   - If a developer attempts to log hours **beyond the assigned quota**, the system restricts it automatically.  
   - The **Project Manager** can increase the allocated hours when needed, and the system records this update — e.g.:  
     *"Assigned hours updated from 20 to 25 for Module X by Project Manager."*  
   - Along with time tracking, the system will automatically **calculate the project’s cost** by multiplying each developer’s **hourly rate (derived from their salary)** with the **assigned hours** for that module.  
   - The **total project cost** will be the sum of all module costs, enabling accurate **budget estimation**, **expense tracking**, and **profitability analysis**.  
   - These logs will help the management monitor whether the project is on track to meet its **time and budget deadlines**.

---


## **Functional Requirements**

---

### **FR-1: User Authentication**

| **Field** | **Description** |
|------------|----------------|
| **Description** | Users must be able to log in securely using their credentials. The system should verify identity before granting access to restricted modules. |
| **Inputs** | Username/email and password.  |
| **Outputs** | Successful login → Redirect to dashboard, Failed login → Display error message. |
| **Acceptance Criteria** | Unauthorized users cannot access restricted pages; passwords must be encrypted; account locked after defined failed attempts. |

---

### **FR-2: Employee Data Management**

| **Field** | **Description** |
|------------|----------------|
| **Description** | The system must allow Admin and HR to store, edit, update, and retrieve employee data, including personal and job details. |
| **Inputs** | Employee ID, name, department, designation, contact info, joining date, etc. |
| **Outputs** | Confirmation message for add/update/delete actions & employee profile view. |
| **Acceptance Criteria** | Employee ID must be unique & only authorized roles can modify records. |

---

### **FR-3: Department Management**

| **Field** | **Description** |
|------------|----------------|
| **Description** | Manage department details and associate employees with their respective departments. |
| **Inputs** | Department name, code, description, and head of department. |
| **Outputs** | List of departments and their associated employees. |
| **Acceptance Criteria** | Department codes must be unique. |

---

### **FR-4: Project Management**

| **Field** | **Description** |
|------------|----------------|
| **Description** | Maintain information about ongoing projects and the employees assigned to them, including their roles in each project. |
| **Inputs** | Project name, ID, description, assigned employees, start/end dates, role in project. |
| **Outputs** | Project list with employee associations and assigned roles. |
| **Acceptance Criteria** | Each project must have at least one assigned employee,  employees cannot be assigned to inactive projects. |

---

### **FR-5: Search Functionality**

| **Field** | **Description** |
|------------|----------------|
| **Description** | Users should be able to search employees, departments, and projects from the dashboard. |
| **Inputs** | Search text (name, email, or project title). |
| **Outputs** | Show matching results with basic info. If no match, show *“No records found.”* |
<!-- | **Acceptance Criteria** | - Supports partial and case-insensitive search.<br>- Results load quickly (within 2 seconds).<br>- Unauthorized users cannot view restricted data. | -->

---

### **FR-6: Role-Based Access Control (RBAC)**

| **Field** | **Description** |
|------------|----------------|
| **Description** | Control system access and permissions based on predefined roles (**Admin**, **HR**, **Employee**). In future iterations, users will be assigned multiple roles such as **User**, **HR**, and **Admin**, each with distinct access levels and permissions. When an **HR** user performs actions like submitting **leave requests** or providing **feedback**, they will temporarily act as an **Employee**, following employee-level permissions for those specific modules. |
| **Inputs** | Role definitions and permissions. |
| **Outputs** | Grant or deny access. |
| **Acceptance Criteria** | - **Employee:** Can view only their profile.<br> - **HR/Admin:** Can view and manage all records.<br> - **Unauthorized actions:** Are denied and logged. |

---

## **Non-Functional Requirements**

1. **Security:** Encryption for sensitive data like passwords.  
2. **Optimized:** The system should perform efficiently and handle concurrent requests gracefully.  

---

## **Technical Requirements**

### **Backend**
- **Framework:** Node.js with Express *(REST API)*  
- **Authentication:** JWT *(JSON Web Tokens)*  
- **Database:** PostgreSQL *(Relational data model)*  
- **Encryption:** bcrypt for password hashing  

---

### **Frontend**
- **Framework:** React.js  
- **UI Components:** Material UI or TailwindCSS  
- **API Handling:** Axios or Fetch API  
- **Routing:** React Router  

---



