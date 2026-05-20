# 09. CSS Animation Timing (Vaqt Funksiyalari)

`animation-timing-function` animatsiyaning tezlashish va sekinlashish dinamikasini belgilaydi. Animatsiya davomida tezlik bir xil qoladimi yoki boshida sekin keyin tezlashadimi — buni shu xususiyat orqali nazorat qilamiz.


# Eng muhim narsa

Timing function animatsiyaning qanday HARAKAT QILISHINI belgilaydi:

✅ sekin-sekin silliq
✅ tez va keskin
✅ sakrab-sakrab

Animatsiya davomiyligi o'zgarmaydi — faqat harakat xarakteri o'zgaradi.

---

# ease (default)

```css id="1a2b3c"
animation-timing-function: ease;
```

* sekin boshlanadi
* o'rtada tezlashadi
* oxirida sekinlashadi

Eng tabiiy ko'rinadigan harakat.

Ko'pchilik animatsiyalarda default ishlatiladi.

---

# linear

```css id="4d5e6f"
animation-timing-function: linear;
```

* boshidan oxirigacha bir xil tezlik
* hech qanday tezlashish yoki sekinlashish yo'q

Loading spinner va cheksiz aylanuvchi elementlar uchun ishlatiladi.

---

# ease-in

```css id="7g8h9i"
animation-timing-function: ease-in;
```

* juda sekin boshlanadi
* keyin tezlashib ketadi
* oxirida tez tugaydi

Elementning ekrandan chiqib ketish animatsiyasida ishlatiladi.

---

# ease-out

```css id="2j3k4l"
animation-timing-function: ease-out;
```

* tez boshlanadi
* oxirida sekinlashadi
* yumshoq to'xtaydi

Elementning ekranga kirish (slideIn, fadeIn) animatsiyasida ishlatiladi.

---

# ease-in-out

```css id="5m6n7o"
animation-timing-function: ease-in-out;
```

* sekin boshlanadi
* o'rtada tezlashadi
* oxirida yana sekinlashadi

`ease` ga o'xshaydi, lekin sekinlashish yanada yaqqolroq.

Professional animatsiyalarda eng ko'p ishlatiladigan qiymat.

---

# steps()

```css id="8p9q1r"
animation-timing-function: steps(4);
```

* animatsiyani `n` ta aniq bosqichlarga bo'ladi
* silliq emas, sakrab-sakrab o'tadi

Qayerda ishlatiladi:

* eski pikselli o'yin spritelari
* analog soat mili effekti
* yozuv mashine effekti (typewriter)

---

## steps misoli: typewriter

```css id="2s3t4u"
@keyframes typing {
    from { width: 0; }
    to   { width: 200px; }
}

.text {
    animation: typing 3s steps(20) forwards;
    overflow: hidden;
    white-space: nowrap;
}
```

Matn harfma-harf yozilib chiqadi.

---

# cubic-bezier()

O'zingning maxsus tezlik funksiyangni yaratish.

```css id="5v6w7x"
animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
```

4 ta qiymat: `x1, y1, x2, y2`

---

## Tayyor cubic-bezier qiymatlari

```css id="8y9z1a"
/* ease */
cubic-bezier(0.25, 0.1, 0.25, 1)

/* ease-in */
cubic-bezier(0.42, 0, 1, 1)

/* ease-out */
cubic-bezier(0, 0, 0.58, 1)

/* ease-in-out */
cubic-bezier(0.42, 0, 0.58, 1)
```

Brauzerning DevTools da vizual tarzda tahrirlash mumkin.

---

# Qaysi timing qachon ishlatiladi?

```text
ease           → umumiy foydalanish (default)
linear         → spinner, cheksiz aylanish
ease-in        → elementni olib ketish
ease-out       → elementni olib kelish
ease-in-out    → professional animatsiyalar
steps(n)       → pikselli / bosqichli effekt
cubic-bezier   → maxsus, o'ziga xos harakat
```

---

# Shorthand ichida

```css id="2b3c4d"
.box {
    animation: siljish 1s ease-in-out infinite;
    /*                    ^^^^^^^^^^^^          */
}
```

Uchinchi qiymat — timing function.

---

# Hover misoli

```css id="5e6f7g"
.box {
    transition: transform 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.box:hover {
    transform: scale(1.2);
}
```

Element elastik tarzda kattayadi — spring effekti.

---

# animation-timing juda ko'p ishlatiladigan joylar

✅ tugma hover effektlari
✅ modal oyna kirishi
✅ slideIn / slideOut
✅ loading spinner (linear)
✅ typewriter effekti (steps)
✅ elastik spring effektlar (cubic-bezier)
✅ professional micro-animatsiyalar

---

# Eng ko'p ishlatiladiganlari

```css id="8h9i1j"
animation-timing-function: ease;
animation-timing-function: linear;
animation-timing-function: ease-in-out;
animation-timing-function: steps(5);
animation-timing-function: cubic-bezier(0.34, 1.56, 0.64, 1);
```
