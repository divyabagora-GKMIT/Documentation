<!-- ```mermaid
erDiagram
    employees {
        int id PK
        enum status "('registered', 'active', 'inactive', 'suspended')"
        varchar(200) name "indexed"
        varchar(200) email "indexed"
        varchar(200) password
        varchar(100) designation
        varchar(15) phone
        varchar(100) address
        date date_of_birth
        varchar(10) gender
        date joining_date
        date created_at 
        date updated_at
        date deleted_at

    }
    departments {
        int id PK
        varchar(50) name "indexed"
        date created_at
        date updated_at
        date deleted_at
    }

    employee_departments{
        int id PK
        int employee_id FK
        int department_id FK
        date created_at 
        date updated_at
        date deleted_at

    }
    roles {
        int id PK
        varchar(10) name
        date created_at 
        date updated_at
        date deleted_at
    }
    employee_roles{
        int id PK
        int employee_id FK
        int role_id FK
        date created_at 
        date updated_at
        date deleted_at
    }


    projects {
        int id PK
        varchar(100) name "indexed"
        date start_date
        date end_date
        enum status "('Active','Completed','Hold')"
        date created_at
        date updated_at
        date deleted_at
    }

    project_members {
       int id PK
       int employee_id FK
       int project_id FK
       varchar(100) project_role
       date start_at
       date end_at
        date created_at
        date updated_at
        date deleted_at
    }

   




    %% -----------------------------
    %% RELATIONSHIPS (Clean format)
    %% -----------------------------

    %% Departments ↔ Employees (1:N)
    departments ||--o{ employees : "many to many"

    %% Employees ↔ Employee_Departments (M:N)
    employees ||--o{ employee_departments : "many to many"
    departments ||--o{ employee_departments : "many to many"

    %% Employees ↔ Roles (M:N)
    employees ||--o{ employee_roles : "many to many"
    roles ||--o{ employee_roles : "many to many"

    %% Employees ↔ Projects (M:N)
    employees ||--o{ project_members : "many to many"
    projects ||--o{ project_members : "many to many"
``` -->
![](./images/mermaid-diagram-2025-11-11-151714.png)