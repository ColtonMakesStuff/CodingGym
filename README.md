# Coding Gym

An AI-powered JavaScript coding gym that generates fresh coding challenges on demand.

Choose a difficulty, optionally enable hints, and give your problems a theme. The gym generates:

- A problem description
- Starter code
- Automated tests
- A hidden reference solution
- Daily problem history

The best part? **Fork it and make it your own.**

---

## Setup

### 1. Clone the repo

```bash
git clone YOUR_FORK_URL
cd CodingGym
npm install
```

### 2. Create `.env`

Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your_api_key_here
THEME=minecraft
```

Never commit your API key.

Your `.gitignore` should include:

```gitignore
.env
.env.*
node_modules/
coding-gym/
.DS_Store
```

The entire `coding-gym/` directory is ignored because problems and history are generated locally.

---

## Generate a Problem

Run:

```bash
npm run gym
```

You'll choose:

1. Easy
2. Medium
3. Hard

Then choose whether you want hints.

The AI generates and validates the exercise before saving it to:

```text
coding-gym/
├── problem.md
├── input.js
├── test.js
└── history/
```

You only modify `input.js`.

**Don't modify `test.js` — it's generated automatically.**

---

## Commands

```bash
npm run gym
```

Generate a new problem.

```bash
npm run gym:test
```

Run the current tests.

```bash
npm run gym:solve
```

Enter interactive solving mode.

```bash
npm run gym:show
```

Show the current problem.

---

## Themes

Set the theme in `.env`:

```env
THEME=minecraft
```

Try anything:

```env
THEME=star wars
THEME=pokemon
THEME=space
THEME=football
THEME=cyberpunk
```

Or make up your own.

---

## Validation

Before an exercise is saved, the gym checks that:

- The generated JavaScript is valid.
- The reference solution passes every test.
- The starter solution fails at least one test.
- Tests are deterministic.
- The exercise doesn't require external services or packages.

This helps prevent the AI from generating broken or already-solved challenges.

---

## Make It Yours

Fork the project and customize it however you want.

Some ideas:

- Add coding streaks
- Add achievements
- Add statistics
- Add timed challenges
- Add custom difficulty levels
- Add problem categories
- Add support for other languages
- Customize the AI prompt
- Create your own themes

The main generator lives in:

```text
scripts/generate.js
```

The `buildGenerationPrompt()` function is a great place to start experimenting.

---

## Security

**Never commit your `.env` file or API key.**

If you accidentally expose an API key, revoke it and create a new one.

---

## The Idea

Coding practice shouldn't require constantly searching for something to solve.

Generate a problem.

Solve it.

Learn something.

Repeat.

**Fork this project, change it, break it, improve it, and build the Coding Gym you want to use.**

## AI Responsibility

The goal of Coding Gym is not to use AI to avoid learning how to code.

It is to use AI as a tool to **keep learning how to code**.

As AI makes writing software easier and more automated, understanding how to think through problems, read code, debug, and build solutions becomes even more important.

Coding Gym is designed around that idea. AI generates the challenge, but **you still have to solve it**.

The project intentionally uses minimal AI involvement where possible. The model is primarily used to generate new exercises, tests, and reference solutions. The actual coding practice happens locally on your machine, without asking AI to write your solution for you.

The goal is to become a developer who knows **how and when to use AI effectively**, while still maintaining the ability to reason, solve problems, and write code independently.

AI is getting better and easier to use every day. Coding skills shouldn't get weaker because of that.

**Use the tools. Keep your skills sharp.**

---
