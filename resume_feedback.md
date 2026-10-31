# SPEC: Resume Review, ATS Check, and Overleaf Redesign (Aligned with Portfolio)

## 0. Inputs (FILL THESE IN BEFORE RUNNING)

### 0.1 Resume LaTeX code (Overleaf)
> Paste the full `main.tex` code. If the resume uses extra files (a `.cls` file, custom packages), paste or list them too.
%-------------------------
% Resume - Sourabh Pande
% Compiler: pdfLaTeX (Overleaf default)
%-------------------------
\documentclass[a4paper,10pt]{article}

\usepackage[T1]{fontenc}
\usepackage{lmodern}
\usepackage{latexsym}
\usepackage[empty]{fullpage}
\usepackage{titlesec}
\usepackage{xcolor}
\usepackage{enumitem}
\usepackage[hidelinks]{hyperref}
\usepackage[a4paper,left=1.3cm,right=1.3cm,top=0.8cm,bottom=0.8cm]{geometry}

% ATS: make PDF text copy/parse cleanly
\input{glyphtounicode}
\pdfgentounicode=1

\pagestyle{empty}
\raggedright
\setlength{\tabcolsep}{0in}
\setlength{\parindent}{0pt}
\setlength{\parskip}{0pt}
\urlstyle{same}

% Section headings: SAME space before and after every heading
\titleformat{\section}{\scshape\large\raggedright}{}{0em}{}[\vspace{-4pt}\titlerule]
\titlespacing*{\section}{0pt}{11pt}{7pt}

%-------------------------
% Custom commands

% Outer list: itemsep controls the gap between projects/articles
\newcommand{\resumeSubHeadingListStart}{\begin{itemize}[leftmargin=0in,label={},itemsep=8pt,topsep=0pt,parsep=0pt,partopsep=0pt]}
\newcommand{\resumeSubHeadingListEnd}{\end{itemize}}

% Bullet list: no extra top or bottom space
\newcommand{\resumeItemListStart}{\begin{itemize}[leftmargin=0.2in,label=$\bullet$,itemsep=2pt,topsep=0pt,parsep=0pt,partopsep=0pt]\small}
\newcommand{\resumeItemListEnd}{\end{itemize}}

