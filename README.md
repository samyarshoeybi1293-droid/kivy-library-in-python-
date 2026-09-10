# 🐍 آموزش Kivy در Python

## 📚 Kivy چیست؟

**Kivy** یک کتابخانه قدرتمند برای زبان برنامه‌نویسی **Python** است که برای ساخت برنامه‌های دارای رابط گرافیکی (GUI) استفاده می‌شود.

با Kivy می‌توان برنامه‌هایی ساخت که به‌جای اجرا شدن فقط در ترمینال، دارای:

* 🖥️ پنجره
* 🔘 دکمه
* 📝 کادر متن
* 🖼️ تصویر
* 📋 منو
* 📱 رابط کاربری لمسی
* 🎮 بازی‌های ساده

باشند.

---

# 🚀 کاربردهای Kivy

با Kivy می‌توان پروژه‌های مختلفی ساخت:

* 🖥️ برنامه‌های دسکتاپ
* 📱 برنامه‌های اندروید
* 🎮 بازی‌های دوبعدی ساده
* 📝 برنامه‌های آموزشی
* 📊 برنامه‌های کاربردی
* 🖱️ برنامه‌های دارای رابط گرافیکی

---

# 🧩 Widget چیست؟

در Kivy تقریباً هر چیزی که روی صفحه مشاهده می‌کنیم یک **Widget** است.

برای مثال:

```python
Button
Label
TextInput
Image
```

ساختار کلی را می‌توان این‌گونه تصور کرد:

```text
Kivy
│
├── Widget
│   ├── Button
│   ├── Label
│   ├── TextInput
│   └── Image
│
└── Layout
    ├── BoxLayout
    ├── GridLayout
    └── FloatLayout
```

---

# 📦 Layout چیست؟

`Layout` مشخص می‌کند Widgetها چگونه و در کجای صفحه قرار بگیرند.

مثلاً `BoxLayout` می‌تواند Widgetها را به‌صورت افقی یا عمودی قرار دهد.

```python
from kivy.uix.boxlayout import BoxLayout

layout = BoxLayout(orientation="vertical")
```

سپس می‌توان Widgetها را به آن اضافه کرد:

```python
layout.add_widget(Button(text="شروع"))
layout.add_widget(Button(text="خروج"))
```

---

# 📦 BoxLayout

`BoxLayout` یکی از مهم‌ترین Layoutهای Kivy است.

## حالت افقی

```python
BoxLayout(orientation="horizontal")
```

نتیجه تقریباً به این شکل است:

```text
┌─────────────────────────────┐
│ دکمه 1 │ دکمه 2 │ دکمه 3    │
└─────────────────────────────┘
```

## حالت عمودی

```python
BoxLayout(orientation="vertical")
```

نتیجه:

```text
┌───────────────┐
│    دکمه 1     │
├───────────────┤
│    دکمه 2     │
├───────────────┤
│    دکمه 3     │
└───────────────┘
```

---

# 🧱 GridLayout

`GridLayout` برای ساختن جدول و شبکه مناسب است.

مثلاً:

```python
from kivy.uix.gridlayout import GridLayout

layout = GridLayout(cols=3)
```

ساختار:

```text
┌────┬────┬────┐
│ 1  │ 2  │ 3  │
├────┼────┼────┤
│ 4  │ 5  │ 6  │
├────┼────┼────┤
│ 7  │ 8  │ 9  │
└────┴────┴────┘
```

---

# 🎯 FloatLayout

`FloatLayout` امکان قرار دادن Widgetها را با موقعیت و اندازه قابل تنظیم فراهم می‌کند.

مثلاً:

```python
from kivy.uix.floatlayout import FloatLayout

layout = FloatLayout()
```

---

# 🎨 Widgetهای مهم Kivy

## Button

برای ساخت دکمه:

```python
from kivy.uix.button import Button

button = Button(text="کلیک کن")
```

---

## Label

برای نمایش متن:

```python
from kivy.uix.label import Label

label = Label(text="سلام Kivy!")
```

---

## TextInput

برای دریافت متن از کاربر:

