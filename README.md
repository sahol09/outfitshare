# OutfitShare: Community Clothing-Sharing Platform

A full-stack web app where students and local residents **lend and borrow outfits** for interviews, formal events and
special occasions, cutting clothing waste and cost. Built by a four-person team over four agile sprints.

**Module:** CMPN204 Software Engineering, Year 2 (Spring 2026), University of Roehampton. **Group project mark: 74% (First)**  
**Team TriCode Labs:** S M Saiem Talha (team lead), **Farhan Ahmed Sahol (Requirements & System Design Lead)**,
Yash Chauhan (UI/UX), Enric Landes (UML & documentation). Original team repo: [saiemtalhaa1/TriCode_Labs](https://github.com/saiemtalhaa1/TriCode_Labs)

**Stack:** Node.js · Express · Pug · MySQL 8 · Docker / Docker Compose · bcrypt · express-session · multer · phpMyAdmin

## My contribution
- Wrote the full Sprint 3 build in [`sprint3/`](sprint3): the Express app (~1,200 lines), 25 Pug views, the MySQL schema and seed data, and the Docker setup
- Authentication (bcrypt, sessions), profiles with image upload, listings with search, filters and **"Match My Size"**
- Borrowing workflow: date-validated requests, double-booking prevention, borrower and lender dashboards
- Reward points and listing boosts, notifications inbox, **admin panel** (stats, suspend users, moderate listings and reviews)
- Sprint 1 documents: [code of conduct](docs/code-of-conduct.md) and [ethics](docs/ethical-issues.md)

## Run it
```bash
cd sprint3
docker compose up --build
```
- App: http://localhost:3000 · phpMyAdmin: http://localhost:8080
- Demo logins (seed data, password `password123`): `jane@example.com` (admin), `alex@example.com`, `priya@example.com`

## Repository layout
| Path | Contents |
|---|---|
| [`sprint3/`](sprint3) | Full application (the version described here) |
| [`pg-sd2/`](pg-sd2) | Simpler course-template version used for the required Sprint 3 pages |
| [`docs/`](docs) | Project description and MVP scope, personas, meeting minutes, code of conduct, ethics |

## Fixes after submission (Oct 2026)
Testing the full build against a live database found and fixed:
- **Double booking:** two overlapping *pending* requests could both be approved. Approval now re-checks for clashes
- **Reward points exploit:** re-sending "confirm return" awarded points every time. It now only completes an active loan, once
- Completed or rejected requests could be re-approved. Approve and reject now only act on pending requests
- Borrow requests accepted end dates before start dates and dates in the past
- Seed passwords were stored in plain text, with a plain-text login fallback. They are now bcrypt-hashed, and the fallback has been removed
- The session secret was hard-coded. It now comes from `SESSION_SECRET`, and the session id is regenerated on login

---

## ✨ Key Features

### 👤 Account & Profile Management
- Secure user registration
- Unified account system (users can both borrow and lend)
- Optional profile personalisation (size, height, preferences)
- Profile management dashboard

---

### 👗 Outfit Listings
- Create and manage listings
- Upload images and descriptions
- Add categories and tags
- Set availability dates
- View detailed listing pages

---

### 🔍 Browse & Search
- Community browse page
- Keyword search functionality
- Filter by category, size, and location
- Personalised "Match My Size" filtering
- Clear card-based layout for easy comparison

---

### 🔄 Borrowing Workflow
- Send borrow requests
- Lender approval or rejection
- Request status tracking (Pending, Approved, Rejected, Active, Returned, Completed)
- Automatic double-booking prevention
- Availability slot validation

---

### ⭐ Reviews & Trust System
- Leave ratings and written reviews
- Optional image uploads with reviews
- Separate trust ratings for borrowing and lending behaviour
- Transparent reputation system

---

### 🎁 Giveaway Feature
- List items as giveaways
- Promote sustainability through clothing donation
- Reward environmentally responsible actions

---

### 🏆 Reward & Boost System
- Earn points for successful transactions
- Referral bonus multipliers
- Use reward points to boost listing visibility
- Visually identifiable boosted listings

---

### 🔔 Notifications
- Approval and rejection alerts
- Reward updates
- Referral notifications
- Profile completion reminders
- Transaction updates

---

### 🛡 Admin Moderation
- Moderate listings and reviews
- Remove inappropriate content
- Suspend users if necessary
- Maintain platform safety and governance

---

## 🧱 System Architecture

OutfitShare is built as a full-stack, database-driven web application using:

- **Frontend:** HTML, CSS, JavaScript, PUG
- **Backend:** Node.js, Express.js
- **Database:** MySQL
- **Containerisation:** Docker
- **Version Control:** Git & GitHub

The system follows a modular architecture separating:
- Client Interface
- Backend Application Logic
- Authentication & Trust Modules
- Reward Processing
- Notification Services
- Database Layer

---

## 🎯 Project Goal

The primary goal of OutfitShare is to reduce fashion waste while building a trusted sharing community. By integrating structured workflows, trust ratings, reward incentives, and moderation mechanisms, the platform ensures both usability and reliability.

OutfitShare demonstrates how technology can support sustainability through collaborative consumption and digital trust systems.

---

## 🚀 Status

The project is currently under active development and continues to evolve with new features and refinements.

---

## 📄 License

This project is developed for educational purposes.

---
*Shared as a portfolio piece after marking. Please do not reuse this work in your own assessed coursework.*
