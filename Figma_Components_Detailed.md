# 🎨 **FIGMA COMPONENTS DETAILED GUIDE**
## *Детальные спецификации компонентов для WMS Design System*

---

## **📋 КОМПОНЕНТЫ ДЛЯ СОЗДАНИЯ В FIGMA**

### **1. 🔲 BUTTONS COMPONENT SET**

#### **Primary Button**
- **Component Name:** `Button/Primary`
- **Frame Size:** 
  - Small: 120x36px
  - Medium: 140x48px  
  - Large: 160x56px
- **Variants (Properties):**
  - `Size`: Small, Medium, Large
  - `State`: Default, Hover, Pressed, Disabled
  - `Icon`: None, Left, Right, Only

**Styling:**
```css
Background: #1976d2
Text Color: #ffffff
Border Radius: 8px
Font: Inter Medium
Padding: 16px horizontal
Shadow: 0 2px 4px rgba(25, 118, 210, 0.2)

States:
- Default: background #1976d2
- Hover: background #1565c0, shadow 0 4px 8px rgba(25, 118, 210, 0.3)
- Pressed: background #0d47a1, shadow inset 0 2px 4px rgba(0,0,0,0.2)
- Disabled: background #bdbdbd, text color #ffffff
```

#### **Secondary Button**
- **Component Name:** `Button/Secondary`
- **Same sizes as Primary**
- **Variants:** Size, State, Icon

**Styling:**
```css
Background: transparent
Border: 1px solid #1976d2
Text Color: #1976d2
Border Radius: 8px

States:
- Default: border #1976d2, text #1976d2
- Hover: background #e3f2fd, border #1565c0
- Pressed: background #bbdefb, border #0d47a1
- Disabled: border #bdbdbd, text #bdbdbd
```

#### **Text Button**
- **Component Name:** `Button/Text`
- **Styling:**
```css
Background: transparent
Text Color: #1976d2
Padding: 8px 16px
Font: Inter Medium

States:
- Hover: background #e3f2fd
- Pressed: background #bbdefb
```

---

### **2. 📝 INPUT COMPONENTS**

#### **Text Input**
- **Component Name:** `Input/Text`
- **Frame Size:** 
  - Small: 200x48px
  - Medium: 250x56px
  - Large: 300x64px
- **Variants:**
  - `Size`: Small, Medium, Large
  - `State`: Default, Focus, Error, Disabled, Filled
  - `Type`: Text, Password, Email, Number

**Styling:**
```css
Background: #ffffff
Border: 1px solid #e0e0e0
Border Radius: 8px
Padding: 16px
Font: Inter Regular 16px
Placeholder Color: #9e9e9e

States:
- Default: border #e0e0e0
- Focus: border #1976d2, shadow 0 0 0 2px rgba(25, 118, 210, 0.2)
- Error: border #d32f2f, shadow 0 0 0 2px rgba(211, 47, 47, 0.2)
- Disabled: background #f5f5f5, border #e0e0e0, text #bdbdbd
- Filled: background #fafafa
```

#### **Select Dropdown**
- **Component Name:** `Input/Select`
- **Same sizes as Text Input**
- **Additional Elements:**
  - Dropdown arrow icon (24x24px)
  - Dropdown menu overlay

---

### **3. 🃏 CARD COMPONENTS**

#### **Base Card**
- **Component Name:** `Card/Base`
- **Variants:**
  - `Elevation`: 1, 2, 3, 4
  - `Padding`: None, Small (16px), Medium (24px), Large (32px)

**Styling:**
```css
Background: #ffffff
Border Radius: 8px
Elevation Shadows:
- 1: 0 1px 3px rgba(0,0,0,0.12)
- 2: 0 3px 6px rgba(0,0,0,0.16)  
- 3: 0 10px 20px rgba(0,0,0,0.19)
- 4: 0 14px 28px rgba(0,0,0,0.25)
```

