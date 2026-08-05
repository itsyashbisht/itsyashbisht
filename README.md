# Hi, I'm Yash 👋

Full-Stack AI Engineer building RAG systems, agentic tool-calling architectures, and production web applications.

📧 [Email](mailto:yashbisht2005@gmail.com) · 💼 [LinkedIn](https://linkedin.com/in/yashbisht26) · 🐙 [GitHub](https://github.com/itsyashbisht)

---

## 👨‍💻 About

I work across the stack — Next.js and Node.js on the application layer, Postgres and pgvector for retrieval, Groq and Gemini for generation. My focus is on the parts of AI engineering that don't show up in tutorials: tool-calling loops that handle partial failures gracefully, RAG pipelines that stay accurate at scale, and multi-tenant systems where access control actually holds under real usage.

Most recently I built and shipped IntelliVault, a RAG platform used to test document-intelligence workflows across isolated workspaces, and NestIQ, a hotel booking concierge with a custom agentic loop written without framework abstractions.

---

## 🛠️ Selected Work

### 🗂️ IntelliVault — Enterprise RAG Platform

A multi-tenant document intelligence platform where retrieval accuracy and access isolation were the two hard constraints.

Documents are parsed, chunked with LangChain's recursive splitter, embedded with Gemini, and indexed into Postgres via pgvector using HNSW for approximate nearest-neighbor search at low latency. Chat responses stream token-by-token through the Vercel AI SDK and cite their source chunks directly, so answers are traceable back to the original document rather than presented as opaque generations.

Access control is enforced at the API layer with an Owner / Editor / Viewer model scoped per workspace, backed by full audit logging — the harder problem in multi-tenant RAG isn't retrieval, it's making sure workspace A can never leak into workspace B's context window.

`Next.js` · `TypeScript` · `Drizzle ORM` · `PostgreSQL / pgvector` · `Clerk` · `Groq (LLaMA)` · `Gemini` · `Vercel AI SDK`

### 🏨 NestIQ — Agentic Hotel Concierge

A hotel booking assistant built around a hand-rolled multi-turn tool-calling loop on LLaMA 3.3-70B — no LangChain, no agent framework, because the failure modes needed to be handled explicitly rather than abstracted away.

The loop tracks `finish_reason` across turns and branches on three outcomes: successful tool execution, tool failure, and truncated generation from hitting token limits mid-call. An earlier version of the system prompt caused the model to inject duplicate action markers under certain conversation states; fixing that meant restructuring how the prompt separated planning from execution, not just patching the symptom. Final responses stream separately from the blocking tool-resolution phase, so the user sees progress instead of a frozen UI while tools run.

`React` · `Redux Toolkit` · `Node.js` · `Express` · `MongoDB` · `Groq (LLaMA 3.3-70B)`

### 👟 Solemate — Full-Stack Commerce Platform

An e-commerce system covering the full purchase flow — catalog, cart, checkout, order management — with a role-separated admin dashboard.

Auth is JWT-based with bcrypt hashing and enforced RBAC between customer and admin roles. State management runs through Redux Toolkit with selectors tuned to cut redundant API calls across the cart-to-checkout path, which was the main source of unnecessary re-fetching in the initial build.

`MongoDB` · `Express` · `React` · `Node.js` · `Redux Toolkit` · `JWT`

---

## ⚙️ Stack

**Languages**
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)

**Frontend**
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white) ![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB) ![Redux](https://img.shields.io/badge/Redux_Toolkit-764ABC?style=flat-square&logo=redux&logoColor=white) ![Tailwind](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwindcss&logoColor=white) ![Framer](https://img.shields.io/badge/Framer_Motion-0055FF?style=flat-square&logo=framer&logoColor=white)

**Backend**
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=flat-square&logo=node.js&logoColor=white) ![Express](https://img.shields.io/badge/Express-404D59?style=flat-square&logo=express&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)

**Data**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white) ![Drizzle](https://img.shields.io/badge/Drizzle_ORM-C5F74F?style=flat-square&logo=drizzle&logoColor=black) ![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=flat-square&logo=mongodb&logoColor=white)

**AI / LLM**
![Groq](https://img.shields.io/badge/Groq-FF6B35?style=flat-square&logoColor=white) ![Gemini](https://img.shields.io/badge/Gemini-4285F4?style=flat-square&logo=googlegemini&logoColor=white) ![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white) ![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)

**Auth / Infra**
![Clerk](https://img.shields.io/badge/Clerk-6C47FF?style=flat-square&logo=clerk&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white) ![Supabase](https://img.shields.io/badge/Supabase-1C1C1C?style=flat-square&logo=supabase&logoColor=3ECF8E)

---

## 🎯 Currently

Open to full-stack and AI engineering roles at product teams — particularly where the work involves RAG, agentic systems, or LLM-integrated products at production scale.
