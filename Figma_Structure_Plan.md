# 🎨 **FIGMA STRUCTURE PLAN**
## *Детальный план для создания WMS Design System в Figma*

---

## 📋 **СТРУКТУРА ФАЙЛА FIGMA**

### **Pages (Страницы):**
1. 🎨 **Design System** - Цвета, типографика, компоненты
2. 📱 **Components** - Библиотека переиспользуемых компонентов  
3. 🖥️ **Desktop Screens** - Десктопные макеты
4. 📱 **Mobile Screens** - Мобильные макеты
5. 🔄 **Prototypes** - Интерактивные прототипы
6. 📐 **Templates** - Шаблоны и wireframes

---

## **1. 🎨 DESIGN SYSTEM PAGE**

### **Frame Size:** 1920x1080

### **Color Styles (создать как Figma Styles):**

#### **Primary Colors:**
```
Name: Primary/Main          HEX: #1976d2    RGB: 25, 118, 210
Name: Primary/Light         HEX: #42a5f5    RGB: 66, 165, 245
Name: Primary/Dark          HEX: #1565c0    RGB: 21, 101, 192
Name: Primary/50            HEX: #e3f2fd    RGB: 227, 242, 253
Name: Primary/100           HEX: #bbdefb    RGB: 187, 222, 251
```

#### **Secondary Colors:**
```
Name: Secondary/Main        HEX: #f57c00    RGB: 245, 124, 0
Name: Secondary/Light       HEX: #ffb74d    RGB: 255, 183, 77
Name: Secondary/Dark        HEX: #ef6c00    RGB: 239, 108, 0
```

#### **Status Colors:**
```
Name: Success/Main          HEX: #388e3c    RGB: 56, 142, 60
Name: Success/Light         HEX: #66bb6a    RGB: 102, 187, 106
Name: Warning/Main          HEX: #f9a825    RGB: 249, 168, 37
Name: Warning/Light         HEX: #ffcc02    RGB: 255, 204, 2
Name: Error/Main            HEX: #d32f2f    RGB: 211, 47, 47
Name: Error/Light           HEX: #ef5350    RGB: 239, 83, 80
Name: Info/Main             HEX: #0288d1    RGB: 2, 136, 209
```

#### **Neutral Colors:**
```
Name: Grey/50               HEX: #fafafa    RGB: 250, 250, 250
Name: Grey/100              HEX: #f5f5f5    RGB: 245, 245, 245
Name: Grey/200              HEX: #eeeeee    RGB: 238, 238, 238
Name: Grey/300              HEX: #e0e0e0    RGB: 224, 224, 224
Name: Grey/400              HEX: #bdbdbd    RGB: 189, 189, 189
Name: Grey/500              HEX: #9e9e9e    RGB: 158, 158, 158
Name: Grey/600              HEX: #757575    RGB: 117, 117, 117
Name: Grey/700              HEX: #616161    RGB: 97, 97, 97
Name: Grey/800              HEX: #424242    RGB: 66, 66, 66
Name: Grey/900              HEX: #212121    RGB: 33, 33, 33
```

### **Text Styles (создать как Figma Text Styles):**

```
Name: H1/Desktop            Font: Inter Bold    Size: 32px    Line: 40px
Name: H2/Desktop            Font: Inter Bold    Size: 24px    Line: 32px
Name: H3/Desktop            Font: Inter Bold    Size: 20px    Line: 28px
Name: H4/Desktop            Font: Inter Medium  Size: 18px    Line: 24px
Name: H5/Desktop            Font: Inter Medium  Size: 16px    Line: 24px
Name: H6/Desktop            Font: Inter Medium  Size: 14px    Line: 20px

Name: Body1/Desktop         Font: Inter Regular Size: 16px    Line: 24px
Name: Body2/Desktop         Font: Inter Regular Size: 14px    Line: 20px
Name: Caption/Desktop       Font: Inter Regular Size: 12px    Line: 16px
Name: Overline/Desktop      Font: Inter Regular Size: 12px    Line: 16px (uppercase)

Name: Button/Large          Font: Inter Medium  Size: 16px    Line: 24px
Name: Button/Medium         Font: Inter Medium  Size: 14px    Line: 20px
Name: Button/Small          Font: Inter Medium  Size: 12px    Line: 16px
```

### **Effect Styles (создать как Figma Effect Styles):**

