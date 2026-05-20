# quiz-cli

`quiz-cli` is an interactive command-line quiz game for learning JavaScript. It runs in Node.js, loads quiz questions from a JSON data file, lets the user choose a category and the number of questions, and then displays a final score summary with explanations for incorrect answers.

The project uses only built-in Node.js modules and ES modules.

## Requirements

- Node.js 18.0.0 or newer

## Installation

No external dependencies are listed in `package.json`, so there is nothing additional to install beyond having Node.js available.

If you want to inspect or modify the quiz content, see:

- `data/questions.json`

## How to Run

From the project root:

```bash
npm start
```

This runs:

```bash
node index.js
```

You can also run the app directly:

```bash
node index.js
```

## Tests

The repository defines a test script that uses Node's built-in test runner:

```bash
npm test
```

This runs:

```bash
node --test
```

## Key Features

- Interactive CLI quiz experience
- Category selection from quiz data
- User-defined number of questions per round
- Randomized question order
- Progress tracking during the quiz
- Score and percentage summary at the end
- Review of incorrect answers with explanations
- Colored terminal output for readability
- Option to play again after finishing

## Project Structure

```text
.
├── data
│   └── questions.json
├── index.js
├── package.json
└── src
    ├── colors.js
    ├── input.js
    └── quiz.js
```

## Data Format

The quiz content is stored in `data/questions.json` and organized into categories:

- `javascript`
- `nodejs`
- `general`

Each question includes:

- `question`
- `options`
- `answer` index
- `explanation`

## How It Works

- `index.js` is the main entry point.
- `src/input.js` handles terminal prompts and selections.
- `src/quiz.js` contains the quiz logic, scoring, progress display, and results output.
- `src/colors.js` provides terminal styling helpers.
