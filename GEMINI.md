# Replit Extension

Create and manage Replit apps using natural language.

## Available Tools

### create_app_from_prompt
Build a brand-new Replit app from a natural language description. Use this when the user asks to create, build, or make a new app.

**Key inputs:**
- `originalUserPrompt`: The user's exact request (verbatim)
- `promptForReplitAgent`: A summary of what the app should do. Can contain additional context from the conversation.
- `suggestedAppName`: A friendly name for the app (optional)

### update_app_using_prompt
Modify an existing app that was created in this conversation. Use when the user wants to add features, fix bugs, or make changes.

**Key inputs:**
- `replId`: The ID of the app to update (from create_app_from_prompt response)
- `originalUserPrompt`: The user's exact change request
- `promptForReplitAgent`: A short summary of the requested change

### ask_question
Ask Replit Agent a question about the app without making changes. Use for explanations, debugging help, or understanding how something works.

**Key inputs:**
- `replId`: The ID of the app to ask about
- `promptForReplitAgent`: The question to ask

## Guidelines

1. **After creating or updating an app**: Wait for Replit Agent to finish before saying the app is ready. Give a brief 1-sentence status update.

2. **Don't show source code**: Direct users to Replit to view or edit code. If asked for code, explain they can see it in Replit.

3. **Keep responses concise**: 1-2 sentences about status is ideal.

4. **Track the replId**: After creating an app, remember the `replId` from the response to use for updates and questions.

5. **Choose the right tool**:
   - New app request → `create_app_from_prompt`
   - Change/add/fix request → `update_app_using_prompt`
   - Question/explanation request → `ask_question`

## Example Flow

1. User: "Build me a todo list app"
   → Call `create_app_from_prompt`
   → Response: "Replit is creating your todo list app."

2. User: "Add a delete button for each todo"
   → Call `update_app_using_prompt` with the replId
   → Response: "Replit is adding delete buttons to your app."

3. User: "How does it store the todos?"
   → Call `ask_question` with the replId
   → Response: Summarize what Replit Agent explains about storage.
