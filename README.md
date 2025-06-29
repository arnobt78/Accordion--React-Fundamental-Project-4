# Accordion Project - React Fundamental Project 4

<img width="827" alt="Screenshot 2025-02-09 at 02 58 59" src="https://github.com/user-attachments/assets/63a532fe-5eed-4ba8-b688-15a54a44073a" />

---

A simple, interactive React application that demonstrates the core concepts of React through an Accordion UI—a set of questions with toggleable answers. This project is ideal for learners looking to strengthen their understanding of React state management and component structure.

- **Live-Demo:** [https://accordion-arnob.netlify.app/](https://accordion-arnob.netlify.app/)

---

## Table of Contents

1. [Project Summary](#project-summary)
2. [Features](#features)
3. [Technology Stack](#technology-stack)
4. [Project Structure](#project-structure)
5. [Component Overview](#component-overview)
6. [How It Works](#how-it-works)
7. [Getting Started](#getting-started)
8. [Code Walkthrough & Examples](#code-walkthrough--examples)
9. [Learning Outcomes & Keywords](#learning-outcomes--keywords)
10. [Conclusion](#conclusion)

---

## Project Summary

This project is designed as a fundamental React exercise, focusing on the creation of a dynamic Accordion (FAQs/questions) interface. It covers essential React concepts such as functional components, props, state management using `useState`, conditional rendering, and iterating over data. Through this project, learners can see how to structure a small React app and manage UI interactions efficiently.

---

## Features

- Lists questions and allows toggling their answers (Accordion behavior).
- Only one answer visible at a time (if implemented as a challenge).
- Uses React functional components and hooks (`useState`).
- Clean and modular code structure.
- Styled with modern CSS.

---

## Technology Stack

- **React** (v18+): UI library for building component-based interfaces.
- **Vite**: Fast development server and build tool.
- **JavaScript (ES6+)**
- **CSS**: For styling.
- **react-icons**: For toggle icons (+, -).

---

## Project Structure

```
Accordion--React-Fundamental-Project-4/
│
├── src/
│   ├── App.jsx               # Main app component
│   ├── Questions.jsx         # Renders list of questions
│   ├── SingleQuestion.jsx    # Component for each question
│   ├── data.js               # Questions data array
│   ├── index.css             # App styling
│   └── main.jsx              # React app entry point
│
├── public/
│   └── index.html            # Main HTML file
│
├── package.json              # Project dependencies and scripts
├── vite.config.js            # Vite config
└── README.md                 # Project documentation
```

---

## Component Overview

### `App.jsx`
- Imports data and manages the `questions` state.
- Renders the `Questions` component.

### `Questions.jsx`
- Receives the `questions` prop.
- Maps each question to a `SingleQuestion` component.

### `SingleQuestion.jsx`
- Handles the toggle state (`showInfo`) for showing/hiding answers.
- Displays question title, and toggles icon (+/-) and answer.

### `data.js`
- Exports an array of question objects:
  ```js
  {
    id: 1,
    title: 'Do I have to allow the use of cookies?',
    info: 'Unicorn vinyl poutine brooklyn, ...'
  }
  ```

---

## How It Works

1. **Data Import:** The questions are defined in `data.js` as an array of objects.
2. **State Setup:** `questions` state is initialized in `App.jsx` using `useState(data)`.
3. **Rendering:** `Questions.jsx` receives the questions and renders a `SingleQuestion` for each.
4. **Toggle Functionality:** Inside each `SingleQuestion`, a local state (`showInfo`) manages answer visibility. Clicking the button toggles the state, either showing or hiding the answer.
5. **Icons:** Uses `react-icons` for the toggle button (+ for expand, - for collapse).
6. **Styling:** Styles are applied via `index.css` for a polished UI.

---

## Getting Started

### Prerequisites

- Node.js (v16+ recommended)
- npm

### Installation

1. **Clone the repository:**
   ```sh
   git clone https://github.com/arnobt78/Accordion--React-Fundamental-Project-4.git
   cd Accordion--React-Fundamental-Project-4
   ```

2. **Install dependencies:**
   ```sh
   npm install
   ```

3. **Run the development server:**
   ```sh
   npm run dev
   ```
   The app will be available at `http://localhost:5173` by default.

---

## Code Walkthrough & Examples

### 1. Main App Component (`src/App.jsx`)

```javascript
import { useState } from 'react';
import data from './data';
import Questions from './Questions';

function App() {
  const [questions, setQuestions] = useState(data);
  return (
    <main>
      <Questions questions={questions} />
    </main>
  );
}

export default App;
```

---

### 2. Data Structure (`src/data.js`)

```javascript
const questions = [
  {
    id: 1,
    title: 'Do I have to allow the use of cookies?',
    info: 'Unicorn vinyl poutine brooklyn, next level direct trade iceland...',
  },
  // ...more questions
];
export default questions;
```

---

### 3. Questions List Component (`src/Questions.jsx`)

```javascript
import SingleQuestion from './SingleQuestion';

const Questions = ({ questions }) => {
  return (
    <section className='container'>
      <h1>Questions</h1>
      {questions.map((question) => (
        <SingleQuestion key={question.id} {...question} />
      ))}
    </section>
  );
};

export default Questions;
```

---

### 4. Single Question Component (`src/SingleQuestion.jsx`)

```javascript
import React, { useState } from 'react';
import { AiOutlineMinus, AiOutlinePlus } from 'react-icons/ai';

const SingleQuestion = ({ title, info }) => {
  const [showInfo, setShowInfo] = useState(false);
  return (
    <article className='question'>
      <header>
        <h5>{title}</h5>
        <button
          className='question-btn'
          onClick={() => setShowInfo(!showInfo)}
        >
          {showInfo ? <AiOutlineMinus /> : <AiOutlinePlus />}
        </button>
      </header>
      {showInfo && <p>{info}</p>}
    </article>
  );
};

export default SingleQuestion;
```

---

### 5. CSS Styling (`src/index.css`)

The CSS uses modern CSS variables for color schemes, box shadows, and layouts to create a visually appealing and responsive design.

---

## Learning Outcomes & Keywords

- **React Functional Components**
- **useState Hook**
- **Props and Data Passing**
- **Conditional Rendering**
- **Component Composition**
- **Event Handling**
- **React Icons Integration**
- **Project Structure and Organization**
- **Iterating Over Data**

---

## Conclusion

This Accordion project is a concise yet powerful demonstration of React fundamentals. It encourages understanding of how to work with state, props, and component-driven design, making it an excellent learning resource for beginners. The modular and well-commented codebase, coupled with modern tooling (Vite, React, ES6+), makes it easy to extend or use as a base for more complex projects.

For more details and code, visit the [GitHub repository](https://github.com/arnobt78/Accordion--React-Fundamental-Project-4).

---
