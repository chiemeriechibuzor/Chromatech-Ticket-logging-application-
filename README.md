# ChromaTech ServiceNow ITSM Implementation

ChromaTech Services is a fictional Canadian telecommunications provider managing roughly 1,500 broadcast transmission sites. We built an IT Service Management (ITSM) system from scratch for them to log customer tickets, track network issues, and manage their hardware inventory.

This project covers a full ServiceNow implementation cycle. I handled the database design, foundation data setup, automated testing, and knowledge base routing.

## Tech Stack & Methodologies

* **Platform:** ServiceNow (Shared Personal Developer Instance)
* **Testing:** Automated Test Framework (ATF), Client Test Runner
* **Project Management:** Agile Workflow, ClickUp
* **Concepts:** Relational Database Design, Process Automation, Incident Deflection, Role-Based Access Control (RBAC)

## Architecture & Data Model

We had to customize the underlying data structure to fit the business requirements.

* **Task Inheritance:** I built the `ChromaTech Customer Queries` table by extending the core `Task` table. This kept it integrated with standard ServiceNow workflows.
* **Product Lifecycle Tracking:** I created a standalone `ChromaTech Sold Products` table. It tracks physical hardware data like manufacturing dates, serial numbers, and warranty expiration.
* **Table Relationships:** I set up reference fields to link customer query tickets directly to the physical products causing network issues.

## Core Features & Configurations

* **UI/UX Personalization:** I built multi-column form layouts and separate user views (`ChromaTech Admin` and `ChromaTech Requester`) to surface different data based on the user's role.
* **Foundation Data & Security:** I configured secure groups (`ChromaTech Helpdesk`, `Developers`, `ITIL`) and provisioned accounts for HR, Finance, Sales, and Admin staff.
* **Service Catalog & Request Fulfillment:** We tested departmental workflows by simulating hardware and software requests for each persona.
* **Incident Deflection:** I built a Knowledge Base organized by areas like 'Field Ops' and 'IT Support'. I added meta tags (like `outlook_crash` or `red_light`) so the system suggests articles before a user submits an incident.
* **Instance Branding:** I set up a high-contrast Black, White, and Yellow theme, updated the header, and changed the regional settings to Canada/Mountain time and 24-hour format.

## Quality Assurance & Testing

* **Automated Validation:** Wrote repeatable tests using ServiceNow's Automated Test Framework (ATF) to verify ticket routing and workflow execution.
* **Manual Validation:** Clicked through the UI manually to check system constraints, form layouts, and branding rules.

## Team & Collaboration

I worked as the Developer in a cross-functional agile team of four alongside a Project Manager, Business Analyst, and QA Engineer. We ran the project in ClickUp, tracking seven major epics from planning to deployment. Because of the tight timeline, we engineered the solution concurrently on a shared Personal Developer Instance (PDI).

## Outcomes

The final product was a working ServiceNow instance handling incident tracking and user management. Getting there took more than technical configuration. It required translating business rules into database architecture, testing edge cases, and keeping four people aligned on a single developer instance.

