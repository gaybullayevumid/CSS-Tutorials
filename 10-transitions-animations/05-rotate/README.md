# 05. CSS Rotate (Aylantirish)

`rotate` funksiyasi elementni o'z o'qi atrofida aylantiradi. O'lchov birligi sifatida `deg` (gradus) ishlatiladi. Musbat qiymat soat mili yo'nalishida, manfiy qiymat soat miliga qarshi aylantiradi.


# Eng muhim narsa

`rotate` elementni:

✅ vizual aylantiradi
❌ boshqa elementlarni joyidan qimirlatmaydi

Bu juda muhim.

---

# Oddiy misol

```html id="2a1b3c"
<div class="box"></div>
```

```css id="5d4e6f"
.box {
    width: 100px;
    height: 100px;
    background: tomato;

    transform: rotate(45deg);
}
```

Natija:

* box 45 gradusga soat mili yo'nalishida aylanadi

---

# rotate()

Elementni 2D tekislikda aylantiradi.

---

## Soat mili yo'nalishida

```css id="8g7h9i"
transform: rotate(90deg);
```

↻ 90 gradus o'ngga

---

## Soat miliga qarshi

```css id="1j2k3l"
transform: rotate(-90deg);
```

↺ 90 gradus chapga

Minus bo'lsa soat miliga qarshi aylanadi.

---

## To'liq aylanish

```css id="4m5n6o"
transform: rotate(360deg);
```

↻ to'liq bir aylanish

---

# rotateX()

Elementni gorizontal o'q atrofida aylantiradi.

3D effekt hosil bo'ladi.

```css id="7p8q9r"
transform: rotateX(60deg);
```

Element tepaga yoki pastga qarab "yiqilgandek" ko'rinadi.

---

# rotateY()

Elementni vertikal o'q atrofida aylantiradi.

3D effekt hosil bo'ladi.

```css id="2s3t4u"
transform: rotateY(60deg);
```

Element chapga yoki o'ngga qarab "burilingandek" ko'rinadi.

Karta o'girilishi effekti shu bilan qilinadi.

---

# perspective bilan ishlashi

`rotateX` va `rotateY` da 3D effekt yaxshi ko'rinishi uchun parent elementga `perspective` beriladi.

```css id="5v6w7x"
.wrapper {
    perspective: 500px;
}

.box {
    transform: rotateY(60deg);
}
```

`perspective` qiymati qanchalik kichik bo'lsa, 3D effekt shunchalik kuchli ko'rinadi.

---

# Nega rotate ishlatiladi?

Chunki:

* juda qulay
* animatsiyada smooth ishlaydi
* performance yaxshi
* hover effektlarda ko'p ishlatiladi

---

# Hover misoli

```html id="9y1z2a"
<button>Button</button>
```

```css id="3b4c5d"
button {
    transition: 0.3s;
}

button:hover {
    transform: rotate(15deg);
}
```

Nima bo'ladi?

Hover qilganda:

* button biroz qiyshayadi

---

# transform-origin bilan ishlashi

Default holatda element o'z markazidan aylanadi.

```css id="6e7f8g"
transform-origin: top left;
transform: rotate(45deg);
```

Bu:

* element chap yuqori burchagidan aylanadi

---

# Transition bilan birga

```css id="9h1i2j"
.box {
    transition: 0.5s;
}

.box:hover {
    transform: rotate(180deg);
}
```

Element silliq aylanadi.

---

# Cheksiz aylanish (animation bilan)

```css id="3k4l5m"
@keyframes spin {
    from { transform: rotate(0deg); }
    to   { transform: rotate(360deg); }
}

.box {
    animation: spin 2s linear infinite;
}
```

Element to'xtamasdan aylanib turadi.

Loading spinner shu usul bilan qilinadi.

---

# rotate juda ko'p ishlatiladigan joylar

✅ hover effektlar
✅ loading spinner
✅ karta o'girilishi
✅ ikonka animatsiyalari
✅ accordion strelkasi
✅ 3D effektlar

---

# Muhim qoida

`rotate` har doim:

```css id="6n7o8p"
transform:
```

ichida yoziladi.

❌

```css id="9q1r2s"
rotate(45deg);
```

✅

```css id="3t4u5v"
transform: rotate(45deg);
```

---

# Eng ko'p ishlatiladiganlari

```css id="6w7x8y"
transform: rotate(45deg);
transform: rotate(-90deg);
transform: rotate(180deg);
transform: rotate(360deg);
transform: rotateX(60deg);
transform: rotateY(60deg);
```
