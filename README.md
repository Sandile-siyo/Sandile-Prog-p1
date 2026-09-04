#  RaceDay System – README

## Overview
The **RaceDay system** is a web-based event management platform designed for running and cycling events in South Africa.  
It allows **organisers** to create and manage events, routes, categories, and results, while **participants** can register, enrol, and track their performance history

The system is built with:
- A **relational database** (SQL Server) (Connolly & Begg, 2015)  
- A **RESTful API** with role-based access (Fielding, 2000)  
- An **Entity Relationship Diagram (ERD)** for clear data modelling (Elmasri & Navathe, 2016)  

---

## Database Design
The database contains six core tables:

- **Organiser** – stores organiser details.  
- **Event** – records event information linked to organisers.  
- **Route** – describes event routes.  
- **Weather** – stores forecasts for events.  
- **Participant** – holds participant details.  
- **Registration** – connects participants to events with status and date.  

Each table uses **primary keys (PK)** and **foreign keys (FK)** to enforce relationships (Date, 2004).

---

## Entity Relationship Diagram (ERD)
The ERD shows how entities are connected:

- Organisers manage multiple events.  
- Events link to routes, categories, and weather forecasts.  
- Participants register for events through the registration entity.  
- Results are recorded per participant and category.  

This ensures **data integrity** and supports efficient queries (Fowler, 2003).

---

## API Endpoints
The REST API provides secure access for organisers and participants:

- **Authentication**: Register and login users.  
- **User Profile**: View and update participant details.  
- **Events**: Create, update, delete, and retrieve events.  
- **Categories**: Manage race categories per event.  
- **Enrolments**: Register participants for events and manage enrolments.  
- **Results**: Record, update, and retrieve race results.  

Role-based access ensures organisers and participants have the correct permissions (REST API Tutorial, 2026).

---

## Example Usage
- A participant registers via `/api/auth/register` and logs in with `/api/auth/login`.  
- They enrol in an event using `/api/events/{eventId}/enrolments`.  
- Organisers create events with `/api/events` and record results using `/api/events/{eventId}/results`.  
- Participants can later view their performance history via `/api/users/me/results`.  

---

## Conclusion
The RaceDay system integrates a **structured database**, a **clear ERD**, and a **role-based API** to provide a complete solution for event management.  
It ensures organisers can manage events professionally, while participants enjoy a seamless way to register, enrol, and track their race results (Microsoft Docs, 2026).

---

## References
- Connolly, T. & Begg, C. (2015) *Database Systems: A Practical Approach to Design, Implementation, and Management*. 6th ed. Harlow: Pearson Education.  
- Elmasri, R. & Navathe, S.B. (2016) *Fundamentals of Database Systems*. 7th ed. Boston: Pearson  
- Date, C.J. (2004) *An 
- Fowler, M. (2003) *UML Distilled: A Brief Guide to the Standard Object Modeling Language*. 3rd ed. Boston: Addison-Wesley.  
- Fielding, R.T. (2000) *Architectural Styles and the Design of Network-based Software Architectures*. Doctoral dissertation, University of California, Irvine.  
- Microsoft Docs (2026) *SQL Server Documentation*. Available at: https://learn.microsoft.com/sql/ (Accessed: 4 September 2026).  
- REST API Tutorial (2026) *REST API Design Best Practices*. Available at: https://restfulapi.net/ (Accessed: 4 September 2026).  