```
Name: Shadow/1              Drop Shadow: X:0 Y:1 Blur:3 Color:#000 12%
Name: Shadow/2              Drop Shadow: X:0 Y:3 Blur:6 Color:#000 16%
Name: Shadow/3              Drop Shadow: X:0 Y:6 Blur:20 Color:#000 19%
Name: Shadow/4              Drop Shadow: X:0 Y:10 Blur:28 Color:#000 25%
Name: Shadow/5              Drop Shadow: X:0 Y:15 Blur:38 Color:#000 30%
```

### **Grid Styles:**

```
Name: Desktop Grid          Columns: 12    Gutter: 24px    Margin: 24px
Name: Tablet Grid           Columns: 8     Gutter: 16px    Margin: 16px  
Name: Mobile Grid           Columns: 4     Gutter: 16px    Margin: 16px
```

---

## **2. 📱 COMPONENTS PAGE**

### **Frame Size:** 1920x1080

### **Основные компоненты для создания:**

#### **2.1 Buttons (Кнопки)**

**Primary Button:**
- Size: 48px height
- Padding: 16px horizontal
- Border Radius: 8px
- Background: Primary/Main
- Text: Button/Medium, White
- States: Default, Hover, Pressed, Disabled

**Secondary Button:**
- Same as Primary
- Background: Transparent
- Border: 1px solid Primary/Main
- Text: Primary/Main

**Text Button:**
- Background: Transparent
- Text: Primary/Main
- No border

#### **2.2 Input Fields**

**Text Input:**
- Size: 56px height
- Padding: 16px horizontal, 16px vertical
- Border: 1px solid Grey/300
- Border Radius: 8px
- Font: Body1/Desktop
- States: Default, Focus, Error, Disabled

**Select Dropdown:**
- Same as Text Input
- Dropdown icon: 24x24px
- Dropdown menu: Shadow/2

#### **2.3 Cards**

**Base Card:**
- Background: White
- Border Radius: 8px
- Shadow: Shadow/1
- Padding: 24px

**KPI Card:**
- Size: 280x120px
- Background: White
- Border Radius: 8px
- Shadow: Shadow/1
- Padding: 20px

#### **2.4 Navigation**

**Sidebar Navigation:**
- Width: 280px (expanded), 72px (collapsed)
- Background: White
- Border: 1px solid Grey/200

**Top Navigation:**
- Height: 64px
- Background: White
- Shadow: Shadow/1

#### **2.5 Table Components**

**Table Row:**
- Height: 56px
- Border Bottom: 1px solid Grey/200
- Hover: Primary/50 background

**Table Header:**
- Height: 56px
- Background: Grey/50
- Font: H6/Desktop
- Border Bottom: 1px solid Grey/300

#### **2.6 Status Badges**

**Status Badge:**
- Height: 24px
- Padding: 4px 8px
- Border Radius: 12px
- Font: Caption/Desktop

**Variants:**
- Success: Success/Main background, White text
- Warning: Warning/Main background, White text  
- Error: Error/Main background, White text
- Info: Info/Main background, White text

#### **2.7 Mobile Components**

**Bottom Tab Bar:**
- Height: 64px
- Background: White
- Border Top: 1px solid Grey/200
- Icons: 24x24px

**Mobile Scanner Overlay:**
- Full screen frame
- Scanner rectangle: 280x200px
- Overlay: Black 50% opacity

---

## **3. 🖥️ DESKTOP SCREENS PAGE**

### **Артборды для создания (Frame 1440x900):**

#### **3.1 Authentication Screens**
- **Login Page** (1440x900)
- **Register Page** (1440x900)  
- **Forgot Password** (1440x900)
- **OTP Verification** (1440x900)

#### **3.2 Dashboard**
- **Main Dashboard** (1440x900)
- **Analytics Dashboard** (1440x900)

#### **3.3 Inventory Management**
- **Product List** (1440x900)
- **Product Detail Modal** (600x800 modal overlay)
- **Stock Overview** (1440x900)

#### **3.4 Inbound Operations**
- **ASN List** (1440x900)
- **ASN Detail** (1440x900)
- **Receiving Interface** (1440x900)

#### **3.5 Outbound Operations** 
- **Order List (Kanban)** (1440x900)
- **Order Detail** (1440x900)
- **Picking List** (1440x900)

#### **3.6 Training Module**
- **Article Feed** (1440x900)
- **Personal Roadmap** (1440x900)
- **Assessment Page** (1440x900)

#### **3.7 Wave Planning**
- **Wave Dashboard** (1440x900)
- **Wave Detail** (1440x900)
- **Wave Optimization** (1440x900)

