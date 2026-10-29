# EX-02-Cross-Platform-Prompting-Evaluating-Diverse-Techniques-in-AI-Powered-Project-Overview-Generation

## AIM

To analyze and compare the performance of various prompting techniques (**Zero-Shot, Few-Shot, Chain-of-Thought, and Role-Based Prompting**) across different AI platforms (**ChatGPT, Gemini, Claude AI, and Microsoft Copilot**) for the purpose of **summarizing and describing a DSA Coding Tracker website project**.

---

# 1. Introduction

## 1.1 What is prompt engineering?

A **prompt** is the instruction, question or context given to a Large Language Model (LLM). **Prompt engineering** is the practice of designing and refining prompts so that the model produces accurate, relevant and well-structured output. The same model can give very different answers to the same task depending on how the prompt is written, so prompt design directly affects quality.

## 1.2 Why prompt structure matters

A weak prompt leaves the model to guess the audience, length, tone and format. A well-structured prompt reduces guessing and gives more predictable results. The five structures used in this experiment add one kind of information at a time:

| Prompt Structure | Information Added | Question It Answers |
|---|---|---|
| Basic Prompt | The task itself | What should the model do? |
| Role Prompt | A persona for the model | Who should the model act as? |
| Context Prompt | Purpose and background | Why is this needed and for whom? |
| Constraint Prompt | Limits and rules | What must be followed or avoided? |
| Output Format Prompt | Layout of the answer | How should the answer look? |

## 1.3 Prompting techniques compared across platforms

| Technique | Description | Typical Use |
|---|---|---|
| Zero-Shot | The task is given with no examples | Quick, simple tasks |
| Few-Shot | A few examples are given so the model copies the style | Consistent style or format |
| Chain-of-Thought (CoT) | The model is asked to reason step by step before answering | Analysis and multi-step tasks |
| Role-Based | The model is told to act as a specific expert | Tone and domain-specific explanations |

## 1.4 Why a DSA Coding Tracker?

Students preparing for placements often practise Data Structures and Algorithms (DSA) problems on several platforms, and their records become scattered. A DSA Coding Tracker website solves this by keeping all practice data in one place. Writing a clear project overview for the README, the project report and the viva is a real task in this project, so it was chosen as the application for prompt design.

---

# 2. Scenario

You are a member of a student development team building a **DSA Coding Tracker website**. The website helps learners log the problems they solve on platforms such as LeetCode and GeeksforGeeks, record the topic, difficulty and status of each problem, write notes, maintain a daily streak and view progress through a dashboard.

The objective is to convert a **detailed project description** into a **150-word project overview** that can be used in the README file, the project report and the viva presentation, using multiple AI platforms and prompting methods.

The generated overviews are assessed based on these factors:

- Accuracy
- Coherence
- Simplicity
- Speed
- User Experience

---

# 3. Project Description Used as Input

```text
Project Name: DSA Coding Tracker

The DSA Coding Tracker is a web application that helps students prepare for coding interviews and placements by tracking their Data Structures and Algorithms practice in one place. After registering and logging in, a user can add every problem they solve, along with the problem name, platform (such as LeetCode or GeeksforGeeks), topic (arrays, strings, linked lists, trees, graphs, dynamic programming), difficulty level (easy, medium, hard), status (solved, attempted, to revise) and personal notes or approach. The dashboard shows total problems solved, topic-wise progress charts, difficulty distribution, and a daily streak counter. Users can filter and search problems, mark problems for revision, and set weekly goals. The frontend is built with React, the backend with Node.js and Express, and data is stored in MongoDB. Authentication is handled using JSON Web Tokens (JWT). Future enhancements include a leaderboard, reminders for revision, and automatic import of solved problems from coding platforms.
```

## 3.1 Key facts the overview must contain

| Category | Facts from the Description |
|---|---|
| Problem solved | Scattered DSA practice records; need for one place to track preparation |
| Core features | Add problems with platform, topic, difficulty, status and notes; dashboard with charts and streak; search, filter, revision marking, weekly goals |
| Technology stack | React, Node.js, Express, MongoDB, JWT authentication |
| Future scope | Leaderboard, revision reminders, automatic import of solved problems |

These facts are used as a checklist to judge accuracy and to detect invented features (hallucination).

---

# 4. Evaluation Method

## 4.1 Experimental setup

