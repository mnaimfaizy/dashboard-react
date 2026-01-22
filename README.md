# Shoppy - Modern Admin Dashboard

A comprehensive, feature-rich admin dashboard application built with React, Syncfusion components, and Tailwind CSS. This dashboard provides a complete solution for managing e-commerce operations, viewing analytics, and visualizing data through interactive charts and tables.

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Available Scripts](#available-scripts)
- [Pages and Features](#pages-and-features)
- [Components](#components)
- [State Management](#state-management)
- [Theming](#theming)
- [Configuration](#configuration)
- [License](#license)

## ✨ Features

### Core Features

- 🎨 **Multiple Theme Support** - Light and Dark mode with customizable color schemes
- 📊 **Interactive Charts** - Line, Area, Bar, Pie, Financial, Pyramid, Stacked, and Color Mapping charts
- 📱 **Responsive Design** - Fully responsive layout that works on desktop, tablet, and mobile devices
- 🎯 **Data Visualization** - Rich data grids with sorting, filtering, and pagination
- 🗓️ **Calendar Integration** - Full-featured calendar for scheduling and event management
- 📝 **Rich Text Editor** - Built-in editor for content creation
- 🎨 **Color Picker** - Advanced color selection tool
- 📋 **Kanban Board** - Task management with drag-and-drop functionality
- 🔔 **Notifications** - Real-time notification system
- 🛒 **Shopping Cart** - E-commerce cart functionality
- 💬 **Chat Interface** - User communication features
- 👤 **User Profile** - User profile management

### Dashboard Capabilities

- **E-Commerce Dashboard** - Revenue tracking, sales statistics, and financial metrics
- **Orders Management** - View and manage customer orders
- **Employee Management** - Employee directory and information
- **Customer Management** - Customer data and analytics
- **Analytics & Reports** - Comprehensive data visualization and insights

## 🛠️ Tech Stack

### Core Technologies

- **React** (v17.0.2) - JavaScript library for building user interfaces
- **React Router DOM** (v6.2.1) - Routing and navigation
- **React Scripts** (v5.0.0) - Build tooling and development server

### UI Framework & Styling

- **Tailwind CSS** (v3.0.19) - Utility-first CSS framework
- **PostCSS** (v8.4.6) - CSS transformation tool
- **Autoprefixer** (v10.4.2) - CSS vendor prefixing
- **CRACO** - Create React App Configuration Override for custom Webpack config

### Syncfusion Components (v19.4.x)

- **@syncfusion/ej2-react-calendars** - Calendar and date picker components
- **@syncfusion/ej2-react-charts** - Advanced charting components
- **@syncfusion/ej2-react-dropdowns** - Dropdown and combobox components
- **@syncfusion/ej2-react-grids** - Data grid components
- **@syncfusion/ej2-react-inputs** - Input components
- **@syncfusion/ej2-react-kanban** - Kanban board component
- **@syncfusion/ej2-react-popups** - Tooltip and popup components
- **@syncfusion/ej2-react-richtexteditor** - Rich text editing
- **@syncfusion/ej2-react-schedule** - Scheduler and calendar events

### Icons

- **React Icons** (v4.3.1) - Comprehensive icon library including:
  - Ant Design Icons (Ai)
  - Feather Icons (Fi)
  - Bootstrap Icons (Bs)
  - Box Icons (Bi)
  - Ionicons (Io)
  - Remix Icons (Ri)
  - Material Design Icons (Md)
  - Game Icons (Gi)
  - Grommet Icons (Gr)
  - Tabler Icons (Ti)

## 📁 Project Structure

```
dashboard-react/
├── public/                          # Static files
│   ├── index.html                   # HTML template
│   ├── manifest.json                # PWA manifest
│   └── robots.txt                   # SEO robots file
│
├── src/
│   ├── App.js                       # Main application component
│   ├── App.css                      # Application styles
│   ├── index.js                     # Application entry point
│   ├── index.css                    # Global styles
│   │
│   ├── components/                  # Reusable UI components
│   │   ├── Button.jsx               # Custom button component
│   │   ├── Cart.jsx                 # Shopping cart component
│   │   ├── ChartsHeader.jsx         # Header for chart pages
│   │   ├── Chat.jsx                 # Chat interface
│   │   ├── Footer.jsx               # Footer component
│   │   ├── Header.jsx               # Page header component
│   │   ├── Navbar.jsx               # Top navigation bar
│   │   ├── Notification.jsx         # Notification panel
│   │   ├── Sidebar.jsx              # Side navigation menu
│   │   ├── ThemeSettings.jsx        # Theme customization panel
│   │   ├── UserProfile.jsx          # User profile dropdown
│   │   ├── index.jsx                # Component exports
│   │   │
│   │   └── Charts/                  # Chart components
│   │       ├── LineChart.jsx        # Line chart wrapper
│   │       ├── Pie.jsx              # Pie chart wrapper
│   │       ├── SparkLine.jsx        # Sparkline chart
│   │       └── Stacked.jsx          # Stacked chart wrapper
│   │
│   ├── pages/                       # Page components (routes)
│   │   ├── Calender.jsx             # Calendar page
│   │   ├── ColorPicker.jsx          # Color picker tool
│   │   ├── Customers.jsx            # Customer management
│   │   ├── ECommerce.jsx            # Main dashboard
│   │   ├── Editor.jsx               # Rich text editor
│   │   ├── Employees.jsx            # Employee management
│   │   ├── Kanban.jsx               # Kanban board
│   │   ├── Orders.jsx               # Orders management
│   │   ├── index.jsx                # Page exports
│   │   │
│   │   └── Charts/                  # Chart pages
│   │       ├── Area.jsx             # Area chart page
│   │       ├── Bar.jsx              # Bar chart page
│   │       ├── ColorMapping.jsx     # Color mapping chart
│   │       ├── Financial.jsx        # Financial chart
│   │       ├── Line.jsx             # Line chart page
│   │       ├── Pie.jsx              # Pie chart page
│   │       ├── Pyramid.jsx          # Pyramid chart
│   │       └── Stacked.jsx          # Stacked chart page
│   │
│   ├── contexts/                    # React Context for state management
│   │   └── ContextProvider.js       # Global state provider
│   │
│   └── data/                        # Static data and utilities
│       ├── dummy.js                 # Mock data for the application
│       ├── avatar.jpg               # User avatar images
│       ├── avatar2.jpg
│       ├── avatar3.png
│       ├── avatar4.jpg
│       ├── product1.jpg             # Product images
│       ├── product2.jpg
│       ├── product3.jpg
│       ├── product4.jpg
│       ├── product5.jpg
│       ├── product6.jpg
│       ├── product7.jpg
│       ├── product8.jpg
│       └── product9.jpg
│
├── craco.config.js                  # CRACO configuration
├── tailwind.config.js               # Tailwind CSS configuration
├── package.json                     # Project dependencies
└── README.md                        # Project documentation
```

## 🚀 Installation

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn package manager

### Steps

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd dashboard-react
   ```

2. **Install dependencies**

   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start the development server**

   ```bash
   npm start
   # or
   yarn start
   ```

4. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

## 📜 Available Scripts

### `npm start`

Runs the app in development mode at [http://localhost:3000](http://localhost:3000). The page will reload when you make changes, and lint errors will appear in the console.

### `npm test`

Launches the test runner in interactive watch mode. See [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder. It correctly bundles React in production mode and optimizes the build for the best performance. The build is minified and filenames include hashes.

### `npm run eject`

**Note: This is a one-way operation. Once you eject, you can't go back!**

This command will remove the single build dependency from your project and copy all configuration files and transitive dependencies (webpack, Babel, ESLint, etc.) into your project for full control.

## 📄 Pages and Features

### Dashboard

- **E-Commerce Dashboard** (`/` or `/ecommerce`)
  - Revenue statistics and earnings display
  - Budget vs. expenses tracking
  - Recent transactions
  - Revenue update charts
  - Quick action buttons
  - Earnings data with percentage changes
  - Medical pro branding section
  - Weekly statistics

### Pages Section

- **Orders** (`/orders`)
  - Order management with data grid
  - Filtering and sorting capabilities
  - Order status tracking
  - Product images and details

- **Employees** (`/employees`)
  - Employee directory
  - Employee information management
  - Profile images and contact details

- **Customers** (`/customers`)
  - Customer database
  - Customer analytics
  - Contact information

### Apps Section

- **Calendar** (`/calendar`)
  - Event scheduling
  - Full calendar integration
  - Date picker functionality

- **Kanban** (`/kanban`)
  - Task management board
  - Drag-and-drop functionality
  - Status columns: To Do, In Progress, Testing, Done
  - Task cards with details

- **Editor** (`/editor`)
  - Rich text editor
  - Content creation and editing
  - Formatting tools

- **Color Picker** (`/color-picker`)
  - Advanced color selection tool
  - RGB, HEX, and HSL support

### Charts Section

- **Line Chart** (`/line`) - Trend visualization
- **Area Chart** (`/area`) - Filled area graphs
- **Bar Chart** (`/bar`) - Comparative bar graphs
- **Pie Chart** (`/pie`) - Proportional data visualization
- **Financial Chart** (`/financial`) - Stock and financial data
- **Color Mapping** (`/color-mapping`) - Heat map visualizations
- **Pyramid Chart** (`/pyramid`) - Hierarchical data
- **Stacked Chart** (`/stacked`) - Stacked bar/area charts

## 🧩 Components

### Layout Components

#### Navbar

- Top navigation bar
- Responsive menu toggle
- Quick access buttons:
  - Shopping cart
  - Chat
  - Notifications
  - User profile
- Adaptive to screen size (collapses on mobile)

#### Sidebar

- Collapsible navigation menu
- Organized into sections:
  - Dashboard
  - Pages (Orders, Employees, Customers)
  - Apps (Calendar, Kanban, Editor, Color Picker)
  - Charts (8 chart types)
- Active link highlighting
- Theme-aware styling
- Mobile-responsive

#### Footer

- Application footer
- Copyright and links

#### Header

- Page-specific headers
- Breadcrumb navigation
- Title display

### Interactive Components

#### ThemeSettings

- Theme mode selector (Light/Dark)
- Color scheme picker
- Customizable accent colors
- Settings panel overlay
- Persistent theme storage (localStorage)

#### Cart

- Shopping cart interface
- Product listings
- Price calculations
- Cart item management

#### Chat

- Messaging interface
- User conversations
- Message notifications

#### Notification

- Notification panel
- Alert system
- Real-time updates

#### UserProfile

- User information display
- Profile dropdown
- Account settings access

### Chart Components

- **LineChart** - Wrapper for line chart visualization
- **Pie** - Pie chart component
- **SparkLine** - Mini trend indicators
- **Stacked** - Stacked chart visualization

All chart components utilize Syncfusion's powerful charting library with interactive features.

## 🎯 State Management

The application uses **React Context API** for global state management through `ContextProvider.js`.

### Global State Properties

```javascript
{
  // UI State
  activeMenu: boolean,           // Sidebar visibility
  screenSize: number,            // Current screen width
  themeSettings: boolean,        // Theme settings panel visibility

  // Theme State
  currentColor: string,          // Active theme color (default: '#03C9D7')
  currentMode: string,           // Theme mode: 'Light' or 'Dark'

  // Component State
  isClicked: {
    chat: boolean,               // Chat panel state
    cart: boolean,               // Cart panel state
    userProfile: boolean,        // User profile state
    notification: boolean        // Notification panel state
  }
}
```

### State Management Functions

- `setMode(e)` - Sets theme mode and persists to localStorage
- `setColor(color)` - Sets theme color and persists to localStorage
- `handleClick(clicked)` - Manages component visibility (cart, chat, etc.)
- `setActiveMenu(boolean)` - Controls sidebar visibility
- `setScreenSize(number)` - Updates current screen size
- `setThemeSettings(boolean)` - Toggles theme settings panel

### Persistent Storage

Theme preferences (mode and color) are automatically saved to browser's localStorage and restored on application reload.

## 🎨 Theming

### Dark Mode Support

The application fully supports dark mode with a class-based approach (`dark:` prefix in Tailwind CSS).

### Theme Colors

Available preset colors:

- Blue (#03C9D7)
- Green
- Purple
- Red
- Indigo
- Orange
- And more...

### Custom Tailwind Configuration

#### Extended Colors

```javascript
backgroundColor: {
  'main-bg': '#FAFBFB',           // Light mode background
  'main-dark-bg': '#20232A',      // Dark mode background
  'secondary-dark-bg': '#33373E', // Dark mode secondary
  'light-gray': '#F7F7F7',
  'half-transparent': 'rgba(0, 0, 0, 0.5)',
}
```

#### Custom Dimensions

- Custom widths: 400px, 760px, 780px, 800px, 1000px, 1200px, 1400px
- Custom heights and min-heights for specific components
- Border width: 1px

#### Font Family

- Primary font: Open Sans

### Responsive Breakpoints

Uses Tailwind's default breakpoints:

- `sm`: 640px
- `md`: 768px
- `lg`: 1024px
- `xl`: 1280px
- `2xl`: 1536px

## ⚙️ Configuration

### CRACO Configuration

The project uses CRACO (Create React App Configuration Override) to customize the build configuration without ejecting.

**craco.config.js:**

```javascript
module.exports = {
  style: {
    postcss: {
      plugins: [require('tailwindcss'), require('autoprefixer')],
    },
  },
};
```

### Tailwind CSS

Configured for JIT (Just-In-Time) mode with dark mode support. See `tailwind.config.js` for complete configuration.

### Browser Support

**Production:**

- \>0.2% market share
- Not dead browsers
- Not Opera Mini

**Development:**

- Last Chrome version
- Last Firefox version
- Last Safari version

## 📦 Dependencies Summary

### Production Dependencies

```json
{
  "@syncfusion/ej2": "^19.4.48",
  "@syncfusion/ej2-react-calendars": "^19.4.48",
  "@syncfusion/ej2-react-charts": "^19.4.50",
  "@syncfusion/ej2-react-dropdowns": "^19.4.52",
  "@syncfusion/ej2-react-grids": "^19.4.50",
  "@syncfusion/ej2-react-inputs": "^19.4.52",
  "@syncfusion/ej2-react-kanban": "^19.4.48",
  "@syncfusion/ej2-react-popups": "^19.4.52",
  "@syncfusion/ej2-react-richtexteditor": "^19.4.50",
  "@syncfusion/ej2-react-schedule": "^19.4.50",
  "react": "^17.0.2",
  "react-dom": "^17.0.2",
  "react-icons": "^4.3.1",
  "react-router-dom": "^6.2.1"
}
```

### Development Dependencies

```json
{
  "autoprefixer": "^10.4.2",
  "postcss": "^8.4.6",
  "tailwindcss": "^3.0.19"
}
```

## 🔑 Key Features Implementation

### Responsive Design

- Sidebar collapses on screens ≤900px
- Adaptive navigation menu
- Mobile-first approach
- Touch-friendly interfaces

### Performance Optimizations

- Code splitting with React Router
- Lazy loading of components
- Optimized builds with webpack
- Efficient re-rendering with React Context

### User Experience

- Smooth transitions and animations
- Tooltip support throughout the app
- Consistent design language
- Intuitive navigation structure

### Data Management

- Mock data structure for development
- Extensible data models
- Easy integration with backend APIs
- Structured data in `dummy.js`

## 📝 License

This project is bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📧 Support

For support, please open an issue in the repository.

---

**Built with ❤️ using React, Syncfusion, and Tailwind CSS**
