# 🎓 Internship & Academic Project Management System

<center><img width="172" height="43" alt="logo" src="https://github.com/user-attachments/assets/4728d696-51fb-4ba6-83f2-6992cfcd64a0" /></center>

<img width="512" height="620" alt="Login" src="https://github.com/user-attachments/assets/df64c336-7c22-40ed-9758-4bb345550079" />

<img width="1912" height="1693" alt="DashboardHome" src="https://github.com/user-attachments/assets/ef7273e5-a00f-4331-b279-0c9d7bc4317e" />


<img width="2048" height="512" alt="Gemini_Generated_Image_uyfczouyfczouyfc" src="https://github.com/user-attachments/assets/605e328b-b38a-4a9b-a963-fe237ec969b9" />

<img width="1912" height="1055" alt="add newUser" src="https://github.com/user-attachments/assets/9e4f4e59-060f-414a-bf91-7c839778cc3e" />


## 📌 Overview

This project is a **web-based management platform** designed to streamline the handling of **internships, academic projects, and official documents** within an academic institution. It supports the full lifecycle of internships and final-year projects (PFE), including documentation, validation processes, and stakeholder communication.

Built with **NestJS**, **Angular**, **Tailwind CSS**, and **TypeORM**, the system provides a modern, modular, and secure architecture that serves both administrative staff and students efficiently. The platform is containerized using **Docker** for easy deployment and scalability.

---

## ⚙️ Features

### 🧑‍🎓 Student & Internship Management
- Manage **mandatory** and **optional internships** with constraints (e.g., only one mandatory per final year).
- Link **academic projects (PFEs)** to 1 or 2 students.
- Support **multiple optional internships** with flexible configurations.

### 📄 Document Workflow & Signatures
- Create and manage **document templates** with dynamic content sections.
- Generate documents with **automatic headers, footers, and page breaks**.
- Upload and validate **electronic signatures** (handwritten image).
- Admin validation for each signed document.

### 🧠 AI & OCR Integration
- Use of **TinyLLaMA** for intelligent content suggestions and document enhancement (experimental).
- **Tesseract.js** for optical character recognition (OCR) to extract text from scanned PDFs.
- Integration of **PDF.js** and **Page.js** for advanced document rendering and navigation in the browser.

### 🏢 Companies & Academic Staff
- Manage and assign **company supervisors** and **academic tutors**.
- Handle multi-party approvals for internships and PFEs.

### 📬 Notification & Validation Process
- Track document statuses (pending, signed, validated).
- (Optional) **Email OTP verification** for document confirmations (coming soon).

### 💬 Real-time Chat (Planned)
- WebSocket-based **real-time messaging system** between students, tutors, and admins.
- **Redis** is used for scalable real-time communication and session management.

---

## 🧱 Tech Stack

| Layer         | Technology                               |
|--------------|-------------------------------------------|
| Frontend     | Angular, Tailwind CSS                     |
| Backend      | NestJS, TypeORM                           |
| AI & OCR     | TinyLLaMA, Tesseract.js                   |
| Document Tools | PDF.js, Page.js                          |
| Database      | PostgreSQL, Redis                         |
| Real-Time     | WebSockets + Redis                        |
| Deployment    | Docker (containerized), on-premise server|

---

## 🗃 Database Design Highlights

- Robust relational schema supporting **internships, projects, students, tutors, companies, and documents**.
- Constraints and relationships tailored to **academic business rules** (e.g., unique mandatory internship per student).
- Easily extendable for new academic use cases.

---

## 🗓 Project Scope & Deployment

- Designed for deployment on a **university-managed server** (2016 hardware).
- Focused on **internal scalability, reliability, and document traceability**.
- No need for external user training; intuitive UI for staff and students.
- 
## 🗃 Database Design Highlights

- **Relational Schema**: Supports core entities (`students`, `internships`, `academic_work`, `documents`, `signatures`) with constraints enforcing academic business rules (e.g., one mandatory internship per student, multi-party approvals).
- **Department Management**: Uses a `departments` table for flexibility in adding/renaming departments. Teachers can belong to multiple departments via a `teacher_departments` junction table (e.g., a math teacher in data science and mechanics).
- **Signature Workflow**: Supports `manual`, `digital`, and future `biometric` signatures, with validation and audit trails. Biometric signatures are planned but not yet implemented.
- **Messaging System**: Planned WebSocket-based real-time chat (group and one-on-one) with persistent storage in PostgreSQL. Redis handles notifications and session management.
- **Chatbot Integration**: Standalone TinyLLaMA-powered chatbot for document enhancement and student queries, with stored interactions for auditing and analytics. Future integration with messaging is possible.
- **Document Types**: Fixed set of document types (e.g., internship agreements, PFE reports) defined via an ENUM, with 19 types currently planned (to be finalized).
- **OTP Verification**: Supports email OTPs for document confirmations, user authentication, and other processes (TBD).
- **Performance Optimizations**: Indexes on high-traffic columns (e.g., `users.email`, `internships.student_id`) and partitioning for audit logs to handle 500+ students, 100–200 internship requests, and 1000+ documents.
- **Extensibility**: Modular design with nullable fields (e.g., `defenses.jury_evaluation_id`) and comments for maintainability, supporting future features like additional document types or chatbot enhancements.

## 🗓 Project Scope & Deployment


- **Target Environment**: Designed for deployment on a university-managed server (potentially upgraded from 2016 hardware). Optimized for moderate data volumes (500+ students, 100–200 concurrent internship requests, 1000+ documents).
- **Scalability**: Indexes, partitioning, and materialized views ensure performance during peak periods (e.g., internship request surges).
- **Traceability**: Audit logs and persistent message/chatbot storage ensure compliance with academic governance.
- **Usability**: Intuitive UI for staff and students, with no external training required.
