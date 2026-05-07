# VitalySync

**An AI-driven mobile wellness application for predictive burnout detection and intelligent lifestyle optimization.**

VitalySync is a full-stack health and productivity companion designed to help users understand lifestyle patterns that may contribute to burnout risk. The app combines daily wellness logging, behavioral analytics, burnout-oriented scoring, adaptive nudges, nutrition tracking, and goal monitoring in a polished Flutter mobile experience backed by a Node.js, Express, PostgreSQL, and OpenAI-powered backend.

> VitalySync is designed as a wellness support tool. It does not diagnose burnout or replace professional medical or mental health care.

---

## Case Study Overview

### The Challenge

Students, professionals, and high-workload individuals often recognize burnout only after symptoms become disruptive. Existing wellness tools usually focus on isolated habits such as sleep, food, mood, or productivity, but they rarely connect these signals into a clear picture of stress, recovery, workload, and lifestyle balance.

VitalySync addresses this gap by turning everyday inputs into structured insights. The project explores how a mobile application can help users build self-awareness, detect early burnout-related patterns, and receive practical recommendations before stress escalates.

### Project Goal

The goal of VitalySync is to provide a clean, scalable, and user-friendly mobile platform that helps users:

- Monitor daily lifestyle habits related to wellness, productivity, and recovery.
- Assess burnout risk using structured questionnaire inputs inspired by established burnout dimensions.
- Track nutrition, activity, workload, sleep, mood, hydration, and symptoms.
- Analyze behavior over time to identify stress and recovery patterns.
- Receive personalized AI-assisted nudges that encourage healthier routines.
- Set and monitor goals that support sustainable productivity and well-being.

---

## Solution

VitalySync brings wellness tracking and burnout awareness into one mobile workflow. Users can complete onboarding, log daily wellness data, track meals and activity, review analytics, and receive timely nudges based on recent behavior.

The application focuses on three core ideas:

**Awareness:** Convert daily habits into visible wellness signals.

**Prediction:** Use structured scoring and trend analysis to estimate potential burnout risk.

**Action:** Provide small, practical recommendations that help users adjust routines before problems compound.

---

## Key Features

### Burnout Risk Assessment

VitalySync includes a structured burnout assessment flow based on burnout dimensions such as emotional exhaustion, detachment, and reduced accomplishment. User responses are converted into baseline and daily risk indicators that help frame future insights.

### Daily Wellness Logging

Users can record lifestyle inputs such as sleep hours, sleep quality, mood, energy, hydration, workload, stress level, break quality, and symptoms. These entries give the system the behavioral data needed to calculate trends over time.

### Behavioral Analytics Dashboard

The dashboard presents wellness metrics, burnout risk trends, symptom frequency, sleep patterns, mood volatility, weekly performance, and wellness index summaries. This gives users a clearer view of how daily behavior connects to long-term well-being.

### Adaptive Smart Nudges

VitalySync generates contextual nudges from burnout patterns, recent activity, user preferences, and risk signals. The backend includes deterministic recommendation logic and optional OpenAI-powered message refinement with safety guardrails that avoid clinical diagnosis.

### Nutrition Monitoring

The nutrition module allows users to log meals, review daily nutrition summaries, and inspect macro balance. This connects diet-related behavior with broader wellness tracking.

### Activity and Exercise Goals

Users can track daily movement, active minutes, and exercise goals. Activity data contributes to burnout-related scoring by factoring in recovery and physical wellness signals.

### Environment Awareness

The app includes environment-related data support, allowing contextual wellness insights to consider external factors where available.

### Offline-Friendly Preferences

Selected app preferences and local user settings are stored using Shared Preferences, supporting a smoother experience even when network access is limited.

---

## Product Experience

VitalySync follows a modern mobile UI direction with glassmorphism, gradients, dark-mode support, reusable widgets, and clean navigation. The interface is designed to feel calm and supportive while still presenting analytics in a practical, readable way.

The frontend is organized around reusable components such as shared cards, bottom navigation, app bars, dashboard widgets, nutrition cards, assistant controls, and notification views. This keeps the experience consistent across screens and makes the codebase easier to maintain.

---

## Technical Architecture

