# Cloud-Native Architecture Learning Hub & Quiz Platform

A responsive, single-page web application designed for learning and self-testing on a 7-lecture academic course covering High-Availability Distributed Systems, Cloud Computing, DevOps, Docker, and Kubernetes. 

This platform parses a structured `data.json` file to dynamically render clean, concise lecture notes and generate advanced multiple-choice quizzes with a custom, rigorous scoring model.

## 🚀 Key Features

- **Fully Responsive UI/UX:** Optimized for seamless navigation and readability on both desktop computers and mobile devices.
- **Dynamic Content Injection:** Powered entirely by a repeatable and easily extendable JSON dataset containing comprehensive summaries and quiz pools for all 7 lectures.
- **Custom Multi-Choice Scoring Model:** Implements a realistic academic grading algorithm for questions with one or multiple correct answers:
  - If a question has $m$ correct answers and $n$ wrong options, selecting a correct answer awards $+1/m$ points, while selecting a wrong answer penalizes by $-1/n$ points.
  - The total score for a single question cannot drop below 0.
- **Instant Quiz Feedback:** Displays the final percentage score and highlights missed correct answers alongside selected errors.

## 🤖 AI-Driven Development & Pipeline

This repository leverages Artificial Intelligence (AI) as a core part of its development lifecycle and content workflow:

1. **Architecture & Code Generation:** The responsive HTML5, modern vanilla CSS configurations, and asynchronous JavaScript logic managing data fetching and grading algorithms were generated and refined using AI.
2. **Automated Material Processing:** Raw lecture materials provided in PDF formats are automatically synthesized by an AI pipeline into highly structured, concise, and academically precise markdown-style lists within the repeatable `data.json` schema.
3. **Smart Question Bank Generation:** The comprehensive 20-question multiple-choice quiz pools per lecture are programmatically formulated by AI, ensuring varied numbers of options ($3$ to $7$) and true multi-correct scenarios to strictly challenge the custom evaluation engine.

## 🛠️ Data Schema (`data.json`)

To add new lectures or expand the question bank, simply append a new lecture object to the `lectures` array using the following schema:

```json
{
  "lectures": [
    {
      "id": 1,
      "title": "Lecture Title Here",
      "sections": [
        {
          "title": "Sub-topic Title",
          "content": [
            "Detailed bullet point generated from the source material.",
            "Another accurate note explaining a core concept."
          ]
        }
      ],
      "quiz": [
        {
          "question": "Which of the following statements are true?",
          "options": [
            { "text": "Correct Option A", "isCorrect": true },
            { "text": "Incorrect Option B", "isCorrect": false },
            { "text": "Correct Option C", "isCorrect": true }
          ]
        }
      ]
    }
  ]
}