- The same project description was used on every platform.
- Each platform was given one prompting technique (Zero-Shot, Few-Shot, Chain-of-Thought, Role-Based), and the five prompt structures were applied progressively.
- The target length was about 150 words.
- Each output was checked against the key facts list in Section 3.1.

## 4.2 Evaluation criteria

| Criterion | Meaning | How It Was Judged |
|---|---|---|
| Accuracy | Facts match the description; nothing invented | Compared with the key facts list |
| Coherence | Ideas flow logically; the text reads as one piece | Reading for order and linking of ideas |
| Simplicity | Easy for undergraduate students to understand | Vocabulary and sentence length |
| Speed | Time taken to generate the response | Observed response time |
| User Experience | Overall usefulness and ease of use of the output | Whether it can be pasted into a README with little editing |

## 4.3 Rating scale

Ratings use the labels Poor, Average, Good, Very Good, High, Very High and Excellent for quality criteria, and Slow, Moderate, Fast and Very Fast for speed.

---

# 5. Prompting Techniques Used

## 5.1 Basic Prompt

A basic prompt states only the task. It is the starting point and shows how the model behaves with minimal guidance.

### Prompt Used
```text
Provide a summary of the following project description of the "DSA Coding Tracker" website in around 150 words.

The summary should:

Include the key features.
Be understandable for undergraduate students.
Preserve the original meaning.

Project Description:
[Paste the project description here]
```

### Expected Behaviour
The model produces a general summary. It may skip the technology stack or future scope because nothing asked for them.

## 5.2 Role Prompt

A role prompt tells the model who to act as, which shapes tone, vocabulary and depth.

### Prompt Used
```text
Assume you are a senior software engineer mentoring final-year computer science students on their academic projects.

Read the project description below and prepare a project overview of approximately 150 words.

Requirements:

Write in simple language.
Emphasize the important features and technologies.
Minimize technical jargon where possible.

Project Description:
[Paste the project description here]
```

### Expected Behaviour
The output sounds more like guidance from a mentor, and it highlights features and technologies more clearly.

## 5.3 Context Prompt

A context prompt explains the purpose and the audience, so the model decides what to include and what to leave out.

### Prompt Used
```text
You are preparing the README overview and viva presentation notes for a college mini-project submission. The project is a DSA Coding Tracker website that helps students prepare for placements.

Read the following project description and produce an overview of about 150 words.

The overview should:

Cover the problem the project solves, the main features and the technology stack.
Remain accurate and well-organized.
Help examiners and recruiters quickly understand the project.

Project Description:
[Paste the project description here]
```

### Expected Behaviour
The output starts with the problem being solved and then moves to features and technologies, which suits a README.

## 5.4 Constraint Prompt

A constraint prompt sets limits and rules. It controls length, style and honesty of the content.

### Prompt Used
```text
Summarize the following DSA Coding Tracker project description while following these conditions:

Limit the summary to 150 words
Use clear and simple English
Avoid bullet points
Suitable for undergraduate students and non-technical examiners
Keep the original meaning intact
Mention the problem solved, the main features and the technology stack only
Do not add features that are not in the description

```

### Expected Behaviour
The output stays within the word limit, is written as a paragraph, and does not add invented features.

## 5.5 Output Format Prompt

An output format prompt defines the exact layout, so the result can be copied directly into a document.

### Prompt Used
```text
Summarize the following DSA Coding Tracker project description.

Present the output using the following format:

Title:
Overview:
Key Features:

Feature 1
Feature 2
Feature 3
Technology Stack:
Future Scope:

Requirements:

Around 150 words
Easy to understand
Appropriate for undergraduate students
Do not add features that are not in the description

Project Description:
[Paste the project description here]
```

### Expected Behaviour
The output follows the headings exactly, which makes it ready to paste into a README or report.

## 5.6 Final Refined Prompt (all five structures combined)

### Prompt Used
```text
Act as a senior software engineer mentoring final-year computer science students (Role).

I am preparing the README overview and viva notes for my college mini-project, a DSA Coding Tracker website that helps students prepare for placements (Context).

Summarize the project description below in about 150 words, using simple English, without bullet points in the overview paragraph, and without adding any feature that is not mentioned (Constraints).

Present the output in this format (Output Format):

Title:
Overview:
Key Features: (three items)
Technology Stack:
Future Scope:

Project Description:
[Paste the project description here]
```

