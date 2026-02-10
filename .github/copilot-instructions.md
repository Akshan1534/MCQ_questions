# AI Coding Instructions for MCQ Questions Repository

## Project Overview
This is an MCQ (Multiple Choice Questions) content repository storing technical assessment questions in JSON format. The questions focus on **C# and .NET technologies** covering fundamentals through advanced concepts.

## Data Structure

### Core Question Schema (`questions.json`)
Each question object follows this structure:
- `_id`: Unique identifier (e.g., "cs1", "net1")
- `category`: Content category (e.g., "development")
- `skillType`: Specific topic (e.g., "C# Language Fundamentals", ".NET Runtime")
- `question`: The MCQ question text
- `options`: Array of 4 options, each with:
  - `id`: Option identifier ("opt1"-"opt4")
  - `text`: Option content
  - `isCorrect`: Boolean flag
- `correctAnswer`: ID of the correct option (e.g., "opt2")
- `explanation`: Why the answer is correct
- `difficulty`: Level designation (e.g., "Level 1")
- `points`: Score value for correct answer
- `tags`: Array of topic keywords (e.g., ["C#", "Methods"])

## Key Patterns & Conventions

### Question Organization
- Questions are organized by `skillType` (not just by category)
- Tag values map to specific domains: "C#", ".NET", "CLR", "LINQ", "Memory Management", "Async", etc.
- Difficulty levels follow pattern "Level N" (Level 1 is foundational)
- Points typically correlate with difficulty

### Content Guidelines
- Each option has both `isCorrect` boolean AND a designated `correctAnswer` field—maintain consistency between them
- Explanations should be concise yet educational
- Tags should be technology-specific, not vague descriptors

### Validation Rules
- `_id` must be unique within the file
- `correctAnswer` value must match one of the option IDs in that question
- All questions must have exactly 4 options
- `category` and `skillType` are both required

## Common Tasks

### Adding Questions
When adding new questions:
1. Generate unique `_id` following pattern (e.g., "topic" prefix + number)
2. Assign appropriate `skillType` and `tags` from existing domain taxonomy
3. Ensure `correctAnswer` ID matches an actual option ID
4. Set reasonable `difficulty` and `points` values
5. Verify explanation provides learning value

### Validating Data Integrity
Before processing questions:
- Check for duplicate `_id` values
- Verify every `correctAnswer` references a valid option ID
- Ensure all required fields are present
- Validate option array has exactly 4 items

### Bulk Operations
When importing or modifying multiple questions, preserve the existing structure and ensure all schema requirements are met.

## Technology Stack
- **Format**: JSON (no special build process)
- **Content Focus**: C# language features, .NET runtime concepts, LINQ, async patterns, OOP fundamentals
- **Use Case**: Assessment/testing platform backend

## Notes for AI Agents
- This is a data-focused project, not application code
- No complex algorithms or business logic—focus is on data validation and transformation
- Questions serve educational purposes, so explanations should be technically accurate and helpful
- Common related skillTypes: "C# Language Fundamentals", ".NET Core Concepts", ".NET Runtime", "Asynchronous Programming", "LINQ"
