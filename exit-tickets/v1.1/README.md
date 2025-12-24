# Exit Tickets API v1.1 - Enhanced Schema

This version adds **pedagogical enhancement fields** to support misconception-driven feedback per the `cs-question-designer` skill.

## What's New in v1.1

| Field | Type | Description |
|-------|------|-------------|
| `questionArchetype` | `string` | Pedagogical pattern: `bebras`, `trace`, `parsons`, `blockmodel` |
| `misconceptionTargets` | `string[]` | Expected misconceptions this question tests |
| `options[].misconceptionId` | `string` | Specific misconception ID for wrong answers |
| `options[].feedback` | `object` | Structured "Not Yet" protocol feedback |

## Enhanced Question Schema

```json
{
  "questionId": "ai-1-l1-q2",
  "prompt": "What will be displayed if a user enters \"reading\" for this code?\n\n```python\nhobby = input(\"What is your favorite hobby? \")\nprint(\"I also love\", hobby)\n```",
  "questionType": "code_understanding",
  "questionArchetype": "trace",
  "misconceptionTargets": ["FUNC_RETURN_PRINT", "PRINT_OUTPUT_FORMAT"],
  "options": [
    {
      "key": "A",
      "text": "What is your favorite hobby?",
      "isCorrect": false,
      "misconceptionId": "INPUT_PROMPT_VS_OUTPUT",
      "feedback": {
        "short": "Not quite! That's the prompt, not the output.",
        "detailed": "The text in input() is a prompt—it asks the user a question. The print() function shows what appears after the user answers.",
        "socraticHint": "Where does the program display its result to the user?"
      }
    },
    {
      "key": "B",
      "text": "I also love reading",
      "isCorrect": true,
      "feedback": {
        "short": "Correct! The print() combines the text with the user's input.",
        "detailed": "print() displays the message along with the value stored in hobby, which is what the user typed."
      }
    },
    {
      "key": "C",
      "text": "hobby",
      "isCorrect": false,
      "misconceptionId": "VARIABLE_NAME_VS_VALUE",
      "feedback": {
        "short": "Not quite! Python prints the value, not the variable name.",
        "detailed": "When you print a variable without quotes, Python displays its contents, not its name.",
        "socraticHint": "What's the difference between hobby (the name) and \"reading\" (the value)?"
      }
    },
    {
      "key": "D",
      "text": "Error - undefined variable",
      "isCorrect": false,
      "misconceptionId": "SEQUENTIAL_EXECUTION",
      "feedback": {
        "short": "Not quite! The variable is defined by the input() line.",
        "detailed": "The input() function both prompts the user AND stores their response in the variable.",
        "socraticHint": "Which line creates the 'hobby' variable?"
      }
    }
  ],
  "correctAnswer": "B",
  "explanation": "The print() function displays 'I also love' followed by the value of hobby.",
  "hasCodeBlock": true,
  "metadata": {
    "difficulty": "medium",
    "bloomsTaxonomy": "understand",
    "estimatedTime": 45
  }
}
```

## Misconception ID Reference

Common misconception IDs (from `cs-question-designer/distractor-analysis.md`):

| ID | Description |
|----|-------------|
| `OFF_BY_ONE` | Loop bounds confusion (0 vs 1 indexing) |
| `ASSIGNMENT_VS_EQUALITY` | `=` vs `==` confusion |
| `VARIABLE_NAME_VS_VALUE` | Printing variable name instead of value |
| `INPUT_PROMPT_VS_OUTPUT` | Confusing input prompt with program output |
| `SEQUENTIAL_EXECUTION` | Misunderstanding code execution order |
| `TYPE_COERCION` | String + number behavior surprises |
| `ZERO_INDEX` | Array indexing starting at 1 |
| `RECURSION_AS_MAGIC` | Not understanding recursive call stack |

## Feedback Structure

The `feedback` object follows the "Not Yet" protocol:

```typescript
interface StructuredFeedback {
  short: string;       // 1-sentence acknowledgment
  detailed: string;    // Full explanation of the misconception
  socraticHint?: string; // Guiding question to lead toward understanding
}
```

## Question Archetypes

| Archetype | Description | When to Use |
|-----------|-------------|-------------|
| `bebras` | Logic-first (no code) | Conceptual understanding |
| `trace` | Trace & Predict (PRIMM) | Mental execution |
| `parsons` | Reorder code blocks | Logic construction |
| `blockmodel` | Surface/Flow/Purpose | Deep comprehension |

## API Endpoint

Validate answers and get feedback:

```bash
POST /api/validate
Content-Type: application/json

{
  "questionId": "ai-1-l1-q2",
  "answer": "A",
  "mode": "formative"
}
```

Response:
```json
{
  "success": true,
  "data": {
    "isCorrect": false,
    "selectedAnswer": "A",
    "feedback": {
      "short": "Not quite! That's the prompt, not the output.",
      "detailed": "The text in input() is a prompt...",
      "socraticHint": "Where does the program display its result?"
    },
    "misconceptionId": "INPUT_PROMPT_VS_OUTPUT",
    "correctAnswer": "B"
  }
}
```

## Migration from v1.0

v1.1 is **backward compatible** with v1.0:
- All v1.0 fields remain unchanged
- New fields use `null` as default
- Existing consumers will ignore unknown fields

## Generation Status

This directory will be populated when the bulk enhancement process completes:
- [ ] AI-1 (100 questions)
- [ ] AI-2 (90 questions)
- [ ] AI-3 (45 questions)
- [ ] W1-W4 (330 questions)
- [ ] M1-M2 (120 questions)
- [ ] BBD, BBW (145 questions)

Total: 830 questions to enhance

## Related Files

- Schema definition: `Question Banks/exit-tickets-api/docs/openapi.yaml`
- Misconception catalog: `.claude/skills/cs-question-designer/distractor-analysis.md`
- Feedback standards: `.claude/skills/cs-question-designer/feedback-standards.md`
- Source questions: `Question Banks/exit-tickets-api/data/courses/*.json`
