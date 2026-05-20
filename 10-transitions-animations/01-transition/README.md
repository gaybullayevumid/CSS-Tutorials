# 01. CSS Transition (O'tishlar)


## Transition nima? Nima uchun kerak?

Tasavvur qiling: siz tugmachaga sichqonchani olib borganingizda uning rangi **bir zumda** o'zgaradi — bu qo'pol va yoqimsiz ko'rinadi.

Endi tasavvur qiling — rang asta-sekin, silliq tarzda o'zgaradi — bu esa professional va zamonaviy ko'rinadi.

Mana shu **"silliqlik"ni** ta'minlaydigan narsa — `transition`!


# Oddiy misol

```html
<button>Button</button>
```

```css
button {
    background: blue;
    transition: 1s;
}

button:hover {
    background: red;
}
```

Nima bo‘ladi?

* Sichqonni olib borsangiz (`hover`)
* Rang birdan emas
* `1 sekund` davomida asta-sekin ko‘kdan qizilga o‘tadi

---

# Transition bo‘lmasa

```css
button:hover {
    background: red;
}
```

Rang bir zumda almashadi.

---

# Transition sintaksisi

```css
transition: property duration timing-function delay;
```

4 qismdan iborat.

---

# 1. Property — nima o‘zgaradi

Qaysi CSS property animatsiya bo‘lishini aytamiz.

Misol:

```css
transition: background 1s;
```

Faqat `background` animatsiya bo‘ladi.

Yoki:

```css
transition: width 1s;
```

Width silliq o‘zgaradi.

---

# 2. Duration — qancha vaqt davom etadi

```css
transition: background 2s;
```

`2s` = 2 sekund

Yoki:

```css
transition: background 500ms;
```

`500ms` = yarim sekund

---

# 3. Timing Function — tezlik qanday o‘zgaradi

Bu animatsiya tezligini boshqaradi.

## Eng ko‘p ishlatiladiganlari

### linear

Bir xil tezlik.

```css
transition: 1s linear;
```

---

### ease

Boshlanish va tugashi yumshoq.

```css
transition: 1s ease;
```

Eng ko‘p ishlatiladi.

---

### ease-in

Sekin boshlanadi.

```css
transition: 1s ease-in;
```

---

### ease-out

Sekin tugaydi.

```css
transition: 1s ease-out;
```

---

### ease-in-out

Sekin boshlanib, sekin tugaydi.

```css
transition: 1s ease-in-out;
```

---

# 4. Delay — kechikish

Animatsiya qancha vaqt kutib boshlanishi.

```css
transition: background 1s 2s;
```

* 2 sekund kutadi
* keyin animatsiya boshlanadi

---

# Amaliy misollar

## 1. Hoverda kattalashish

```css
.box {
    width: 100px;
    height: 100px;
    background: blue;

    transition: 0.5s;
}

.box:hover {
    transform: scale(1.2);
}
```

Hover qilinsa element kattalashadi.

---

## 2. Width o‘zgarishi

```css
.box {
    width: 100px;
    transition: width 1s;
}

.box:hover {
    width: 300px;
}
```

Width asta-sekin kattalashadi.

---

## 3. Bir nechta property

```css
transition: background 1s, width 2s;
```

* background → 1s
* width → 2s

---

# transition: all

```css
transition: all 1s;
```

Barcha o‘zgaradigan propertylarga animatsiya beradi.

Lekin katta loyihalarda ko‘p ishlatilmaydi, chunki keraksiz narsalarni ham animatsiya qiladi.

Yaxshisi:

```css
transition: background 1s, transform 0.5s;
```

---

# Transition qaysi propertylarda ishlaydi?

Ko‘p propertylarda ishlaydi:

✅ `background`
✅ `color`
✅ `width`
✅ `height`
✅ `transform`
✅ `opacity`
✅ `margin`
✅ `padding`

Ba’zilarida ishlamaydi:

❌ `display: none -> block`

---

# Eng muhim qoida

`transition`ni odatda asosiy elementga yoziladi, `:hover`ga emas.

✅ To‘g‘ri:

```css
.box {
    transition: 1s;
}

.box:hover {
    background: red;
}
```

❌ Noto‘g‘ri:

```css
.box:hover {
    transition: 1s;
}
```

---

# Transition va Transform farqi

`transform` → elementni o‘zgartiradi

Masalan:

```css
transform: scale(1.2);
```

`transition` → shu o‘zgarishni silliq qiladi

Ko‘pincha ikkalasi birga ishlatiladi.

---

# Real loyiha misoli

Button hover effekti:

```css
button {
    padding: 12px 20px;
    background: blue;
    color: white;
    border: none;

    transition: 0.3s ease;
}

button:hover {
    background: darkblue;
    transform: translateY(-3px);
}
```

Natija:

* rang o‘zgaradi
* tepaga biroz ko‘tariladi
* hammasi silliq bo‘ladi

---

# Qisqa xulosa

`transition`:

* CSS animatsiya uchun ishlatiladi
* o‘zgarishni silliq qiladi
* hover effektlarda juda ko‘p ishlatiladi
* odatda `transform` bilan birga ishlaydi

Eng ko‘p ishlatiladigan yozilishi:

```css
transition: 0.3s ease;
```

yoki

```css
transition: all 0.3s ease;
```
