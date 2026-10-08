
# Case Study: ChromaTech ServiceNow ITSM Implementation

## 📌 Project Overview

ChromaTech Services is a fictional Canadian telecommunications company that manages approximately 1,500 broadcast transmission sites. The objective of this project was to implement a robust IT Service Management (ITSM) system from the ground up to log customer tickets, track network issues, and manage product inventory.

This project demonstrates end-to-end ServiceNow implementation capabilities, from database design and foundation data setup to automated testing and knowledge base deflection.

## 🛠️ Tech Stack & Methodologies

* **Platform:** ServiceNow (Shared Personal Developer Instance)


* **Testing:** Automated Test Framework (ATF), Client Test Runner


* **Project Management:** Agile Workflow, ClickUp


* **Concepts:** Relational Database Design, Process Automation, Incident Deflection, Role-Based Access Control (RBAC)



## 🏗️ Architecture & Data Model

To accurately capture the business requirements, the underlying data structure was customized:

* **Task Inheritance:** Built the `ChromaTech Customer Queries` table by extending the core `Task` table to ensure seamless integration with standard ServiceNow workflows.


* **Product Lifecycle Tracking:** Created a standalone `ChromaTech Sold Products` table to track critical hardware data, including manufacturing dates, serial numbers, and warranty expiration timelines.


* **Table Relationships:** Established reference fields to link customer query tickets directly to the physical products affected by network issues.



## ⚙️ Core Features & Configurations

* **UI/UX Personalization:** Designed multi-column form layouts and built distinct user views (`ChromaTech Admin` vs. `ChromaTech Requester`) to surface relevant data based on user roles.


* **Foundation Data & Security:** Configured secure groups (e.g., `ChromaTech Helpdesk`, `Developers`, `ITIL`) and provisioned personas across HR, Finance, Sales, and Admin departments.


* **Service Catalog & Request Fulfillment:** Validated departmental workflows by simulating persona-specific hardware and software requests.


* **Incident Deflection:** Designed a Knowledge Base categorized into areas like 'Field Ops' and 'IT Support'. Integrated meta tags (e.g., 'outlook_crash', 'red_light') to trigger proactive article suggestions during incident logging, significantly promoting ticket deflection.


* **Instance Branding:** Aligned the platform with corporate identity by applying a high-contrast Black, White, and Yellow theme, updating the header to "Towards more innovation," and configuring regional parameters (Canada/Mountain time zone, 24-hour format).



## 🧪 Quality Assurance & Testing

* **Automated Validation:** Leveraged ServiceNow's Automated Test Framework (ATF) to build consistent, repeatable tests for ticket routing and workflow execution.


* **Manual Validation:** Conducted manual UI validation to handle system constraints and verify form layouts and branding rules.



## 🤝 Team & Collaboration

Serving as the Developer in a cross-functional agile team of four (including a Project Manager, Business Analyst, and QA Engineer), collaboration was key.

* **Task Management:** Utilized ClickUp to track 7 major epics, from project coordination to deployment.


* **Real-Time Development:** Engineered the solution collaboratively on a shared Personal Developer Instance (PDI) within a tight timeline.



## 💡 Key Learnings & Outcomes

This implementation successfully delivered a cohesive, functioning ServiceNow instance capable of handling complex incident tracking and user management. The process reinforced that successful system implementation requires more than just technical configuration; it demands meticulous business process translation, rigorous automated testing, and cross-functional alignment.
