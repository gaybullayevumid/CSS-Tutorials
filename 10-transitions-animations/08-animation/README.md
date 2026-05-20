# 08. CSS Animation

`animation` xususiyati `@keyframes` ni elementga ulaydi va uning xatti-harakatini to'liq nazorat qiladi. Kamida `animation-name` va `animation-duration` bo'lishi shart.


# Eng muhim narsa

`animation` ishlatish uchun:

✅ `@keyframes` bilan animatsiya yaratiladi
✅ `animation` bilan elementga ulanadi

Ikkalasi bo'lmasa animatsiya ishlamaydi.

---

# Oddiy misol

```css id="1a2b3c"
@keyframes siljish {
    from { transform: translateX(0); }
    to   { transform: translateX(200px); }
}

.box {
    animation-name: siljish;
    animation-duration: 1s;
}
```

Natija:

* box 1 soniya ichida 200px o'ngga siljiydi

---

# animation-name

Qaysi `@keyframes` ishlatilishini belgilaydi.

```css id="4d5e6f"
animation-name: siljish;
```

---

# animation-duration

Animatsiya qancha vaqt davom etishini belgilaydi.

```css id="7g8h9i"
animation-duration: 2s;
animation-duration: 500ms;
```

Bu xususiyat bo'lmasa animatsiya ishlamaydi (default: `0s`).

---

# animation-iteration-count

Animatsiya necha marta takrorlanishini belgilaydi.

```css id="2j3k4l"
animation-iteration-count: 3;        /* 3 marta */
animation-iteration-count: infinite; /* cheksiz */
```

Loading spinner va pulse effektlarda `infinite` ishlatiladi.

---

# animation-direction

Animatsiya qaysi yo'nalishda ishlashini belgilaydi.

```css id="5m6n7o"
animation-direction: normal;           /* 0% → 100% */
animation-direction: reverse;          /* 100% → 0% */
animation-direction: alternate;        /* oldinga → orqaga */
animation-direction: alternate-reverse;
```

`alternate` yurak urishi va nafas olish effektlari uchun mukammal.

---

# animation-delay

Animatsiya qancha kutib boshlanishini belgilaydi.

```css id="8p9q1r"
animation-delay: 1s;    /* 1 soniya kutadi */
animation-delay: -1s;   /* allaqachon boshlanganday ko'rinadi */
```

---

# animation-fill-mode

Animatsiya tugagandan keyin element qanday holatda qolishini belgilaydi.

```css id="2s3t4u"
animation-fill-mode: none;      /* boshlang'ich holatga qaytadi */
animation-fill-mode: forwards;  /* oxirgi holatda qoladi */
animation-fill-mode: backwards; /* boshlang'ich holatni saqlaydi */
animation-fill-mode: both;      /* forwards + backwards */
```

Ko'p hollarda `forwards` ishlatiladi.

---

# animation-play-state

Animatsiyani to'xtatish yoki davom ettirish.

```css id="5v6w7x"
animation-play-state: running;  /* ishlayapti */
animation-play-state: paused;   /* to'xtatilgan */
```

Hover qilganda to'xtatish:

```css id="8y9z1a"
.box:hover {
    animation-play-state: paused;
}
```

---

# animation-timing-function

Animatsiyaning tezlashish dinamikasi.

```css id="2b3c4d"
animation-timing-function: ease;
animation-timing-function: linear;
animation-timing-function: ease-in;
animation-timing-function: ease-out;
animation-timing-function: ease-in-out;
```

---

# Shorthand (qisqa yozuv)

```css id="5e6f7g"
/* name | duration | timing | delay | count | direction | fill-mode */
animation: siljish 2s ease-in-out 0.5s infinite alternate forwards;
```

---

# Ko'p animatsiya birga

```css id="8h9i1j"
.box {
    animation:
        siljish 2s ease infinite,
        rangOzgar 3s linear infinite;
}
```

Vergul bilan ajratiladi.

---

# Amaliy misollar

---

## FadeIn

```css id="2k3l4m"
@keyframes fadeIn {
    from { opacity: 0; }
    to   { opacity: 1; }
}

.box { animation: fadeIn 1s ease forwards; }
```

---

## Spinner

```css id="5n6o7p"
@keyframes spin {
    from { transform: rotate(0deg); }
    to   { transform: rotate(360deg); }
}

.loader { animation: spin 1s linear infinite; }
```

---

## Pulse

```css id="8q9r1s"
@keyframes pulse {
    0%   { transform: scale(1); }
    50%  { transform: scale(1.1); }
    100% { transform: scale(1); }
}

.box { animation: pulse 1.5s ease-in-out infinite; }
```

---

## Shake (Titratish)

```css id="2t3u4v"
@keyframes shake {
    0%   { transform: translateX(0); }
    25%  { transform: translateX(-10px); }
    50%  { transform: translateX(10px); }
    75%  { transform: translateX(-10px); }
    100% { transform: translateX(0); }
}

.box { animation: shake 0.5s ease; }
```

Xato kiritilganda form maydonini titratish uchun ishlatiladi.

---

# transition vs animation farqi

* `transition` — faqat hover yoki holat o'zgarganda ishlaydi
* `animation` — o'zi avtomatik ishlaydi, JavaScript shart emas

---

# animation juda ko'p ishlatiladigan joylar

✅ loading spinner
✅ skeleton loading
✅ fadeIn / fadeOut
✅ slideIn / slideOut
✅ pulse va yurak urishi
✅ shake effekti
✅ cheksiz loop animatsiyalar

---

# Eng ko'p ishlatiladigan pattern

```css id="5w6x7y"
@keyframes animatsiyaNomi {
    from { /* boshlang'ich */ }
    to   { /* tugash */ }
}

.element {
    animation: animatsiyaNomi 1s ease-in-out infinite alternate;
}
```
