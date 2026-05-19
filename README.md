# Quiz CLI

An interactive command-line quiz game for learning JavaScript, Node.js, and general programming concepts.

## Project Overview

**Quiz CLI** is a terminal-based quiz application written in modern JavaScript using ES Modules. It loads quiz questions from a JSON file, lets the user choose a category and question count, then runs an interactive multiple-choice quiz with colored terminal output, progress tracking, score reporting, and answer review.

### Notable features

- Interactive CLI flow using Node.js `readline`
- Multiple quiz categories:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Optional question count selection:
  - All questions
  - 3 questions
  - 5 questions
- Shuffled question order for each quiz session
- Progress bar display while answering questions
- Final score summary with performance feedback
- Review of incorrect answers
- ANSI color styling without external dependencies

## Setup Instructions

### Requirements

- Node.js **18.0.0 or newer**

### Installation

1. Clone the repository.
2. Change into the project directory.
3. Install dependencies if desired.

This project does not declare any external packages in `package.json`, so there is nothing extra to install beyond Node.js itself.

### Run the application

```bash
npm start
```

or

```bash
node index.js
```

## Usage Examples

After starting the app, you will be prompted to:

1. Choose a quiz category
2. Choose how many questions to answer
3. Select answers by entering the option number
4. Review your score and incorrect answers
5. Decide whether to play again

### Example session flow

```text
Choose a category:
  1. JavaScript Basics
  2. Node.js Fundamentals
  3. General Programming

How many questions?
  1. All questions
  2. 3 questions
  3. 5 questions

Your choice (enter number): 2
```

During the quiz, each question is presented with numbered answer choices. Enter the number of the option you want to select.

## File Structure

```text
.
├── data/
│   └── questions.json    # Quiz categories, questions, answers, and explanations
├── index.js              # Application entry point and main loop
├── package.json          # Project metadata and npm scripts
└── src/
    ├── colors.js         # ANSI color helpers for terminal output
    ├── input.js          # Readline-based input helpers
    └── quiz.js           # Quiz game logic and result display
```

## Implementation Details

### `index.js`

- Loads questions from `data/questions.json`
- Displays the welcome banner
- Handles category and question-count selection
- Creates and runs a `Quiz` instance
- Repeats the game until the user chooses to stop

### `src/quiz.js`

- Implements the `Quiz` class
- Shuffles questions using the Fisher-Yates algorithm
- Tracks score, progress, and submitted answers
- Displays per-question feedback and final results

### `src/input.js`

- Wraps Node.js `readline` in Promise-based helpers
- Provides:
  - `createInterface()`
  - `prompt()`
  - `select()`
  - `confirm()`
  - `pressEnter()`

### `src/colors.js`

- Provides ANSI color utility functions for terminal output
- Includes convenience helpers such as `success`, `error`, `info`, and `highlight`

### `data/questions.json`

Contains all quiz content, organized by category. Each question includes:

- `question`
- `options`
- `answer` index
- `explanation`

## Scripts

Defined in `package.json`:

- `npm start` — runs the quiz application
- `npm test` — runs Node's built-in test runner (`node --test`)

## License

This project is licensed under the **MIT** license.