---

# 6. Progressive Improvement: Sample Outputs from Basic to Final

> **Note:** The outputs in this section and the next are illustrative samples. Replace them with the actual responses you get when you run the prompts.

## 6.1 Output of the Basic Prompt

> The DSA Coding Tracker is a web application that helps students track their Data Structures and Algorithms practice. Users can add problems they have solved with details such as topic and difficulty. A dashboard shows progress and a streak counter. Users can search and filter problems and set weekly goals. The application is built using web technologies and has plans for future improvements.

**Observation:** The summary is correct but general. It does not name the technology stack or the future features.

## 6.2 Output of the Role Prompt

> As a mentor, I would describe the DSA Coding Tracker as a simple tool that keeps a student's coding practice in one place. A student logs in, adds each problem they solve with its topic, difficulty and notes, and then sees progress on a dashboard with charts and a daily streak. The project is built with React for the screens, Node.js and Express for the server, and MongoDB for storing data.

**Observation:** The tone is friendlier and the technologies are named, but filters, revision marking and future scope are missing.

## 6.3 Output of the Context Prompt

> Many students practise coding problems on different websites and lose track of their progress. The DSA Coding Tracker solves this by letting them record every problem with its platform, topic, difficulty, status and notes in one place. A dashboard shows total problems solved, topic-wise charts and a daily streak, and users can search, filter and mark problems for revision. It is built using React, Node.js, Express, MongoDB and JWT authentication.

**Observation:** The problem statement is clear and most features and the stack are covered. Future scope is still missing.

## 6.4 Output of the Constraint Prompt

> The DSA Coding Tracker helps students keep all their coding practice records in one place. Users register, log in and add each problem with its platform, topic, difficulty, status and notes. A dashboard displays problems solved, topic-wise progress, difficulty distribution and a daily streak, and users can filter problems, mark them for revision and set weekly goals. The website uses React, Node.js, Express, MongoDB and JWT for secure login.

**Observation:** The summary is a clean paragraph with no bullets and no invented features, and it stays near 150 words.

## 6.5 Output of the Output Format Prompt

> **Title:** DSA Coding Tracker
> **Overview:** A web application that lets students record and review their Data Structures and Algorithms practice in one place.
> **Key Features:**
> Feature 1: Add problems with platform, topic, difficulty, status and notes.
> Feature 2: Dashboard with topic-wise charts, difficulty distribution and daily streak.
> Feature 3: Search, filters, revision marking and weekly goals.
> **Technology Stack:** React, Node.js, Express, MongoDB, JWT.
> **Future Scope:** Leaderboard, revision reminders and automatic import of solved problems.

**Observation:** All sections are present in the requested layout, which is ready to paste into a README.

## 6.6 Output of the Final Refined Prompt

> **Title:** DSA Coding Tracker
> **Overview:** Students preparing for placements often practise problems on several websites and lose track of their progress. The DSA Coding Tracker solves this by giving them one web application to log every problem with its platform, topic, difficulty, status and notes, and to see their growth through a dashboard with charts and a daily streak.
> **Key Features:**
> 1. Problem logging with topic, difficulty, status and personal notes.
> 2. Dashboard with topic-wise progress, difficulty distribution and streak counter.
> 3. Search, filters, revision marking and weekly goals.
> **Technology Stack:** React (frontend), Node.js and Express (backend), MongoDB (database), JWT (authentication).
> **Future Scope:** Leaderboard, revision reminders and automatic import of solved problems.

**Observation:** This version has the problem statement, the main features, the stack and the future scope, written in simple language and in the required format.

## 6.7 Summary of improvement

| Prompt Structure | What Was Added | Effect on Output |
|---|---|---|
| Basic Prompt | Task, length and audience only | Correct but generic; stack and future scope missing |
| Role Prompt | Senior software engineer mentoring students | Friendlier tone; technologies named |
| Context Prompt | README and viva purpose | Problem statement and features covered |
| Constraint Prompt | Word limit, no bullets, no invented features | Shorter, accurate, no hallucination |
| Output Format Prompt | Fixed headings | Ready-to-paste structure |
| Final Refined Prompt | All five combined | Most complete and directly usable result |

---

# 7. AI Platform Evaluation

## 7.1 ChatGPT + Zero-Shot Prompting

