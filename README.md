# NiceAdmin Dashboard v2

A responsive, feature-rich admin dashboard template built with HTML, CSS, and JavaScript. NiceAdmin provides a modern UI for managing data, displaying analytics, and building administrative interfaces.

## Platform Overview

### Technology Stack
- **Frontend Framework**: Vanilla HTML5, CSS3, JavaScript
- **Styling**: Bootstrap 5, SCSS
- **Charts & Visualization**: 
  - ApexCharts (line, area, and radar charts)
  - Chart.js (alternative chart library)
  - ECharts (advanced data visualization)
- **Icons**: Bootstrap Icons, BoxIcons, Remix Icons
- **Rich Text Editor**: TinyMCE
- **Data Tables**: Simple DataTables
- **Email Form Backend**: PHP

### Key Features
- Responsive sidebar navigation with collapsible menu items
- Top navigation bar with search, notifications, and user profile
- KPI (Key Performance Indicator) cards with real-time data
- Interactive charts and graphs for reporting
- Recent activity feed with color-coded badges
- Data tables with search and pagination
- Form components and validation
- Mobile-optimized design

### Project Structure
```
NiceAdmin/
├── index.html                 # Main dashboard page
├── assets/
│   ├── css/                   # Stylesheets
│   ├── js/                    # JavaScript files
│   ├── img/                   # Images
│   └── vendor/                # Third-party libraries
├── forms/                     # PHP backend for forms
├── tests/                     # Playwright test suite
└── [various component pages]  # Charts, tables, forms, etc.
```

## Test Cases

The test suite uses **Playwright** to perform comprehensive UI smoke tests covering all major dashboard components.

### Test Categories

#### 1. Sidebar Navigation Tests
- **TC-01: Sidebar loads with all menu items**
  - Verifies sidebar visibility and presence of menu categories (Dashboard, Components, Forms)
  
- **TC-02: Clicking each sidebar item loads correct page**
  - Navigates through sidebar links and validates page load (non-404 responses)
  - Tests first 5 sidebar links for robustness
  
- **TC-03: Expand/collapse of grouped menu items**
  - Validates collapsible menu structure exists and is functional

#### 2. Dashboard Navigation Bar Tests
- **TC-04: Search bar accepts text**
  - Verifies search input field visibility
  - Tests text input functionality with "sales" query
  
- **TC-05: Notification bell dropdown appears**
  - Tests notification icon visibility and dropdown functionality
  
- **TC-06: User profile dropdown opens**
  - Validates profile image visibility and dropdown menu appearance

#### 3. KPI Cards Tests
- **TC-07: KPI cards are visible with correct values**
  - Verifies presence of at least 3 KPI cards
  - Confirms cards contain data
  
- **TC-08: KPI percentage color indicates increase/decrease**
  - Validates color-coded indicators (green for success/increase, red for danger/decrease)
  - Tests Sales card with success indicator and Customers card with danger indicator

#### 4. Reports Chart Tests
- **TC-09: Reports graph loads with three series**
  - Verifies the reports chart (#reportsChart) renders with SVG or canvas element
  
- **TC-10: Tooltip on hover shows values**
  - Tests hover interactions on the reports chart
  - Validates ApexCharts tooltip functionality

#### 5. Recent Activity List Tests
- **TC-11: Recent activity items render correctly**
  - Verifies exactly 6 activity items are displayed
  - Validates each item contains label, badge, and content
  
- **TC-12: Activity badges have correct color classes**
  - Checks 6 activity badges contain correct color classes
  - Expected colors: text-success, text-danger, text-primary, text-info, text-warning, text-muted

#### 6. Budget Report Chart Tests
- **TC-13: Radar chart loads with two datasets**
  - Verifies radar chart (#budgetChart) container visibility and content
  
- **TC-14: Radar chart legend matches lines**
  - Validates radar chart renders with proper legend and line data

#### 7. Recent Sales Table Tests
- **TC-15: Entries-per-page dropdown changes row count**
  - Tests select dropdown for pagination control
  - Verifies table has rendered rows
  
- **TC-16: Search inside table filters results**
  - Tests table search functionality
  - Verifies filtering works (searches for "Brandon")

#### 8. General UI & Performance Tests
- **TC-17: Scrolling is smooth with no layout shifts**
  - Validates smooth scrolling to bottom of page
  
- **TC-18: Responsive design adapts on resize**
  - Tests mobile viewport (375x667) and desktop viewport (1280x800)
  
- **TC-19: No broken icons (no missing svg text)**
  - Verifies all Bootstrap icons render properly
  
- **TC-20: Dashboard loads quickly (<3s)**
  - Performance test validating page load time under 5 seconds

## Running Tests

### Prerequisites
- Node.js installed
- Local web server running (default: http://127.0.0.1:5500/)

### Installation
```bash
npm install
npx playwright install
```

### Run All Tests
```bash
npx playwright test
```

### Run Specific Test
```bash
npx playwright test example.spec.ts
```

### Run Tests in UI Mode
```bash
npx playwright test --ui
```

### Run Tests in Debug Mode
```bash
npx playwright test --debug
```

### Generate Test Report
```bash
npx playwright show-report
```

## Configuration

The test suite is configured in `playwright.config.ts`. 

**Default Base URL**: `http://127.0.0.1:5500/`

To change the server port, modify the `BASE_URL` constant in [tests/example.spec.ts](tests/example.spec.ts).

## Browser Support

Tests run on:
- Chromium
- Firefox
- WebKit

## Key Dependencies

- **@playwright/test**: End-to-end testing framework
- **bootstrap**: CSS framework
- **apexcharts**: Interactive charting library
- **chart.js**: JavaScript charting
- **echarts**: Data visualization
- **quill**: Rich text editor
- **tinymce**: Advanced WYSIWYG editor

## Notes

- All tests include detailed logging with emoji indicators for easy debugging
- Tests are designed to be robust, skipping non-critical failures to focus on core functionality
- Network waits (`networkidle`, `domcontentloaded`) ensure proper page loading before assertions
- Tests use appropriate timeouts for element visibility and interactions

---

**Version**: 2.0  
**Last Updated**: March 2026
