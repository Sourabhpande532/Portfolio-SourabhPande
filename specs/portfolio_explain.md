# Portfolio Walkthrough & 15-Minute Interview Explanation Script

> **Candidate:** Sourabh Pande  
> **Role Target:** Full Stack Developer (MERN Stack & Agentic AI)  
> **Portfolio URL:** [https://saurabh-pande.netlify.app/](https://saurabh-pande.netlify.app/)  
> **Total Spoken Word Count:** ~2,250 words (approx. 15 minutes at a relaxed 145–150 wpm pace)

---

## Part 1: Introduction & Who I Am (1 Minute | ~150 words)

*[Smile, look directly into the camera or at the interviewer, take a calm breath]*

"Hi, thanks for taking the time to chat with me today. My name is Sourabh Pande, and I'm a full-stack engineer specializing in the MERN stack, Python, and modern AI architectures like RAG pipelines and agentic workflows. 

*[Brief pause]*

What drives my work is building web applications that solve practical, everyday problems without unnecessary bloat. I like taking complex systems—whether that's role-based hiring workflows, real-time messaging over WebSockets, or AI assistants that can query internal documents—and turning them into clean, reliable software that users find intuitive.

*[Show hero section on screen: name, role badge, contact links]*

I built this portfolio to give you an honest, clear window into the software I write, the technical decisions I make, and how I approach engineering end-to-end. I'm excited to walk you through my projects and answer any questions you have along the way."

---

## Part 2: Portfolio Overview & Design Philosophy (2 Minutes | ~290 words)

*[Scroll gently from the hero section to the navigation and project cards]*

"Before we dive into individual apps, I want to take a couple of minutes to explain how and why I built this portfolio site itself. 

*[Pause]*

When a lot of developers build a portfolio, the default impulse is to grab Next.js, Gatsby, or a heavy React template. But when I sat down to design this site, I asked myself: *what is the actual job of this website?* The job is to deliver information fast, look clean, work reliably on any screen, and showcase my projects with zero friction.

So, I deliberately chose to build the portfolio using pure semantic HTML5, modular Vanilla CSS, and lightweight Vanilla JavaScript. No heavy client-side JavaScript bundles, no hydration delays, and no complex build pipelines. 

*[Show navbar and mobile hamburger menu]*

The navigation uses a straightforward structure: About, Projects, Blogs, and Connect. On mobile, I implemented a custom hamburger menu in vanilla JavaScript with an accessible toggle state, click-outside dismissal, and smooth scrolling to each section. 

*[Point out the theme and typography]*

Visually, I went with a dark, high-contrast engineering theme. I divided the styling across small, focused CSS files—`style.css`, `navbar.css`, `card.css`, `skills.css`, `blog.css`, and `Responsive.css`. That kept the code maintainable without needing a CSS preprocessor. 

I deployed it directly on Netlify, which gives me near-instant page loads worldwide. It proves that I don't just use frameworks for the sake of using them—I choose the simplest, most effective tool for the specific problem in front of me."

### 🧠 Section 2 Recall Box
- **Memory Trick:** *KISS* (Keep It Simple, Static) → **H-C-J-N** (HTML5, Clean CSS, JS Vanilla, Netlify).
- **Analogy:** Choosing a bicycle instead of a semi-truck to deliver a letter across town. A full React SPA is overkill for static content; vanilla web standards make it fly.
- **2 Common Follow-up Examples:**
  1. *If asked about bundle size:* "By skipping React here, I avoided shipping 150KB+ of framework runtime just to render static text and cards."
  2. *If asked about accessibility:* "I used semantic `<section>` and `<nav>` elements with `aria-label` and `aria-expanded` attributes on the mobile hamburger toggle."

---

## Part 3: Deep Dive: Main Project — TalentHub (5 Minutes | ~720 words)

*[Scroll to Project 01: TalentHub – AI-Powered Hiring Platform]*

"Now, let's look at my primary featured project: **TalentHub**. 

### 1. What I Built & The Problem It Solves
*[Show TalentHub live demo card on screen]*

TalentHub is a full-stack, AI-powered hiring platform that connects recruiters and job applicants in a single, organized system. 

The problem I wanted to solve came from watching how messy hiring usually is. Recruiters often juggle spreadsheets, multiple job boards, and manual applicant tracking. Meanwhile, candidates apply into a void and have no structured way to prepare for specific role requirements. 

I built TalentHub to streamline that pipeline. Recruiters can create, publish, and manage job listings, track applications stage-by-stage, and view applicant profiles. Applicants can search for open positions, submit applications, track their status, and use built-in interview preparation assistance.

### 2. Why I Chose This Architecture
*[Pause]*

From an architecture standpoint, this app has two very distinct user personas: recruiters and applicants. Because their permissions and workflows are completely different, I made three foundational architectural decisions:

First, on the backend, I structured the code using the **MVC (Model-View-Controller)** pattern on Node.js and Express. It keeps business logic cleanly separated from database operations and route handlers.

Second, I built a strict **Role-Based Access Control (RBAC)** system backed by JWT authentication. An applicant should never be able to trigger a candidate status update, and a recruiter shouldn't be applying to their own postings. The backend checks role permissions on protected API endpoints via custom middleware.

Third, on the frontend, I used **React with Redux Toolkit**. As users move between job browsing, application tracking, and profile updates, multiple UI components need the current authentication state and application status. Redux Toolkit gave me predictable state management with slices, without the boilerplate of legacy Redux.

### 3. How the Flows Work (End-to-End)
*[Point to the workflow]*

Let me walk you through how the system works during a typical user journey:

**Authentication Flow:**  
When a user signs up, they pick their role. The backend hashes their password with bcrypt, creates the user record in MongoDB, and issues a signed JSON Web Token containing their user ID and role. On the frontend, that token is stored securely and dispatched to our Redux auth slice so the UI instantly adapts to either the recruiter dashboard or candidate view.

**Recruiter Flow:**  
A recruiter logs in and clicks 'Create Job'. The frontend validates the form inputs and dispatches an API request. The Express controller runs role verification middleware—if the token role isn't 'recruiter', it returns a 403 Forbidden immediately. Once verified, the job document is saved in MongoDB. The recruiter's dashboard then updates via Redux state to display the active job post along with real-time applicant counts.

**Applicant & Tracking Flow:**  
An applicant discovers the job, uploads or submits their details, and applies. The backend records an Application document linking the candidate ID and the job ID with an initial status of 'Pending'. When the recruiter reviews the profile and updates the status to 'Interviewing' or 'Shortlisted', that update modifies the database and immediately reflects on the candidate's tracking dashboard.

For the UI, I used Bootstrap to build clean, responsive dashboards quickly, ensuring that both recruiters on desktop monitors and job seekers on mobile phones have an equally comfortable layout."

### 🧠 Section 3 Recall Box
- **Memory Trick:** **R-M-J-R** → **R**edux Toolkit (State) → **M**VC (Backend structure) → **J**WT (Authentication) → **R**BAC (Security boundaries).
- **Analogy:** Airport security gates. Everyone gets an ID card (JWT), but the boarding pass specifies your role (Economy vs. Pilot). The door guards (RBAC middleware) stop unauthorized passengers from entering the cockpit (Recruiter controls).
- **2 Common Follow-up Examples:**
  1. *If asked how RBAC is enforced:* "I created an Express middleware function `checkRole(['recruiter'])` that reads the decoded JWT payload from `req.user` before the controller logic executes."
  2. *If asked why Redux Toolkit:* "Because application status changes need to reflect across both the job card list and the applicant's status history page without prop drilling through five component layers."

---

## Part 4: Secondary Projects Tour (3 Minutes | ~460 words)

*[Scroll through the remaining project cards: AstraAIs, AvoCart, CollabCore, Imgixy, Chat APP]*

"Beyond TalentHub, I've built several full-stack and specialized applications that demonstrate different engineering strengths.

### 1. AstraAIs — Enterprise AI Employee Assistant
*[Show AstraAIs card]*
Right next to TalentHub is **AstraAIs**, which is an AI-driven employee management system. It handles leave tracking, scheduling, and employee growth analytics. The technical highlight here is that I used **TypeScript and RAG (Retrieval-Augmented Generation)** with agentic AI principles. Instead of an employee having to search through a 50-page company policy PDF, the system embeds policy documents and retrieves exact contextual answers while handling internal requests like leave calculations.

### 2. AvoCart — E-Commerce Platform
*[Show AvoCart card]*
Next is **AvoCart**, a full-stack MERN e-commerce application. Beyond the standard product catalog, shopping cart, and checkout flow, I integrated an **AI shopping assistant chatbot** to help users discover products, and implemented dual authentication using both standard **JWT and Google OAuth 2.0**. That gave users a frictionless social login option while preserving secure session handling.

### 3. CollabCore — Project Management Application
*[Show CollabCore card]*
Then there's **CollabCore**, which is a team collaboration and task tracking app built with React, Express, Node.js, and MongoDB. The core challenge here was managing relational-style data—teams, projects, task boards, and member assignments—inside MongoDB. I designed clean schema references and built indexed queries so task status transitions happen smoothly across team boards.

### 4. Imgixy — AI Photo Library
*[Show Imgixy card]*
**Imgixy** is a media management tool built in TypeScript. Storing raw binary image files directly in a database is an antipattern, so I integrated **Cloudinary's API**. The client uploads directly or via server signatures, and MongoDB only stores secure image URLs, metadata, and auto-generated tags, keeping database storage minimal and media delivery fast via CDN.

### 5. Chat APP / CHAT_FLOW — Real-Time Messenger
*[Show Chat APP card]*
Finally, I built **Chat APP (CHAT_FLOW)** to master real-time communication. While traditional HTTP requests are request-response, real-time messaging needs persistent, bidirectional communication. I used **WebSockets with Node.js and MongoDB**. When a user sends a message, it doesn't poll an API; it pushes through an active WebSocket connection, checks if the recipient's socket ID is active, and delivers the message with sub-second latency."

### 🧠 Section 4 Recall Box
- **Memory Trick:** **A-A-C-I-C** → **A**straAIs (RAG/AI) → **A**voCart (OAuth/Ecom) → **C**ollabCore (Task/Teams) → **I**mgixy (Cloudinary Media) → **C**hatFlow (WebSockets).
- **Analogy:** A versatile toolbox. A hammer (REST) is great for forms, but you need a walkie-talkie (WebSockets) for instant chat, and a filing cabinet (Cloudinary CDN) for heavy photos.
- **2 Common Follow-up Examples:**
  1. *If asked about WebSockets vs Polling:* "Polling wastes server bandwidth with empty HTTP headers every 2 seconds. A persistent WebSocket handshake keeps an open TCP channel that only transfers data when an event actually fires."
  2. *If asked why Cloudinary in Imgixy:* "Storing image binaries in MongoDB would blow past the 16MB document limit and slow down queries. Cloudinary handles transformations and edge caching."

---

## Part 5: Performance, Responsiveness & Web Standards (1.5 Minutes | ~220 words)

*[Scroll up to the Skills section and highlight the frontend/tools grid]*

"Now, let's talk about performance and responsiveness, because a full-stack engineer needs to care about the user experience on actual devices.

*[Pause]*

On this portfolio, I achieved great responsiveness without adding any CSS utility library like Tailwind or Bootstrap. I wrote standard **CSS Flexbox and CSS Grid** rules in `style.css` and `card.css`, with dedicated media query breakpoints in `Responsive.css`. 

*[Point out mobile responsiveness]*

On desktop, the projects display in an organized multi-column grid. When the viewport narrows down to a tablet or mobile screen, the grid gracefully stacks into single columns, cards adjust their padding, and the horizontal navigation collapses into a slide-out drawer.

For assets, I used modern vector SVG icons and optimized WebP and PNG previews. I also set explicit width and height attributes on SVGs to prevent layout shifts. 

*[Pause]*

One honest note: this portfolio is a lightweight static site, not a Progressive Web App (PWA). I didn't register a Service Worker or offline cache manifest here because it's purely informational. Instead, I focused on high initial rendering speed: minimal DOM nodes, asynchronous script loading, and zero render-blocking framework scripts. When a recruiter opens this link on their phone, it loads in a fraction of a second."

### 🧠 Section 5 Recall Box
- **Memory Trick:** **G-F-M-S** → **G**rid (Layout) → **F**lexbox (Alignment) → **M**edia Queries (Breakpoints) → **S**VG/WebP (Optimized Assets).
- **Analogy:** Packing light for a quick day trip. You don't need heavy luggage (Service Workers, PWA manifests, CSS runtimes) when all you need is a map and your keys.
- **2 Common Follow-up Examples:**
  1. *If asked how mobile layout was tested:* "I tested using Chrome DevTools across standard viewports—375px mobile, 768px tablet, and 1440px desktop—ensuring touch targets for buttons are at least 44 pixels high."
  2. *If asked about cumulative layout shift (CLS):* "I specified explicit icon dimensions and aspect ratio constraints on project preview images so the page doesn't jump as images load."

---

## Part 6: Engineering Challenges & Real Learnings (1.5 Minutes | ~230 words)

*[Shift to an open, reflective tone]*

"Every project I've built came with real technical problems that forced me to dig deep. I want to highlight two specific challenges I faced.

*[Pause]*

The first challenge was **state synchronization and token expiration in TalentHub**. When you have role-based protected routes, token expiry can cause weird UI glitches if not handled correctly. For instance, if a recruiter's session token expires while they are in the middle of reviewing applicants, naive client code might let them click 'Accept' only to throw an unhandled 401 error. 

I solved this by writing an Axios response interceptor. Whenever any API call returned a 401, the interceptor automatically dispatched an action to reset the Redux auth state, cleared the expired token from storage, and redirected the user to the login screen with a friendly message indicating their session had timed out.

The second challenge was **connection state management in Chat APP**. With WebSockets, network drops happen—someone closes their laptop lid or switches Wi-Fi networks. Initially, severed connections left ghost users in the online list. 

I resolved this by implementing socket heartbeat ping-pong events and listening to the `disconnect` event on the server. When a client socket disconnects, the server immediately updates the user's active status in the online registry and broadcasts the updated list to all active rooms."

### 🧠 Section 6 Recall Box
- **Memory Trick:** **I-H** → **I**nterceptor (Graceful 401 recovery) + **H**eartbeat (Socket disconnect cleanup).
- **Analogy:** A smoke detector with a backup battery. You don't wait for the house to catch fire (unhandled crash); you handle the low-battery beep gracefully before it causes panic.
- **2 Common Follow-up Examples:**
  1. *If asked about Axios interceptors:* "Axios interceptors let you centralize error handling so individual React components don't need boilerplate try-catch blocks for session timeouts."
  2. *If asked about WebSocket disconnections:* "Using the `socket.on('disconnect')` handler, we emit a `user_offline` event with the user's ID to clean up UI status indicators."

---

## Part 7: Closing & What's Next (1 Minute | ~160 words)

*[Scroll to Connect section with email and social links]*

"To wrap up, building these projects has given me a solid end-to-end foundation: from architecting REST APIs and database schemas to building responsive frontends and integrating AI workflows.

*[Pause]*

What I'm focused on learning next is deepening my knowledge of distributed systems—specifically advanced PostgreSQL query optimization, database indexing strategies, and deploying autonomous multi-agent systems using tools like LangGraph.

I'm actively looking for a full-stack engineering role where I can contribute clean, maintainable code, collaborate with a strong team, and continue growing as an engineer. 

My contact details, GitHub, and LinkedIn are right here in the Connect section, and you can also check out my technical articles on Hashnode where I break down topics like the JavaScript Event Loop and Closures.

Thank you so much for your time, and I'd love to answer any questions you have!"

---

## 8. Honest Gaps & How to Talk About Them Confidently

As an engineer, knowing your boundaries and being truthful about trade-offs builds immense credibility with senior interviewers. Here are the honest gaps in the portfolio and projects, along with how to speak about them:

| Gap Identified | Technical Reality | How to Answer Confidently |
|---|---|---|
| **No PWA / Service Worker** | The portfolio is a static HTML/CSS site with no offline cache manifest or service worker. | *"I kept this portfolio as a lightweight static site without service workers because it is purely informational. In an e-commerce or messaging app, I'd implement service workers for offline caching, but here, standard browser caching and Netlify CDN gave me the fastest load times."* |
| **README mentions React** | The repository `README.md` lists React under technologies used, but the portfolio code is pure HTML5, CSS3, and Vanilla JS. | *"When I first initiated the portfolio repository, I had planned a React SPA, but after evaluating the requirements, I recognized that React added unnecessary bundle weight for a static portfolio. I deliberately switched to clean HTML and CSS, though I should clean up that line in the README."* |
| **No automated test suite** | There are no Jest/Playwright tests in this portfolio repo. | *"For the static portfolio, visual regression and responsive DevTools testing were sufficient. For complex business logic like the RBAC middleware and application state transitions in TalentHub, I prioritize unit testing API endpoints with Jest and Supertest."* |
| **Free-tier hosting cold starts** | Projects deployed on Vercel/Render free tiers may experience a 10–20 second delay on initial API spin-up. | *"Because my demo backend APIs are hosted on cloud free tiers, they spin down during inactivity and take a few seconds to warm up on first request. In a production environment, we'd use persistent container instances or warm serverless functions behind a CDN."* |
| **No dark/light theme toggle button** | The site uses a fixed dark developer theme with no toggle switch. | *"I designed the portfolio with a deliberate, cohesive dark aesthetic tailored for developers. Adding a theme toggle is straightforward with CSS custom variables, and it's on my roadmap for future polish."* |

---

## 9. Likely Interview Questions & Natural Answers (20 Q&A)

### Topic 1: Project & Architectural Decisions
**Q1: Why did you build TalentHub instead of a standard CRUD to-do or blog app?**  
*Answer:* "A simple to-do app only tests basic CRUD operations. TalentHub let me solve a real multi-actor problem: having two completely distinct user journeys—recruiters and applicants—with different permissions, validation rules, and relational status workflows."

**Q2: How did you decide between MongoDB and a relational database like PostgreSQL for TalentHub?**  
*Answer:* "TalentHub's job listings have flexible attributes—salary ranges, custom requirement tags, and varying application question formats. MongoDB's document model allowed me to evolve that schema quickly without heavy database migrations during development."

**Q3: Why did you build the portfolio itself in Vanilla HTML and CSS instead of React?**  
*Answer:* "Because engineering is about trade-offs. Shipping 150KB of React JavaScript runtime just to render static project cards and contact links hurts mobile load performance. Vanilla HTML and CSS load in milliseconds with zero dependencies."

**Q4: In AstraAIs, what was your approach to RAG?**  
*Answer:* "Instead of feeding an entire 50-page company policy to an LLM on every query—which is expensive and hits context limits—I chunk the policy documents, generate vector embeddings, retrieve only the top relevant chunks for the user's question, and feed that focused context to the model."

---

### Topic 2: Frontend Engineering
**Q5: Why did you choose Redux Toolkit over React Context in TalentHub?**  
*Answer:* "React Context is great for low-velocity global state like themes or auth tokens. But in TalentHub, where application statuses, filter states, and job lists update frequently, Context can cause unnecessary re-renders across the component tree. Redux Toolkit gives fine-grained selector subscriptions and organized slice reducers."

**Q6: How did you handle mobile navigation on the portfolio?**  
*Answer:* "I wrote a vanilla JS event listener that toggles an `.open` class on both the hamburger button and the navigation group. I also added click handlers to all navigation links and the document body so tapping any link or clicking outside automatically dismisses the menu."

**Q7: How do you prevent layout shifts (CLS) when images load?**  
*Answer:* "In CSS, I define fixed aspect ratios and wrapper constraints for project preview cards. In the HTML, I set explicit `width` and `height` attributes on SVGs so the browser reserves the layout space before the asset finishes downloading."

**Q8: What is your approach to CSS organization without utility frameworks?**  
*Answer:* "I divide styles by domain: `style.css` for typography and base layout, `navbar.css` for navigation, `card.css` for project grids, and `Responsive.css` for media query overrides. This avoids 1,000-line monolithic files and makes debugging straightforward."

---

### Topic 3: Backend & Authentication
**Q9: How does your Role-Based Access Control (RBAC) work in Express?**  
*Answer:* "When a user logs in, their verified role is embedded inside their signed JWT payload. I created a reusable middleware `requireRole(['recruiter'])`. It intercepts incoming requests, decodes the token, checks if `req.user.role` matches the allowed list, and either calls `next()` or returns a `403 Forbidden`."

**Q10: Where do you store JWT tokens on the client, and why?**  
*Answer:* "For maximum security in production, httpOnly secure cookies are ideal because they protect against XSS token theft. In quick client demos, localStorage is often used for simplicity, but I always configure backend CORS and sanitization to mitigate risks."

**Q11: Why did you structure the backend using MVC?**  
*Answer:* "MVC creates strict separation of concerns. The router only maps paths, the controller handles request orchestration and response codes, the service/model layer interacts with Mongoose, and views (or JSON responses) return clean payloads. It makes testing and maintenance much simpler."

**Q12: How do you handle file uploads in Imgixy?**  
*Answer:* "I don't store image binaries in MongoDB because of the 16MB BSON limit and performance degradation. Instead, files are uploaded directly to Cloudinary using their SDK, and MongoDB only stores the HTTPS CDN URL, asset ID, and metadata."

---

### Topic 4: Real-Time & Communications
**Q13: Why did you use WebSockets instead of Long Polling for Chat APP?**  
*Answer:* "Long polling keeps opening and closing HTTP connections, sending duplicate headers every few seconds. WebSockets establish a single TCP handshake and maintain an open duplex connection. That means near-zero latency and drastically lower server overhead for live messaging."

**Q14: How do you ensure users receive messages meant only for them?**  
*Answer:* "When a user authenticates their socket, the server maps their user ID to their active `socket.id`. When User A messages User B, the server queries the active socket map and emits the message payload specifically to User B's socket channel rather than broadcasting to everyone."

---

### Topic 5: Performance & Web Standards
**Q15: How did you optimize asset delivery on your portfolio?**  
*Answer:* "I used vector SVGs for all technical skill badges and compressed preview images in WebP format. The static assets are served directly from Netlify's global CDN edge nodes."

**Q16: Why doesn't your portfolio use a Progressive Web App (PWA) setup?**  
*Answer:* "PWAs provide offline caching and app manifests, which are great for dynamic web applications. For a static portfolio site, an aggressive service worker cache can actually cause visitors to see stale project links when you update your work. A clean CDN-backed site is simpler and always fresh."

---

### Topic 6: Behavioral & Work Style
**Q17: What is your process when debugging a tricky production issue?**  
*Answer:* "First, I reproduce the problem locally and isolate whether it's frontend state, network transport, or backend logic using DevTools and server logs. Then I formulate a hypothesis, test it in isolation, and verify that the fix doesn't break edge cases."

**Q18: You write technical articles on Hashnode. Why do you do that?**  
*Answer:* "Teaching is the best way to solidify your own knowledge. Writing articles like my deep dive on the JavaScript Event Loop forces me to understand microtasks, macrotasks, and call stacks down to the engine level, not just surface syntax."

**Q19: How do you keep up with rapid changes in AI and web frameworks?**  
*Answer:* "I build small proof-of-concepts rather than just watching tutorials. When RAG and agentic workflows became prominent, I didn't just read documentation—I built AstraAIs to see where vector search works well and where context windows fail."

**Q20: What kind of team environment brings out your best work?**  
*Answer:* "An environment with high code standards, clear communication, and pragmatic engineering. I value constructive code reviews and teams that focus on delivering real value to users rather than over-engineering."

---

## 10. One-Page Quick Recall Sheet

### The Portfolio in 10 Lines
1. **Who I am:** Sourabh Pande, Full Stack Developer focused on MERN stack, Python, and Agentic AI.
2. **What this site is:** A fast, responsive portfolio built with semantic HTML5 and Vanilla CSS/JS.
3. **Core philosophy:** Use the right tool for the job; avoid unnecessary framework bloat for static content.
4. **Project 1 (Star):** **TalentHub** – Full-stack AI-assisted hiring portal with dual roles, Redux Toolkit, and RBAC.
5. **Project 2:** **AstraAIs** – Enterprise AI employee assistant using TypeScript, RAG, and Agentic workflows.
6. **Project 3:** **AvoCart** – E-commerce platform with MERN, OAuth 2.0 social login, and AI shopping assistant.
7. **Project 4:** **CollabCore** – Team collaboration and project management board with scoped access.
8. **Project 5:** **Imgixy** – AI photo library offloading media storage to Cloudinary CDN.
9. **Project 6:** **Chat APP** – Real-time bidirectional messaging powered by WebSockets and Node.js.
10. **Writing:** Hashnode author covering JavaScript Event Loop internals, Closures, and CI/CD automation.

### The Tech Stack at a Glance
- **Frontend:** React, Redux Toolkit, TypeScript, JavaScript (ES6+), HTML5, CSS3, Bootstrap.
- **Backend & APIs:** Node.js, Express.js, Python, REST APIs, WebSockets, MVC Architecture.
- **Databases:** MongoDB (Mongoose), PostgreSQL, SQL.
- **AI & Integrations:** RAG Pipelines, Vector Search, LLM Tool Calling, Cloudinary, OAuth 2.0, JWT.
- **Deployment & Tools:** Netlify, Vercel, Git/GitHub, VS Code.

### 5 Critical Flows to Remember in Interviews
```
1. TalentHub RBAC Flow:
   Login -> Issue JWT (with role) -> Redux Store -> Protected Route -> Express checkRole(['recruiter']) -> 200 OK / 403 Forbidden.

2. AstraAIs RAG Flow:
   Policy Document -> Chunks -> Embeddings -> User Question -> Vector Similarity Search -> Top Chunks + Prompt -> LLM Answer.

3. Chat APP WebSocket Flow:
   Client Connect -> TCP Handshake -> Map User ID to socket.id -> Send Message -> Server routes to recipient socket.id -> Instant UI render.

4. Imgixy Media Flow:
   Select Image -> Stream to Cloudinary API -> Receive Secure CDN URL -> Save URL in MongoDB -> Render lightweight image preview.

5. Session Recovery Flow:
   Client API Call -> 401 Unauthorized -> Axios Interceptor intercepts -> Reset Redux Auth Slice -> Redirect to Login with Session Expired notice.
```
