## Functional Requirements

---

### FR-1: User Authentication

| **Field** | **Description** |
|------------|----------------|
| **Description** | Users must be able to log in securely using their credentials. The system should verify identity before granting access to restricted modules. |
| **Inputs** | Username/email and password. Optionally, MFA code (if enabled). |
| **Outputs** | Successful login → Redirect to dashboard; Failed login → Display error message. |
| **Acceptance Criteria** | Unauthorized users cannot access restricted pages; passwords must be encrypted; account locked after defined failed attempts. |

---

### FR-2: Employee Data Management

| **Field** | **Description** |
|------------|----------------|
| **Description** | The system must allow Admin and HR to store, edit, update, and retrieve employee data, including personal and job details. |
| **Inputs** | Employee ID, name, department, designation, contact info, joining date, etc. |
| **Outputs** | Confirmation message for add/update/delete actions; employee profile view. |
| **Acceptance Criteria** | Employee ID must be unique; only authorized roles can modify records; all changes logged for audit. |

---

### FR-3: Department Management

| **Field** | **Description** |
|------------|----------------|
| **Description** | Manage department details and associate employees with their respective departments. |
| **Inputs** | Department name, code, description, and head of department. |
| **Outputs** | List of departments and their associated employees. |
| **Acceptance Criteria** | Departments cannot be deleted if employees are assigned; department codes must be unique. |

---

### FR-4: Project Management

| **Field** | **Description** |
|------------|----------------|
| **Description** | Maintain information about ongoing projects and the employees assigned to them, including their roles in each project. |
| **Inputs** | Project name, ID, description, assigned employees, start/end dates, role in project. |
| **Outputs** | Project list with employee associations and assigned roles. |
| **Acceptance Criteria** | Each project must have at least one assigned employee; employees cannot be assigned to inactive projects. |

---

### FR-5: Role-Based Access Control (RBAC)

| **Field** | **Description** |
|------------|----------------|
| **Description** | Control system access and privileges based on predefined roles (Admin, HR, Employee). |
| **Inputs** | Role definitions and permissions matrix. |
| **Outputs** | Grant or deny access; log access violations. |
| **Acceptance Criteria** | - Employee: Can view only their profile.<br> - HR/Admin: Can view and manage all records.<br> - Unauthorized actions are denied and logged. |
