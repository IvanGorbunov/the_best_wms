# 🚀 **FIGMA IMPLEMENTATION GUIDE**
## *Пошаговое руководство по созданию WMS Design System в Figma*

---

## **📋 ПОДГОТОВИТЕЛЬНЫЙ ЭТАП**

### **1. Установка необходимых плагинов:**

```
Обязательные плагины:
1. Material Design Icons - для иконок
2. Auto Layout - для responsive компонентов
3. Component Properties - для вариантов
4. Content Reel - для placeholder контента

Рекомендуемые плагины:  
5. Stark - для проверки accessibility
6. Design System Organizer - для организации компонентов
7. Figma Tokens - для design tokens
8. Color Palette - для работы с цветами
9. Figma to React - для экспорта компонентов
10. Grids & Guides - для точного позиционирования
```

### **2. Настройка рабочего пространства:**

```
File Settings:
- Font: Inter (загрузить если нет)
- Canvas Background: #f8f9fa
- Grid: 8px base grid
- Rulers: показать

Team Library:
- Создать team для WMS проекта
- Настроить права доступа
```

---

## **🎨 ПОШАГОВОЕ СОЗДАНИЕ DESIGN SYSTEM**

### **ШАГ 1: Создание Color Styles**

```figma
1. Открыть Assets Panel (Alt + 2)
2. Создать Color Styles:

Primary Colors:
- Primary/Main: #1976d2
- Primary/Light: #42a5f5  
- Primary/Dark: #1565c0
- Primary/50: #e3f2fd
- Primary/100: #bbdefb

Secondary Colors:
- Secondary/Main: #f57c00
- Secondary/Light: #ffb74d
- Secondary/Dark: #ef6c00

Status Colors:
- Success/Main: #388e3c
- Success/Light: #66bb6a
- Warning/Main: #f9a825
- Warning/Light: #ffcc02
- Error/Main: #d32f2f
- Error/Light: #ef5350
- Info/Main: #0288d1

Neutral Colors:
- Grey/50: #fafafa
- Grey/100: #f5f5f5
- Grey/200: #eeeeee
- Grey/300: #e0e0e0
- Grey/400: #bdbdbd
- Grey/500: #9e9e9e
- Grey/600: #757575
- Grey/700: #616161
- Grey/800: #424242
- Grey/900: #212121

3. Organize в группы: Primary, Secondary, Status, Neutral
```

### **ШАГ 2: Создание Text Styles**

```figma
Text Styles (Create via Type Panel):

Desktop Headers:
- H1/Desktop: Inter Bold 32px/40px
- H2/Desktop: Inter Bold 24px/32px
- H3/Desktop: Inter Bold 20px/28px
- H4/Desktop: Inter Medium 18px/24px
- H5/Desktop: Inter Medium 16px/24px
- H6/Desktop: Inter Medium 14px/20px

Body Text:
- Body1/Desktop: Inter Regular 16px/24px
- Body2/Desktop: Inter Regular 14px/20px
- Caption/Desktop: Inter Regular 12px/16px

Button Text:
- Button/Large: Inter Medium 16px/24px
- Button/Medium: Inter Medium 14px/20px
- Button/Small: Inter Medium 12px/16px

Mobile Variants:
- Создать аналогичные стили с суффиксом /Mobile
- Размеры уменьшить на 2-4px
```

### **ШАГ 3: Создание Effect Styles**

```figma
Shadow Effects:

1. Shadow/1:
   - Type: Drop Shadow
   - X: 0, Y: 1, Blur: 3, Spread: 0
   - Color: #000000, Opacity: 12%

2. Shadow/2:
   - X: 0, Y: 3, Blur: 6, Spread: 0
   - Color: #000000, Opacity: 16%

3. Shadow/3:
   - X: 0, Y: 10, Blur: 20, Spread: 0
   - Color: #000000, Opacity: 19%

4. Shadow/4:
   - X: 0, Y: 14, Blur: 28, Spread: 0
   - Color: #000000, Opacity: 25%

5. Shadow/5:
   - X: 0, Y: 19, Blur: 38, Spread: 0
   - Color: #000000, Opacity: 30%
```

