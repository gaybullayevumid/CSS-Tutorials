# 07. CSS @keyframes

`@keyframes` yordamida elementning animatsiya davomida qanday o'zgarishini bosqichma-bosqich belgilab beramiz. Faqat hover yoki click ga javob qaytarish emas — element o'zi avtomatik harakatlanadi.


# Eng muhim narsa

`@keyframes` ikki qismdan iborat:

✅ animatsiyani BELGILAYMIZ (`@keyframes`)
✅ elementga ULAYMIZ (`animation`)

Faqat `@keyframes` yozish yetarli emas, uni elementga ulash kerak.

---

# Oddiy misol

```css id="1a2b3c"
@keyframes siljish {
    from { transform: translateX(0); }
    to   { transform: translateX(200px); }
}

.box {
    animation: siljish 1s;
}
```

Natija:

* box chapdan o'ngga 200px siljiydi

---

# from va to

Eng oddiy usul.

```css id="4d5e6f"
@keyframes misol {
    from { /* boshlanish holati */ }
    to   { /* tugash holati */ }
}
```

`from` = 0%
`to` = 100%

---

## Misol: rang o'zgarishi

```css id="7g8h9i"
@keyframes rangOzgarsin {
    from { background-color: blue; }
    to   { background-color: red; }
}
```

Element ko'k rangdan qizilga o'tadi.

---

# Foizlar bilan

Ko'proq bosqich kerak bo'lsa foizlar ishlatiladi.

```css id="2j3k4l"
@keyframes misol {
    0%   { /* boshlanish */ }
    50%  { /* o'rta holat */ }
    100% { /* tugash */ }
}
```

---

## Misol: uch bosqichli harakat

```css id="5m6n7o"
@keyframes harakatlan {
    0%   { transform: translateX(0); }
    50%  { transform: translateX(200px); }
    100% { transform: translateX(0); }
}
```

Bu:

* 0% → boshlanish joyida
* 50% → o'ngga 200px siljiydi
* 100% → qaytib keladi

---

## Misol: to'rt bosqich

```css id="8p9q1r"
@keyframes pulse {
    0%   { transform: scale(1); }
    25%  { transform: scale(1.2); }
    75%  { transform: scale(0.9); }
    100% { transform: scale(1); }
}
```

Yurak urishi effekti shu usulda qilinadi.

---

# Ko'p xususiyatni birga o'zgartirish

Bir vaqtda bir nechta xususiyatni o'zgartirish mumkin.

```css id="2s3t4u"
@keyframes effekt {
    0% {
        transform: translateX(0) scale(1);
        opacity: 1;
    }
    100% {
        transform: translateX(300px) scale(1.5);
        opacity: 0;
    }
}
```

---

# Nomlash qoidasi

```css id="5v6w7x"
@keyframes mening-animatsiyam { }
@keyframes slideIn { }
@keyframes fadeOut { }
```

Nom ixtiyoriy, lekin tushunarli bo'lishi kerak.

Nom bo'sh joy qabul qilmaydi — tire (`-`) yoki camelCase ishlatiladi.

---

# Elementga ulash

```css id="8y9z1a"
.box {
    animation-name: harakatlan;
    animation-duration: 2s;
}
```

`animation-name` — `@keyframes` nomini yozamiz
`animation-duration` — qancha vaqt davom etishi

---

# Shorthand bilan ulash

```css id="2b3c4d"
.box {
    animation: harakatlan 2s ease 0s infinite;
}
```

Bu ham xuddi shunday ishlaydi, faqat qisqaroq.

---

# Muhim qoidalar

❌ `@keyframes` yozib, elementga ulаmasang — hech narsa bo'lmaydi

❌ `animation-duration` bermasang — animatsiya ko'rinmaydi (default 0s)

✅ Har doim ikkisini birga yoz

---

# @keyframes juda ko'p ishlatiladigan joylar

✅ loading spinner
✅ yurak urishi effekti
✅ fadeIn / fadeOut
✅ slideIn / slideOut
✅ attention effektlar (shake, bounce)
✅ cheksiz loop animatsiyalar

---

# Tayyor misol: fadeIn

```css id="5e6f7g"
@keyframes fadeIn {
    from { opacity: 0; }
    to   { opacity: 1; }
}

.box {
    animation: fadeIn 1s ease;
}
```

Element asta-sekin paydo bo'ladi.

---

# Tayyor misol: bounce

```css id="8h9i1j"
@keyframes bounce {
    0%   { transform: translateY(0); }
    30%  { transform: translateY(-30px); }
    60%  { transform: translateY(-15px); }
    100% { transform: translateY(0); }
}

.box {
    animation: bounce 0.6s ease;
}
```

Element sakrab tushadi.

---

# Eng ko'p ishlatiladigan struktura

```css id="2k3l4m"
@keyframes animatsiyaNomi {
    0%   { /* boshlang'ich holat */ }
    50%  { /* o'rta holat */ }
    100% { /* tugash holati */ }
}

.element {
    animation: animatsiyaNomi 1s ease infinite;
}
```
