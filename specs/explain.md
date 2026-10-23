# SPEC: Portfolio Study and 15-Minute (if case, extend) Interview Explanation Script

## 0. Inputs

### 0.1 Portfolio link
```
https://saurabh-pande.netlify.app/

```


## 1. Type & Intent
- **Type:** Analysis + Documentation (read-only task)
- **Goal:** Study & analysis the portfolio and its projects properly, then write a **15-minute spoken explanation script or you can extend if you want** (as a markdown file) that I can use to explain my work to a recruiter or interviewer, and to record a video walkthrough. you have been with me so very time you know my project very well just tell how to explain my portfolio to recruiter all point should be cover whaterver present in portfolio so i can explain.
- **Purpose:** I should be able to confidently recall **what I built, why I built it, and how each major feature works**, in my own natural voice. 

## 2. Mandatory Study Phase (do this before writing anything)
1. Open the live portfolio and go through every section and every project link tell how to explain. 
2. Note real technical decisions visible in the code (why this library, this folder structure, this data model).
3. Build an internal fact list of what is truly implemented. The script may only use this list.

## 3. Output Deliverables
1. **`portfolio-explanation-script.md`**: the main 15-minute script or extend as per if case
2. **Quick recall sheet** at the end of the same file: a one-page cheat sheet with the project in 10 lines, the tech stack, and the 5 flows to remember.
3. **Likely interview questions** (15-20) with short, natural answers based only on the real implementation (details in Section 7).
4. **Honest gaps list**: things that are not implemented or are simple, with a truthful way to talk about them confidently.

## 4. Script Structure (about 2,000 to 2,300 spoken words, roughly 15 minutes)
| Part | Time | What to cover |
|---|---|---|
| Introduction | 1 min | Who I am, what I build, what this portfolio is |
| Portfolio overview | 2 min | Layout, sections, design choices, why I built it this way |
| Project 1 (or main project) | 5 min | Problem, why I built it, features, frontend flow, backend flow, database |
| Other projects | 3 min | Short version of each: purpose, stack, one interesting decision |
| Performance, responsiveness, PWA | 1.5 min | What I did and how I checked it (only if actually implemented) |
| Challenges and learnings | 1.5 min | Real problems faced and how I solved them |
| Closing | 1 min | What I would improve next, why I am a good fit |

For each major feature, explain in this order: **what I built → why I built it → how it works.**

## 5. Voice and Style Rules
- Write in the first person ("I built", "I decided", "I used").
- Use simple, natural, spoken English, with short sentences and contractions (I'm, I've, it's).
- It should sound like a real candidate talking, not a document: conversational, calm, and slightly informal.
- Explain the **thinking behind decisions**, not just a list of features.
- Use natural connectors such as "So the first thing I did was...", "The reason I chose this was...", "One problem I ran into was...".
- Do not sound AI-generated, copied, or overly formal. Avoid buzzwords and filler such as "leverage", "seamless", "robust", "cutting-edge", "delve", "comprehensive solution", "in today's world".
- Do not over-explain code. Stay at the level of flows and decisions, with a small technical detail only where it helps recall.
- Do not overclaim. If something is basic, say it simply.
- Add short spoken pauses or cues in brackets, such as *[pause]* or *[show this section on screen]*, to help during a video.

## 6. Recall Aids (required for every major section of the script)
For each major feature or project section, add a small box after the script text with:
1. **Memory trick:** a short mnemonic or keyword chain to remember the flow.
2. **Analogy:** one simple real-life analogy to explain the idea.
3. **2 common examples:** two simple, common examples I can use if the interviewer asks me to explain further.

## 7. Interview Q&A (extension)
Include likely questions grouped by topic, each with a short, natural spoken answer:
- Project and decisions: why this project, why this stack, what was hard.
- Frontend: component structure, state management, routing, responsiveness.
- Backend: API design, authentication, validation, error handling, database choices.
- Performance and PWA: Lighthouse, optimization steps, caching, service worker.
- Behavioral: teamwork, learning, what I would improve.
Every answer must be traceable to the real code or portfolio.

## 8. Accuracy Rules (hard rules)
- Do **not** invent features, architecture, files, libraries, metrics, or technical decisions that are not present in the project.
- Do **not** assume. If something cannot be confirmed from the code or the live site, mark it as `[CONFIRM WITH ME]` instead of guessing.
- Do **not** claim scores, user counts, or results unless they are visible in the project.
- Every statement in the script must match the actual implementation.

## 9. Constraints (hard rules)
- **Read-only task.** Do **not** modify any code, file, config, dependency, or environment variable in the project.
- Do **not** add new features, refactor, restyle, or fix anything. If a bug or weakness is noticed, list it in the "Honest gaps" section only.
- Create only the new markdown output file(s); touch nothing else.

## 10. Acceptance Criteria
- [ ] The portfolio and all project were studied before writing.
- [ ] The script fits about 15 minutes when spoken and follows the structure
- [ ] It reads like a real person speaking in the first person, with no AI-sounding phrasing.
- [ ] Every major section explains what, why, and how.
- [ ] Every major section has a memory trick, an analogy, and 2 common examples.
- [ ] Interview Q&A, quick recall sheet, and honest gaps list are included.
- [ ] No invented or unverifiable claims; uncertain points are marked `[CONFIRM WITH ME]`.
- [ ] No project file was modified.

---
### Execution order for the agent
Study portfolio and code → build the verified fact list → draft the script in my voice → add recall aids → add Q&A, recall sheet, and gaps → check every claim against the code → confirm no file was changed → deliver the markdown file.