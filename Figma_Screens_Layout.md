# 🖥️ **FIGMA SCREENS LAYOUT GUIDE**
## *Детальные макеты экранов WMS для создания в Figma*

---

## **🖥️ DESKTOP SCREENS (1440x900px)**

### **1. 🔐 LOGIN PAGE**

**Frame:** `Desktop/Login` (1440x900px)

```
Background: Linear Gradient
  - Start: #e3f2fd (top-left)
  - End: #fafafa (bottom-right)
  - Angle: 135°

Center Card: 400x500px
  - Position: X: 520px, Y: 200px (centered)
  - Background: #ffffff
  - Border Radius: 8px
  - Shadow: 0 8px 24px rgba(0,0,0,0.12)
  - Padding: 32px

Elements Inside Card:
1. Logo: 
   - Size: 80x80px
   - Position: Top center, margin-bottom: 16px
   
2. Title: "Warehouse Management System"
   - Font: Inter Bold 20px
   - Color: #424242
   - Text Align: Center
   - Margin-bottom: 32px

3. Email Input:
   - Component: Input/Text (336x56px)
   - Label: "Email Address"
   - Placeholder: "Enter your email"
   - Margin-bottom: 16px

4. Password Input:
   - Component: Input/Text (336x56px)
   - Label: "Password"
   - Type: Password
   - Margin-bottom: 16px

5. Remember Checkbox:
   - Component: Checkbox + Text
   - Text: "Remember me"
   - Margin-bottom: 24px

6. Sign In Button:
   - Component: Button/Primary (336x48px)
   - Text: "SIGN IN"
   - Margin-bottom: 16px

7. Forgot Password Link:
   - Text: "Forgot password?"
   - Font: Inter Medium 14px
   - Color: #1976d2
   - Text Align: Center
```

### **2. 📊 MAIN DASHBOARD**

**Frame:** `Desktop/Dashboard` (1440x900px)

```
Layout Structure:
├── Top Navigation (1440x64px) - Y: 0
├── Sidebar (280x836px) - X: 0, Y: 64  
└── Main Content (1160x836px) - X: 280, Y: 64

Top Navigation Elements:
- Logo (120x32px) - X: 24, Y: 16
- Breadcrumbs "Dashboard" - X: 164, Y: 20
- Search Bar (300x40px) - X: 570, Y: 12
- Notification Bell (40x40px) - X: 1320, Y: 12
- User Avatar (40x40px) - X: 1376, Y: 12

Sidebar Menu Items:
1. Dashboard (Active) - Y: 16
2. Inventory - Y: 64
3. Inbound - Y: 112
4. Outbound - Y: 160
5. Wave Planning - Y: 208
6. Cross-Docking - Y: 256
7. Training - Y: 304
8. Analytics - Y: 352

Main Content Grid (1112px wide, 24px padding):
Row 1 - Page Header (1112x48px):
  - H2: "Dashboard Overview" - X: 0, Y: 0
  - Last Updated - X: 880, Y: 8

Row 2 - KPI Cards (1112x120px, Y: 72):
  Grid: 4 columns x 1 row, Gap: 24px
  - Card 1: Active Orders (262x120px)
  - Card 2: Low Stock Items (262x120px)  
  - Card 3: Active Staff (262x120px)
  - Card 4: On-time Delivery (262x120px)

Row 3 - Charts (1112x300px, Y: 216):
  Grid: 2 columns x 1 row, Gap: 24px
  - Chart 1: Order Trends (544x300px)
  - Chart 2: Inventory Status (544x300px)

Row 4 - Recent Activities (1112x200px, Y: 540):
  - Activity Feed Card (full width)
```

### **3. 📦 PRODUCT LIST PAGE**

**Frame:** `Desktop/ProductList` (1440x900px)

```
Layout: Same Top Nav + Sidebar structure

Main Content (1112px wide):
Row 1 - Page Header (1112x56px, Y: 24):
  - H2: "Products" - Left aligned
  - Button: "+ Add Product" - Right aligned

Row 2 - Filters Panel (1112x80px, Y: 104):
  Card with horizontal layout:
  - Search Input (300x56px) - X: 24, Y: 12
  - Category Select (150x56px) - X: 344, Y: 12
  - Warehouse Select (150x56px) - X: 514, Y: 12
  - Status Select (120x56px) - X: 684, Y: 12
  - Reset Button (80x40px) - X: 1008, Y: 20

Row 3 - Data Table (1112x500px, Y: 208):
  Table Structure:
  - Header Row (1112x56px)
  - 8 Data Rows (1112x56px each)
  
  Columns:
  1. SKU (120px)
  2. Name (300px) 
  3. Category (150px)
  4. Stock (100px)
  5. Location (120px)
  6. Actions (100px)

Row 4 - Pagination (1112x48px, Y: 732):
  - Centered pagination controls
```

