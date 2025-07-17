# 🎨 **WMS FRONTEND DESIGN GUIDE**
## *Berry MUI Design System для Warehouse Management System*

---

## 📋 **СОДЕРЖАНИЕ**

1. [🎨 Design System и Color Palette](#1-design-system-и-color-palette)
2. [🏗️ Layout Architecture](#2-layout-architecture)  
3. [🔐 Authentication Pages](#3-authentication-pages)
4. [📊 Dashboard и Analytics](#4-dashboard-и-analytics)
5. [📦 Inventory Management](#5-inventory-management)
6. [📥 Inbound Operations](#6-inbound-operations)
7. [📤 Outbound Operations](#7-outbound-operations)
8. [🎓 Training Module](#8-training-module)
9. [🌊 Wave Planning](#9-wave-planning)
10. [🚛 Cross-Docking](#10-cross-docking)
11. [📱 Mobile Components](#11-mobile-components)
12. [🔔 Notifications System](#12-notifications-system)

---

## **1. 🎨 DESIGN SYSTEM И COLOR PALETTE**

### **Primary Color Palette (Berry MUI)**
```css
/* Primary Colors */
--primary-main: #1976d2;      /* Main Blue */
--primary-light: #42a5f5;     /* Light Blue */
--primary-dark: #1565c0;      /* Dark Blue */
--primary-50: #e3f2fd;        /* Very Light Blue */
--primary-100: #bbdefb;       /* Light Blue Background */

/* Secondary Colors */
--secondary-main: #f57c00;    /* Orange */
--secondary-light: #ffb74d;   /* Light Orange */
--secondary-dark: #ef6c00;    /* Dark Orange */

/* Status Colors */
--success-main: #388e3c;      /* Green */
--success-light: #66bb6a;     /* Light Green */
--warning-main: #f9a825;      /* Yellow */
--warning-light: #ffcc02;     /* Light Yellow */
--error-main: #d32f2f;        /* Red */
--error-light: #ef5350;       /* Light Red */
--info-main: #0288d1;         /* Info Blue */

/* Neutral Colors */
--grey-50: #fafafa;           /* Background Light */
--grey-100: #f5f5f5;          /* Background */
--grey-200: #eeeeee;          /* Border Light */
--grey-300: #e0e0e0;          /* Border */
--grey-400: #bdbdbd;          /* Border Dark */
--grey-500: #9e9e9e;          /* Text Secondary */
--grey-600: #757575;          /* Text Primary Light */
--grey-700: #616161;          /* Text Primary */
--grey-800: #424242;          /* Text Primary Dark */
--grey-900: #212121;          /* Text Primary Darkest */

/* Background Colors */
--bg-default: #fafafa;        /* Page Background */
--bg-paper: #ffffff;          /* Card Background */
--bg-level1: #ffffff;         /* Level 1 Background */
--bg-level2: #f8f9fa;         /* Level 2 Background */

/* Text Colors */
--text-primary: #212121;      /* Primary Text */
--text-secondary: #757575;    /* Secondary Text */
--text-disabled: #bdbdbd;     /* Disabled Text */
```

### **Typography Scale**
```css
/* Headers */
--font-h1: 2rem;              /* 32px - Page Title */
--font-h2: 1.5rem;            /* 24px - Section Title */
--font-h3: 1.25rem;           /* 20px - Card Title */
--font-h4: 1.125rem;          /* 18px - Subsection */
--font-h5: 1rem;              /* 16px - Small Header */
--font-h6: 0.875rem;          /* 14px - Caption Header */

/* Body Text */
--font-body1: 1rem;           /* 16px - Primary Body */
--font-body2: 0.875rem;       /* 14px - Secondary Body */
--font-caption: 0.75rem;      /* 12px - Caption */
--font-overline: 0.75rem;     /* 12px - Overline */

/* Font Weights */
--font-weight-light: 300;
--font-weight-regular: 400;
--font-weight-medium: 500;
--font-weight-bold: 700;

/* Font Family */
--font-family: 'Inter', 'Roboto', 'Helvetica', 'Arial', sans-serif;
```

### **Spacing System**
```css
/* Base spacing unit: 8px */
--spacing-1: 0.25rem;         /* 4px */
--spacing-2: 0.5rem;          /* 8px */
--spacing-3: 0.75rem;         /* 12px */
--spacing-4: 1rem;            /* 16px */
--spacing-5: 1.25rem;         /* 20px */
--spacing-6: 1.5rem;          /* 24px */
--spacing-8: 2rem;            /* 32px */
--spacing-10: 2.5rem;         /* 40px */
--spacing-12: 3rem;           /* 48px */
--spacing-16: 4rem;           /* 64px */
```

### **Shadow System**
```css
--shadow-1: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
--shadow-2: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
--shadow-3: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
--shadow-4: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
--shadow-5: 0 19px 38px rgba(0,0,0,0.30), 0 15px 12px rgba(0,0,0,0.22);
```

---

## **2. 🏗️ LAYOUT ARCHITECTURE**

### **Main Layout Structure**
```
┌─────────────────────────────────────────────────────────────┐
│                     TOP NAVIGATION BAR                     │ 64px
│ [Logo] [Breadcrumbs]    [Search]  [Notifications] [User]   │
├─────────────────────────────────────────────────────────────┤
│ SIDE │                                                     │
│ BAR  │                 MAIN CONTENT AREA                   │
│ 280px│                                                     │
│      │              [Page Content]                         │
│ [Nav │                                                     │
│ Menu]│                                                     │
│      │                                                     │
│      │                                                     │
└─────────────────────────────────────────────────────────────┘
```

### **Top Navigation (AppBar)**
- **Height:** 64px
- **Background:** `--bg-paper` (white)
- **Shadow:** `--shadow-1`
- **Sticky position:** `position: sticky, top: 0, z-index: 1200`

**Components:**
- Logo (120px width)
- Breadcrumbs (dynamic)
- Global Search Bar (300px width)
- Notification Bell with Badge
- User Avatar with Dropdown

### **Side Navigation (Drawer)**
- **Width:** 280px (expanded), 72px (collapsed)
- **Background:** `--bg-paper` (white)
- **Border:** `1px solid --grey-200`

**Navigation Items:**
```
📊 Dashboard
📦 Inventory
  ├── Products
  ├── Stock Overview
  └── Locations
📥 Inbound
  ├── ASN List
  ├── Receiving
  └── Put-away
📤 Outbound  
  ├── Orders
  ├── Picking
  └── Shipping
🌊 Wave Planning
🚛 Cross-Docking
🎓 Training
📊 Analytics
⚙️ Settings
```

### **Content Area**
- **Padding:** `24px`
- **Background:** `--bg-default`
- **Min Height:** `calc(100vh - 64px)`

---

## **3. 🔐 AUTHENTICATION PAGES**

### **3.1 Login Page**

**Layout:**
```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│         ┌─────────────────────────────────┐                 │
│         │                                 │                 │
│         │          [WMS LOGO]             │                 │
│         │                                 │                 │
│         │      Warehouse Management      │                 │
│         │           System               │                 │
│         │                                 │                 │
│         │    ┌─────────────────────────┐  │                 │
│         │    │  Email Address          │  │                 │
│         │    └─────────────────────────┘  │                 │
│         │                                 │                 │
│         │    ┌─────────────────────────┐  │                 │
│         │    │  Password               │  │                 │
│         │    └─────────────────────────┘  │                 │
│         │                                 │                 │
│         │    ☐ Remember me                │                 │
│         │                                 │                 │
│         │    ┌─────────────────────────┐  │                 │
│         │    │      SIGN IN            │  │                 │
│         │    └─────────────────────────┘  │                 │
│         │                                 │                 │
│         │    Forgot password?             │                 │
│         │                                 │                 │
│         └─────────────────────────────────┘                 │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**Specifications:**
- **Card Width:** 400px
- **Card Padding:** 32px
- **Card Shadow:** `--shadow-2`
- **Background:** Gradient from `--primary-50` to `--grey-50`
- **Input Height:** 56px
- **Button Height:** 48px
- **Primary Button:** `--primary-main` background

### **3.2 Registration Page**

**Additional Fields:**
- First Name / Last Name
- Position Selection (Dropdown)
- Warehouse Selection (Dropdown)
- Phone Number
- Terms & Conditions Checkbox

### **3.3 Forgot Password Page**

**Flow:**
1. Email Input → Send OTP
2. OTP Input (6 digits) → Verify
3. New Password → Confirm → Success

**OTP Input Design:**
```
┌───┐ ┌───┐ ┌───┐ ┌───┐ ┌───┐ ┌───┐
│ 1 │ │ 2 │ │ 3 │ │ 4 │ │ 5 │ │ 6 │
└───┘ └───┘ └───┘ └───┘ └───┘ └───┘
```
- **Box Size:** 48x48px
- **Font Size:** 24px
- **Border:** `2px solid --grey-300`
- **Focus Border:** `2px solid --primary-main`

---

## **4. 📊 DASHBOARD И ANALYTICS**

### **4.1 Main Dashboard Layout**

**Grid Structure (12 columns):**
```
┌─────────────────────────────────────────────────────────────┐
│                    Page Header                              │
│  Dashboard Overview              Last Updated: 10:30 AM     │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐           │
│ │  KPI 1  │ │  KPI 2  │ │  KPI 3  │ │  KPI 4  │  (4x3)    │
│ └─────────┘ └─────────┘ └─────────┘ └─────────┘           │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────┐ ┌─────────────────────────────┐ │
│ │                         │ │                             │ │
│ │     Order Trends        │ │    Inventory Status         │ │
│ │       (Chart)           │ │       (Donut Chart)         │ │ (6x6)
│ │                         │ │                             │ │
│ └─────────────────────────┘ └─────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │                Recent Activities                        │ │ (12x4)
│ │  [Activity Feed with Real-time Updates]                │ │
│ └─────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

### **4.2 KPI Cards**

**Design Specifications:**
- **Card Height:** 120px
- **Padding:** 20px
- **Background:** `--bg-paper`
- **Border Radius:** 8px
- **Shadow:** `--shadow-1`

**KPI Card Layout:**
```
┌─────────────────────────────┐
│ 📦                    ↗ 12% │
│                             │
│ 1,234                       │
│ Active Orders               │
└─────────────────────────────┘
```

**Components:**
- Icon (24x24px, colored)
- Trend Indicator (Arrow + Percentage)
- Main Value (2rem, bold)
- Label (0.875rem, secondary text)

### **4.3 Real-time Chart Components**

**Order Trends Chart:**
- **Type:** Line Chart
- **Library:** Chart.js or Recharts
- **Height:** 300px
- **Colors:** Primary palette
- **Features:** 
  - Real-time updates via SSE
  - Tooltip with details
  - Zoom/Pan functionality

**Inventory Status Donut:**
- **Type:** Donut Chart
- **Height:** 300px
- **Legend:** Right side
- **Colors:** Status colors (success, warning, error)

---

## **5. 📦 INVENTORY MANAGEMENT**

### **5.1 Product List Page**

**Layout Structure:**
```
┌─────────────────────────────────────────────────────────────┐
│ Page Header: Products                        [+ Add Product]│
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Filters & Search                                        │ │
│ │ [Search] [Category ▼] [Warehouse ▼] [Status ▼] [Reset] │ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │                  Data Table                             │ │
│ │ ┌──────────────────────────────────────────────────────┐│ │
│ │ │SKU      │Name       │Category │Stock │Location │Acts ││ │
│ │ ├──────────────────────────────────────────────────────┤│ │
│ │ │SKU-001  │Product A  │Category1│ 150  │A-1-01   │⚙️  ││ │
│ │ │SKU-002  │Product B  │Category2│  89  │A-1-02   │⚙️  ││ │
│ │ │SKU-003  │Product C  │Category1│   5  │B-2-01   │⚙️  ││ │
│ │ └──────────────────────────────────────────────────────┘│ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│                    [< Previous] [1][2][3][4] [Next >]      │
└─────────────────────────────────────────────────────────────┘
```

**Filter Panel:**
- **Height:** 80px
- **Background:** `--bg-paper`
- **Padding:** 16px
- **Border Bottom:** `1px solid --grey-200`

**Data Table Features:**
- **Row Height:** 56px
- **Striped Rows:** Alternating `--bg-paper` and `--grey-50`
- **Hover Effect:** `--primary-50` background
- **Sortable Headers:** Arrow indicators
- **Action Column:** 
  - View (👁️)
  - Edit (✏️)
  - Delete (🗑️)

### **5.2 Product Detail/Form**

**Layout (Modal or Side Panel):**
```
┌─────────────────────────────────────────────────────────────┐
│ Product Details                                      [✕]    │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │                   Product Info                          │ │
│ │                                                         │ │
│ │ SKU: ┌──────────────────┐  Name: ┌─────────────────────┐│ │
│ │      │ SKU-001          │        │ Product Name        ││ │
│ │      └──────────────────┘        └─────────────────────┘│ │
│ │                                                         │ │
│ │ Category: ┌──────────────┐  Unit: ┌─────────────────────┐│ │
│ │           │ Electronics ▼│        │ PCS                ││ │
│ │           └──────────────┘        └─────────────────────┘│ │
│ │                                                         │ │
│ │ Description:                                            │ │
│ │ ┌─────────────────────────────────────────────────────┐ │ │
│ │ │ Product description here...                         │ │ │
│ │ │                                                     │ │ │
│ │ └─────────────────────────────────────────────────────┘ │ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│                              [Cancel] [Save Product]       │
└─────────────────────────────────────────────────────────────┘
```

**Form Specifications:**
- **Input Height:** 56px
- **Label Position:** Above input
- **Required Field:** Red asterisk (*)
- **Validation:** Real-time validation with error messages

### **5.3 Stock Overview Dashboard**

**Card Grid Layout:**
```
┌─────────────────────────────────────────────────────────────┐
│ Stock Overview                          [🔄 Refresh]        │
├─────────────────────────────────────────────────────────────┤
│ ┌───────────────┐ ┌───────────────┐ ┌───────────────┐     │
│ │ 📦 Total SKUs │ │ ⚠️  Low Stock │ │ 🚫 Out of Stock│     │
│ │               │ │               │ │                │     │ (4x4x4)
│ │    1,234      │ │      23       │ │       5        │     │
│ └───────────────┘ └───────────────┘ └───────────────┘     │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │              Stock Level Trends                         │ │ (12x6)
│ │                 [Line Chart]                            │ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │              Low Stock Alerts                           │ │ (12x4)
│ │ [Table with products below minimum threshold]           │ │
│ └─────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

---

## **6. 📥 INBOUND OPERATIONS**

### **6.1 ASN (Advanced Shipping Notice) List**

**Layout Structure:**
```
┌─────────────────────────────────────────────────────────────┐
│ Inbound Operations > ASN List               [+ Create ASN]  │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Status Filters                                          │ │
│ │ [🟡 Pending] [🔵 In Transit] [🟢 Arrived] [All]        │ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │                     ASN Table                           │ │
│ │ ┌─────────────────────────────────────────────────────┐ │ │
│ │ │ASN #    │Supplier │Expected │Status    │Items │Acts│ │ │
│ │ ├─────────────────────────────────────────────────────┤ │ │
│ │ │ASN-001  │ABC Corp │Jan 15   │🟡 Pending│  25  │👁️ │ │ │
│ │ │ASN-002  │XYZ Ltd  │Jan 16   │🔵 Transit│  12  │👁️ │ │ │
│ │ │ASN-003  │DEF Inc  │Jan 17   │🟢 Arrived│   8  │✅ │ │ │
│ │ └─────────────────────────────────────────────────────┘ │ │
│ └─────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

**Status Badge Design:**
- **Height:** 24px
- **Padding:** 4px 8px
- **Border Radius:** 12px
- **Font Size:** 0.75rem
- **Colors:**
  - Pending: `--warning-main` background, white text
  - In Transit: `--info-main` background, white text
  - Arrived: `--success-main` background, white text

### **6.2 ASN Detail Page**

**Three-Column Layout:**
```
┌─────────────────────────────────────────────────────────────┐
│ ASN-001 Details                             [📝 Edit]       │
├─────────────────────────────────────────────────────────────┤
│ ┌──────────────┐ ┌──────────────┐ ┌─────────────────────┐  │
│ │   ASN Info   │ │  Line Items  │ │   Receiving Log     │  │ (4x4x4)
│ │              │ │              │ │                     │  │
│ │ ASN#: 001    │ │ SKU-001  20  │ │ Jan 15 10:30       │  │
│ │ Supplier:    │ │ SKU-002  15  │ │ Started receiving   │  │
│ │ ABC Corp     │ │ SKU-003  10  │ │                     │  │
│ │              │ │              │ │ Jan 15 11:45       │  │
│ │ Expected:    │ │ Total: 45    │ │ Completed receiving │  │
│ │ Jan 15       │ │              │ │                     │  │
│ │              │ │ [Receive All]│ │ Discrepancies: 0   │  │
│ └──────────────┘ └──────────────┘ └─────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
```

---

## **7. 📤 OUTBOUND OPERATIONS**

### **7.1 Order List Page**

**Kanban-Style Status Board:**
```
┌─────────────────────────────────────────────────────────────┐
│ Orders Management                         [+ Create Order]  │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌────────┐│
│ │📝 New   │ │🎯 Alloc │ │📦 Pick  │ │📋 Pack  │ │🚚 Ship ││
│ │         │ │         │ │         │ │         │ │        ││
│ │ ┌─────┐ │ │ ┌─────┐ │ │ ┌─────┐ │ │ ┌─────┐ │ │ ┌────┐ ││
│ │ │ORD1 │ │ │ │ORD5 │ │ │ │ORD8 │ │ │ │ORD12│ │ ││ORD15││
│ │ └─────┘ │ │ └─────┘ │ │ └─────┘ │ │ └─────┘ │ │ └────┘ ││
│ │ ┌─────┐ │ │ ┌─────┐ │ │ ┌─────┐ │ │         │ │        ││
│ │ │ORD2 │ │ │ │ORD6 │ │ │ │ORD9 │ │ │         │ │        ││
│ │ └─────┘ │ │ └─────┘ │ │ └─────┘ │ │         │ │        ││
│ │         │ │         │ │         │ │         │ │        ││
│ └─────────┘ └─────────┘ └─────────┘ └─────────┘ └────────┘│
└─────────────────────────────────────────────────────────────┘
```

**Order Card Design:**
- **Width:** 200px
- **Height:** 120px
- **Padding:** 12px
- **Border Radius:** 8px
- **Background:** `--bg-paper`
- **Border:** `1px solid --grey-200`
- **Shadow:** `--shadow-1`

**Order Card Content:**
```
┌─────────────────────┐
│ ORD-2024-001  [🔴]  │
│                     │
│ Customer: ACME Corp │
│ Items: 5            │
│ Priority: High      │
│                     │
│ Due: Jan 15, 14:00  │
└─────────────────────┘
```

### **7.2 Picking Interface (Mobile-First)**

**Mobile Picking Screen:**
```
┌─────────────────────────────────────────┐
│ 🔙 Picking Task #PT-001          📱📶  │
├─────────────────────────────────────────┤
│              Progress                   │
│ ■■■■■■■■■□ 9/10 items                  │
├─────────────────────────────────────────┤
│ ┌─────────────────────────────────────┐ │
│ │          Current Item               │ │
│ │                                     │ │
│ │  📦 SKU-001234                      │ │
│ │     Product Name                    │ │
│ │                                     │ │
│ │  📍 Location: A-1-05                │ │
│ │  📋 Quantity: 5 PCS                 │ │
│ │                                     │ │
│ │  [📷 Scan Barcode]                  │ │
│ │                                     │ │
│ │  Picked: [___] / 5                  │ │
│ │                                     │ │
│ │  [✅ Confirm Pick] [⏭️ Skip]        │ │
│ └─────────────────────────────────────┘ │
├─────────────────────────────────────────┤
│ 🎤 Voice Commands Active               │
│ Say "Confirm" or "Skip"                │
└─────────────────────────────────────────┘
```

**Design Elements:**
- **Large Touch Targets:** Minimum 44px
- **High Contrast:** Dark text on light backgrounds
- **Progress Indicator:** Visual progress bar
- **Voice Commands:** Hands-free operation
- **Scanner Integration:** Camera barcode scanning

---

## **8. 🎓 TRAINING MODULE**

### **8.1 Article Feed (News Feed Style)**

**Instagram/LinkedIn-Style Layout:**
```
┌─────────────────────────────────────────────────────────────┐
│ Training Center                          [📝 Write Article] │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ 👤 John Smith • 2 hours ago                      [⋯]  │ │
│ │                                                         │ │
│ │ 📝 Safety Procedures Update                             │ │
│ │                                                         │ │
│ │ Lorem ipsum dolor sit amet, consectetur adipiscing elit │ │
│ │ sed do eiusmod tempor incididunt ut labore et dolore... │ │
│ │                                                         │ │
│ │ 📷 [Image/Video Thumbnail]                              │ │
│ │                                                         │ │
│ │ 👍 24 likes  💬 5 comments  👁️ 156 views               │ │
│ │                                                         │ │
│ │ [👍 Like] [💬 Comment] [🔗 Share]                      │ │
│ └─────────────────────────────────────────────────────────┘ │
│                                                             │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ 👤 Sarah Johnson • 1 day ago                     [⋯]  │ │
│ │                                                         │ │
│ │ 📋 New Picking Procedures                               │ │
│ │ ...                                                     │ │
│ └─────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

### **8.2 Personal Roadmap**

**Gamified Progress Interface:**
```
┌─────────────────────────────────────────────────────────────┐
│ My Learning Roadmap                       🎯 Level 3 (75%)  │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │                Progress Overview                         │ │
│ │ ████████████████████████████████░░░░░░░ 75%            │ │
│ │                                                         │ │
│ │ 🏆 Badges Earned: 5/8                                   │ │
│ │ [🔰][⭐][🎯][📈][💡][  ][  ][  ]                      │ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│ ┌───────────────┐ ┌───────────────┐ ┌─────────────────────┐ │
│ │ ✅ Completed  │ │ 🔄 In Progress│ │  📅 Upcoming        │ │
│ │               │ │               │ │                     │ │
│ │ • Warehouse   │ │ • Picking     │ │  • Advanced Ops     │ │
│ │   Safety      │ │   Procedures  │ │  • Team Leadership  │ │
│ │ • Basic Ops   │ │ ■■■■░ 80%     │ │  • Quality Control  │ │
│ │ • Inventory   │ │               │ │                     │ │
│ │   Management  │ │ [Continue]    │ │  [Coming Soon]      │ │
│ └───────────────┘ └───────────────┘ └─────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

---

## **9. 🌊 WAVE PLANNING**

### **9.1 Wave Planning Dashboard**

**Workflow Visualization:**
```
┌─────────────────────────────────────────────────────────────┐
│ Wave Planning                         [⚡ Create New Wave]  │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │                  Active Waves                           │ │
│ │                                                         │ │
│ │ ┌─────────────┐ ┌─────────────┐ ┌─────────────────────┐ │ │
│ │ │ 🌊 WAVE-001 │ │ 🌊 WAVE-002 │ │ 🌊 WAVE-003         │ │ │
│ │ │             │ │             │ │                     │ │ │
│ │ │ 📦 25 Orders│ │ 📦 18 Orders│ │ 📦 32 Orders        │ │ │
│ │ │ ⏱️ 2:30 ETA │ │ ⏱️ 1:45 ETA │ │ ⏱️ 3:15 ETA        │ │ │
│ │ │ 👥 3 Pickers│ │ 👥 2 Pickers│ │ 👥 4 Pickers       │ │ │
│ │ │             │ │             │ │                     │ │ │
│ │ │ [■■■■░] 80% │ │ [■■■░░] 60% │ │ [■░░░░] 20%        │ │ │
│ │ │             │ │             │ │                     │ │ │
│ │ │ [View Wave] │ │ [View Wave] │ │ [View Wave]         │ │ │
│ │ └─────────────┘ └─────────────┘ └─────────────────────┘ │ │
│ └─────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │              Wave Optimization                          │ │
│ │                                                         │ │
│ │ Optimization Strategy: [FIFO ▼]                         │ │
│ │ Priority Rules: [Customer Priority ▼]                   │ │
│ │ Route Optimization: [✅] Enabled                        │ │
│ │                                                         │ │
│ │ Estimated Efficiency Gain: +15%                        │ │
│ │ Estimated Time Savings: 45 minutes                     │ │
│ │                                                         │ │
│ │                          [🚀 Optimize Waves]           │ │
│ └─────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

---

## **10. 🚛 CROSS-DOCKING**

### **10.1 Dock Management Interface**

**Real-time Dock Status:**
```
┌─────────────────────────────────────────────────────────────┐
│ Cross-Docking Operations              🔄 Last Update: 10:35 │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────────────────────────────────────────────┐ │
│ │                  Dock Bay Status                        │ │
│ │                                                         │ │
│ │  INBOUND DOCKS              OUTBOUND DOCKS              │ │
│ │                                                         │ │
│ │ ┌─────────┐ ┌─────────┐    ┌─────────┐ ┌─────────────┐  │ │
│ │ │🚛 BAY 1 │ │🚛 BAY 2 │    │🚚 BAY 5 │ │  🚚 BAY 6   │  │ │
│ │ │ OCCUPIED│ │  EMPTY  │    │LOADING  │ │   OCCUPIED  │  │ │
│ │ │         │ │         │    │         │ │             │  │ │
│ │ │ABC Corp │ │Available│    │XYZ Ship │ │  DEF Cargo  │  │ │
│ │ │ETA:11:00│ │         │    │■■■░ 75% │ │  ■■■■■ 100% │  │ │
│ │ │         │ │ [Book]  │    │         │ │             │  │ │
│ │ └─────────┘ └─────────┘    └─────────┘ └─────────────┘  │ │
│ │                                                         │ │
│ │ ┌─────────┐ ┌─────────┐    ┌─────────┐ ┌─────────────┐  │ │
│ │ │ 🚛 BAY 3│ │🚛 BAY 4 │    │🚚 BAY 7 │ │  🚚 BAY 8   │  │ │
│ │ │UNLOADING│ │SCHEDULED│    │PREPARING│ │   AVAILABLE │  │ │
│ │ └─────────┘ └─────────┘    └─────────┘ └─────────────┘  │ │
│ └─────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

---

## **11. 📱 MOBILE COMPONENTS**

### **11.1 Mobile Navigation (Bottom Tabs)**

```
┌─────────────────────────────────────────┐
│                Content                  │
│                                         │
│                                         │
│                                         │
│                                         │
│                                         │
├─────────────────────────────────────────┤
│ 📊     📦     📋     🌊     👤         │
│ Dash  Stock  Tasks  Waves  Profile     │
└─────────────────────────────────────────┘
```

**Specifications:**
- **Tab Bar Height:** 64px
- **Icon Size:** 24x24px
- **Active Color:** `--primary-main`
- **Inactive Color:** `--grey-500`
- **Background:** `--bg-paper`
- **Border Top:** `1px solid --grey-200`

### **11.2 Mobile Scanner Component**

**Camera Overlay:**
```
┌─────────────────────────────────────────┐
│ 🔙  Scan Barcode              💡 🔄    │
├─────────────────────────────────────────┤
│                                         │
│                                         │
│        ┌─────────────────┐              │
│        │                 │              │
│        │                 │              │
│        │      📷         │              │
│        │                 │              │
│        │                 │              │
│        └─────────────────┘              │
│                                         │
│           Scan product barcode          │
│                                         │
├─────────────────────────────────────────┤
│          [Manual Entry]                 │
└─────────────────────────────────────────┘
```

---

## **12. 🔔 NOTIFICATIONS SYSTEM**

### **12.1 Notification Bell (Header)**

**Notification Badge:**
```
🔔 (8)
```
- **Badge Position:** Top-right of bell icon
- **Badge Color:** `--error-main`
- **Badge Size:** 18px diameter
- **Text Color:** White
- **Font Size:** 10px

### **12.2 Notification Dropdown**

**Dropdown Panel:**
```
┌─────────────────────────────────────────┐
│ Notifications                    [⚙️]   │ 
├─────────────────────────────────────────┤
│ ┌─────────────────────────────────────┐ │
│ │ 🔴 High Priority                    │ │
│ │ Low stock alert: SKU-001            │ │
│ │ 2 minutes ago                       │ │
│ └─────────────────────────────────────┘ │
│ ┌─────────────────────────────────────┐ │
│ │ 🟡 Medium Priority                  │ │
│ │ Order ORD-123 ready for shipping    │ │
│ │ 5 minutes ago                       │ │
│ └─────────────────────────────────────┘ │
│ ┌─────────────────────────────────────┐ │
│ │ 🔵 Info                             │ │
│ │ Wave WAVE-001 completed             │ │
│ │ 10 minutes ago                      │ │
│ └─────────────────────────────────────┘ │
├─────────────────────────────────────────┤
│            [Mark All Read]              │
│            [View All]                   │
└─────────────────────────────────────────┘
```

**Real-time Toast Notifications:**
```
┌─────────────────────────────────────────┐
│ ✅ Order ORD-456 successfully created    │
│                                    [✕] │
└─────────────────────────────────────────┘
```
- **Position:** Top-right corner
- **Duration:** 5 seconds
- **Animation:** Slide in from right
- **Types:** Success (green), Error (red), Warning (yellow), Info (blue)

---

## **🎨 RESPONSIVE DESIGN BREAKPOINTS**

### **Mobile (320px - 767px)**
- Single column layout
- Bottom navigation tabs
- Collapsible cards
- Touch-optimized controls
- Swipe gestures

### **Tablet (768px - 1023px)** 
- Two column layout
- Side navigation drawer
- Expandable data tables
- Optimized for touch

### **Desktop (1024px+)**
- Full multi-column layout
- Persistent side navigation  
- Data tables with all columns
- Hover states and tooltips
- Keyboard shortcuts

---

## **🎯 ACCESSIBILITY STANDARDS**

### **WCAG 2.1 AA Compliance**
- **Color Contrast:** Minimum 4.5:1 ratio
- **Keyboard Navigation:** Full keyboard support
- **Screen Reader:** ARIA labels and descriptions
- **Focus Management:** Visible focus indicators
- **Alt Text:** Images and icons
- **Form Labels:** Associated with inputs

### **Keyboard Shortcuts**
- `Ctrl+/` - Search
- `Ctrl+N` - New item
- `Ctrl+S` - Save
- `Escape` - Close modal/drawer
- `Tab/Shift+Tab` - Navigate
- `Enter/Space` - Activate

---

## **🚀 PERFORMANCE TARGETS**

### **Core Web Vitals**
- **First Contentful Paint:** < 1.5s
- **Largest Contentful Paint:** < 2.5s
- **Cumulative Layout Shift:** < 0.1
- **First Input Delay:** < 100ms

### **Bundle Size Targets**
- **Initial Bundle:** < 200KB gzipped
- **Vendor Bundle:** < 500KB gzipped
- **Lazy Loaded Routes:** < 100KB each
- **Images:** WebP format, responsive sizes

### **Runtime Performance**
- **60fps** smooth animations
- **< 100ms** interaction response time
- **< 3s** data loading time
- **Infinite scroll** for large datasets

---

*Этот дизайн-гайд служит основой для создания современного, отзывчивого и доступного интерфейса WMS системы в стиле Berry MUI.* 