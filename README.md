# 🎓 LearnForge Frontend (`LearnForge_frontend`)

[![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-5-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.4-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Three.js](https://img.shields.io/badge/Three.js-3D%20Avatar-black?logo=three.js&logoColor=white)](https://threejs.org/)

The frontend client application for **LearnForge**, an AI-powered personalized tutoring and adaptive learning platform. It provides a multi-modal learning experience including a real-time 3D talking avatar with audio lip-sync, an interactive AI tutor chat, adaptive diagnostics, dynamic study roadmap planning, and automated assessments.

---

## 🔗 Repositories

- **Frontend Repository**: [https://github.com/Aditya9207/LearnForge_frontend.git](https://github.com/Aditya9207/LearnForge_frontend.git)
- **Backend Repository**: [https://github.com/Aditya9207/LearnForge_backend-.git](https://github.com/Aditya9207/LearnForge_backend-.git)

---

## ✨ Features

- **Real-Time 3D Talking Avatar**: Client-side 3D avatar head (`face9.glb`) rendered in WebGL using Three.js, driven by the browser's Web Audio API with Root-Mean-Square (RMS) amplitude calculation for smooth, cost-free procedural lip-syncing.
- **Interactive Multi-Column Learning Hub**:
  - **Left**: 3D Talking Avatar on a glassmorphic stage + live educational reference links via Serper.
  - **Center**: Structured document summaries enriched with LaTeX mathematical rendering (KaTeX) and contextually fetched educational diagrams.
  - **Right**: Context-aware AI tutor chat with voice transcription (Groq Whisper) and speech playback.
- **Adaptive Diagnostic Quizzes**: Multiple-choice diagnostic testing with instant feedback, misconception identification, and topological prerequisite navigation.
- **Personalized Lesson Loop**: "Teach $\rightarrow$ Check $\rightarrow$ Adapt" sequence with automated micro-lesson remediation if foundational concepts are weak.
- **Assessment Suite**: Practice mode offering both Multiple Choice Questions (with hints and explanations) and Theoretical free-response questions with AI grading.
- **Responsive & Modern Design**: Glassmorphic UI built with TailwindCSS, Lucide icons, responsive drawer navigation, and mobile bottom navigation sheets.
- **Authentication**: Seamless user sign-in and session management powered by Clerk.

---

## 🛠️ Tech Stack

- **Core**: React 18, TypeScript, Vite
- **Styling**: TailwindCSS, PostCSS, Glassmorphism design tokens
- **3D & Audio**: Three.js, GLTFLoader, Web Audio API (`AudioContext`, `AnalyserNode`)
- **Math & Markdown**: `react-markdown`, `remark-math`, `remark-gfm`, `rehype-katex`, `rehype-raw`, KaTeX
- **Authentication**: `@clerk/react`
- **Icons**: `lucide-react`
- **Routing**: `react-router-dom`

---

## 📁 Project Structure

```
LearnForgeFrontend/
├── client/
│   ├── components/
│   │   ├── avatar/              # 3D Avatar canvas with WebGL & Web Audio RMS lip sync
│   │   ├── tutor/               # Diagnostic, LessonView, Roadmap, Sidebar, Mobile sheets
│   │   ├── ui/                  # Reusable UI primitives, loaders, and skeletons
│   │   ├── Navigation.tsx       # Top navbar & brand header
│   │   └── UserMenu.tsx         # Clerk authentication profile menu
│   ├── hooks/                   # Custom React hooks
│   ├── lib/                     # API client services, auth headers, and contexts
│   ├── pages/
│   │   ├── Home.tsx             # Landing page with interactive feature walkthrough
│   │   ├── Study.tsx            # Full Study Room (Upload, Learning Hub, Assessment, Tutor)
│   │   ├── PrivacyPolicy.tsx    # Privacy policy
│   │   └── Terms.tsx            # Terms of service
│   ├── App.tsx                  # Main router setup
│   └── global.css               # Global styles, Tailwind directives, theme variables
├── public/
│   ├── models/                  # 3D model assets (face9.glb)
│   └── how it works image/      # Landing page demonstration graphics
├── package.json
├── tailwind.config.ts
├── tsconfig.json
└── vite.config.ts
```

---

## ⚙️ Environment Configuration

Create a `.env` file in the root directory:

```env
# URL of your running LearnForge Flask backend API
VITE_API_BASE_URL=http://localhost:5000

# Clerk Publishable Key (from your Clerk Dashboard > API Keys)
VITE_CLERK_PUBLISHABLE_KEY=pk_test_...
```

*(A template is provided in `.env.example`)*

---

## 🚀 Getting Started

### 1. Install Dependencies
```bash
npm install
```

### 2. Run the Development Server
```bash
npm run dev
```
Open your browser and navigate to `http://localhost:5173`.

### 3. Build for Production
```bash
npm run build
```
The optimized production bundle will be generated in `./dist/spa`.

### 4. Preview Production Build
```bash
npm run preview
```

---

## 🌐 Deployment (e.g. Render / Vercel / Netlify)

- **Build Command**: `npm install && npm run build`
- **Publish Directory**: `dist/spa`
- **Single Page Application (SPA) Rewrite**: Ensure all routes (`/*`) rewrite to `/index.html`.
- **Environment Variables**:
  - `VITE_API_BASE_URL`: Deployed backend URL (e.g. `https://your-backend.onrender.com`)
  - `VITE_CLERK_PUBLISHABLE_KEY`: Your Clerk publishable key

---

## 📄 License

This project is licensed under the MIT License.
