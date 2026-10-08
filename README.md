# ChromaTech ServiceNow ITSM Implementation

ChromaTech Services is a fictional telecommunications provider managing roughly 1,500 broadcast transmission sites. I built a structured, scalable IT Service Management (ITSM) system for them from scratch to log customer tickets, track network issues, and manage their hardware inventory.

This project covers a full ServiceNow implementation cycle. I handled the database design, foundation data setup, workflow automation, client-side scripting, automated testing, and knowledge base routing.

## Tech Stack & Methodologies

* **Platform:** ServiceNow (Shared Personal Developer Instance)
* **Testing:** Automated Test Framework (ATF), Client Test Runner
* **Project Management:** Agile Workflow, ClickUp
* **Concepts:** Relational Database Design, Process Automation, Incident Deflection, Role-Based Access Control (RBAC), UI Policies, Client Scripts

## Architecture & Data Model

We had to customize the underlying data structure to fit the business requirements.

* **Task Inheritance:** I built the `ChromaTech Customer Queries` table by extending the core `Task` table. This kept it integrated with standard ServiceNow workflows. I configured custom fields for Requester, Contact Type, and First Reported On, inheriting standard task fields like Number, State, and Assignment group.


* **Product Lifecycle Tracking:** I created a standalone `ChromaTech Sold Products` table. It tracks physical hardware data like Product Name, Serial Number, Product Type (Air Conditioners, Coolers, Ceiling Fans), Cost, Manufacturing Date, Date Sold On, Warranty Period, and Warranty Expiring At.


* **Table Relationships:** I set up reference fields to link customer query tickets directly to the physical products causing network issues.



## Core Features & Configurations

* **UI/UX Personalization:** I built multi-column form layouts and separate user views (`ChromaTech Admin` and `ChromaTech Requester`) to surface different data based on the user's role. I also created form sections, grouping date-related fields like Date Sold On, Manufacturing Date, and Warranty dates together for easy review.


* **Application Navigation:** I created a dedicated "ChromaTech Queries" application menu with modules to Create New queries, view All queries, and view All Sold Products.


* **Foundation Data & Security:** I configured secure groups (`ChromaTech Helpdesk`, `Developers`, `ITIL`) and provisioned accounts for HR, Finance, Sales, and Admin staff.
* **Helpdesk Structure:** Set up a dedicated "ChromaTech Helpdesk" group for assignment, as well as specialized technician groups for Air Conditioners, Coolers, and Ceiling Fans.


* **Role-Based Access Control (RBAC):** Configured access rules so requesters only see their own queries and are blocked from seeing internal fields like Assignment Group or Assigned To.



## Business Rules & Workflow Automation

I built automation to reduce manual handling and enforce process controls:

* **Query Initialization:** New queries automatically default to 'New' state, route to the 'ChromaTech Helpdesk' assignment group, and set the approval status to 'Not yet requested'.


* **Approval Controls:** Made the inherited Task Approval field read-only on the `ChromaTech Customer Queries` form so decisions follow workflow logic instead of manual overrides, without affecting the core Task table.


* **Manager Approval Routing:** Automated the approval request trigger to send directly to the Helpdesk Manager before technical work begins.


* **Dynamic Assignment:** Built conditional logic so that once a query is approved, the state changes to 'In Progress' and the ticket is automatically assigned to the correct technician group (Air Conditioners, Coolers, or Ceiling Fans) based on the Product Type.



## Client-Side Scripting & UI Policies

To ensure data integrity on the front end, I implemented Client Scripts and UI Policies on the Sold Products form:

* **Dynamic Warranty Fields:** Built a UI policy to make the "Warranty Extending Date" field visible only when the "Is Extended Warranty" checkbox is ticked.


* **Automated Expiry Calculation:** Wrote an `onChange` client script that watches the 'Date Sold On' and 'Warranty Period (months)' fields. It parses the inputs, adds the months to the start date, and auto-populates the 'Warranty Expiring At' field with the correct timestamp (yyyy-MM-dd HH:mm:ss).


* **Validation Logic:** Added another `onChange` client script to validate warranty extensions. If a user tries to set the 'Warranty Extending Date' to a time before the 'Warranty Expiring At' date, the script triggers a field-level error message and clears the invalid input.



## Quality Assurance & Testing

* **Automated Validation:** Wrote repeatable tests using ServiceNow's Automated Test Framework (ATF) to verify ticket routing and workflow execution.
* **Manual Validation:** Validated end-to-end ticket logging, confirming that query creation, assignments, and product linking functioned as expected.



## Team & Collaboration

I worked as the Developer in a cross-functional agile team of four alongside a Project Manager, Business Analyst, and QA Engineer. We ran the project in ClickUp, tracking major epics from planning to deployment. Because of the tight timeline, we engineered the solution concurrently on a shared Personal Developer Instance (PDI).

## Outcomes

The final product was a working ServiceNow instance handling incident tracking,  automated workflows, and user management. Getting there took more than technical configuration. It required concurrent sprints, translating business rules and user stories into database architecture, enforcing data integrity with client scripts, and working together with the crossfunctional team of four to bring it to live. 

**This project was carried out under the mentorship, guidance, and real life implementation process by CODEKITCHEN poweredby Customizo;Servicenow ElitePartner**
