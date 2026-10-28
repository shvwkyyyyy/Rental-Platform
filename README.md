# Project Description: Rental Marketplace Platform

## 1. Executive Summary & Vision

The **Rental Marketplace Platform** is an enterprise-grade, peer-to-peer (P2P) digital ecosystem designed to connect item owners with renters securely, transparently, and efficiently. Operating initially as an MVP focused in **Alexandria, Egypt**, and targeting high-value technology devices (cameras, laptops, gaming consoles, and audio equipment), the platform facilitates transactions entirely in **Egyptian Pounds (EGP)**.

Acting strictly as a technology intermediary, the platform provides robust escrow mechanisms for refundable security deposits, guided physical inspection workflows, structured dispute resolution, and immutable audit trails, ensuring trust and legal compliance without owning or inspecting physical items directly.

## 2. Core Operational Pillars

* **Approval-First Booking Workflow:** Renters submit reservation requests, but payments are triggered *only* after explicit Owner approval, locking calendar availability atomically to prevent double-booking.

* **Segregated Escrow & Payments:** Integration with PCI-DSS compliant payment gateways (Paymob/Fawry) to handle secure EGP transactions, itemized checkouts (Rental Fee, Platform Service Fee, and Refundable Security Deposit), and escrow management.

* **Trust, Safety & Identity Protection:** Multi-tier verification spanning Email, Phone OTP, and National ID verification reviewed by Admins. National IDs are stored securely using AES-256 encryption with short-lived pre-signed URLs and dynamic administrative watermarking.

* **Progressive Enforcement & Dispute Adjudication:** Structured workflows for warnings, restrictions, temporary suspensions, and permanent identity-based bans. Disputes are triaged by Support Agents and adjudicated exclusively by Admins using immutable on-platform evidence (chat logs, check-in/check-out condition photos).

* **AI & Data Science Integration:** Built-in intelligence featuring Policy RAG (grounded in a 13-chapter Policies Book), AI Smart Pricing, Smart Deposit estimation, Risk/Fraud scoring, Damage Detection, and Recommendation Engines with a strict "Human-in-the-Loop" policy for serious sanctions.

## 3. Architecture & Tech Stack Highlights

* **Backend Services:** Modular RESTful APIs adhering to clean architecture principles, OpenAPI 3.0 documentation, and RFC 7807 error handling standards.

* **Database & State Management:** Relational database with spatial indexing (PostGIS support) for geographic discovery and strict ACID-compliant state machine lifecycle enforcement.

* **Security:** Deny-by-default role-based access control (RBAC), Argon2id/bcrypt password hashing, short-lived JWT tokens, and an append-only immutable audit logging system.

##  Repository Structure

```text
rental-marketplace-platform/
│
├── .github/                      # GitHub automation workflows & PR templates
│   └── workflows/
│       └── ci.yml                # CI/CD pipeline for automated testing and builds
│
├── docs/                         # Project documentation and system design
│   ├── architecture/
│   │   ├── system-architecture.png # Overall system architecture diagram
│   │   ├── c4-model/             # C4 model diagrams (Context, Containers, etc.)
│   │   └── sequence-diagrams/    # Core sequence diagrams (Booking, Payments, Disputes)
│   ├── database/
│   │   ├── er-diagram.png        # Entity Relationship Diagram (ERD)
│   │   └── schema-design.sql     # Initial database schema and table definitions
│   ├── api/
│   │   └── swagger-openapi.yaml  # Initial API contracts (Contract-First Design)
│   └── policies/
│       └── policies-book.md      # Platform policies book and business rules (13 chapters)
│
├── src/                          # Actual source code
│   ├── backend/                  # Backend services and APIs
│   ├── frontend/                 # Client interfaces (Web / Mobile apps)
│   └── ai-ml/                    # AI/ML models & data science modules (Policy RAG, Smart Pricing, Risk Scoring)
│
├── .gitignore                    # Excluded files (e.g., .env, node_modules, virtual environments)
├── README.md                     # Main repository landing page
└── LICENSE                       # Project license