### **4. 📤 ORDER KANBAN BOARD**

**Frame:** `Desktop/OrderKanban` (1440x900px)

```
Main Content (1112px wide):
Row 1 - Page Header (1112x56px):
  - H2: "Orders Management"
  - Button: "+ Create Order"

Row 2 - Kanban Board (1112x700px, Y: 80):
  5 Columns, Each: 200px wide, 24px gap

  Column 1 - New Orders (200x700px, X: 0):
    - Header: "📝 New (12)"
    - Cards: 200x100px each, 8px gap
    
  Column 2 - Allocated (200x700px, X: 224):
    - Header: "🎯 Allocated (8)"
    - Cards: 200x100px each
    
  Column 3 - Picking (200x700px, X: 448):
    - Header: "📦 Picking (15)"
    - Cards: 200x100px each
    
  Column 4 - Packing (200x700px, X: 672):
    - Header: "📋 Packing (6)"
    - Cards: 200x100px each
    
  Column 5 - Shipped (200x700px, X: 896):
    - Header: "🚚 Shipped (23)"
    - Cards: 200x100px each

Order Card Layout (200x100px):
  - Order Number (Top left)
  - Priority Badge (Top right)
  - Customer Name (Line 2)
  - Items Count (Line 3)
  - Due Date (Bottom)
```

---

## **📱 MOBILE SCREENS (375x812px)**

### **1. 📱 MOBILE LOGIN**

**Frame:** `Mobile/Login` (375x812px)

```
Background: Same gradient as desktop

Login Card (327x400px):
  - Position: X: 24, Y: 200 (centered vertically)
  - Background: #ffffff
  - Border Radius: 16px
  - Padding: 24px
  - Shadow: 0 8px 24px rgba(0,0,0,0.12)

Elements:
1. Logo (60x60px) - Center, Y: 24
2. App Name "WMS" - Center, Y: 100
3. Email Input (279x56px) - Y: 140
4. Password Input (279x56px) - Y: 212
5. Sign In Button (279x48px) - Y: 284
6. Forgot Password Link - Center, Y: 348
```

### **2. 📱 MOBILE DASHBOARD**

**Frame:** `Mobile/Dashboard` (375x812px)

```
Layout Structure:
├── Mobile Header (375x56px) - Y: 0
├── Content Area (375x692px) - Y: 56  
└── Bottom Tabs (375x64px) - Y: 748

Mobile Header:
  - Menu Icon (24x24px) - X: 16, Y: 16
  - Title "Dashboard" - X: 56, Y: 18
  - Notification Bell (24x24px) - X: 335, Y: 16

Content (Padding: 16px):
KPI Grid (343x200px, Y: 72):
  2x2 Grid, Gap: 12px
  - Each Card: 165.5x94px
  
  Cards:
  1. Orders (Top Left)
  2. Alerts (Top Right)  
  3. Staff (Bottom Left)
  4. Efficiency (Bottom Right)

Quick Actions Card (343x200px, Y: 292):
  - Header: "Quick Actions" 
  - Button 1: "📷 Scan Barcode" (315x48px)
  - Button 2: "📦 Check Stock" (315x48px)
  - Button 3: "📋 My Tasks" (315x48px)

Bottom Navigation (375x64px):
  5 Tabs, Each: 75px wide
  1. Dashboard (Active)
  2. Stock  
  3. Tasks
  4. Waves
  5. Profile
```

### **3. 📷 MOBILE SCANNER**

**Frame:** `Mobile/Scanner` (375x812px)

```
Background: #000000 (Full screen camera)

Scanner Header (375x80px, Y: 0):
  - Background: rgba(0,0,0,0.7)
  - Back Button (24x24px) - X: 16, Y: 28
  - Title "Scan Barcode" - X: 56, Y: 30
  - Flashlight Toggle (24x24px) - X: 335, Y: 28

Scanner Overlay (Center of screen):
  - Scanner Frame: 280x200px
  - Border: 2px solid #ffffff
  - Corner Markers: 4 corners, 20px lines
  - Position: X: 47.5, Y: 306 (centered)

Instructions (Below scanner):
  - Text: "Position barcode within the frame"
  - Color: #ffffff
  - Position: X: Center, Y: 540

Scanner Footer (375x120px, Y: 692):
  - Background: rgba(0,0,0,0.7)
  - Manual Entry Button (200x48px) - Center X, Y: 36
```

