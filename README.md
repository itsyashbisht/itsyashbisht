# Yash Bisht

Full-Stack AI Engineer building RAG systems, agentic tool-calling architectures, and production web applications.

[Email](mailto:yashbisht2005@gmail.com) · [LinkedIn](https://linkedin.com/in/yashbisht26) · [GitHub](https://github.com/itsyashbisht)

---

## About

I work across the stack — Next.js and Node.js on the application layer, Postgres and pgvector for retrieval, Groq and Gemini for generation. My focus is on the parts of AI engineering that don't show up in tutorials: tool-calling loops that handle partial failures gracefully, RAG pipelines that stay accurate at scale, and multi-tenant systems where access control actually holds under real usage.

Most recently I built and shipped IntelliVault, a RAG platform used to test document-intelligence workflows across isolated workspaces, and NestIQ, a hotel booking concierge with a custom agentic loop written without framework abstractions.

---

## Selected Work

### IntelliVault — Enterprise RAG Platform

A multi-tenant document intelligence platform where retrieval accuracy and access isolation were the two hard constraints.

Documents are parsed, chunked with LangChain's recursive splitter, embedded with Gemini, and indexed into Postgres via pgvector using HNSW for approximate nearest-neighbor search at low latency. Chat responses stream token-by-token through the Vercel AI SDK and cite their source chunks directly, so answers are traceable back to the original document rather than presented as opaque generations.

Access control is enforced at the API layer with an Owner / Editor / Viewer model scoped per workspace, backed by full audit logging — the harder problem in multi-tenant RAG isn't retrieval, it's making sure workspace A can never leak into workspace B's context window.

`Next.js` · `TypeScript` · `Drizzle ORM` · `PostgreSQL / pgvector` · `Clerk` · `Groq (LLaMA)` · `Gemini` · `Vercel AI SDK`

### NestIQ — Agentic Hotel Concierge

A hotel booking assistant built around a hand-rolled multi-turn tool-calling loop on LLaMA 3.3-70B — no LangChain, no agent framework, because the failure modes needed to be handled explicitly rather than abstracted away.

The loop tracks `finish_reason` across turns and branches on three outcomes: successful tool execution, tool failure, and truncated generation from hitting token limits mid-call. An earlier version of the system prompt caused the model to inject duplicate action markers under certain conversation states; fixing that meant restructuring how the prompt separated planning from execution, not just patching the symptom. Final responses stream separately from the blocking tool-resolution phase, so the user sees progress instead of a frozen UI while tools run.

`React` · `Redux Toolkit` · `Node.js` · `Express` · `MongoDB` · `Groq (LLaMA 3.3-70B)`

### Solemate — Full-Stack Commerce Platform

An e-commerce system covering the full purchase flow — catalog, cart, checkout, order management — with a role-separated admin dashboard.

Auth is JWT-based with bcrypt hashing and enforced RBAC between customer and admin roles. State management runs through Redux Toolkit with selectors tuned to cut redundant API calls across the cart-to-checkout path, which was the main source of unnecessary re-fetching in the initial build.

`MongoDB` · `Express` · `React` · `Node.js` · `Redux Toolkit` · `JWT`

---

## Stack

**Languages** — TypeScript, JavaScript, Python, Java

**Frontend** — Next.js (App Router), React, Redux Toolkit, Tailwind CSS, shadcn/ui, Framer Motion

**Backend** — Node.js, Express, FastAPI

**Data** — PostgreSQL (Neon), Drizzle ORM, MongoDB, pgvector

**AI / LLM** — RAG pipelines, agentic tool-calling, Vercel AI SDK, Groq, Gemini, OpenAI, LangChain

**Auth / Infra** — Clerk, JWT, Vercel, Supabase, Firebase

---

## Currently

Open to full-stack and AI engineering roles at product teams — particularly where the work involves RAG, agentic systems, or LLM-integrated products at production scale.
