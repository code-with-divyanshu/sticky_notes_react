# <img src="./public/favicon.ico" alt="Sticky Notes React" width="32" height="32" align="absmiddle" /> Sticky Notes React

> A simple, colorful workspace for capturing ideas, tasks, and reminders.

[![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-5-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![Appwrite](https://img.shields.io/badge/Appwrite-16-F02E65?logo=appwrite&logoColor=white)](https://appwrite.io/)

**Sticky Notes React** is a lightweight notes board built with React and Vite. Create notes, move them around the canvas, change their colors, and keep everything synchronized with an Appwrite database.

## Features

- Create and delete notes
- Drag notes around a free-form canvas
- Automatically grow the note editor as you type
- Automatically save note content after editing
- Bring notes to the front when selected
- Change the header, body, and text colors
- Persist notes with Appwrite
- Show loading and saving states

## Tech stack

- **React** for the user interface
- **Vite** for development and production builds
- **Appwrite** for database persistence
- **ESLint** for code quality

## Getting started

### Prerequisites

- Node.js 18 or newer
- An Appwrite project with a database and notes collection

### 1. Install dependencies

```bash
npm install
```

### 2. Configure Appwrite

Create a `.env` file in the project root:

```env
VITE_ENDPOINT=https://cloud.appwrite.io/v1
VITE_PROJECT_ID=your_project_id
VITE_DATABASE_ID=your_database_id
VITE_COLLECTION_NOTES_ID=your_notes_collection_id
```

In Appwrite, create the database and collection referenced above. The notes collection should support these string fields:

- `body` - note content
- `position` - serialized note coordinates
- `colors` - serialized note color settings

Configure collection permissions according to how you want users to access their notes. Keep `.env` local; it is intentionally ignored by Git.

### 3. Start the development server

```bash
npm run dev
```

Open the local URL printed by Vite in your browser.

## Usage

1. Select the **plus** button to create a note.
2. Click and drag a note header to reposition it.
3. Click inside a note to edit its content. Changes are saved automatically.
4. Select a note, then choose a color from the controls to update its appearance.
5. Use the trash icon on a note to remove it.

## Available scripts

| Command           | Description                          |
| ----------------- | ------------------------------------ |
| `npm run dev`     | Start the development server         |
| `npm run build`   | Create a production build            |
| `npm run preview` | Preview the production build locally |
| `npm run lint`    | Run ESLint                           |

## Project structure

```text
src/
├── appwrite/       # Appwrite client and database helpers
├── components/     # Note cards and controls
├── context/        # Shared notes state
├── pages/          # Application pages
├── assets/         # Color definitions and static assets
└── icons/          # Reusable SVG icons
```

## License

This project is available for learning and personal use. Add a license file if you plan to distribute or reuse it publicly.
