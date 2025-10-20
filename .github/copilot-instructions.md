# CSNE - Quiz Application AI Coding Guide

## Project Overview
French-language quiz application (CSNE = Certified Stormshield Network Expert exam prep) using vanilla JavaScript, JSON-based question bank, and modern client-side rendering. No build tools, frameworks, or backend—pure static HTML/CSS/JS with modern ES6+ features.

## Architecture & Data Flow

**Question Loading Pipeline:**
1. `loadQuestions()` → Async fetch request for `questions.json`
2. `shuffleArray()` → Randomize questions using Fisher-Yates algorithm
3. `displayQuestion()` → Render one question at a time with progress tracking
4. State management via module-level variables (no localStorage dependency)

**JSON Schema:**
```json
{
  "questions": [
    {
      "id": 1,
      "question": "Question text",
      "type": "text",
      "answers": ["Answer 1", "Answer 2", ...],
      "correctAnswers": [0, 2],  // 0-indexed array of correct answer positions
      "image": null  // or URL string for image-based questions
    }
  ]
}
```

## Critical Conventions

### State Management
- **Module-level variables** (ES6):
  - `allQuestions`: Complete question bank from JSON
  - `shuffledQuestions`: Randomized subset for current quiz
  - `currentQuestionIndex`: Current question (0-indexed)
  - `score`: Correct answer count
- No localStorage—state resets on page reload

### Input Type Logic
```javascript
// Single correct answer = radio, multiple = checkbox
type="${question.correctAnswers.length === 1 ? 'radio' : 'checkbox'}"
```

### Answer Validation
```javascript
// Arrays must be sorted before comparison
arraysEqual(selectedAnswers.sort(), question.correctAnswers.sort())
```

## Development Workflow

**Testing the App:**
```powershell
# Serve locally (no build step needed)
python -m http.server 8000  # Or use Live Server extension
```
Open browser to `http://localhost:8000` → Select question count → Start quiz

**Adding Questions:**
1. Edit `questions.json` with proper JSON formatting
2. Ensure UTF-8 encoding (supports French accents natively)
3. Structure:
```json
{
  "id": 95,
  "question": "Your question here?",
  "type": "text",
  "answers": ["Ans1", "Ans2", "Ans3"],
  "correctAnswers": [0, 2],
  "image": null
}
```

## Key Files

- **`script.js`**: Modern async/await, template literals, ES6 arrow functions
- **`questions.json`**: 94 questions about Stormshield Network certification (UTF-8 encoded)
- **`index.html`**: Semantic HTML5 with modern meta tags, Google Fonts integration
- **`style.css`**: CSS custom properties (variables), gradients, animations, responsive flexbox

## Modern CSS Features

### CSS Variables
```css
:root {
    --primary-color: #2563eb;
    --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
}
```

### Animations
- `slideIn` keyframes for smooth transitions
- Progress bar with gradient fill
- Hover effects with transform/shadow

### Responsive Design
- Mobile-first approach
- Media query breakpoint at 768px
- Flexible button groups (stack on mobile)

## Common Patterns

### Async Data Loading
```javascript
async function loadQuestions() {
    const response = await fetch('questions.json');
    const data = await response.json();
    allQuestions = data.questions;
}
```

### Template Literals for DOM
```javascript
const html = `
    <div class="question-text">${question.question}</div>
    ${question.image ? `<img src="${question.image}">` : ''}
`;
```

### Dynamic Score Messages
- ≥90%: "Excellent ! 🎉" + 🏆
- ≥75%: "Très bien ! 👏" + ⭐
- ≥60%: "Bien joué ! 👍" + ✅
- <60%: "Continuez à réviser ! 📚" + 💪

## Non-Standard Decisions

1. **No build tools**: Pure ES6+ in browser (no transpilation)
2. **No state persistence**: Intentional—fresh start on each reload
3. **Inline event handlers**: Some `onclick` attributes for simplicity (e.g., `onclick="checkAnswer()"`)
4. **French UI**: All text/comments in French—preserve language when editing strings
5. **Progress bar**: Updates on question display (not on answer)

## External Dependencies
- Google Fonts (Inter family): `400`, `600`, `700`, `800` weights
- Pure browser APIs only (Fetch, DOM, ES6+)

## Design System
- **Color palette**: Blue/purple gradient primary, green success, red error
- **Typography**: Inter font family, varying weights for hierarchy
- **Spacing**: Consistent rem-based spacing (1rem = 16px)
- **Shadows**: 4 levels (`sm`, `md`, `lg`, `xl`) for depth
- **Border radius**: Generous (0.75rem-1.5rem) for modern look