### **4. 📋 MOBILE PICKING TASK**

**Frame:** `Mobile/PickingTask` (375x812px)

```
Task Header (375x56px):
  - Back Button (24x24px) - X: 16, Y: 16
  - Title "Picking Task #PT-001" - X: 56, Y: 18
  - Progress "9/10" - X: 315, Y: 18

Progress Bar (375x40px, Y: 56):
  - Background: #f5f5f5
  - Progress: 90% (#1976d2)
  - Height: 4px, Y: 18

Current Item Card (343x160px, Y: 116):
  - Margin: 16px
  - Background: #ffffff
  - Border Radius: 8px
  - Padding: 20px
  
  Elements:
  - Header: "Current Item"
  - SKU: "📦 SKU-001234"
  - Product Name
  - Location: "📍 A-1-05"  
  - Quantity: "📋 5 PCS"

Scanner Button (343x56px, Y: 296):
  - Text: "📷 Scan Barcode"
  - Component: Button/Primary

Quantity Input (343x56px, Y: 372):
  - Label: "Picked Quantity"
  - Placeholder: "0 / 5"

Action Buttons (343x48px, Y: 448):
  2 Column Grid, Gap: 12px:
  - Confirm Pick (165.5x48px)
  - Skip (165.5x48px)

Voice Commands (375x60px, Y: 516):
  - Background: #e3f2fd  
  - Text: "🎤 Voice Commands Active"
  - Subtext: "Say 'Confirm' or 'Skip'"
```

---

## **🎨 FIGMA LAYOUT BEST PRACTICES**

### **Grid Systems:**
```
Desktop (1440px):
- Columns: 12
- Gutter: 24px
- Margin: 24px
- Max Width: 1392px

Mobile (375px):
- Columns: 4  
- Gutter: 16px
- Margin: 16px
- Max Width: 343px
```

### **Spacing System:**
```
Base Unit: 8px
Scale: 4, 8, 12, 16, 20, 24, 32, 40, 48, 64px

Component Spacing:
- Padding: 8px, 16px, 24px, 32px
- Margins: 8px, 16px, 24px, 32px
- Gaps: 8px, 12px, 16px, 24px
```

### **Typography Hierarchy:**
```
Desktop:
- H1: 32px (Page Titles)
- H2: 24px (Section Headers)  
- H3: 20px (Card Titles)
- H4: 18px (Subsections)
- Body1: 16px (Primary Text)
- Body2: 14px (Secondary Text)
- Caption: 12px (Meta Text)

Mobile:
- H1: 24px
- H2: 20px
- H3: 18px  
- H4: 16px
- Body1: 16px
- Body2: 14px
- Caption: 12px
```

### **Color Usage:**
```
Primary Actions: #1976d2
Secondary Actions: #f57c00
Success States: #388e3c
Warning States: #f9a825
Error States: #d32f2f
Info States: #0288d1

Backgrounds:
- Page: #fafafa
- Cards: #ffffff
- Inputs: #ffffff
- Disabled: #f5f5f5

Text:
- Primary: #212121
- Secondary: #757575  
- Disabled: #bdbdbd
- On Primary: #ffffff
```

---

## **📐 CONSTRAINTS И AUTO LAYOUT**

### **Desktop Constraints:**
```
Top Navigation:
- Left & Right: Stretch to fill
- Top: Fixed to top

Sidebar:
- Left & Top: Fixed
- Bottom: Stretch to fill

Main Content:
- Left & Right: Stretch to fill
- Top & Bottom: Stretch to fill
```

### **Mobile Constraints:**
```
Header:
- Left & Right: Stretch to fill
- Top: Fixed to top

Content:
- Left & Right: Stretch to fill  
- Top & Bottom: Stretch to fill

Bottom Tabs:
- Left & Right: Stretch to fill
- Bottom: Fixed to bottom
```

### **Component Auto Layout:**
```
Cards:
- Direction: Vertical
- Spacing: 16px
- Padding: 24px
- Align: Stretch

Buttons:
- Direction: Horizontal
- Spacing: 8px
- Padding: 16px horizontal
- Align: Center

Form Layouts:
- Direction: Vertical
- Spacing: 16px
- Align: Stretch
```

---

*Эти детальные спецификации позволят точно воссоздать все экраны WMS системы в Figma с соблюдением принципов Berry MUI design system.* 