#### **KPI Card**
- **Component Name:** `Card/KPI`
- **Frame Size:** 280x120px
- **Variants:**
  - `Type`: Standard, Compact
  - `Trend`: Positive, Negative, Neutral

**Layout Structure:**
```
┌─────────────────────────────────┐
│ 📦 Icon        ↗ +12% Trend    │
│                                 │
│ 1,234 Value                     │
│ Label Text                      │
└─────────────────────────────────┘
```

**Styling:**
```css
Background: #ffffff
Padding: 20px
Border Radius: 8px
Shadow: 0 1px 3px rgba(0,0,0,0.12)

Icon: 24x24px, colored
Value: Inter Bold 24px, #212121
Label: Inter Regular 14px, #757575
Trend: Inter Medium 12px
- Positive: #388e3c
- Negative: #d32f2f  
- Neutral: #757575
```

---

### **4. 📊 STATUS BADGE COMPONENTS**

#### **Status Badge**
- **Component Name:** `Badge/Status`
- **Frame Size:** Auto width x 24px
- **Variants:**
  - `Type`: Success, Warning, Error, Info, Neutral
  - `Size`: Small (20px), Medium (24px), Large (28px)

**Styling per Type:**
```css
Success:
- Background: #388e3c
- Text Color: #ffffff

Warning:  
- Background: #f9a825
- Text Color: #ffffff

Error:
- Background: #d32f2f
- Text Color: #ffffff

Info:
- Background: #0288d1  
- Text Color: #ffffff

Neutral:
- Background: #757575
- Text Color: #ffffff

Common:
- Border Radius: 50% of height
- Padding: 4px 8px
- Font: Inter Medium 12px
```

---

### **5. 🧭 NAVIGATION COMPONENTS**

#### **Sidebar Navigation**
- **Component Name:** `Navigation/Sidebar`
- **Frame Size:** 
  - Expanded: 280x800px
  - Collapsed: 72x800px
- **Variants:**
  - `State`: Expanded, Collapsed
  - `Theme`: Light, Dark

**Navigation Item:**
- **Component Name:** `Navigation/Item`
- **Frame Size:** 248x48px (in expanded mode)
- **Variants:**
  - `State`: Default, Hover, Active
  - `Type`: With Icon, Icon Only

**Styling:**
```css
Sidebar Background: #ffffff
Border: 1px solid #eeeeee

Navigation Item:
- Padding: 12px 16px
- Border Radius: 8px (when active)
- Font: Inter Medium 14px

States:
- Default: transparent background
- Hover: background #f5f5f5
- Active: background #e3f2fd, text #1976d2, icon #1976d2
```

#### **Top Navigation Bar**
- **Component Name:** `Navigation/TopBar`
- **Frame Size:** 1440x64px
- **Elements:**
  - Logo area (120px)
  - Breadcrumbs (flexible)
  - Search bar (300px)
  - Notification bell with badge
  - User avatar dropdown

#### **Bottom Tab Navigation (Mobile)**
- **Component Name:** `Navigation/BottomTabs`
- **Frame Size:** 375x64px
- **Elements:** 5 tabs with icons and labels

---

### **6. 📱 MOBILE COMPONENTS**

#### **Mobile KPI Card**
- **Component Name:** `Mobile/KPICard`
- **Frame Size:** 160x100px
- **Layout:** Compact version of desktop KPI card

#### **Scanner Overlay**
- **Component Name:** `Mobile/ScannerOverlay`
- **Frame Size:** 375x812px (full screen)
- **Elements:**
  - Camera background (black)
  - Scanner frame (280x200px, white border)
  - Instructions text
  - Control buttons

#### **Picking Task Card**
- **Component Name:** `Mobile/PickingTask`
- **Frame Size:** 343x200px (with 16px margin)
- **Elements:**
  - Product info
  - Location info  
  - Quantity controls
  - Action buttons

---

### **7. 📊 DATA COMPONENTS**

