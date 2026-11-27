# LPU Hostel Allocation & Roommate Matching System

<div align="center">

<img src="public/images/lpu/lpu-logo-media.png" alt="Lovely Professional University Logo" width="180" />

### **Official-Style Smart Residential & Roommate Matching Portal for Lovely Professional University**

[![Next.js](https://img.shields.io/badge/Next.js-14.2-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-18-blue?style=for-the-badge&logo=react)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-22-green?style=for-the-badge&logo=node.js)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-7-green?style=for-the-badge&logo=mongodb)](https://www.mongodb.com/)
[![Express](https://img.shields.io/badge/Express-4-grey?style=for-the-badge&logo=express)](https://expressjs.com/)

[ Live Demo](https://hostelallocationlpuproject.vercel.app/) â€¢ [ Documentation](#project-structure) â€¢ [ Report Bug](https://github.com/vaishnavi339/HostelRoomAllocationSystem/issues) â€¢ [ Request Feature](https://github.com/vaishnavi339/HostelRoomAllocationSystem/issues)

</div>

---

## Table of Contents

- [Overview](#-overview)
- [Key Highlights & Latest Updates](#-key-highlights--latest-updates)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Module Architecture](#-module-architecture)
- [Installation & Setup](#-installation--setup)
- [Usage Guide](#-usage-guide)
- [API Documentation](#-api-documentation)
- [LPU Campus & Hostel Gallery Preview](#-lpu-campus--hostel-gallery-preview)
- [Vercel Deployment](#-vercel-deployment)
- [Contributing](#-contributing)
- [License](#-license)

---

## Overview

The **LPU Hostel Allocation & Roommate Matching System** is a full-stack residential portal built for **Lovely Professional University (Jalandhar â€“ Delhi G.T. Road, Phagwara, Punjab)**. It streamlines hostel booking across **Boys Hostels (`BH-1` to `BH-9`)** and **Girls Hostels (`GH-1` to `GH-3`)**, combining **gender-based smart hostel recommendation at login**, **preference-based roommate matching**, **friend request & group booking**, and **automated 8-tier priority room allocation**.

---

##  Key Highlights & Latest Updates

- **Gender-Based Hostel Recommendation (`BH` for Boys / `GH` for Girls)**:
  - At student login (`/student/login`), the portal asks whether the student is **Male (Boy)** or **Female (Girl)**.
  - **Male (Boy)** students are automatically recommended **Boys Hostels (`BH-1` to `BH-9`)** and have their dashboard pre-filtered to `BH` blocks.
  - **Female (Girl)** students are automatically recommended **Girls Hostels (`GH-1` to `GH-3`)** and have their dashboard pre-filtered to `GH` blocks.
  - Includes **1-Click Demo Login** for both **Boy Student (`BH-1` to `BH-9`)** and **Girl Student (`GH-1` to `GH-3`)**.
-  **100% Authentic LPU Hostel & Campus Photography (`44+ Official Photos`)**:
  - Uses real photographs from **Lovely Professional University** (`public/images/lpu/`) across the entire applicationâ€”zero generic or stock placeholders.
  - Showcases actual LPU `BH-1` to `BH-9` and `GH-1` to `GH-3` residential towers, AC/Non-AC Standard Rooms (1/2/3/4/5 Seater), AC Studio Apartments, Dormitories, Central Hostel Mess, Shanti Devi Mittal Auditorium, Central Library, Indoor Sports Complex (Olympic Pool, Badminton, Gym), Uni Mall, Uni Hospital, and Turnstile/Main Gate Security.
-  **Interactive Exterior / Room Interior Card View**:
  - Every hostel block card (`BH-1` to `BH-9`, `GH-1` to `GH-3`) includes a live toggle between **Building Exterior** and **Room Interior** photographs.
-  **30-Photo LPU Residential & Campus Gallery**:
  - Filterable by category (*Hostel Towers*, *Rooms & Apartments*, *Dining & Mess*, *Sports & Gym*, *Campus & Mall*, *Security & Care*) with a full-screen Lightbox modal.

---


## Features

###  For Students (`/student/login` & `/student/dashboard`)

-  **Gender Selection & Smart Wing Recommendation** â€” Select **Male (Boy)** or **Female (Girl)** at login to get tailored recommendations for **Boys Hostels (`BH-1` to `BH-9`)** or **Girls Hostels (`GH-1` to `GH-3`)**.
-  **Interactive Hostel Directory** â€” Inspect all 12 LPU hostel blocks (`BH-1`â€“`BH-9`, `GH-1`â€“`GH-3`) with real LPU photos, fee structures, mess fees, and live bed availability.
-  **LPU UMS-Style Booking Modes**:
  - **Individual Booking** â€” Apply solo with room category (`4-Seater`, `3-Seater`, `2-Seater`, `1-Seater`, `Dormitory`), AC/Non-AC, Mess plan, Floor preference, Quiet Zone, and Study-Focused tags.
  - **Roommate Group Booking** â€” Apply together as a 2â€“4 student group in the same room.
  - **Waitlist Priority Queue** â€” Join the CGPA-weighted priority queue for high-demand blocks.
-  **Friend Requests & Roommate Matching** â€” Send, receive, accept, or reject roommate friend requests by LPU Registration Number.
-  **Real-Time Application Tracker** â€” Track status (`SUBMITTED`, `UNDER_REVIEW`, `ALLOCATED`, `WAITLISTED`) and view complete fee breakdowns.

###  For Chief Warden & Administrators (`/admin/dashboard`)

-  **Live Occupancy Analytics** â€” Visual statistics across all 12 hostel blocks (`BH-1` to `BH-9` and `GH-1` to `GH-3`), total beds, occupied beds, and pending applications.
-  **Smart 8-Tier Allocation Engine**:
  - **Tier 1**: Complete roommate groups with matching block availability
  - **Tier 2**: Students with mutually accepted roommate friend requests
  - **Tier 3â€“5**: Floor, Quiet Zone, and Study-Focused lifestyle compatibility
  - **Tier 6â€“8**: CGPA-weighted priority & general pool allocation
-  **Application Review & Approval** â€” Filter applications by status, gender (`Male` / `Female`), department, and CGPA; approve or reject applications with one click.
-  **Hostel Inventory Overview** â€” Real-time capacity bar charts and real LPU exterior/interior imagery for every block.

---

## Tech Stack

### Frontend
- **Framework:** Next.js 14.2 (App Router)
- **Library:** React 18
- **Styling:** Tailwind CSS + Custom LPU Theme (`Orange #f97316` & `White`)
- **State & Persistence:** React Hooks (`useState`, `useEffect`, `useMemo`, `Suspense`) + `localStorage` gender & session sync

### Backend
- **Runtime:** Node.js
- **Framework:** Express.js 4
- **Architecture:** RESTful API (`/api/hostels`, `/api/applications`, `/api/allocations`, `/api/friend-requests`, `/api/rooms`, `/api/stats`)

### Database
- **Database:** MongoDB 7 (with automatic fallback to `mongodb-memory-server`)
- **ODM:** Mongoose 8
- **Seeder:** Automatic & standalone seeder (`server/seed.js`) populating `BH-1` to `BH-9` and `GH-1` to `GH-3`, 4,320 beds, sample students, and applications

---

##  Project Structure

```text
HostelRoomAllocationSystem/
â”‚
â”œâ”€â”€  app/                          # Next.js 14 App Router (Frontend)
â”‚   â”œâ”€â”€ page.js                      # Landing page: Hero, 12 Hostels, Room Types, 30-Photo Gallery
â”‚   â”œâ”€â”€ globals.css                  # Global styles & animations
â”‚   â”œâ”€â”€ layout.js                    # Root layout & metadata
â”‚   â”‚
â”‚   â”œâ”€â”€  components/               # Reusable UI components
â”‚   â”‚   â”œâ”€â”€ LpuLogo.js               # Official LPU Logo component
â”‚   â”‚   â””â”€â”€ Chatbot.js               # Interactive LPU Hostel Assistant
â”‚   â”‚
â”‚   â”œâ”€â”€  student/                  # Student Portal
â”‚   â”‚   â”œâ”€â”€ login/page.js            # Gender selection (Boy->BH / Girl->GH) & Student Login
â”‚   â”‚   â””â”€â”€ dashboard/page.js        # Personalized BH/GH recommendation, Booking, Friends & Groups
â”‚   â”‚
â”‚   â””â”€â”€  admin/                    # Chief Warden / Admin Portal
â”‚       â”œâ”€â”€ login/page.js            # Admin authentication
â”‚       â””â”€â”€ dashboard/page.js        # Occupancy analytics, Application review & Smart Allocation
â”‚
â”œâ”€â”€ server/                       # Express.js Backend API
â”‚   â”œâ”€â”€ index.js                     # API server entry point (Port 5000)
â”‚   â”œâ”€â”€ db.js                        # MongoDB connection with in-memory fallback
â”‚   â”œâ”€â”€ seed.js                      # Seeds BH-1..BH-9 & GH-1..GH-3 with real LPU images
â”‚   â”œâ”€â”€  models/                   # Mongoose Models (Hostel, Room, Student, Application, etc.)
â”‚   â””â”€â”€  routes/                   # REST API Route Handlers
â”‚
â”œâ”€â”€  public/                       # Static Assets
â”‚   â””â”€â”€  images/lpu/               # 44+ Official LPU Hostel, Room, Mess, Sports & Campus Photos
â”‚
â”œâ”€â”€  docs/                         # Technical & Deployment Documentation
â”œâ”€â”€ next.config.mjs                  # Next.js configuration
â”œâ”€â”€ package.json                     # Dependencies & scripts
â””â”€â”€ README.md                        # Project documentation
```

---

## Module Architecture

1. **Module 1: Gender-Aware Student Authentication** â€” Captures student gender (`Male` / `Female`) at login and maps Boys to `BH-1`â€“`BH-9` and Girls to `GH-1`â€“`GH-3`.
2. **Module 2: LPU Hostel & Room Inventory** â€” Manages 9 Boys Hostels (`BH-1` to `BH-9`) and 3 Girls Hostels (`GH-1` to `GH-3`) with real LPU photos and live bed counts.
3. **Module 3: Multi-Mode Application System** â€” Supports Individual, Group (2â€“4 roommates), and Waitlist applications.
4. **Module 4: Roommate Friend Request System** â€” Bi-directional friend request workflow using LPU Registration Numbers.
5. **Module 5: Automatic Roommate Group Formation** â€” Links accepted friends into co-allocated roommate groups.
6. **Module 6: 8-Tier Smart Allocation Engine** â€” Automated room assignment balancing group integrity, lifestyle preferences, and CGPA merit.
7. **Module 7: Chief Warden Analytics Dashboard** â€” Real-time occupancy monitoring, approval workflow, and allocation trigger.
8. **Module 8: Authentic LPU Visual Experience** â€” 30-photo filterable campus gallery, exterior/interior card toggles, and responsive mobile-first UI.

---

##  Installation & Setup

### Prerequisites
- **Node.js** 18+ installed
- **MongoDB** running locally on `mongodb://127.0.0.1:27017` (or automatic in-memory fallback)
- **Git** installed

### Step 1: Clone the Repository
```bash
git clone https://github.com/vaishnavi339/HostelRoomAllocationSystem.git
cd HostelRoomAllocationSystem
```

### Step 2: Install Dependencies
```bash
npm install
```

### Step 3: Configure Environment Variables (Optional)
Create a `.env` file in the root directory (defaults are pre-configured):
```env
MONGODB_URI=mongodb://127.0.0.1:27017/hostel_db
PORT=5000
NEXT_PUBLIC_API_URL=http://localhost:5000
```

### Step 4: Seed the Database with LPU Hostels & Photos
```bash
node ./server/seed.js
```

### Step 5: Run the Project
```bash
npm run dev
```
> **Note for Windows paths containing `&`**: If your folder path contains `&`, run the servers directly with `node`:
> ```powershell
> node ./server/index.js
> node ./node_modules/next/dist/bin/next dev -p 3000
> ```

- **Frontend Portal:** http://localhost:3000
- **Student Login:** http://localhost:3000/student/login
- **Student Dashboard:** http://localhost:3000/student/dashboard
- **Admin Dashboard:** http://localhost:3000/admin/dashboard
- **Backend API:** http://localhost:5000/api/hostels

---

##  Usage Guide

### Student Workflow
1. Visit **`/student/login`**.
2. **Step 1 â€” Select Gender**:
   - Choose ** Male (Boy)** â†’ System immediately recommends **Boys Hostels (`BH-1` to `BH-9`)**.
   - Choose ** Female (Girl)** â†’ System immediately recommends **Girls Hostels (`GH-1` to `GH-3`)**.
3. Enter your LPU Registration Number & UMS Password (or click **Demo Boy (`BH-1 to BH-9`)** / **Demo Girl (`GH-1 to GH-3`)** for instant autofill).
4. On **`/student/dashboard`**, review your personalized **Recommended Hostels Banner**, switch between `BH` or `GH` blocks, inspect real LPU room interiors, and submit an **Individual**, **Roommate Group**, or **Waitlist** booking.

### Administrator Workflow
1. Visit **`/admin/dashboard`**.
2. Review live occupancy across `BH-1`â€“`BH-9` and `GH-1`â€“`GH-3`.
3. Click **" Run Smart Allocation"** to execute the 8-tier roommate matching and bed assignment engine.
4. Approve or reject individual student applications in the **Applications** tab.

---

## ðŸ“¡ API Documentation

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/api/health` | API health check & version info |
| `GET` | `/api/hostels` | List all 12 LPU hostels (`BH-1`â€“`BH-9`, `GH-1`â€“`GH-3`) with real LPU image paths & availability |
| `GET` | `/api/applications` | Fetch all submitted student hostel applications |
| `POST` | `/api/applications` | Submit a new hostel application with preferences & roommate IDs |
| `POST` | `/api/allocations/run` | Trigger the 8-tier smart hostel & roommate allocation algorithm |
| `POST` | `/api/friend-requests/send` | Send a roommate friend request by registration number |
| `GET` | `/api/friend-requests/received/:rollNumber` | List incoming roommate requests for a student |
| `PATCH` | `/api/friend-requests/:id/accept` | Accept a roommate request and form a booking group |

---

##  LPU Campus & Hostel Gallery Preview

<div align="center">
  <table>
    <tr>
      <td align="center">
        <img src="public/images/lpu/boys-hostel.webp" width="280" alt="LPU Boys Hostel BH Blocks" /><br />
        <sub><b>LPU Boys Hostels (BH-1 to BH-9)</b></sub>
      </td>
      <td align="center">
        <img src="public/images/lpu/girls-hostel.webp" width="280" alt="LPU Girls Hostel GH Blocks" /><br />
        <sub><b>LPU Girls Hostels (GH-1 to GH-3)</b></sub>
      </td>
      <td align="center">
        <img src="public/images/lpu/apartments-room-1.webp" width="280" alt="LPU AC Apartment Room" /><br />
        <sub><b>LPU AC Residential Rooms & Apartments</b></sub>
      </td>
    </tr>
    <tr>
      <td align="center">
        <img src="public/images/lpu/hostel-mess.webp" width="280" alt="LPU Hostel Mess" /><br />
        <sub><b>LPU Central Hostel Mess & Dining</b></sub>
      </td>
      <td align="center">
        <img src="public/images/lpu/indoor-sports-complex.webp" width="280" alt="LPU Indoor Sports Complex" /><br />
        <sub><b>LPU Indoor Sports Complex & Gym</b></sub>
      </td>
      <td align="center">
        <img src="public/images/lpu/uni-mall.webp" width="280" alt="LPU Uni Mall" /><br />
        <sub><b>LPU Uni Mall & Campus Plaza</b></sub>
      </td>
    </tr>
  </table>
</div>

---

##  Vercel Deployment

The frontend is deployed on Vercel with built-in static LPU hostel fallback data so all pages, real LPU photos, and interactive flows work seamlessly even without a live backend connection:

- **Production URL:** [https://hostelallocationlpuproject.vercel.app/](https://hostelallocationlpuproject.vercel.app/)

To deploy updates:
```bash
git add -A
git commit -m "Update LPU Hostel Portal"
git push origin main
```

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**LPU Hostel Room Allocation & Roommate Matching System**

 Star this repository if you find it helpful!

</div>

