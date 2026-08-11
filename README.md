<div align="center">

<img src="https://img.shields.io/badge/⚡-ExamForge_AI-3b82f6?style=for-the-badge&labelColor=0a0a18" height="60" alt="ExamForge AI"/>

### Turn Study Material Into Exams with AI.

Upload any PDF, book, or handwritten notes — get a personalized, gradable exam back in minutes.

<br/>

[![Status](https://img.shields.io/badge/status-in%20development-facc15?style=flat-square)](#roadmap)
[![Frontend](https://img.shields.io/badge/frontend-complete-22c55e?style=flat-square)](#-tech-stack)
[![Backend](https://img.shields.io/badge/backend-planned-a855f7?style=flat-square)](#-tech-stack)
[![License](https://img.shields.io/badge/license-MIT-64748b?style=flat-square)](#-license)
[![Made with](https://img.shields.io/badge/made%20with-HTML%20·%20CSS%20·%20JS-3b82f6?style=flat-square)](#-tech-stack)

<br/>

[Overview](#-overview) •
[Features](#-features) •
[Tech Stack](#-tech-stack) •
[Getting Started](#-getting-started) •
[Project Structure](#-project-structure) •
[Roadmap](#-roadmap)

</div>

<br/>

## 📖 Overview

**ExamForge AI** is an AI-powered educational platform that turns raw study
material — textbooks, class notes, scanned pages, even handwritten
notes — into structured, personalized exams. Instead of manually writing
question papers, the platform reads a document for *meaning* (chapters,
topics, definitions, formulas, concept relationships), then generates
questions grounded in what it actually understood, not keyword-matched
text extraction.

Built for **students** prepping for exams on their own, **teachers**
generating quizzes and assignments, and **coaching institutes** running
mock tests for large batches of students.

> 🎓 Upload a chapter → AI extracts the structure → set your difficulty
> and question mix → get a full exam with answers and explanations,
> ready to take.

<br/>

## ✨ Features

<table>
<tr>
<td width="50%" valign="top">

### 📄 Intelligent Upload
- PDF, DOCX, PPTX, TXT, scanned pages, handwritten notes
- OCR pipeline with noise removal, contrast enhancement, and skew correction for scanned/handwritten content
- Automatic chapter, topic, and concept extraction

### 🧠 Personalized Exam Builder
- Choose subject, chapter scope, and difficulty (Easy / Medium / Hard / Mixed)
- Set question count, marks distribution, and duration
- Mix question types freely per exam

</td>
<td width="50%" valign="top">

### 📝 11 Question Types
MCQ · True/False · Fill in the Blanks · Matching · Assertion & Reasoning
· Short Answer · Long Answer · Numerical · Case-Based · Diagram-Based ·
Higher-Order Thinking

### 📊 Analytics & Bookmarks
- Score breakdown with per-question explanations
- Accuracy, average score, and attempt history over time
- Bookmark exams for quick access later

</td>
</tr>
</table>

<br/>

## 🖥️ Pages

| Page | Route | What it does |
|---|---|---|
| Landing | `index.html` | Marketing site — features, pricing, how it works, docs, FAQ |
| Sign Up | `signup.html` | Account creation with live password-strength feedback |
| Log In | `login.html` | Auth entry point |
| Forgot Password | `forgot-password.html` | Password reset flow |
| Dashboard | `dashboard.html` | Overview — stats, quick actions, recent activity |
| My Exams | `my-exams.html` | Generate, take, and review exams |
| Uploads | `upload.html` | Drag-and-drop document upload + processing status |
| Analytics | `analytics.html` | Score trends and full attempt history |
| Bookmarks | `bookmarks.html` | Starred exams |
| Settings | `settings.html` | Profile, preferences, account management |

<br/>

## 🛠️ Tech Stack

**Frontend — built**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

Vanilla HTML/CSS/JS, no framework or build step. State currently runs on
`localStorage` via a shared `app-core.js`, standing in for a real backend
during frontend development.

**Backend — planned**

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=flat-square&logo=celery&logoColor=white)

FastAPI + PostgreSQL (with `pgvector` for embeddings) + Celery/Redis for
async OCR and AI jobs. Full architecture, data model, API contract, and a
zero-cost hosting plan are documented in [`backend-plan.md`](./backend-plan.md).

**AI pipeline (planned)**: Tesseract OCR → LLM-based chapter/concept
extraction → local embeddings → RAG retrieval → LLM question generation
with strict JSON output.

<br/>

## 🚀 Getting Started

The frontend runs standalone — no build tools, no dependencies.

```bash
# clone the repo
git clone https://github.com/<your-username>/examforge-ai.git
cd examforge-ai

# serve it locally (any static server works)
python3 -m http.server 8000
# or: npx serve .
```

Then open `http://localhost:8000` in your browser.

> **Note:** There's no backend yet — signup/login/upload/generation are
> all simulated with `localStorage` so the full user flow is demoable
> end to end. See [`backend-plan.md`](./backend-plan.md) for the plan to
> replace that with a real API.

<br/>

## 📁 Project Structure

```
examforge-ai/
├── index.html              # Landing page
├── login.html               ├─ Auth pages
├── signup.html               │
├── forgot-password.html      ┘
├── dashboard.html           # App shell — overview
├── my-exams.html            # Generate / take / review exams
├── upload.html              # Document upload
├── analytics.html           # Performance analytics
├── bookmarks.html           # Starred exams
├── settings.html            # Profile & preferences
├── styles.css               # Shared design system
├── app-core.js              # Shared state, question bank, render helpers
├── dashboard-page.js         ├─ Page-specific logic
├── my-exams-page.js          │  (one file per dashboard page)
├── upload-page.js            │
├── analytics-page.js         │
├── bookmarks-page.js         │
├── settings-page.js          ┘
└── backend-plan.md          # Full backend architecture & roadmap
```

<br/>

## 🗺️ Roadmap

- [x] Marketing site (landing, features, pricing, docs, about)
- [x] Auth UI (signup, login, forgot password)
- [x] Dashboard app shell with working upload simulation
- [x] Exam generation, taking, and scoring (client-side question bank)
- [x] Analytics and bookmarks
- [x] Backend architecture plan (data model, API contract, $0-cost hosting)
- [ ] FastAPI backend — auth, documents, exams (Phase 0–1)
- [ ] Real OCR + LLM-based chapter/concept extraction (Phase 2)
- [ ] RAG-based question generation (Phase 3)
- [ ] Server-side scoring & analytics (Phase 4)
- [ ] Quota system, rate limiting, monitoring (Phase 5)
- [ ] Terms of Service / Privacy Policy pages
- [ ] Institute / multi-user accounts

Full phase-by-phase detail lives in [`backend-plan.md`](./backend-plan.md).

<br/>

## 🤝 Contributing

This is currently a solo project in active early development — issues and
suggestions are welcome, but expect the structure to shift as the backend
comes online.

<br/>

## 📄 License

Licensed under the [MIT License](./LICENSE).

<br/>

<div align="center">

Built with ⚡ by a student who got tired of writing practice papers by hand.

</div>