---

## **🔧 СОЗДАНИЕ КОМПОНЕНТОВ**

### **ШАГ 4: Button Components**

```figma
Primary Button:
1. Create Rectangle (140x48px)
2. Corner Radius: 8px
3. Fill: Primary/Main color style
4. Add Text: "Button"
5. Text Style: Button/Medium
6. Text Color: #ffffff

Auto Layout:
- Direction: Horizontal
- Spacing: 8px
- Padding: 16px horizontal, 12px vertical
- Align: Center

Component Properties:
- Size: Boolean (Large/Medium/Small)
- State: Variant (Default/Hover/Pressed/Disabled)
- Icon: Instance Swap (None/Icon)
- Label: Text Property

Variants Creation:
1. Select component
2. Create Component Set
3. Add properties via right panel
4. Duplicate for each variant
5. Modify styles per variant

Secondary Button:
- Same structure
- Fill: Transparent
- Stroke: 1px Primary/Main
- Text Color: Primary/Main
```

### **ШАГ 5: Input Components**

```figma
Text Input:
1. Create Rectangle (250x56px)
2. Corner Radius: 8px
3. Fill: #ffffff
4. Stroke: 1px Grey/300

Auto Layout:
- Direction: Horizontal
- Spacing: 12px
- Padding: 16px
- Align: Center

Elements:
- Placeholder Text: Body1/Desktop
- Label (above): Body2/Desktop

States Variants:
- Default: Border Grey/300
- Focus: Border Primary/Main + Shadow
- Error: Border Error/Main + Shadow
- Disabled: Fill Grey/100

Properties:
- Size: Small/Medium/Large
- State: Default/Focus/Error/Disabled
- Type: Text/Password/Email
- Label: Text Property
- Placeholder: Text Property
```

### **ШАГ 6: Card Components**

```figma
Base Card:
1. Create Rectangle
2. Corner Radius: 8px
3. Fill: #ffffff
4. Shadow: Shadow/1 effect style

Auto Layout:
- Direction: Vertical
- Spacing: 16px
- Padding: 24px
- Align: Stretch

Properties:
- Elevation: 1/2/3/4 (change shadow)
- Padding: None/Small/Medium/Large

KPI Card (280x120px):
1. Base Card structure
2. Add elements:
   - Icon (24x24px) - top left
   - Trend indicator - top right
   - Value (H2 style) - center
   - Label (Body2 style) - bottom

Layout:
- Icon + Trend: Horizontal Auto Layout
- Value + Label: Vertical Auto Layout
- Main container: Vertical Auto Layout

Properties:
- Type: Standard/Compact
- Trend: Positive/Negative/Neutral
- Icon: Instance Swap
- Value: Text Property
- Label: Text Property
```

---

## **📱 MOBILE КОМПОНЕНТЫ**

### **ШАГ 7: Mobile Navigation**

```figma
Bottom Tab Navigation:
1. Frame: 375x64px
2. Fill: #ffffff
3. Border Top: 1px Grey/200

Tab Item:
1. Frame: 75x64px (375/5 tabs)
2. Auto Layout: Vertical, Spacing: 4px
3. Elements:
   - Icon: 24x24px (Material Icons)
   - Label: Caption/Desktop

States:
- Active: Icon & Text Primary/Main
- Inactive: Icon & Text Grey/500

Auto Layout Container:
- Direction: Horizontal
- Spacing: 0
- Align: Stretch
- Distribute: Space Between
```

### **ШАГ 8: Mobile Cards**

```figma
Mobile KPI Card (165x94px):
1. Base: Rectangle with Corner Radius 8px
2. Fill: #ffffff
3. Shadow: Shadow/1

Layout (Auto Layout Vertical):
- Icon + Value: Horizontal layout
- Label: Below, full width

Responsive behavior:
- Width: Fixed 165px
- Height: Hug Contents
- Content: Responsive to text length
```

