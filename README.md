
Study AI by UBED

A practical, production-ready Retrieval-Augmented Generation (RAG) study assistant built completely using visual programming in Bubble.io. I designed this application to solve a frustrating everyday problem: the friction of manually digging through pages of long-form academic notes or text documents to pull out key study insights.
Live Demo Workspace: Study AI Live Preview

Why I Built This (The Problem)

As students and lifelong learners, we spend too much time scrolling through massive document files or lecture notes just to find specific information or cross-reference concepts before an exam. Traditional search looks for keywords, but it misses structural context.
I built Study AI to streamline this workflow—giving users the ability to drop in raw text documentation and interact with a contextual AI engine that actually understands the underlying study material.

Core Features I Implemented

• Document Ingestion & Parsing: Users can paste raw text notes directly into a clean UI canvas to seed the contextual brain of the assistant.
• Contextual Q&A: A conversational chat interface that references the active study document to answer questions without inventing external facts.
• Instant Summarization: One-click automated summary extractions tailored to highlight key definitions and core study takeaways fast.
• Zero-Code Full Stack Deployment: Built entirely within the Bubble.io framework, handling frontend layouts, reactive custom application states, and back-end logic natively.

Behind the Scenes: My Build Process & Architecture

When building a RAG application without a traditional programmatic backend, the key challenge is ensuring clean asynchronous timing and robust API payload formatting. Here is how I structured the application layout in Bubble:

1. The Context Engine & State Architecture

Instead of expensive database calls for every chat message, I engineered the text context layer using localized Custom Page States.
• When text is inputted, it is securely held in an active memory variable (extracted_text).
• I initialized an asynchronous loader panel controlled by an underlying boolean flag (is_loading = yes/no). This prevents users from double-clicking button triggers and breaking api calls mid-flight.

2. Handling the LLM API Integration

Connecting Bubble to the generative AI models required precise structural handling inside the Bubble API Connector plugin.
• The "One-Line" Challenge: Generative AI endpoints expect strict, continuous JSON blocks. I configured the dynamic workflow to feed text parameters cleanly on a single line string to eliminate data parsing failures caused by random line breaks or special characters inside user-submitted notes.
• The workflow sequence programmatically opens the loading overlay \(\rightarrow \) passes the prompt string wrapped in localized context \(\rightarrow \) processes the API endpoint callback \(\rightarrow \) updates the UI text view \(\rightarrow \) drops the loading screen overlay.

3. Debugging Through Production Launch

Building this product taught me a lot about testing under constraints. I utilized Bubble’s development runtime mode (version-test) to monitor real-time server payloads, trace performance bottlenecks during API response lags, and sanitize system error codes before shipping the deployment live.


Key Takeaways from This Project

This project highlights my product philosophy: Focus on solving real problems fast using whatever tools get the best product to users the quickest.
• Speed to Market: Leveraging visual no-code tools allowed me to wire up a complex AI orchestration pattern in days instead of weeks.
• AI Product Management: I learned firsthand how to manage API latency, construct resilient prompt contexts, and design graceful error UI states when external systems experience downtime.
• User-Centric Design: Every feature was mapped directly to a real student pain point—eliminating conversational fluff in favor of immediate answers.

