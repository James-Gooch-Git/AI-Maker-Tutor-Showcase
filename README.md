# AI Maker Tutor

*3rd Year Final Individual University Project*

An AI-guided educational platform that teaches electronics and programming through Socratic questioning. Rather than providing direct answers, the AI tutor guides students through maker hardware projects by asking targeted questions that build understanding incrementally.

---

## The Problem

Standard AI assistants hand over answers directly, which undermines learning. This platform constrains the LLM's responses so it can only guide, prompt, and question — never solve — keeping the student in the driver's seat.

---

## Features

- **Socratic AI tutoring** — constrained LLM responses that guide without giving answers
- **Maker project packages** — structured hardware projects with bills of materials, schematics, and code templates
- **Student progress tracking** — per-project session state and history
- **3D component visualisation** — Three.js-powered views of circuits and components
- **Role-based access** — student and educator views
- **Deployed web app** — accessible from any browser, no local install needed

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | FastAPI + Python |
| Frontend | React 18 + Vite |
| Database | PostgreSQL + SQLAlchemy + Alembic |
| Auth | JWT (python-jose / passlib) |
| 3D Visualisation | Three.js |
| AI | Claude API (constrained prompting) |
| Deployment | Railway (backend), Vercel (frontend) |

---

## Architecture Overview

```
┌─────────────────────────────┐
│       React / Vite          │
│   (Student & Tutor UI)      │
└──────────────┬──────────────┘
               │ REST API
   ┌───────────▼───────────┐
   │       FastAPI          │
   │  ┌─────────────────┐  │
   │  │ Constraint Layer │  │  <-- Keeps LLM in tutor mode
   │  └────────┬────────┘  │
   │           │            │
   │  ┌────────▼────────┐  │
   │  │   Claude API    │  │
   │  └─────────────────┘  │
   └──────────┬────────────┘
              │
   ┌──────────▼────────────┐
   │      PostgreSQL        │
   │ (sessions, progress,   │
   │  projects, users)      │
   └────────────────────────┘
```

---

## Screenshots

*Contact me for a live demo or walkthrough.*

---

## Source Code

This is a portfolio showcase. The full source code is private as this project has commercial potential.

**Interested in the codebase or a walkthrough?** Reach out via [GitHub](https://github.com/James-Gooch-Git) or [email](mailto:gewainwright@gmail.com).
