# Copilot Instructions - Next.js Dashboard

## 🎯 Project Context

Next.js Dashboard for managing various aspects of the application using **Next.js** and **TypeScript**.

**Features**: User authentication, data visualization, and responsive design.

## 🛠️ Core Stack

- **Next.js 13** + **TypeScript 4.9** + **React 18**
- **Tailwind CSS** (styling)
- **Zustand** (global state management)
- **React Query** (data fetching)
- **GraphQL** (API client)
- **Jest** + **React Testing Library** (testing)

## 📁 Structure

```
app/
├── layout.tsx          # Main layout component
├── page.tsx            # Main page component
├── lib/                # Utility functions
├── query/              # API routes
├── seed/               # Seed data
└── ui/                 # UI components
    ├── button.tsx      # Button component
    ├── global.css      # Global styles
    └── ...            # Other UI components
```

## 🎨 Code Standards

### Naming

- **Components**: `PascalCase.tsx`
- **Hooks**: `useCamelCase.ts`
- **Constants**: `UPPER_SNAKE_CASE`
- **Functions**: `camelCase`

### Component Skeleton

```typescript
import { useState } from 'react';
import { Button } from 'ui/button';

type Props = { id: string };

export const MyComponent = ({ id }: Props) => {
  const [state, setState] = useState();

  const handleClick = () => {};

  return <Button onClick={handleClick}>Click Me</Button>;
};
```

### Global State (Zustand)

```typescript
import create from 'zustand';

const useStore = create((set) => ({
  user: null,
  setUser: (user) => set({ user }),
}));
```

### Data Fetching (React Query + GraphQL)

```typescript
import { useQuery } from 'react-query';
import { gql } from 'graphql-request';

const MY_QUERY = gql`query MyQuery { ... }`;

export const useMyData = () => {
  return useQuery('myData', async () => {
    const data = await fetchGraphQL(MY_QUERY);
    return data;
  });
};
```

### Testing

```typescript
import { render, screen } from '@testing-library/react';
import { MyComponent } from './MyComponent';

describe('MyComponent', () => {
  it('renders correctly', () => {
    render(<MyComponent id="1" />);
    expect(screen.getByText('Click Me')).toBeInTheDocument();
  });
});
```

## 🚀 Scripts

```bash
pnpm run dev            # Start development server
pnpm run build          # Build for production
pnpm run test           # Run tests
pnpm run lint           # Lint code
```

## ✅ Git Conventions

Commits follow Conventional Commits (`feat`, `fix`, `docs`, `refactor`, `test`, `chore`).

```text
feat(ui): add new button component

Closes #123
```

Branches: `feat/*`, `fix/*`, `chore/*`

## 📝 Key Rules

1. Components: max 200 lines
2. Always type props and returns
3. Use Tailwind CSS for styling
4. Tests: `.test.tsx` file beside source
5. GraphQL: use queries + hooks
6. Maintain clean code and follow best practices.
