# 🧪 NiceAdmin UI Testing Guide

## Overview
This project includes **20 comprehensive UI test cases** using Playwright that validate the NiceAdmin dashboard functionality.

---

## 🚀 Running Tests with Visual Browser

### **Option 1: Run All Tests (Headed Mode - See Browser)**
```bash
npm test
```
This runs tests in **headed mode** with:
- ✅ Browser window visible (watch interactions in real-time)
- ✅ 1-second slowMo (slows down actions for visibility)
- ✅ Console logs showing each test step
- ✅ Tests run sequentially (one after another)

### **Option 2: Run Specific Test**
```bash
npx playwright test TC-01
```

### **Option 3: Run Only Chromium Browser**
```bash
npx playwright test --project=chromium
```

### **Option 4: Run in Debug Mode**
```bash
npx playwright test --debug
```
Opens Playwright Inspector - step through each action.

### **Option 5: Headless Mode (Background)**
```bash
npm run test:headed -- --headed=false
```

---

## 📊 Viewing Test Results

After tests complete:

```bash
npm run test:report
```

This opens an HTML report with:
- ✅ Test status (passed/failed)
- 📹 Video recordings (if failed)
- 📸 Screenshots (if failed)
- 📝 Trace logs (for debugging)

---

## 📋 Test Cases Covered

### **1. Sidebar Navigation (3 tests)**
- TC-01: Sidebar loads with all menu items
- TC-02: Clicking sidebar items loads correct pages
- TC-03: Menu expand/collapse works

### **2. Top Navigation Bar (3 tests)**
- TC-04: Search bar accepts text
- TC-05: Notification bell dropdown appears
- TC-06: User profile dropdown opens

### **3. KPI Dashboard Cards (2 tests)**
- TC-07: KPI cards visible with correct values
- TC-08: Percentage indicators show correct colors

### **4. Charts & Visualizations (4 tests)**
- TC-09: Reports graph loads
- TC-10: Tooltip appears on hover
- TC-13: Radar chart loads with data
- TC-14: Chart legend matches lines

### **5. Activity & Recent Items (2 tests)**
- TC-11: Recent activity items render
- TC-12: Activity badges have correct colors

### **6. Data Table (2 tests)**
- TC-15: Entries-per-page dropdown works
- TC-16: Table search filters results

### **7. UI Behaviors (2 tests)**
- TC-17: Scrolling is smooth
- TC-18: Responsive design adapts

### **8. Performance (1 test)**
- TC-20: Dashboard loads quickly

---

## 🛠️ Configuration

### Playwright Settings
Located in `playwright.config.ts`:
- **headless: false** - Browser window visible
- **slowMo: 1000** - 1-second delay between actions
- **timeout: 30000** - 30 seconds per test
- **fullyParallel: false** - Tests run sequentially for visibility

### Base URL
Tests point to: `http://127.0.0.1:5500/`

**Make sure your local server is running:**
```bash
npx http-server -p 5500 -c-1
# or
python -m http.server 5500
```

---

## 📺 Understanding Console Output

When running tests, you'll see:
```
🚀 Starting test - navigating to dashboard...
✅ Dashboard loaded

📋 TC-01: Checking sidebar menu items...
   ✓ Sidebar is visible
   ✓ Dashboard found in menu
   ✓ Components found in menu
   ✓ Forms found in menu
✅ TC-01 PASSED
```

Each ✅ shows that a step completed successfully.

---

## 🐛 Debugging Failed Tests

1. **Run in debug mode:**
   ```bash
   npx playwright test --debug
   ```

2. **Check video/screenshot:**
   ```bash
   npm run test:report
   ```

3. **Inspect specific browser:**
   ```bash
   npx playwright test --project=firefox --debug
   ```

---

## ✨ Tips for Best Visibility

1. **Make terminal full-screen** - Better view of logs
2. **Resize browser window** - Position next to terminal
3. **Run one test** - `npx playwright test TC-01` for focused view
4. **Increase slowMo** - Edit `slowMo: 2000` in config for slower actions

---

## 📝 Adding New Tests

Create tests in `tests/example.spec.ts`:

```typescript
test('TC-XX my new test', async ({ page }) => {
  console.log('\n🎯 TC-XX: My test description...');
  
  // Your test code here
  
  console.log('✅ TC-XX PASSED');
});
```

---

## 🎯 Browser Support

Tests run on:
- ✅ **Chromium** (Chrome, Edge)
- ✅ **Firefox**
- ✅ **WebKit** (Safari)

---

## 📞 Support

For Playwright documentation: https://playwright.dev/