---

## **🖥️ СОЗДАНИЕ ЭКРАНОВ**

### **ШАГ 9: Desktop Layout Template**

```figma
Master Layout (1440x900px):

1. Top Navigation (1440x64px):
   - Component: Navigation/TopBar
   - Constraints: Left & Right Fixed
   - Position: X:0, Y:0

2. Sidebar (280x836px):
   - Component: Navigation/Sidebar
   - Constraints: Left & Top Fixed, Bottom Stretch
   - Position: X:0, Y:64

3. Main Content (1160x836px):
   - Frame with Auto Layout
   - Constraints: All Stretch
   - Position: X:280, Y:64
   - Padding: 24px

Grid Setup:
- Layout Grid: 12 columns
- Gutter: 24px
- Margin: 24px
- Count: 12
- Type: Stretch
```

### **ШАГ 10: Конкретные экраны**

```figma
Login Page:
1. Frame: 1440x900px
2. Background: Linear Gradient
   - Type: Linear
   - Angle: 135°
   - Stop 1: Primary/50 (0%)
   - Stop 2: Grey/50 (100%)

3. Login Card (400x500px):
   - Position: Center (X:520, Y:200)
   - Component: Card/Base with Large padding
   - Content: Auto Layout Vertical, Spacing 16px

Dashboard Page:
1. Use Master Layout template
2. Main content grid:
   - Row 1: Page header (12 cols)
   - Row 2: KPI cards (3+3+3+3 cols)
   - Row 3: Charts (6+6 cols)
   - Row 4: Activity feed (12 cols)

Product List:
1. Master Layout
2. Content structure:
   - Header with button (space-between)
   - Filters panel (horizontal auto layout)
   - Data table (component)
   - Pagination (center-aligned)
```

---

## **📐 RESPONSIVE НАСТРОЙКИ**

### **ШАГ 11: Constraints & Auto Layout**

```figma
Desktop Constraints:
- Top Navigation: Left & Right (stretch)
- Sidebar: Left & Top (fixed), Bottom (stretch)
- Main Content: All sides (stretch)
- Cards in grid: Top & Left (fixed)

Auto Layout настройки:
- Page containers: Vertical, Hug Contents
- Card grids: Horizontal, Fixed spacing
- Form elements: Vertical, Space Between
- Button groups: Horizontal, Packed

Mobile Constraints:
- Header: Left & Right (stretch), Top (fixed)
- Content: All sides (stretch)
- Bottom tabs: Left & Right (stretch), Bottom (fixed)
```

### **ШАГ 12: Breakpoint Variants**

```figma
Component Variants for Screen Sizes:
1. Desktop (1440px+): Full components
2. Tablet (768-1439px): Condensed
3. Mobile (375-767px): Simplified

Method:
1. Create variant property "Breakpoint"
2. Adjust component sizes/content per variant
3. Hide/show elements as needed
4. Update typography styles for mobile
```

---

## **🎯 ОРГАНИЗАЦИЯ И ПУБЛИКАЦИЯ**

### **ШАГ 13: Структура файла**

```figma
Pages Organization:
📄 🎨 Design System
  ├── Color Styles showcase
  ├── Typography showcase
  ├── Effect styles showcase
  └── Spacing/Grid documentation

📄 📱 Components
  ├── Buttons section
  ├── Inputs section
  ├── Cards section
  ├── Navigation section
  ├── Data Display section
  └── Mobile Components section

📄 🖥️ Desktop Screens
  ├── Authentication flows
  ├── Dashboard views
  ├── Inventory management
  ├── Inbound operations
  ├── Outbound operations
  └── Admin interfaces

📄 📱 Mobile Screens
  ├── Mobile auth
  ├── Mobile dashboard
  ├── Mobile scanner
  ├── Mobile picking
  └── Mobile navigation
```

### **ШАГ 14: Documentation**