### Prompt Used
```text
Summarize the following DSA Coding Tracker project description using simple language suitable for undergraduate students.
```

### Summary Generated

> The DSA Coding Tracker is a website that helps students keep track of the coding problems they practise for interviews and placements. Users can add each problem with its platform, topic, difficulty and status, and save personal notes. A dashboard shows the number of problems solved, topic-wise progress and a daily streak, while filters and revision marking make it easier to revise. The project uses React for the frontend, Node.js and Express for the backend, MongoDB for storage and JWT for secure login. Planned improvements include a leaderboard, revision reminders and automatic import of solved problems.

### Evaluation

| Criterion | Result |
|---|---|
| Accuracy | High |
| Coherence | Good |
| Simplicity | Excellent |
| Speed | Very Fast |
| User Experience | Excellent |

---

## 7.2 Gemini + Few-Shot Prompting

### Prompt Used
```text
Review the following sample project overviews and create an overview of the DSA Coding Tracker project in the same style.

Example 1: "Expense Manager is a web app that lets users record daily spending, group it by category and view monthly charts. It is built with React and Firebase."
Example 2: "Library Portal is a website where students search and reserve books and view due dates. It uses Node.js, Express and MySQL."
```

### Summary Generated

> DSA Coding Tracker is a web app that lets students record the coding problems they solve, grouped by topic, difficulty and status, along with personal notes. A dashboard displays progress charts and a daily streak so users can monitor their preparation. It is built with React, Node.js, Express and MongoDB, with JWT-based authentication, and is planned to add a leaderboard and revision reminders.

### Evaluation

| Criterion | Result |
|---|---|
| Accuracy | Very High |
| Coherence | Excellent |
| Simplicity | Good |
| Speed | Fast |
| User Experience | Good |

---

## 7.3 Claude AI + Chain-of-Thought Prompting

### Prompt Used
```text
Carefully analyze the project description, identify the problem solved, the main features and the technology stack step by step, and then prepare a concise overview suitable for undergraduate students.
```

### Summary Generated

> The DSA Coding Tracker solves the problem of scattered practice records by giving students one place to log and review the Data Structures and Algorithms problems they solve. Users register, log in with JWT-secured authentication, and add problems with platform, topic, difficulty, status and notes. A dashboard presents total problems solved, topic-wise charts, difficulty distribution and a daily streak, and users can search, filter, mark problems for revision and set weekly goals. The application is built with React, Node.js, Express and MongoDB. Future work includes a leaderboard, revision reminders and automatic problem import from coding platforms.

### Evaluation

| Criterion | Result |
|---|---|
| Accuracy | Excellent |
| Coherence | Excellent |
| Simplicity | Good |
| Speed | Moderate |
| User Experience | Very Good |

---

## 7.4 Microsoft Copilot + Role-Based Prompting

### Prompt Used
```text
Act as a senior software engineer and give a brief overview of the DSA Coding Tracker website for undergraduate students.
```

### Summary Generated

> The DSA Coding Tracker is a website where students can store the coding problems they have solved and see their progress in one dashboard. It shows topic-wise charts and a daily streak to keep users consistent. The project uses React, Node.js and MongoDB, and future versions may include a leaderboard and reminders.

### Evaluation

| Criterion | Result |
|---|---|
| Accuracy | Good |
| Coherence | Good |
| Simplicity | Excellent |
| Speed | Fast |
| User Experience | Good |

---

# 8. Fact Coverage Check

Each summary was checked against the key facts in Section 3.1 (Yes = included, Partial = briefly mentioned, No = missing).

| Key Fact | ChatGPT | Gemini | Claude AI | Microsoft Copilot |
|---|---|---|---|---|
| Problem solved (scattered practice) | Partial | No | Yes | No |
| Problem logging fields (platform, topic, difficulty, status, notes) | Yes | Yes | Yes | Partial |
| Dashboard and streak | Yes | Yes | Yes | Yes |
| Search, filter, revision, weekly goals | Partial | No | Yes | No |
| Technology stack | Yes | Yes | Yes | Partial |
| Future scope | Yes | Partial | Yes | Partial |
| No invented features | Yes | Yes | Yes | Yes |

---

# 9. Comparison Table