% Two-line heading (used for Education)
\newcommand{\resumeSubheading}[4]{
  \item
  \begin{tabular*}{\textwidth}[t]{l@{\extracolsep{\fill}}r}
    \textbf{#1} & \small #2 \\
    \textit{\small #3} & \textit{\small #4} \\
  \end{tabular*}
}

% One-line heading: bold title | links | date
\newcommand{\resumeProject}[3]{
  \item
  \begin{tabular*}{\textwidth}[t]{l@{\extracolsep{\fill}}r}
    \textbf{#1} & \small #2 $|$ \textit{#3} \\
  \end{tabular*}
}

\begin{document}

%----------HEADING-----------------
\begin{center}
  {\Huge \scshape Sourabh Pande} \\ \vspace{3pt}
  {\normalsize Full-Stack Software Engineer (MERN Stack)} \\ \vspace{3pt}
  \small Nagpur, Maharashtra, India $|$ +91 9665053959 $|$
  \href{https://mail.google.com/mail/u/0/?tf=cm&to=sourabhpande43@gmail.com&fs=1}{sourabhpande43@gmail.com} \\ \vspace{2pt}
  \small Portfolio: \href{https://saurabh-pande.netlify.app/}{saurabh-pande.netlify.app} $|$
  GitHub: \href{https://github.com/Sourabhpande532}{github.com/Sourabhpande532} $|$
  LinkedIn: \href{https://www.linkedin.com/in/sourabh-pande-412170224/}{linkedin.com/in/sourabh-pande-412170224}
\end{center}
\vspace{-8pt}

%-----------SUMMARY-----------------
\section{Summary}
{\small
Full-Stack Software Engineer specializing in the MERN stack, TypeScript, and Python. Hands-on experience in architecting scalable REST APIs, implementing role-based access control (RBAC), and building AI-driven workflows, including RAG pipelines, tool calling, and WebSocket integration. Committed to delivering clean, production-grade applications with strong test coverage and optimized database performance. Seeking a Full-Stack Developer role to build scalable, user-focused products.\par}

%-----------TECHNICAL SKILLS-----------------
\section{Technical Skills}
\begin{itemize}[leftmargin=0in,label={},itemsep=2.5pt,topsep=0pt,parsep=0pt,partopsep=0pt]
  \small
  \item \textbf{Languages:} JavaScript (ES6+), TypeScript, Python, SQL, HTML5, CSS3
  \item \textbf{Frontend:} React.js, Redux Toolkit, Context API, Bootstrap, Responsive UI/UX
  \item \textbf{Backend \& APIs:} Node.js, Express.js, FastAPI, RESTful APIs, WebSockets (Socket.IO), MVC Architecture
  \item \textbf{Databases:} MongoDB (Mongoose), PostgreSQL, MySQL
  \item \textbf{AI \& Tooling:} Retrieval-Augmented Generation (RAG), Agentic AI Workflows, Tool Calling, OpenRouter API
  \item \textbf{DevOps \& Security:} Git, GitHub, Postman, CI/CD Pipelines, JWT Authentication, OAuth 2.0, Vercel
  \item \textbf{Core Concepts:} Object-Oriented Programming, REST API Design, Authentication \& Authorization, State Management, Database Design
\end{itemize}

%-----------PROJECTS-----------------
\section{Featured Projects}
\resumeSubHeadingListStart

  \resumeProject
    {TalentHub --- AI-Powered Hiring Platform}
    {\href{https://talenthub-client-rho.vercel.app/}{\underline{Live Demo}} $|$ \href{https://github.com/Sourabhpande532/talenthub-client}{\underline{GitHub}}}
    {07/2026 -- 09/2026}
  \resumeItemListStart
    \item Engineered a dual-role recruitment portal (Recruiter and Candidate) with granular RBAC, smart applicant filtering, and automated interview-readiness evaluation.
    \item Integrated LLM-driven job description generation and dynamic interview preparation using the OpenRouter API.
    \item Designed RESTful APIs with cached serverless MongoDB connection pooling and Redux Toolkit state management, achieving sub-200ms page transitions.
    \item \textbf{Tech Stack:} React.js, Redux Toolkit, Node.js, Express.js, MongoDB, JWT, OpenRouter API, RAG, Tailwind CSS
  \resumeItemListEnd

  \resumeProject
    {AvoCart --- E-Commerce Platform}
    {\href{https://avo-cart-client.vercel.app/}{\underline{Live Demo}} $|$ \href{https://github.com/Sourabhpande532/AvoCartClient}{\underline{GitHub}}}
    {01/2026 -- 07/2026}
  \resumeItemListStart
    \item Developed a scalable multi-category e-commerce application with product catalogs, persistent shopping carts, wishlists, and order processing.
    \item Integrated an intelligent customer-support chatbot using Retrieval-Augmented Generation (RAG) to resolve order and product queries in real time.
    \item Implemented secure multi-provider authentication with OAuth 2.0 and JWT, and optimized MongoDB aggregation pipelines for inventory calculations.
    \item \textbf{Tech Stack:} React.js, Node.js, Express.js, MongoDB, RAG, OAuth 2.0, JWT, CSS
  \resumeItemListEnd

  \resumeProject
    {CollabCore --- Project Management Application}
    {\href{https://collab-core-br21.vercel.app/}{\underline{Live Demo}} $|$ \href{https://github.com/Sourabhpande532/CollabCore}{\underline{GitHub}}}
    {04/2026 -- 08/2026}
  \resumeItemListStart
    \item Architected a team productivity application supporting real-time task lifecycle tracking, sprint planning, and interactive project status dashboards.
    \item Implemented multi-criteria search filters, nested task discussions, and activity audit logging, secured with JWT token authentication.
    \item Built a responsive user interface that gives teams a clear, real-time view of project progress across devices.
    \item \textbf{Tech Stack:} React.js, Node.js, Express.js, MongoDB, JWT, RESTful APIs, Bootstrap
  \resumeItemListEnd

\resumeSubHeadingListEnd

%-----------PUBLICATIONS-----------------
\section{Technical Publications \& Writing}
\resumeSubHeadingListStart

  \resumeProject
    {Mastering the JavaScript Event Loop}
    {\href{https://saurabh532.hashnode.dev/mastering-the-javascript-event-loop-microtasks-vs-macrotasks-with-example}{\underline{Hashnode}}}
    {March 18, 2026}
  \resumeItemListStart
    \item Explained microtasks, macrotasks, and the V8 runtime execution stack, showing how JavaScript handles asynchronous operations.
  \resumeItemListEnd

  \resumeProject
    {The Closure Cookbook: Practical Recipes for Real-World JavaScript}
    {\href{https://saurabh532.hashnode.dev/the-closure-cookbook-practical-recipes-for-real-world-javascript}{\underline{Hashnode}}}
    {May 11, 2026}
  \resumeItemListStart
    \item Wrote a comprehensive guide to lexical scoping, memory management, and closure patterns, with practical real-world examples.
  \resumeItemListEnd

  \resumeProject
    {Beginner's Guide to CI/CD: How Automation Saved My Weekends}
    {\href{https://saurabh532.hashnode.dev/beginners-guide-to-ci-cd-how-automation-saved-my-weekends}{\underline{Hashnode}}}
    {June 22, 2026}
  \resumeItemListStart
    \item Documented GitHub Actions deployment pipelines for modern web applications, covering automated build, test, and deploy workflows.
  \resumeItemListEnd

\resumeSubHeadingListEnd

%-----------EDUCATION-----------------
\section{Education}
\resumeSubHeadingListStart
  \resumeSubheading
    {Bachelor of Vocational (B.Voc) in Hardware \& Networking}{2018 -- 2022}
    {Rashtrasant Tukadoji Maharaj Nagpur University (RTMNU)}{CGPA: 9.23 / 10.0 (First Class with Distinction)}
  \resumeItemListStart
    \item \textbf{Relevant Coursework:} Computer Architecture, Data Communications, Operating Systems, Network Protocols
  \resumeItemListEnd
\resumeSubHeadingListEnd

\end{document}


### 0.2 Current resume PDF (optional)
> Attach the compiled PDF or paste its text. This helps check how the resume actually looks and how text is extracted.
This I share with prompt form of pdf


### 0.3 Portfolio
```
https://saurabh-pande.netlify.app/
```

### 0.4 Projects and blogs shown in the portfolio
> The portfolio has 3 projects and 3 blogs. If left blank, the agent will read them directly from the portfolio.
Project Name: TalentHub,AvoCart,CollabCore
Blog Name: EventLoop, closure, and CICD
NOTE:  you can also read from Resume PDF, or current overleaf code or portfolio but it should be consistant no mismatch just for idea i shared to you some name 

### 0.5 Target role and level
```
[ e.g. Full-Stack Developer (MERN), fresher / entry level, location, job type ]
```

### 0.6 Sample job descriptions (optional)
> Paste 1 to 3 real job descriptions I am applying to. They help with keyword alignment.
```
[ PASTE JOB DESCRIPTIONS HERE ]
```

### 0.7 Extra notes (optional)
```
[ ANYTHING ELSE THE AGENT SHOULD KNOW ]
```

## 1. Objective
Review my current resume from a **recruiter's and ATS's point of view**, tell me honestly what is good and what must improve, check that it is **consistent with my portfolio**, recommend the best Overleaf template if my current one is not suitable, and then **redesign the resume in Overleaf (LaTeX)** so that it is clean, organised, well structured, easy to scan, ATS-friendly, and fully genuine.

My work, my projects, and my blogs must stay exactly the same. Only the presentation, wording, structure, and quality improve.

## 2. Questions to Answer (every one must be answered clearly)
1. **Market standard:** Does this resume meet the market standard for my target role and level? If not, what should change?
2. **Clean, organised, well structured:** From a recruiter's point of view, is it clean and easy to scan? If not, what exactly should change, and how should it align with my portfolio?
3. **ATS friendliness:** Is the resume ATS-friendly? What could break parsing? (See the honesty rule in Section 7.)
4. **Template:** Is my current Overleaf template suitable? If not, which Overleaf template should I use, and where exactly do I find it in Overleaf?
5. **Portfolio consistency:** Is the resume consistent with the portfolio, including the 3 projects and 3 blogs? List every mismatch.
6. **Genuine impression:** Does the resume show genuine interest and real work? Are there any mistakes, exaggerations, or anything that could look fake?
7. **Redesign:** Provide the improved resume as complete, working Overleaf (LaTeX) code.

## 3. Phase 1: Review (no redesign yet)

### 3.1 Recruiter scan (the first 6 to 10 seconds)
Judge what a recruiter notices first: name and contact line, headline or summary, skills, projects, education. Is the most important information easy to find? Is the layout balanced, with consistent spacing and no crowding?

### 3.2 Content review
- **Header:** name, email, phone, location, and links (portfolio, GitHub, LinkedIn). Every link must be correct, working, and shown in a clean way.
- **Summary or headline:** short, specific, and honest, or removed if it adds nothing.
- **Skills:** grouped logically (languages, frontend, backend, databases, tools). Only real skills that I can explain. Nothing duplicated or padded.
- **Projects:** each project has a clear purpose, the tech stack, what I built, and the real result. Bullets start with strong action verbs, are specific, and are not vague. Numbers only if they are real.
- **Blogs and other sections:** presented clearly, with correct titles and links.
- **Education and certifications:** correct, consistent, and in a sensible order.
- **Length and density:** one page is expected for a fresher or entry level, unless there is a strong reason for more.
- **Consistency:** the same date format, the same tense for similar items, the same bullet style, and the same capitalization rules.
- **Keyword alignment** with the target role (Section 0.5 and 0.6), without keyword stuffing.

### 3.3 Language check
Spelling, grammar, typos, punctuation, capitalization of technology names (for example JavaScript, Node.js, MongoDB, React, PostgreSQL), and wording that sounds copied, generic, or AI-written. List every issue with the exact line.

### 3.4 ATS and technical check
- One-column, simple layout. No tables used for layout, no text boxes, no text inside images, no icons that replace text, no unusual fonts.
- Standard section names (for example Education, Skills, Projects, Experience).
- Text must be selectable and extract in the right reading order. Check the PDF text extraction if possible, and confirm that the LaTeX produces machine-readable text (for example `\input{glyphtounicode}` and `\pdfgentounicode=1` where the compiler supports them).
- Hyperlinks work and the visible text is meaningful. Important URLs should also appear as visible text.
- Contact details are plain text, not inside the PDF header or footer metadata only.
- No hidden text, no white text, no keyword tricks.
- Clean LaTeX: compiles without errors or serious warnings on Overleaf, with no unusual packages.

### 3.5 Resume vs portfolio consistency matrix
Create a table with one row per project and per blog, and these columns: **Item | Resume says | Portfolio says | Match? | Fix needed**. Compare names, descriptions, tech stack, features, links, and dates. Also compare my skills, education, and contact links. Every mismatch must be listed.

### 3.6 Scorecard
Give a score from 1 to 10 with a short reason for each: recruiter scan, structure and cleanliness, content quality, language, ATS compatibility, portfolio consistency, and overall market readiness. Be honest and specific. Do not flatter.

## 4. Template Recommendation
1. Judge my current template against these criteria: single column, clean typography, standard fonts, good use of space, easy to maintain, and ATS-safe.
2. If it is already suitable, say so and keep it. Do not change the template without a real reason.
3. If it is not suitable, recommend **one best template**, plus at most two alternatives, with a short reason for each. Avoid two-column, photo-heavy, icon-heavy, or graphic-heavy templates.
4. Give the **exact path** to find the recommended template in Overleaf, step by step (for example: Overleaf → Templates gallery → CV / Resume category → template name → Open as Template), with the link if available. If the agent can browse, it must verify that the template still exists and is current. If it cannot verify, it must say clearly that this is unverified.
5. Explain how to move my content into the new template safely.

## 5. Phase 2: Redesign in Overleaf (LaTeX)
1. Produce a **complete `main.tex`** (and any extra file needed) that compiles on Overleaf without errors.
2. Keep the same facts: same projects, same blogs, same education, same skills, same links, same dates. Improve only the structure, wording, spacing, and consistency.
3. Wording rules:
   - Simple, clear, professional English, written the way a real candidate writes.
   - Short, specific bullets that start with strong action verbs and explain what I built, how, and with what result.
   - No buzzwords or filler such as "passionate", "hard-working", "leveraged", "cutting-edge", "seamless", or "robust", unless they carry real meaning.
   - No spelling, grammar, or typo mistakes.
4. Layout rules: clean, balanced, easy to scan, consistent spacing and alignment, one page where possible, and no unnecessary decoration.
5. Align the resume with the portfolio: the same project names, the same descriptions in a shorter form, the same tech stack, and working links.
6. Add short comments in the LaTeX code only where they help me edit it later (for example where to change a link).

## 6. Hard Constraints
- **Do not invent anything.** No fake experience, skills, tools, certifications, metrics, numbers, dates, company names, or achievements. Use only what is in my resume, my portfolio, and what I tell the agent.
- If information is missing or unclear, write `[CONFIRM WITH ME]` and ask. Do not guess.
- Do not exaggerate. If something is simple, describe it simply and honestly.
- Do not use hidden text, keyword stuffing, or any trick to fool an ATS.
- Do not change my portfolio or my project code. This task is read-only for those.
- Do not remove any of my 3 projects or 3 blogs.
- Do not use a photo, graphics, or icons that replace text.
- Do not change my Portfolio as current you are while doing this resume work!
- Portfolio remain intack and unchange!

## 7. Honesty Rule About ATS and Shortlisting
- No one can guarantee shortlisting, and ATS systems differ from each other. The agent must **not** promise or predict that the resume will be shortlisted.
- Instead, give a clear **ATS compatibility assessment**: what is safe, what is risky, and why, plus the factors that affect shortlisting (relevance to the job, keywords, clarity, and proof of work).
- If the agent cannot test something (for example a real ATS parser), it must say so.

## 8. Deliverables
1. **Review report** with answers to all 7 questions in Section 2.
2. **Scorecard** (Section 3.6).
3. **Consistency matrix** (Section 3.5) with the exact fixes.
4. **Template recommendation** with the exact Overleaf path (Section 4).
5. **Redesigned resume**: complete, ready-to-paste LaTeX code.
6. **Change log:** what changed and why, section by section.
7. **Confirm list:** every `[CONFIRM WITH ME]` item.
8. **Proofreading result:** a final spelling and grammar pass with no remaining mistakes.
9. **Resume talking points:** the 5 questions a recruiter is most likely to ask about this resume, each with a short, natural answer in simple English. For every answer, include a memory trick, one analogy, and 2 common examples I can use to explain it.

## 9. Acceptance Criteria
- [ ] All 7 questions are answered clearly and honestly.
- [ ] Every mismatch between the resume and the portfolio is listed and fixed.
- [ ] The ATS assessment is honest, with no shortlisting promise.
- [ ] The template recommendation is justified, with a verified or clearly marked exact Overleaf path.
- [ ] The redesigned LaTeX code compiles on Overleaf and uses only real, confirmed information.
- [ ] The resume is clean, well structured, easy to scan, and consistent.
- [ ] No spelling, grammar, or typo mistakes remain.
- [ ] Nothing is fake, exaggerated, or invented, and unclear points are marked `[CONFIRM WITH ME]`.
- [ ] My portfolio and project code were not modified.

---
### Execution order for the agent
Read Section 0 fully → open and read my portfolio (projects and blogs) → review the resume (Phase 1) → build the consistency matrix and scorecard → recommend the template if needed → ask me to confirm anything unclear → redesign in LaTeX (Phase 2) → proofread and check against the portfolio again → deliver everything in Section 8.