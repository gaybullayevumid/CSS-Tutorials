# 03. CSS Translate (Siljitish)

`translate` funksiyasi elementni o'zining joriy joylashgan o'rnidan X (gorizontal) yoki Y (vertikal) o'qlari bo'yicha siljitadi. `position: relative` yoki `absolute` orqali siljitishdan farqli ravishda, `translate` bilan siljitish animatsiyalarda silliqroq ishlaydi.


# Eng muhim narsa

`translate` elementni:

✅ vizual suradi
❌ boshqa elementlarni joyidan qimirlatmaydi

Bu juda muhim.

---

# Oddiy misol

```html id="8z0m1n"
<div class="box"></div>
```

```css id="s7m9l2"
.box {
    width: 100px;
    height: 100px;
    background: blue;

    transform: translateX(100px);
}
```

Natija:

* box o‘ngga 100px yuradi

---

# translateX()

Gorizontal suradi.

---

## O‘ngga

```css id="1j6g2v"
transform: translateX(100px);
```

➡ o‘ngga 100px

---

## Chapga

```css id="v3h8q1"
transform: translateX(-100px);
```

⬅ chapga 100px

Minus bo‘lsa chapga ketadi.

---

# translateY()

Vertikal suradi.

---

## Pastga

```css id="u5r1k9"
transform: translateY(100px);
```

⬇ pastga

---

## Tepaga

```css id="4t8n2x"
transform: translateY(-100px);
```

⬆ tepaga

Minus bo‘lsa tepaga ketadi.

---

# translate()

X va Y ni birdan ishlatadi.

```css id="f7m2w8"
transform: translate(100px, 50px);
```

Bu:

* x = 100px → o‘ngga
* y = 50px → pastga

---

# Koordinata kabi ishlaydi

Tasavvur qil:

```text
x  → chap/o‘ng
y  → tepa/past
```

---

# Nega translate ishlatiladi?

Chunki:

* juda qulay
* animatsiyada smooth ishlaydi
* performance yaxshi
* hover effektlarda ko‘p ishlatiladi

---

# Hover misoli

```html id="a8k2p4"
<button>Button</button>
```

```css id="r6d9f1"
button {
    transition: 0.3s;
}

button:hover {
    transform: translateY(-5px);
}
```

Nima bo‘ladi?

Hover qilganda:

* button tepaga 5px chiqadi

Bu juda mashhur effekt.

---

# translate va margin farqi

Ko‘pchilik adashtiradi.

---

# margin-left

```css id="2v9n6y"
margin-left: 100px;
```

✅ boshqa elementlarni ham suradi

---

# translateX

```css id="q4c8m7"
transform: translateX(100px);
```

✅ faqat o‘zi vizual yuradi
❌ layout buzmaydi

---

# Real hayotdagi tushuncha

Tasavvur qil:

* Stol ustida telefon turibdi

`margin-left`

→ stolni o‘zgartirib joyini suradi

`translateX`

→ telefonni qo‘ling bilan itarib qo‘yasan

---

# Percent bilan ishlashi

`translate` `%` ham qabul qiladi.

```css id="n2x7p5"
transform: translateX(50%);
```

Bu:

* o‘zining widthini 50%iga suradi

---

# Center qilishda juda ko‘p ishlatiladi

```css id="m8q1z4"
position: absolute;
top: 50%;
left: 50%;

transform: translate(-50%, -50%);
```

Bu elementni markazga qo‘yadi.

---

# Nega -50% ishlatiladi?

`top: 50%`
`left: 50%`

→ elementning chap yuqori burchagini markazga olib keladi.

Keyin:

```css id="y6p3r8"
transform: translate(-50%, -50%);
```

→ elementning o‘zini yarim width va yarim heightga qaytaradi.

Natijada PERFECT center bo‘ladi.

---

# Transition bilan birga

```css id="e1u9o6"
.box {
    transition: 0.5s;
}

.box:hover {
    transform: translateX(50px);
}
```

Element silliq yuradi.

---

# translate juda ko‘p ishlatiladigan joylar

✅ hover effektlar
✅ animatsiyalar
✅ modal oynalar
✅ center qilish
✅ card effectlar
✅ navbar animatsiyalar

---

# Muhim qoida

`translate` har doim:

```css id="w9k4v2"
transform:
```

ichida yoziladi.

❌

```css id="g3f7n1"
translateX(50px);
```

✅

```css id="h5d2s8"
transform: translateX(50px);
```

---

# Eng ko‘p ishlatiladiganlari

```css id="k7m1x9"
transform: translateX(50px);
transform: translateY(-10px);
transform: translate(20px, 30px);
```