```figma
Component Documentation:
1. Description text layer for each component
2. Usage examples
3. Do's and Don'ts examples
4. Spacing annotations
5. Color annotations

Method:
- Use text layers with specific styling
- Create annotation components
- Use connector lines for spacing
- Include code snippets for developers
```

### **ШАГ 15: Team Library Publishing**

```figma
Publishing Process:
1. Select all components to publish
2. Write clear release notes
3. Organize by categories
4. Set proper naming conventions
5. Publish to team library

Library Organization:
├── 🎨 Foundations (Colors, Typography)
├── 🔧 Components (Buttons, Inputs, Cards)
├── 🧩 Patterns (Navigation, Layout)
├── 📱 Mobile (Mobile-specific components)
└── 🎭 Templates (Page templates)

Version Control:
- Use semantic versioning (1.0.0)
- Document breaking changes
- Maintain changelog
- Test before publishing
```

---

## **⚡ FIGMA SHORTCUTS И TIPS**

### **Полезные горячие клавиши:**

```
Создание компонентов:
- Ctrl/Cmd + Alt + K - Create Component
- Ctrl/Cmd + Alt + B - Create Component Set
- Alt + 2 - Toggle Assets Panel

Layout:
- Shift + A - Auto Layout
- Alt + Drag - Duplicate with spacing
- Ctrl/Cmd + G - Group
- Ctrl/Cmd + Shift + G - Ungroup

Навигация:
- Ctrl/Cmd + / - Quick Actions
- F - Fit to Screen
- Shift + 1 - Zoom to Fit
- Z - Zoom Tool

Редактирование:
- Tab - Select Next Object
- Enter - Edit Text/Component
- Ctrl/Cmd + D - Duplicate
- R - Rectangle Tool
- T - Text Tool
```

### **Best Practices:**

```
Component Naming:
- Use forward slashes: Button/Primary/Large
- Be descriptive but concise
- Use consistent naming patterns
- Group related components

Auto Layout Tips:
- Use for responsive components
- Set proper spacing values (8px increments)
- Use "Hug Contents" vs "Fixed" wisely
- Test resizing behavior

Performance:
- Optimize large files (>50MB)
- Use components instead of copying
- Minimize the use of complex effects
- Organize layers properly
```

---

## **🔗 ИНТЕГРАЦИЯ С РАЗРАБОТКОЙ**

### **Экспорт ассетов:**

```figma
For Developers:
1. Setup proper export settings
2. Use 1x, 2x, 3x for icons
3. Export SVGs for icons
4. PNG for complex graphics

Code Generation:
- Use Figma to Code plugins
- Export CSS for styling
- Generate React components
- Extract design tokens
```

### **Design Tokens:**

```json
// Экспорт в JSON формат
{
  "colors": {
    "primary": {
      "main": "#1976d2",
      "light": "#42a5f5",
      "dark": "#1565c0"
    }
  },
  "typography": {
    "h1": {
      "fontSize": "32px",
      "lineHeight": "40px",
      "fontWeight": "700"
    }
  },
  "spacing": {
    "base": "8px",
    "small": "16px",
    "medium": "24px",
    "large": "32px"
  }
}
```

---

## **✅ ФИНАЛЬНЫЙ ЧЕКЛИСТ**

```
Перед публикацией:
□ Все Color Styles созданы и организованы
□ Text Styles покрывают все случаи использования
□ Effect Styles настроены для теней
□ Компоненты имеют все необходимые варианты
□ Auto Layout настроен для responsive поведения
□ Constraints установлены правильно
□ Naming convention соблюдается
□ Documentation добавлена к компонентам
□ Экраны используют компоненты из библиотеки
□ Prototype flows настроены
□ Accessibility проверено
□ Performance оптимизирован
□ Team Library готов к публикации
```

---

*Следуя этому руководству, вы создадите полноценную design system для WMS проекта в Figma, готовую для использования командой дизайнеров и разработчиков.* 