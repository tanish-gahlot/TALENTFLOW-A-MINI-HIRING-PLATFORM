# TALENTFLOW-A-MINI-HIRING-PLATFORM
TalentFlow is a cutting-edge hiring platform that simplifies recruitment management. Developed with React.js, Vite, and Tailwind CSS, it features a responsive interface, light/dark mode, and comprehensive analytics, all driven by mock APIs for fast prototyping and testing.

## Table of Contents

- [Features]
- [Technology Stack]
- [Project Structure]
- [Setup and Installation]
- [Architecture]
- [Technical Decisions]
- [Known Issues]
- [Future Improvements]
- [Contributing]
- [License]

## Features

Dashboard: Provides an overview of jobs and key hiring metrics.

Job Management: Create, view, and manage job listings efficiently.

Candidate Tracking: Track candidates across all hiring stages visually.

Assessments: Create and administer tests for applicants.

Analytics: Interactive charts for pipeline, velocity, scores, and top jobs, with CSV export.

Theme Toggle: Switch between light and dark modes, with preferences saved in localStorage.

Global Search: Quickly search jobs, candidates, and assessments.

Responsive Design: Fully mobile-friendly UI built with Tailwind CSS.

Mocked API: Uses MSW to simulate backend endpoints for smooth development.

## Tech Stack

Frontend: React.js (v18+) with TypeScript

Build Tool: Vite

Routing: React Router (v6+)

Styling: Tailwind CSS (OKLCH colors, dark mode)

UI Components: Shadcn/UI

Icons: Lucide React

Charts & Data Visualization: Recharts

API Mocking: MSW (Mock Service Worker)

Theme Management: Custom React Context

Utilities: clsx, tailwind-merge

Linting & Formatting: ESLint, Prettier

## Project Structure

```
/ENTNT/
├── public/
│   ├── index.html
│   └── mockServiceWorker.js
├── src/
│   ├── components/
│   │   ├── assessments/
│   │   ├── candidates/
│   │   ├── jobs/
│   │   ├── layout/
│   │   ├── ui/
│   │   └── ThemeProvider.tsx
│   ├── hooks/
│   ├── lib/
│   ├── mocks/
│   ├── styles/
│   ├── App.tsx
│   ├── main.tsx
│   ├── AnalyticsPage.tsx
│   ├── AssessmentsPage.tsx
│   ├── TakeAssessmentPage.tsx
│   ├── AssessmentBuilder.tsx
│   ├── NotFoundPage.tsx
│   ├── HomePage.tsx
│   └── index.tsx
├── tailwind.config.js
├── vite.config.ts
├── package.json
├── .env
└── README.md
```

## Setup Instructions

### Prerequisites

- **Node.js**: v18 or higher
- **npm**: v9 or higher

### Installation

1. **Clone the Repository**
  ```bash
  git clone <repository-url>
  cd ENTNT
  ```

2. **Install Dependencies**
  ```bash
  npm install
  ```

3. **Set Up Environment**
  - Create a `.env` file in the root:
    ```
    VITE_API_URL=http://localhost:5173
    ```

4. **Initialize MSW**
  ```bash
  npx msw init public/ --save
  ```

5. **Run the Development Server**
  ```bash
  npm run dev
  ```
  Open [http://localhost:5173](http://localhost:5173) in your browser.

6. **Build for Production**
  ```bash
  npm run build
  npm run preview
  ```

### Scripts

- `npm run dev`: Start the development server
- `npm run build`: Build for production
- `npm run preview`: Preview the production build
- `npm run lint`: Run ESLint
- `npm run format`: Run Prettier

## Architecture

### Frontend

React.js: Component-based architecture using TypeScript for type safety.

React Router: Handles client-side routing for paths like /, /jobs, /candidates, /assessments, and /analytics.

ThemeProvider: Custom React Context manages light/dark mode, toggling Tailwind’s dark class and persisting preference in localStorage.

Shadcn/UI: Provides reusable, accessible UI components

Tailwind CSS: Utility-first styling framework with OKLCH color support and dark mode.

Recharts: Renders analytics charts including Bar, Pie, and Line types.

### Data Layer

DatabaseService: Mock data layer (src/lib/db.ts) managing jobs, candidates, and assessments.

MSW (Mock Service Worker): Simulates API endpoints with realistic delays and error handling.

Analytics: Performs local processing for pipeline metrics, candidate velocity, scores, and top jobs.

### Key Components

Navigation: Responsive navbar with routing and light/dark mode toggle.

AnalyticsPage: Displays key metrics with interactive charts and CSV export functionality.

ThemeProvider: Centralized context managing theme state and persistence across sessions.

## Technical Decisions

Vite: Selected over CRA for faster builds and simpler configuration.

Tailwind CSS (OKLCH): Provides utility-first, accessible, and consistent styling.

Custom ThemeProvider: Uses React Context for theme management without relying on Next.js.

MSW: Simulates APIs for rapid frontend development and testing.

Recharts: Lightweight, theme-aware charts for analytics.

Client-Side CSV Export: Implements Blob API for exporting analytics data.

Shadcn/UI: Delivers accessible and customizable UI components.

## Known Issues

- **Tailwind CSS Resolution**:  
  If you see `Can't resolve 'tailwindcss'`, clear cache:
  ```bash
  - **Kanban Board Drag-and-Drop Integration**:  
    Integrating drag-and-drop functionality for the Kanban board is in progress. While the UI supports moving cards between columns, updating the underlying data state is not yet fully implemented. Ensure that state changes are properly handled and persisted when cards are moved. Further enhancements are planned to synchronize UI interactions with the mock data layer.
  npm install
  ```
  Ensure `vite.config.ts` includes `@tailwindcss/vite`.

- **Mock Data Limitations**:  
  Analytics use static mock data. For dynamic metrics, extend `DatabaseService`.

## Future Improvements

Integrate with a real backend (e.g., Node.js/Express) for persistent data.

Link candidates to jobs and assessments to enable dynamic analytics.

Add toast notifications for enhanced user feedback.

Improve accessibility with ARIA attributes and Lighthouse audits.

Implement server-side pagination to efficiently handle large datasets.

## Contributing

1. Fork the repository.
2. Create a feature branch:
  ```bash
  git checkout -b feature/xyz
  ```
3. Commit your changes:
  ```bash
  git commit -m "Add feature xyz"
  ```
4. Push to your branch:
  ```bash
  git push origin feature/xyz
  ```
5. Open a pull request.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.# TALENTFLOW-A-MINI-HIRING-PLATFORM