```text
VitalySync
+-- vitalysync-frontend/     Flutter mobile app
|   +-- lib/app/             App shell, theme, and navigation
|   +-- lib/features/        Feature modules and screens
|   +-- lib/shared/          Reusable widgets, services, preferences, assistant, notifications
|
+-- vitalysync-backend/      Node.js + Express API
    +-- src/routes/          REST API route definitions
    +-- src/controllers/     Request handling logic
    +-- src/services/        Business logic, scoring, nudges, integrations
    +-- src/config/          Database configuration
    +-- migrations/          PostgreSQL schema migrations
```

### Frontend

- **Framework:** Flutter
- **State and local settings:** Shared Preferences and local controllers
- **UI patterns:** Reusable widgets, feature-based screens, responsive dark/light theme
- **Notable modules:** Home, Dashboard, Log, Nutrition, Activity, Exercise, Onboarding, Profile, Notifications, Settings, Assistant

### Backend

- **Runtime:** Node.js
- **Framework:** Express
- **Database:** PostgreSQL
- **API structure:** RESTful routes grouped by domain
- **AI integration:** OpenAI API for refined wellness nudge messaging
- **Data layer:** SQL migrations and service-based database access

### Database

The PostgreSQL schema is organized around analytics-friendly wellness data, including user onboarding profiles, daily logs, nutrition records, environment snapshots, activity logs, exercise goals, burnout score history, reminder preferences, and AI nudge audit records.

---

## Burnout Scoring Approach

VitalySync combines onboarding baseline data with daily and weekly behavioral inputs. The scoring service considers signals such as:

- Perceived stress
- Workload strain
- Sleep duration and quality
- Mood and energy
- Hydration
- Symptoms
- Break quality
- Activity completion
- Productivity focus
- Recovery and detachment
- Accomplishment level

The backend then produces structured outputs including:

- Overall burnout risk score
- Risk level classification
- Confidence score
- Completeness score
- Contributing factors
- Source data snapshot
- Score history for trend analysis

This approach keeps the system explainable and suitable for user-facing wellness insights.

---

## AI Nudge Design

The AI nudge system is designed around safety, clarity, and usefulness. Deterministic backend logic first identifies the recommendation context, priority, trigger reason, and focus area. OpenAI is then used only to refine the wording into a short, human, actionable message.

Guardrails are included to:

- Avoid diagnosis or medical claims.
- Preserve the original risk and priority generated by deterministic logic.
- Keep suggestions small and behavior-focused.
- Audit generated outputs for validation and traceability.

---

## Tech Stack

| Layer | Technology |
| --- | --- |
| Mobile App | Flutter, Dart |
| Backend API | Node.js, Express |
| Database | PostgreSQL |
| AI Integration | OpenAI API |
| Charts and Analytics UI | fl_chart |
| Local Storage | Shared Preferences |
| Notifications | flutter_local_notifications |
| Location Context | geolocator |
| Motion and UI Polish | Lottie, Google Fonts |

---

## Development Setup

### Frontend

```bash
cd vitalysync-frontend
flutter pub get
flutter analyze
flutter run
```

### Backend

```bash
cd vitalysync-backend
npm install
npm run migrate
npm run dev
```

The backend requires environment variables for database access and AI integration. Do not commit `.env` files or sensitive keys.

---

## Portfolio Highlights

- Designed and developed a full-stack wellness monitoring system with Flutter, Express, and PostgreSQL.
- Built a modular mobile architecture using feature folders and reusable shared components.
- Implemented burnout-oriented scoring logic using multiple behavioral and lifestyle signals.
- Created an analytics dashboard for trends, wellness index summaries, and risk visibility.
- Integrated OpenAI-assisted nudges with safety-focused validation and audit logging.
- Added support for nutrition, activity, onboarding, reminders, notifications, and user preferences.
- Maintained a dark-mode compatible UI direction with glassmorphism, gradients, and consistent visual components.

---

## Future Improvements

- Add clinician or wellness professional review workflows for study validation.
- Expand reporting with exportable weekly wellness summaries.
- Add stronger accessibility checks for font scaling, color contrast, and screen reader support.
- Improve offline sync for logs created without internet access.
- Add automated backend and frontend tests around scoring, nudges, and critical user flows.
- Include portfolio screenshots, demo video links, or hosted API documentation when available.

---

## Status

VitalySync is an active full-stack academic and portfolio project focused on predictive burnout awareness, behavioral analytics, and intelligent lifestyle recommendations.