#### **3.8 Cross-Docking**
- **Dock Management** (1440x900)
- **Appointment Scheduler** (1440x900)

---

## **4. 📱 MOBILE SCREENS PAGE**

### **Артборды для создания (Frame 375x812 - iPhone X/11/12):**

#### **4.1 Mobile Authentication**
- **Mobile Login** (375x812)
- **Mobile Register** (375x812)
- **Mobile OTP** (375x812)

#### **4.2 Mobile Dashboard**
- **Mobile Dashboard** (375x812)
- **Mobile Stats** (375x812)

#### **4.3 Mobile Inventory**
- **Mobile Product List** (375x812)
- **Mobile Scanner** (375x812)
- **Mobile Stock Check** (375x812)

#### **4.4 Mobile Picking**
- **Picking Task List** (375x812)
- **Picking Interface** (375x812)
- **Picking Confirmation** (375x812)

#### **4.5 Mobile Navigation**
- **Bottom Tab Navigation** (375x64)
- **Mobile Menu** (375x812)

---

## **5. 🔄 PROTOTYPES PAGE**

### **Интерактивные прототипы для создания:**

#### **5.1 Desktop User Flow**
- Login → Dashboard → Product Management
- Order Creation → Wave Planning → Picking

#### **5.2 Mobile User Flow**  
- Mobile Login → Scanner → Picking Task
- Mobile Dashboard → Stock Check

#### **5.3 Animations**
- Loading states
- Modal transitions
- Tab switching
- Toast notifications

---

## **6. 📐 TEMPLATES PAGE**

### **Шаблоны для создания:**

#### **6.1 Layout Templates**
- **Desktop Layout Template** (1440x900)
  - Header (1440x64)
  - Sidebar (280x836) 
  - Content Area (1136x836)

- **Mobile Layout Template** (375x812)
  - Header (375x56)
  - Content (375x692)
  - Bottom Tabs (375x64)

#### **6.2 Form Templates**
- **Desktop Form Template**
- **Mobile Form Template** 
- **Modal Form Template**

#### **6.3 Data Display Templates**
- **Table Template**
- **Card Grid Template**
- **List Template**

---

## **📋 ПОШАГОВЫЙ ПЛАН СОЗДАНИЯ В FIGMA:**

### **Шаг 1: Настройка проекта**
1. Создать новый файл "WMS Design System"
2. Создать 6 страниц (Pages)
3. Установить плагины: "Material Design Icons", "Auto Layout"

### **Шаг 2: Design System**
1. Создать все Color Styles
2. Создать все Text Styles  
3. Создать все Effect Styles
4. Настроить Grid Styles

### **Шаг 3: Components**
1. Создать базовые компоненты
2. Настроить Auto Layout для адаптивности
3. Создать варианты (Variants) для каждого компонента
4. Настроить Component Properties

### **Шаг 4: Desktop Screens**
1. Создать артборды 1440x900
2. Применить компоненты из библиотеки
3. Настроить constraints для responsive

### **Шаг 5: Mobile Screens**  
1. Создать артборды 375x812
2. Адаптировать компоненты для mobile
3. Настроить touch-friendly размеры

### **Шаг 6: Prototyping**
1. Связать экраны переходами
2. Настроить hover states
3. Добавить анимации переходов

---

## **🔧 FIGMA PLUGINS ДЛЯ ИСПОЛЬЗОВАНИЯ:**

1. **Material Design Icons** - для иконок
2. **Auto Layout** - для responsive компонентов  
3. **Content Reel** - для placeholder контента
4. **Stark** - для проверки accessibility
5. **Design System Organizer** - для организации компонентов

---

## **📁 ASSETS ДЛЯ ПОДГОТОВКИ:**

### **Иконки (24x24px, SVG):**
- Dashboard: 📊 
- Inventory: 📦
- Inbound: 📥
- Outbound: 📤  
- Wave Planning: 🌊
- Cross-Docking: 🚛
- Training: 🎓
- Analytics: 📈
- Settings: ⚙️
- Notifications: 🔔

### **Логотип:**
- WMS Logo (SVG, различные размеры)
- Favicon (16x16, 32x32)

### **Изображения:**
- Dashboard graphics
- Training article images
- User avatars (placeholder)

---

*Этот план позволит создать полноценную design system в Figma для WMS проекта с учетом всех современных практик и стандартов Berry MUI.* 