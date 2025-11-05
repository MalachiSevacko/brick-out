### Brick-Out
**Files:** `brick-out.html`, `brick-out-mvc.html`

A classic Breakout/Brick Out game with paddle, ball, and bricks.

**Features:**
- 5 rows of colorful bricks (50 total)
- Mouse-controlled paddle
- Ball physics with paddle velocity transfer
- Scoring system (10 points per brick)
- 3 lives
- Win/loss conditions

**Architecture:**
- `brick-out.html` - View/Controller 
- `brick-out-model.js` - JavaScript game model 
- `brick-out-model-test.js` - Comprehensive unit tests
- `brick-out-model-test.html` - Unit tests in browser

## Testing

The Brick Out model includes comprehensive test coverage:

### Installation

To run the Cucumber.js BDD tests, you need to install the dependencies:

**If you already have a package.json file:**
```bash
npm install
```

**If you don't have a package.json file:**
```bash
# Initialize a new npm project (follow the prompts or use -y for defaults)
npm init -y

# Install cucumber.js
npm install --save-dev @cucumber/cucumber
```

This will install cucumber.js and other required packages.

### Unit Tests (30+ tests)
Basic unit tests covering individual components.

**Run in browser:**
```bash
# Start a local web server (required for ES6 modules)
python3 -m http.server 8000

# Then open: http://localhost:8000/brick-out-model-test.html
```

**Run in Node.js:**
```bash
node brick-out-model-test.js
# or
npm test
```

### BDD Tests with Cucumber.js (25 scenarios, 115 steps)
Behavior-driven development tests using Gherkin syntax.

**Run Cucumber tests:**
```bash
npm run test:cucumber
```

**Run all tests:**
```bash
npm run test:all
```

**Features tested:**
- `features/paddle.feature` - Paddle movement, boundaries, velocity tracking
- `features/ball.feature` - Ball physics, wall bounces, paddle collisions
- `features/gameplay.feature` - Complete game flow, scoring, win/loss conditions

## Continuous Integration

This project uses GitHub Actions for automated testing. The workflow is defined in `.github/workflows/test.yml` and runs on every push and pull request to the main branch.

**The workflow includes:**

- **Automatic triggers:** Runs on push/pull request to main branch
- **Manual trigger:** Can be run manually using `workflow_dispatch` from the GitHub Actions tab
- **Test steps:**
  1. Unit tests (`npm test`) - 30+ tests covering individual components
  2. Cucumber BDD tests (`npm run test:cucumber`) - 25 scenarios with 115 steps

The workflow uses Ubuntu Linux with Node.js 18, automatically installs dependencies, and reports test results in the GitHub Actions UI.

**To manually run the workflow:**
1. Go to the "Actions" tab in your GitHub repository
2. Select "Tests" from the workflows list
3. Click "Run workflow" and choose the branch

## About P5.js

P5.js is a JavaScript library that makes coding accessible for artists, designers, educators, and beginners. It's a modern interpretation of Processing for the web.

- Website: https://p5js.org/
- Reference: https://p5js.org/reference/
- Examples: https://p5js.org/examples/

## Local Development

Most examples can be opened directly in your browser. However, for examples using ES6 modules (like the MVC version), you'll need to serve them via HTTP:

```bash
python3 -m http.server 8000
# Then open http://localhost:8000/
```
