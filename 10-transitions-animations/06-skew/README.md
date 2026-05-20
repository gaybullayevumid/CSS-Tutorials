# 06. CSS Skew (Qiyshaytirish)

`skew` funksiyasi elementni X yoki Y o'qi bo'yicha qiyshaytirib, parallelogramm shaklini hosil qiladi. O'lchov birligi sifatida `deg` (gradus) ishlatiladi.


# Eng muhim narsa

`skew` elementni:

✅ vizual qiyshaytiradi
❌ boshqa elementlarni joyidan qimirlatmaydi

Bu juda muhim.

---

# Oddiy misol

```html id="1a2b3c"
<div class="box"></div>
```

```css id="4d5e6f"
.box {
    width: 100px;
    height: 100px;
    background: crimson;

    transform: skewX(20deg);
}
```

Natija:

* box gorizontal o'q bo'yicha 20 gradusga qiyshayadi

---

# skewX()

Elementni gorizontal o'q bo'yicha qiyshaytiradi.

Elementning yuqori va pastki tomonlari chapga yoki o'ngga siljiydi.

---

## O'ngga qiyshaytirish

```css id="7g8h9i"
transform: skewX(20deg);
```

/ belgisi kabi qiyshayadi (o'ng tomonga)

---

## Chapga qiyshaytirish

```css id="2j3k4l"
transform: skewX(-20deg);
```

\ belgisi kabi qiyshayadi (chap tomonga)

Minus bo'lsa teskari tomonga qiyshayadi.

---

# skewY()

Elementni vertikal o'q bo'yicha qiyshaytiradi.

Elementning chap va o'ng tomonlari tepaga yoki pastga siljiydi.

---

## Pastga qiyshaytirish

```css id="5m6n7o"
transform: skewY(20deg);
```

Element pastga qarab qiyshayadi.

---

## Tepaga qiyshaytirish

```css id="8p9q1r"
transform: skewY(-20deg);
```

Element tepaga qarab qiyshayadi.

---

# skew()

X va Y ni birdan ishlatadi.

```css id="2s3t4u"
transform: skew(20deg, 10deg);
```

Bu:

* x = 20deg → gorizontal qiyshaytiradi
* y = 10deg → vertikal qiyshaytiradi

---

# Bitta qiymat bilan

```css id="5v6w7x"
transform: skew(20deg);
```

Bu:

* faqat X o'qi bo'yicha 20 gradusga qiyshayadi
* Y = 0 (o'zgarmaydi)

---

# Nega skew ishlatiladi?

Chunki:

* dekorativ elementlar yaratish uchun qulay
* dinamik va zamonaviy dizayn effektlari
* banner va section qirralarini qiyshaytirish uchun
* hover effektlarda original ko'rinish beradi

---

# Hover misoli

```html id="9y1z2a"
<div class="card"></div>
```

```css id="3b4c5d"
.card {
    transition: 0.3s;
}

.card:hover {
    transform: skewX(5deg);
}
```

Nima bo'ladi?

Hover qilganda:

* karta biroz qiyshayadi — dinamik effekt

---

# Amaliy foydalanish: diagonal section

```css id="6e7f8g"
.section {
    transform: skewY(-3deg);
}

.section .content {
    transform: skewY(3deg);
}
```

Bu:

* sectionni diagonal qilib ko'rsatadi
* ichidagi content ni teskari skew bilan tiklaydi

Ko'p zamonaviy saytlarda ishlatiladi.

---

# transform-origin bilan ishlashi

Default holatda element markazidan qiyshayadi.

```css id="9h1i2j"
transform-origin: left center;
transform: skewX(20deg);
```

Bu:

* element chap tomondan qiyshayadi

---

# Transition bilan birga

```css id="3k4l5m"
.box {
    transition: 0.4s;
}

.box:hover {
    transform: skew(15deg, 5deg);
}
```

Element silliq qiyshayadi.

---

# skew juda ko'p ishlatiladigan joylar

✅ hover effektlar
✅ diagonal section dizayni
✅ parallelogramm shakllar
✅ banner va hero sectionlar
✅ zamonaviy karta effektlari
✅ dekorativ elementlar

---

# Muhim qoida

`skew` har doim:

```css id="6n7o8p"
transform:
```

ichida yoziladi.

❌

```css id="9q1r2s"
skewX(20deg);
```

✅

```css id="3t4u5v"
transform: skewX(20deg);
```

---

# Eng ko'p ishlatiladiganlari

```css id="6w7x8y"
transform: skewX(20deg);
transform: skewX(-15deg);
transform: skewY(10deg);
transform: skew(20deg, 10deg);
transform: skew(-5deg);
```
