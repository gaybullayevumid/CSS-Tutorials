# 04. CSS Scale (Masshtablash)

`scale` funksiyasi elementni kattalashtirish yoki kichraytirish uchun ishlatiladi. `1` qiymati asl o'lchamni bildiradi. Undan katta qiymat kattalashtiradi, kichik qiymat kichraytiradi.


# Eng muhim narsa

`scale` elementni:

✅ vizual kattalashtiradi yoki kichraytiradi
❌ boshqa elementlarni joyidan qimirlatmaydi

Bu juda muhim.

---

# Oddiy misol

```html id="4a1b2c"
<div class="box"></div>
```

```css id="7d3e4f"
.box {
    width: 100px;
    height: 100px;
    background: teal;

    transform: scale(1.5);
}
```

Natija:

* box asl o'lchamidan 1.5 marta kattalashadi

---

# scaleX()

Faqat gorizontal o'q bo'yicha kenglashtiradi yoki toraytiradi.

---

## Kenglashtirish

```css id="2g5h6i"
transform: scaleX(2);
```

↔ ikki marta kengayadi

---

## Toraytirish

```css id="9j7k8l"
transform: scaleX(0.5);
```

↔ yarmiga torayadi

Minus bo'lsa element oynasi orqali aks etadi (mirror).

---

# scaleY()

Faqat vertikal o'q bo'yicha cho'zadi yoki qisqartiradi.

---

## Cho'zish

```css id="3m1n2o"
transform: scaleY(2);
```

↕ ikki marta balandlashadi

---

## Qisqartirish

```css id="6p4q5r"
transform: scaleY(0.5);
```

↕ yarmiga qisqaradi

Minus bo'lsa element vertikal aks etadi (flip).

---

# scale()

X va Y ni birdan ishlatadi.

```css id="8s2t3u"
transform: scale(1.5);
```

Bu:

* x = 1.5 → kengligi 1.5 marta kattayadi
* y = 1.5 → balandligi 1.5 marta kattayadi

---

# Ikki qiymat bilan

```css id="5v9w1x"
transform: scale(2, 0.5);
```

Bu:

* x = 2 → kengligi ikki marta kattayadi
* y = 0.5 → balandligi yarmiga qisqaradi

---

# Kichraytirish

```css id="4y7z8a"
transform: scale(0.8);
```

Bu:

* element asl o'lchamining 80% gacha kichrayadi

---

# Nol qiymat

```css id="1b6c2d"
transform: scale(0);
```

Element butunlay yo'qoladi (lekin DOM da qoladi).

---

# Nega scale ishlatiladi?

Chunki:

* juda qulay
* animatsiyada smooth ishlaydi
* performance yaxshi
* hover effektlarda ko'p ishlatiladi

---

# Hover misoli

```html id="3e8f4g"
<button>Button</button>
```

```css id="7h1i5j"
button {
    transition: 0.3s;
}

button:hover {
    transform: scale(1.1);
}
```

Nima bo'ladi?

Hover qilganda:

* button biroz kattalashadi

Bu juda mashhur effekt.

---

# scale va width farqi

Ko'pchilik adashtiradi.

---

# width

```css id="2k9l6m"
width: 200px;
```

✅ boshqa elementlarni ham suradi

---

# scaleX

```css id="5n3o7p"
transform: scaleX(2);
```

✅ faqat o'zi vizual kattayadi
❌ layout buzmaydi

---

# Real hayotdagi tushuncha

Tasavvur qil:

* Stol ustida kitob turibdi

`width: 200px`

→ stolni qayta joylashtiradi, boshqa narsalar siljiydi

`scaleX(2)`

→ kitobni lupa orqali ko'ryapsan, aslida hech narsa o'zgarmagan

---

# transform-origin bilan ishlashi

`scale` markazdan kattayadi (default).

```css id="8q2r1s"
transform-origin: top left;
transform: scale(1.5);
```

Bu:

* element chap yuqori burchakdan kattayadi

---

# Transition bilan birga

```css id="4t6u9v"
.box {
    transition: 0.5s;
}

.box:hover {
    transform: scale(1.3);
}
```

Element silliq kattayadi.

---

# scale juda ko'p ishlatiladigan joylar

✅ hover effektlar
✅ animatsiyalar
✅ rasm galereya
✅ card effectlar
✅ button press effektlar
✅ modal animatsiyalar

---

# Muhim qoida

`scale` har doim:

```css id="7w5x8y"
transform:
```

ichida yoziladi.

❌

```css id="1z4a3b"
scale(1.5);
```

✅

```css id="6c2d7e"
transform: scale(1.5);
```

---

# Eng ko'p ishlatiladiganlari

```css id="9f8g5h"
transform: scale(1.5);
transform: scale(0.8);
transform: scaleX(2);
transform: scaleY(0.5);
transform: scale(1.2, 0.9);
```
