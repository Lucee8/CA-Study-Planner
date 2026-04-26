# 📚 CA Study Planner

A full-featured, AI-powered study planner built specifically for **CA Inter Group 1** students. Single HTML file — no framework, no build step. Just open and study.

**Live Demo:** [ca-study-planner-swart.vercel.app](https://ca-study-planner-swart.vercel.app)

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔐 Google Login | Sign in with Google — data syncs across all devices |
| 📅 Timetable | 12pm–2am schedule with 13 sessions, checkboxes, notes, rename & delete |
| 🎯 Focus Mode | Full-screen countdown on the active session |
| 📊 Stats Bar | Live tracking — hours studied, sessions done, breaks, time remaining |
| 🤖 AI Mock Test | Groq-powered MCQ generator with adaptive difficulty (Easy → Medium → Hard) |
| 📈 Analytics | Monthly calendar + 14-day completion history |
| 🔥 Streak Tracker | Daily streak based on hitting your study target |
| 📅 Exam Countdown | Set your exam date — shows days left with urgency colors |
| 💧 Water Reminder | Alert every 45 minutes to stay hydrated |
| 💬 Daily Quote | Rotating CA-specific motivational quotes with fade animation |
| 🌙 Dark Mode | Full dark theme toggle |
| 📄 PDF Export | Print-ready timetable export |
| ☁️ Cloud Sync | All data auto-saves to Firebase Firestore in real time |

---

## 🤖 Mock Test — How It Works

The Mock Test tab uses the **Groq API** (Llama 3.1 model) to generate fresh MCQ questions every time — no hardcoded question bank.

**Subjects covered:**
- Advanced Accounting
- Financial Reporting
- Corporate & Other Laws
- Taxation (Income Tax + GST)
- Cost & Management Accounting
- Strategic Financial Management
- Auditing & Ethics

**How difficulty adapts:**
- First 33% of questions → Easy
- Middle 33% → Medium
- Last 33% → Hard

**Two modes:**
- **Practice** — explanation shown after each answer
- **Mock Exam** — timer runs, results shown only at end

---

## 🛠️ Tech Stack

| Technology | Purpose | Cost |
|---|---|---|
| **Vercel** | Hosting & auto-deployment | Free |
| **Firebase Auth** | Google Sign-In | Free |
| **Firebase Firestore** | Cloud database for all user data | Free |
| **Groq API** | AI question generation (Llama 3.1) | Free |
| **Vanilla HTML/CSS/JS** | Frontend — no framework needed | — |

---

## 🚀 Deploy Your Own

### 1. Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/ca-study-planner.git
cd ca-study-planner
```

### 2. Set up Firebase
1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Create a new project
3. Enable **Authentication** → Google Sign-In
4. Enable **Firestore Database**
5. Go to Project Settings → copy your `firebaseConfig`
6. Replace the config object in `index.html`:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  ...
};
```

### 3. Get a Groq API key
1. Go to [console.groq.com](https://console.groq.com)
2. Sign up free → Create API Key
3. Replace in `index.html`:

```js
const GROQ_API_KEY = 'YOUR_GROQ_API_KEY';
```

### 4. Deploy to Vercel
1. Push `index.html` to a GitHub repo
2. Go to [vercel.com](https://vercel.com) → New Project → Import repo
3. Click Deploy — done ✅

### 5. Add your Vercel domain to Firebase
1. Firebase Console → Authentication → Settings → Authorized Domains
2. Add `your-project.vercel.app`

---

## 📁 Project Structure

```
ca-study-planner/
└── index.html        ← entire app (HTML + CSS + JS in one file)
```

No dependencies. No `package.json`. No build process.

---

## 📸 App Overview

```
┌─────────────────────────────────────────┐
│  CA Study Planner    🔥 0d  Lucee  🌙  │
│  Friday, 25 April 2026                  │
├─────────────┬───────────┬───────────────┤
│ Timetable   │ Analytics │ Mock Test ... │
├─────────────┴───────────┴───────────────┤
│ 💬 "Every page you study today is a    │
│     brick in the foundation..."         │
├────────┬────────┬─────────┬─────────────┤
│Studied │Sessions│ Breaks  │ Remaining   │
│ 4h 30m │  3/7   │   2     │   5h 30m   │
├────────┴────────┴─────────┴─────────────┤
│ ████████████████░░░░░░  62%            │
├─────────────────────────────────────────┤
│ ✅ 12:00 PM — 1:30 PM  Session 1  Study│
│ ✅ 1:30 PM — 2:00 PM   Lunch      Meal │
│ 🟩 2:00 PM — 4:00 PM   Session 2  Study│ ← active now
│ ☐  4:00 PM — 4:15 PM   Break      Break│
└─────────────────────────────────────────┘
```

---

## ⚙️ Configuration

You can change these defaults directly in `index.html`:

| Setting | Location | Default |
|---|---|---|
| Study sessions | `DEFAULT_SLOTS` array | 12pm – 2am (13 sessions) |
| Daily study goal | Settings tab | 10 hours |
| Water reminder interval | `setupWaterTimer()` | Every 45 mins |
| Questions per test | Dropdown in Mock Test | 10 |
| AI model | `GROQ_URL` | `llama-3.1-8b-instant` |

---

## 🔐 Environment Variables

> ⚠️ This project stores API keys directly in the HTML file. This is fine for personal/educational use. For a public production app, move keys to a backend proxy or serverless function.

Keys used:
- `GROQ_API_KEY` — from [console.groq.com](https://console.groq.com)
- `firebaseConfig.apiKey` — from Firebase Console (safe to expose, Firebase security rules protect data)

---

## 🗺️ Roadmap

- [ ] Subject & chapter tracker (syllabus completion %)
- [ ] Pomodoro timer inside focus mode
- [ ] Weekly bar chart in Analytics
- [ ] Mock test score trend graph
- [ ] Revision planner with exam date

---

## 🙋 Built By

**Lucee (Bhavesh Koyande)**
BSc IT Student · Web Developer · CA Inter Aspirant
GitHub: [@lucee8](https://github.com/lucee8)

---

## 📄 License

MIT License — free to use, modify, and share.