#### **Data Table**
- **Component Name:** `Table/DataTable`
- **Components:**
  - `Table/Header` - sortable column headers
  - `Table/Row` - data rows with hover states
  - `Table/Cell` - individual cells
  - `Table/Pagination` - pagination controls

**Table Row Styling:**
```css
Height: 56px
Border Bottom: 1px solid #eeeeee
Padding: 0 16px

States:
- Default: background #ffffff
- Hover: background #f5f5f5
- Selected: background #e3f2fd
```

#### **Chart Container**
- **Component Name:** `Chart/Container`
- **Frame Sizes:**
  - Small: 300x200px
  - Medium: 400x300px
  - Large: 500x400px

---

### **8. 🔔 NOTIFICATION COMPONENTS**

#### **Toast Notification**
- **Component Name:** `Notification/Toast`
- **Frame Size:** 400x56px
- **Variants:**
  - `Type`: Success, Error, Warning, Info
  - `Action`: None, Single Button, Double Button

**Styling:**
```css
Background: #ffffff
Border Radius: 8px
Shadow: 0 6px 20px rgba(0,0,0,0.15)
Padding: 16px

Border Left (4px):
- Success: #388e3c
- Error: #d32f2f
- Warning: #f9a825
- Info: #0288d1
```

#### **Notification Bell**
- **Component Name:** `Notification/Bell`
- **Frame Size:** 40x40px
- **Elements:**
  - Bell icon (24x24px)
  - Badge (18x18px) with number

---

## **🎨 СОЗДАНИЕ В FIGMA - ПОШАГОВЫЙ ПЛАН**

### **Шаг 1: Настройка файла**
1. Создать файл "WMS Design System - Berry MUI"
2. Создать 4 страницы:
   - 🎨 Design System
   - 📱 Components  
   - 🖥️ Desktop Screens
   - 📱 Mobile Screens

### **Шаг 2: Design System (страница 1)**
1. **Color Styles:**
   - Создать все цвета как Figma Color Styles
   - Группировать по: Primary, Secondary, Status, Neutral

2. **Text Styles:**
   - Создать все типографские стили
   - Группировать по: Headers, Body, Captions, Buttons

3. **Effect Styles:**
   - Создать 5 уровней теней
   - Настроить как Figma Effect Styles

### **Шаг 3: Components (страница 2)**
1. **Создать компоненты в порядке:**
   - Buttons (Primary, Secondary, Text)
   - Inputs (Text, Select)
   - Cards (Base, KPI)
   - Navigation (Sidebar, TopBar, BottomTabs)
   - Status Badges
   - Mobile Components

2. **Настроить Variants для каждого компонента**
3. **Настроить Auto Layout для адаптивности**

### **Шаг 4: Desktop Screens (страница 3)**
1. Создать артборды 1440x900px
2. Использовать компоненты из библиотеки
3. Настроить constraints для responsive поведения

### **Шаг 5: Mobile Screens (страница 4)**  
1. Создать артборды 375x812px
2. Адаптировать компоненты для мобильных устройств
3. Учесть touch targets (минимум 44px)

---

## **📐 FIGMA SPECIFIC SETTINGS**

### **Grid Settings:**
- **Desktop:** 12 columns, 24px gutter, 24px margin
- **Mobile:** 4 columns, 16px gutter, 16px margin

### **Auto Layout Settings:**
- **Spacing:** 8px (base unit)
- **Padding:** кратно 8px (8, 16, 24, 32px)
- **Border Radius:** 8px (стандарт)

### **Component Properties:**
- Использовать Boolean для переключения состояний
- Использовать Instance Swap для иконок
- Использовать Text для редактируемого контента

### **Constraints:**
- **Left & Right:** для растягивания по ширине
- **Top & Bottom:** для растягивания по высоте
- **Center:** для центрирования элементов

---

*Эта спецификация содержит все необходимые детали для создания полноценной design system в Figma для WMS проекта в стиле Berry MUI.* 