```python
from kivy.uix.textinput import TextInput

text_input = TextInput()
```

---

## Image

برای نمایش تصویر:

```python
from kivy.uix.image import Image

image = Image(source="photo.png")
```

---

# 🖥️ ساخت اولین برنامه Kivy

کد زیر یک برنامه ساده Kivy ایجاد می‌کند:

```python
from kivy.app import App
from kivy.uix.boxlayout import BoxLayout
from kivy.uix.label import Label
from kivy.uix.button import Button


class MyApp(App):

    def build(self):

        layout = BoxLayout(orientation="vertical")

        label = Label(text="سلام Kivy!")

        button = Button(text="کلیک کن")

        layout.add_widget(label)
        layout.add_widget(button)

        return layout


MyApp().run()
```

---

# 🖱️ Event چیست؟

در برنامه‌های گرافیکی، کاربر می‌تواند کارهایی مثل کلیک کردن روی دکمه انجام دهد.

Kivy این اتفاق‌ها را به‌عنوان **Event** مدیریت می‌کند.

مثلاً:

```python
button.bind(on_press=self.clicked)
```

و سپس:

```python
def clicked(self, instance):
    print("دکمه کلیک شد!")
```

ساختار اتفاق:

```text
کاربر روی دکمه کلیک می‌کند
          ↓
       on_press
          ↓
      clicked()
          ↓
     اجرای Python
```

---

# 🧠 Python و Kivy

می‌توان رابطه Python و Kivy را این‌گونه در نظر گرفت:

```text
Python
  ↓
منطق برنامه 🧠

Kivy
  ↓
رابط گرافیکی 🎨
```

یعنی Python کارهای اصلی برنامه را انجام می‌دهد و Kivy ابزارهای لازم برای ساخت رابط کاربری را فراهم می‌کند.

---

# 📚 مسیر پیشنهادی یادگیری Kivy

اگر می‌خواهید Kivy را از پایه یاد بگیرید، این مسیر مناسب است:

```text
1️⃣ Python پایه
       ↓
2️⃣ App و build()
       ↓
3️⃣ Widget
       ↓
4️⃣ Label
       ↓
5️⃣ Button
       ↓
6️⃣ BoxLayout
       ↓
7️⃣ GridLayout
       ↓
8️⃣ TextInput
       ↓
9️⃣ Event و bind
       ↓
🔟 ScreenManager
       ↓
1️⃣1️⃣ ساخت برنامه واقعی
       ↓
1️⃣2️⃣ ساخت بازی ساده
       ↓
1️⃣3️⃣ ساخت APK اندروید
```

---

# 🏆 پروژه‌های پیشنهادی

بعد از یادگیری مباحث بالا، می‌توان پروژه‌های زیر را ساخت:

### 🧮 ماشین حساب

```text
┌────────────────────┐
│        125         │
├────┬────┬────┬────┤
│ 7  │ 8  │ 9  │ +  │
├────┼────┼────┼────┤
│ 4  │ 5  │ 6  │ -  │
├────┼────┼────┼────┤
│ 1  │ 2  │ 3  │ ×  │
├────┼────┼────┼────┤
│ 0  │ .  │ =  │ ÷  │
└────┴────┴────┴────┘
```

### 📝 برنامه یادداشت

استفاده از:

```python
TextInput
Button
Label
BoxLayout
```

### 🎮 بازی ساده

استفاده از:

```python
Widget
Button
Image
Clock
```

---

# 💡 جمع‌بندی

Kivy یک ابزار بسیار خوب برای ساخت رابط‌های گرافیکی با Python است.

مفاهیم مهمی که باید یاد بگیریم:

* `App`
* `Widget`
* `Button`
* `Label`
* `TextInput`
* `Image`
* `BoxLayout`
* `GridLayout`
* `FloatLayout`
* `Event`
* `bind()`
* `ScreenManager`

اگر این مفاهیم را به‌ترتیب یاد بگیری، می‌توانی از برنامه‌های ساده شروع کنی و به ساخت **برنامه‌های کامل و بازی‌های Kivy** برسی.
