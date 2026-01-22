# Development Documentation

This guide provides detailed information for developers working on the Shoppy Dashboard project.

## Table of Contents

- [Getting Started](#getting-started)
- [Project Architecture](#project-architecture)
- [Development Workflow](#development-workflow)
- [Code Organization](#code-organization)
- [Component Development](#component-development)
- [State Management](#state-management)
- [Styling Guidelines](#styling-guidelines)
- [Working with Syncfusion](#working-with-syncfusion)
- [Adding New Features](#adding-new-features)
- [Testing](#testing)
- [Build & Deployment](#build--deployment)
- [Troubleshooting](#troubleshooting)

## Getting Started

### Prerequisites

- **Node.js**: v14.0.0 or higher (v18+ recommended)
- **npm**: v6.0.0 or higher (comes with Node.js)
- **Git**: For version control
- **Code Editor**: VS Code recommended with the following extensions:
  - ESLint
  - Prettier
  - Tailwind CSS IntelliSense
  - ES7+ React/Redux/React-Native snippets

### Initial Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/mnaimfaizy/dashboard-react.git
   cd dashboard-react
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Start development server**

   ```bash
   npm start
   ```

   The app will open at [http://localhost:3000](http://localhost:3000)

4. **Verify installation**
   - Check that all pages load without errors
   - Test theme switching (Light/Dark mode)
   - Verify sidebar navigation works

### Development Environment

```bash
# Start development server
npm start

# Run tests
npm test

# Build for production
npm run build

# Analyze bundle size (after installing dependencies)
npm install -g source-map-explorer
npm run build
source-map-explorer 'build/static/js/*.js'
```

## Project Architecture

### Technology Stack

- **React 18.3.1**: UI library with Hooks and Context API
- **React Router v6**: Client-side routing
- **Tailwind CSS 3.4**: Utility-first CSS framework
- **Syncfusion Components**: Enterprise-grade UI components
- **React Icons**: Icon library with multiple icon sets
- **CRACO**: Custom CRA configuration

### Folder Structure Explained

```
src/
├── components/           # Reusable UI components
│   ├── Charts/          # Chart wrapper components
│   ├── Button.jsx       # Custom button component
│   ├── Navbar.jsx       # Top navigation
│   ├── Sidebar.jsx      # Side navigation
│   └── ...
├── pages/               # Route-level components
│   ├── Charts/          # Chart pages
│   ├── ECommerce.jsx    # Main dashboard
│   └── ...
├── contexts/            # React Context providers
│   └── ContextProvider.js
├── data/                # Static data and mock data
│   ├── dummy.js         # Mock data for UI
│   └── *.jpg            # Images and assets
├── App.js               # Root component with routing
├── index.js             # Entry point (React 18 API)
└── index.css            # Global styles
```

### Design Patterns

1. **Component-Based Architecture**: Each UI element is a reusable component
2. **Container/Presentational Pattern**: Pages (containers) use components (presentational)
3. **Context API**: Global state management without prop drilling
4. **Composition**: Components compose smaller components
5. **Single Responsibility**: Each component has one clear purpose

## Development Workflow

### Git Workflow

1. **Create a feature branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes**
   - Write clean, readable code
   - Follow existing code style
   - Add comments for complex logic

3. **Commit your changes**

   ```bash
   git add .
   git commit -m "feat: add your feature description"
   ```

4. **Push to repository**

   ```bash
   git push origin feature/your-feature-name
   ```

5. **Create Pull Request**
   - Provide clear description
   - Reference related issues
   - Request code review

### Commit Message Convention

Follow [Conventional Commits](https://www.conventionalcommits.org/):

- `feat:` New feature
- `fix:` Bug fix
- `docs:` Documentation changes
- `style:` Code style changes (formatting)
- `refactor:` Code refactoring
- `test:` Adding or updating tests
- `chore:` Maintenance tasks

**Examples:**

```bash
feat: add user authentication
fix: resolve sidebar navigation bug
docs: update README with API documentation
refactor: optimize chart rendering performance
```

## Code Organization

### Component Structure

Each component should follow this structure:

```jsx
import React from 'react';
import { useStateContext } from '../contexts/ContextProvider';
import './ComponentName.css'; // Only if needed

const ComponentName = ({ prop1, prop2 }) => {
  // 1. Context and State
  const { currentColor, currentMode } = useStateContext();
  const [localState, setLocalState] = useState(initialValue);

  // 2. Side Effects
  useEffect(() => {
    // Effect logic
  }, [dependencies]);

  // 3. Event Handlers
  const handleClick = () => {
    // Handler logic
  };

  // 4. Render Helpers (if needed)
  const renderItem = (item) => {
    return <div>{item.name}</div>;
  };

  // 5. Return JSX
  return <div className="component-wrapper">{/* Component content */}</div>;
};

export default ComponentName;
```

### File Naming Conventions

- **Components**: PascalCase (`Button.jsx`, `ThemeSettings.jsx`)
- **Pages**: PascalCase (`ECommerce.jsx`, `Customers.jsx`)
- **Utilities**: camelCase (`helpers.js`, `constants.js`)
- **Contexts**: PascalCase (`ContextProvider.js`)
- **Data files**: camelCase (`dummy.js`)

### Import Organization

Organize imports in this order:

```javascript
// 1. React imports
import React, { useState, useEffect } from 'react';

// 2. External libraries
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import { TooltipComponent } from '@syncfusion/ej2-react-popups';

// 3. Internal components
import { Navbar, Sidebar, Footer } from './components';
import { ECommerce, Orders, Customers } from './pages';

// 4. Contexts
import { useStateContext } from './contexts/ContextProvider';

// 5. Assets and styles
import './App.css';
import logo from './assets/logo.png';
```

## Component Development

### Creating a New Component

1. **Create component file** in `src/components/`

   ```jsx
   // src/components/NewComponent.jsx
   import React from 'react';
   import { useStateContext } from '../contexts/ContextProvider';

   const NewComponent = ({ title, children }) => {
     const { currentColor } = useStateContext();

     return (
       <div className="new-component">
         <h2 style={{ color: currentColor }}>{title}</h2>
         {children}
       </div>
     );
   };

   export default NewComponent;
   ```

2. **Export from index file**

   ```javascript
   // src/components/index.jsx
   export { default as NewComponent } from './NewComponent';
   ```

3. **Use in pages**

   ```jsx
   import { NewComponent } from '../components';

   <NewComponent title="Hello">
     <p>Content here</p>
   </NewComponent>;
   ```

### Component Best Practices

1. **Keep components small and focused**
   - One component = one responsibility
   - Extract complex logic into custom hooks

2. **Use proper prop types**

   ```jsx
   const Button = ({ text, onClick, color = 'blue', disabled = false }) => {
     // Component logic
   };
   ```

3. **Destructure props early**

   ```jsx
   // Good
   const Header = ({ title, subtitle }) => {
     return <h1>{title}</h1>;
   };

   // Avoid
   const Header = (props) => {
     return <h1>{props.title}</h1>;
   };
   ```

4. **Use meaningful names**

   ```jsx
   // Good
   const handleUserSubmit = () => {};
   const isUserLoggedIn = true;

   // Avoid
   const handleClick = () => {};
   const flag = true;
   ```

## State Management

### Global State (Context API)

The application uses React Context for global state management.

**Available Global State:**

```javascript
const {
  // Theme
  currentColor, // Active theme color
  currentMode, // 'Light' or 'Dark'
  setColor, // Update theme color
  setMode, // Update theme mode

  // UI State
  activeMenu, // Sidebar visibility
  setActiveMenu, // Toggle sidebar
  screenSize, // Current screen width
  setScreenSize, // Update screen size
  themeSettings, // Settings panel visibility
  setThemeSettings, // Toggle settings panel

  // Component State
  isClicked, // { chat, cart, userProfile, notification }
  handleClick, // Update component visibility
  setIsClicked, // Set component state
  initialState, // Reset state
} = useStateContext();
```

### Using Global State

```jsx
import { useStateContext } from '../contexts/ContextProvider';

const MyComponent = () => {
  const { currentColor, currentMode, handleClick } = useStateContext();

  return (
    <button
      style={{ backgroundColor: currentColor }}
      onClick={() => handleClick('cart')}
      className={currentMode === 'Dark' ? 'dark-button' : 'light-button'}
    >
      Open Cart
    </button>
  );
};
```

### Local State

For component-specific state, use `useState`:

```jsx
const [formData, setFormData] = useState({
  name: '',
  email: '',
});

const handleChange = (e) => {
  setFormData({
    ...formData,
    [e.target.name]: e.target.value,
  });
};
```

### State Management Best Practices

1. **Keep state close to where it's used**
2. **Lift state up when multiple components need it**
3. **Use Context for truly global state only**
4. **Avoid unnecessary re-renders** with proper dependency arrays
5. **Use useCallback and useMemo** for expensive operations

## Styling Guidelines

### Tailwind CSS

The project uses Tailwind CSS utility classes for styling.

**Common Patterns:**

```jsx
// Layout
<div className="flex items-center justify-between">
<div className="grid grid-cols-3 gap-4">

// Spacing
<div className="p-4 m-2">          // padding and margin
<div className="mt-6 mb-8">        // margin top/bottom

// Colors
<div className="bg-white dark:bg-secondary-dark-bg">
<p className="text-gray-700 dark:text-gray-200">

// Responsive
<div className="w-full md:w-1/2 lg:w-1/3">
<div className="hidden md:block">  // Hide on mobile

// Effects
<button className="hover:bg-light-gray rounded-lg shadow-xl">
```

### Dark Mode Support

Always provide dark mode alternatives:

```jsx
<div className="bg-white dark:bg-main-dark-bg">
  <p className="text-gray-900 dark:text-gray-100">Text</p>
  <button className="bg-blue-500 dark:bg-blue-700">Button</button>
</div>
```

### Theme Color Integration

Use the global `currentColor` for theme-aware components:

```jsx
const { currentColor } = useStateContext();

<button style={{ backgroundColor: currentColor }} className="text-white rounded-lg">
  Themed Button
</button>;
```

### Custom Tailwind Configuration

Custom values are defined in `tailwind.config.js`:

```javascript
// Custom colors
'main-bg': '#FAFBFB'
'main-dark-bg': '#20232A'

// Custom widths
w-400, w-760, w-1000, w-1200, w-1400

// Use in components
<div className="bg-main-bg w-400">
```

## Working with Syncfusion

### Syncfusion Components

The project uses Syncfusion Essential JS 2 for React.

**Common Components:**

```jsx
// Grid/Table
import { GridComponent, ColumnsDirective, ColumnDirective } from '@syncfusion/ej2-react-grids';

// Charts
import { ChartComponent, SeriesCollectionDirective, SeriesDirective } from '@syncfusion/ej2-react-charts';

// Calendar
import { ScheduleComponent } from '@syncfusion/ej2-react-schedule';

// Kanban
import { KanbanComponent } from '@syncfusion/ej2-react-kanban';

// Editor
import { RichTextEditorComponent } from '@syncfusion/ej2-react-richtexteditor';
```

### Example: Data Grid

```jsx
import { GridComponent, ColumnsDirective, ColumnDirective, Page, Inject } from '@syncfusion/ej2-react-grids';

const CustomersGrid = () => {
  return (
    <GridComponent dataSource={customersData} allowPaging allowSorting pageSettings={{ pageSize: 12 }}>
      <ColumnsDirective>
        <ColumnDirective field="CustomerID" headerText="ID" width="100" />
        <ColumnDirective field="CustomerName" headerText="Name" width="150" />
        <ColumnDirective field="Email" headerText="Email" width="150" />
      </ColumnsDirective>
      <Inject services={[Page]} />
    </GridComponent>
  );
};
```

### Example: Chart

```jsx
import {
  ChartComponent,
  SeriesCollectionDirective,
  SeriesDirective,
  Inject,
  Legend,
  Category,
  Tooltip,
  DataLabel,
  LineSeries,
} from '@syncfusion/ej2-react-charts';

const LineChartComponent = () => {
  return (
    <ChartComponent
      primaryXAxis={{ valueType: 'Category' }}
      primaryYAxis={{ labelFormat: '{value}%' }}
      tooltip={{ enable: true }}
    >
      <Inject services={[LineSeries, Legend, Tooltip, DataLabel, Category]} />
      <SeriesCollectionDirective>
        <SeriesDirective dataSource={lineChartData} xName="x" yName="y" type="Line" marker={{ visible: true }} />
      </SeriesCollectionDirective>
    </ChartComponent>
  );
};
```

### Syncfusion Best Practices

1. **Only import what you need** to reduce bundle size
2. **Use Inject** to register services for each component
3. **Provide data in correct format** (check Syncfusion docs)
4. **Handle events properly** with callbacks
5. **Apply custom styling** through className and style props

## Adding New Features

### Adding a New Page

1. **Create page component**

   ```jsx
   // src/pages/NewPage.jsx
   import React from 'react';
   import { Header } from '../components';

   const NewPage = () => {
     return (
       <div className="m-2 md:m-10 mt-24 p-2 md:p-10 bg-white rounded-3xl">
         <Header category="Page" title="New Page" />
         {/* Page content */}
       </div>
     );
   };

   export default NewPage;
   ```

2. **Export from pages index**

   ```javascript
   // src/pages/index.jsx
   export { default as NewPage } from './NewPage';
   ```

3. **Add route in App.js**

   ```jsx
   import { NewPage } from './pages';

   <Routes>
     {/* ... other routes */}
     <Route path="/newpage" element={<NewPage />} />
   </Routes>;
   ```

4. **Add to sidebar navigation**
   ```javascript
   // src/data/dummy.js
   export const links = [
     // ... existing links
     {
       title: 'Pages',
       links: [
         // ... existing page links
         {
           name: 'newpage',
           icon: <FiNewIcon />,
         },
       ],
     },
   ];
   ```

### Adding a New Chart

1. **Create chart component**

   ```jsx
   // src/components/Charts/CustomChart.jsx
   import React from 'react';
   import {
     ChartComponent,
     SeriesCollectionDirective,
     SeriesDirective,
     Inject,
     Legend,
     Category,
     Tooltip,
   } from '@syncfusion/ej2-react-charts';

   const CustomChart = ({ data }) => {
     return (
       <ChartComponent>
         <Inject services={[Legend, Category, Tooltip]} />
         <SeriesCollectionDirective>
           <SeriesDirective dataSource={data} xName="x" yName="y" type="Column" />
         </SeriesCollectionDirective>
       </ChartComponent>
     );
   };

   export default CustomChart;
   ```

2. **Create chart page**

   ```jsx
   // src/pages/Charts/CustomChartPage.jsx
   import React from 'react';
   import { ChartsHeader, CustomChart } from '../../components';

   const CustomChartPage = () => {
     return (
       <div className="m-4 md:m-10 mt-24 p-10 bg-white dark:bg-secondary-dark-bg rounded-3xl">
         <ChartsHeader category="Chart" title="Custom Chart" />
         <CustomChart data={chartData} />
       </div>
     );
   };

   export default CustomChartPage;
   ```

### Adding Mock Data

Add data to `src/data/dummy.js`:

```javascript
export const newFeatureData = [
  {
    id: 1,
    name: 'Item 1',
    value: 100,
    status: 'Active',
  },
  // ... more data
];
```

## Testing

### Running Tests

```bash
# Run all tests
npm test

# Run tests in watch mode
npm test -- --watch

# Run tests with coverage
npm test -- --coverage
```

### Writing Tests

Create test files next to components:

```javascript
// src/components/Button.test.js
import { render, screen, fireEvent } from '@testing-library/react';
import Button from './Button';

describe('Button Component', () => {
  test('renders button with text', () => {
    render(<Button text="Click Me" />);
    expect(screen.getByText('Click Me')).toBeInTheDocument();
  });

  test('calls onClick when clicked', () => {
    const handleClick = jest.fn();
    render(<Button text="Click" onClick={handleClick} />);
    fireEvent.click(screen.getByText('Click'));
    expect(handleClick).toHaveBeenCalledTimes(1);
  });
});
```

## Build & Deployment

### Production Build

```bash
# Create optimized build
npm run build

# The build folder will contain:
# - Minified JavaScript
# - Optimized CSS
# - Compressed assets
```

### Build Optimization

1. **Code Splitting**: Lazy load routes

   ```jsx
   const NewPage = React.lazy(() => import('./pages/NewPage'));

   <Suspense fallback={<Loading />}>
     <Route path="/newpage" element={<NewPage />} />
   </Suspense>;
   ```

2. **Tree Shaking**: Import only what you need

   ```jsx
   // Good
   import { Button } from './components';

   // Avoid
   import * as Components from './components';
   ```

3. **Image Optimization**: Use WebP format and lazy loading

### Deployment Options

**Vercel:**

```bash
npm install -g vercel
vercel
```

**Netlify:**

```bash
npm install -g netlify-cli
netlify deploy --prod --dir=build
```

**GitHub Pages:**

```bash
npm install --save-dev gh-pages

# Add to package.json
"homepage": "https://username.github.io/dashboard-react",
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build"
}

npm run deploy
```

## Troubleshooting

### Common Issues

**1. Module not found errors**

```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

**2. Tailwind styles not applying**

```bash
# Restart development server
npm start
```

**3. React Router not working after build**

- Configure server for client-side routing
- Use HashRouter as fallback

**4. Syncfusion components not rendering**

- Check if you've registered services with `<Inject services={[...]} />`
- Verify data format matches component requirements

**5. Dark mode not toggling**

- Check `tailwind.config.js` has `darkMode: 'class'`
- Verify parent element has `dark` class

### Debug Mode

Enable React DevTools for debugging:

1. Install React Developer Tools browser extension
2. Open browser DevTools
3. Navigate to Components tab
4. Inspect component state and props

### Performance Issues

```bash
# Analyze bundle size
npm install -g source-map-explorer
npm run build
source-map-explorer 'build/static/js/*.js'

# Profile component rendering
# Use React DevTools Profiler tab
```

## Resources

### Documentation Links

- [React Documentation](https://react.dev/)
- [React Router](https://reactrouter.com/)
- [Tailwind CSS](https://tailwindcss.com/docs)
- [Syncfusion React Components](https://ej2.syncfusion.com/react/documentation/)
- [React Icons](https://react-icons.github.io/react-icons/)

### Learning Resources

- [React Patterns](https://reactpatterns.com/)
- [JavaScript Info](https://javascript.info/)
- [CSS Tricks](https://css-tricks.com/)
- [Web.dev](https://web.dev/)

### Community

- GitHub Issues: Report bugs and request features
- Stack Overflow: Tag questions with `react`, `tailwindcss`, `syncfusion`

---

**Happy Coding! 🚀**

For questions or contributions, please refer to the main [README.md](README.md) file.