| AI Platform | Prompting Technique | Accuracy | Coherence | Simplicity | Speed | User Experience |
|---|---|---|---|---|---|---|
| ChatGPT | Zero-Shot | High | Good | Excellent | Very Fast | Excellent |
| Gemini | Few-Shot | Very High | Excellent | Good | Fast | Good |
| Claude AI | Chain-of-Thought | Excellent | Excellent | Good | Moderate | Very Good |
| Microsoft Copilot | Role-Based | Good | Good | Excellent | Fast | Good |

## 9.1 Numerical scoring (out of 5)

| AI Platform | Accuracy | Coherence | Simplicity | Speed | User Experience | Total (out of 25) | Average |
|---|---|---|---|---|---|---|---|
| ChatGPT | 4 | 4 | 5 | 5 | 5 | 23 | 4.6 |
| Gemini | 5 | 5 | 4 | 4 | 4 | 22 | 4.4 |
| Claude AI | 5 | 5 | 4 | 3 | 4 | 21 | 4.2 |
| Microsoft Copilot | 3 | 4 | 5 | 4 | 4 | 20 | 4.0 |

*Scoring key: Excellent = 5, Very High = 5, High = 4, Very Good = 4, Good = 4 (3 for accuracy where details are missing), Moderate = 3, Fast = 4, Very Fast = 5. This weighting treats speed and simplicity equally with quality, so the platform with the best **content** (Claude AI) is not the one with the highest total.*

---

# 10. Overall Findings

| Platform | Key Strength | Limitation |
|---|---|---|
| ChatGPT | Excellent combination of clarity, readability and speed | May include fewer technical details than Claude AI |
| Gemini | Produces organized and highly accurate overviews that follow the given example style | Depends on the quality of the examples provided |
| Claude AI | Generates the most detailed and logically consistent overviews | Takes a little longer to generate responses |
| Microsoft Copilot | Offers concise and beginner-friendly explanations | Covers fewer details, such as goals and filters |

## 10.1 Observations on prompting techniques

- **Zero-Shot** is fast and simple, and works well when the source text is clear, but the output style is not controlled.
- **Few-Shot** gives a consistent style, but the quality of the examples decides the quality of the result.
- **Chain-of-Thought** gives the most complete coverage because the model identifies the problem, features and stack first, but it takes more time.
- **Role-Based** improves tone and simplicity, but a short role prompt without constraints can lead to missing details.

## 10.2 Observations on prompt structures

- Adding **context** (purpose and audience) improved relevance more than adding a role alone.
- Adding **constraints** reduced length problems and prevented invented features.
- Adding an **output format** made the response directly usable in a README or report.
- Combining all five structures gave the best result, because each structure fixes a different weakness.

---

# 11. Limitations and Best Practices

## 11.1 Limitations of the experiment

- Only one project description and one task were tested.
- Each technique was tested on one platform, so differences may come from the platform and not from the technique.
- Ratings for accuracy, coherence and simplicity are partly subjective.
- Speed depends on system load and internet connection and may change between runs.
- AI platforms update frequently, so results may differ over time.

## 11.2 Best practices learned

- State the task, audience and length clearly.
- Give the purpose of the output so the model can choose what to include.
- Add constraints such as "do not add features that are not in the description".
- Specify the output format when the result will be pasted into a document.
- Check every output against the source and remove any invented content.
- Refine the prompt step by step instead of writing one long prompt at once.

---

# 12. Final Result

Different prompting techniques were tested across several AI platforms for summarizing the project description of a **DSA Coding Tracker website**.

The experiment led to the following conclusions:

- **Claude AI with Chain-of-Thought Prompting** created the most accurate, coherent and well-structured overview by first identifying the problem, features and technology stack before writing the final response.
- **ChatGPT with Zero-Shot Prompting** provided the best combination of simplicity, readability, response speed and overall user experience, making it a good choice for quick README content.
- **Gemini with Few-Shot Prompting** produced accurate and well-organized overviews that matched the style of the examples, although it depended on the examples given.
- **Microsoft Copilot with Role-Based Prompting** generated short, easy-to-understand overviews that were beginner-friendly but contained fewer details.
- Moving from the **Basic Prompt** to the **Final Refined Prompt**, which combines role, context, constraints and output format, gave the most complete and directly usable project overview.

Thus, the objective of designing prompts using different prompt structures and applying them to a project-related task was successfully achieved.

---
