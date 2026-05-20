# 01. CSS Transition (O'tishlar)


## Transition nima? Nima uchun kerak?

Tasavvur qiling: siz tugmachaga sichqonchani olib borganingizda uning rangi **bir zumda** o'zgaradi — bu qo'pol va yoqimsiz ko'rinadi.

Endi tasavvur qiling — rang asta-sekin, silliq tarzda o'zgaradi — bu esa professional va zamonaviy ko'rinadi.

Mana shu **"silliqlik"ni** ta'minlaydigan narsa — `transition`!

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

## Transition sintaksisi

```txt
transition: property duration timing-function delay;
```

## index.html ning tuzilmasi

`index.html` faylida 3 ta quti bor. Ularning hammasi `body` va `.container` ichiga joylashtirilgan.

### Umumiy uslublar (barcha qutilar uchun)

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f4f7f6;
    color: #333;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 50px;
}
```

Bu yerda:
- `font-family` — brauzerning standart shrifti o'rniga chiroyli shrift tanlanmoqda
- `background-color: #f4f7f6` — butun sahifaning foni och kulrang
- `display: flex` + `flex-direction: column` + `align-items: center` — barcha elementlarni o'rtaga tekislab vertikal joylashtirilmoqda
- `padding: 50px` — sahifa chegarasidan 50px bo'sh joy qoldirilmoqda

```css
.container {
    display: flex;
    gap: 20px;
    margin-top: 30px;
}
```

Bu yerda:
- `display: flex` — 3 ta qutini **yonma-yon** qo'yadi
- `gap: 20px` — qutichalar o'rtasida 20px bo'shliq
- `margin-top: 30px` — sarlavhadan 30px pastda joylashadi

---

### Umumiy `.box` uslubi (3 ta quticha uchun umumiy)

```css
.box {
    width: 150px;
    height: 150px;
    background-color: #3498db;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    border-radius: 8px;
    cursor: pointer;
    text-align: center;
    padding: 10px;
}
```

Har bir qatorni tushuntiramiz:

| Xususiyat | Qiymati | Nima uchun? |
|---|---|---|
| `width: 150px` | 150px | Qutining kengligi |
| `height: 150px` | 150px | Qutining balandligi — kvadrat shakl |
| `background-color: #3498db` | Ko'k rang | Barcha qutilarning boshlang'ich rangi |
| `color: white` | Oq | Qutidagi matn rangi |
| `display: flex` | flex | Matnni o'rtaga joylashtirish uchun |
| `justify-content: center` | center | Matnni gorizontal markazga |
| `align-items: center` | center | Matnni vertikal markazga |
| `font-weight: bold` | bold | Qalin matn |
| `border-radius: 8px` | 8px | Burchaklar biroz yumaloq |
| `cursor: pointer` | pointer | Ustiga borganda qo'l belgisi ko'rinadi |
| `text-align: center` | center | Matnni o'rtaga hizalanadi |
| `padding: 10px` | 10px | Matn chegaradan 10px ichkarida bo'ladi |

> `.box` — bu umumiy stillar. Har bir qutiga o'z `transition` va `:hover` qo'shiladi.

---

## 1-Quti: Oddiy rang o'zgarishi

### HTML:
```html
<div class="box box-1">Rang o'zgarishi<br>(0.5s ease)</div>
```

Bu element ikki klassga ega: `box` (umumiy) va `box-1` (o'ziga xos).

### CSS:
```css
/* 1. Oddiy transition */
.box-1 {
    transition: background-color 0.5s ease;
}
.box-1:hover {
    background-color: #e74c3c;
}
```

### Tahlil:

**`transition: background-color 0.5s ease;`** — bu qator 3 qismdan iborat:

| Qism | Qiymati | Ma'nosi |
|---|---|---|
| `background-color` | xususiyat nomi | FAQAT rang o'zgarganda animatsiya bo'lsin |
| `0.5s` | davomiylik | 0.5 soniya (500 millisekund) ichida |
| `ease` | tezlik grafigi | Sekin boshlab, tezlashib, yana sekinlashadi |

**`.box-1:hover { background-color: #e74c3c; }`**
- `:hover` — foydalanuvchi sichqonchani ustiga olib kelganda ishlaydi
- `#e74c3c` — qizil rang (Flat UI ranglar palitrasidan)

**Nima sodir bo'ladi?**
1. Sichqoncha keladi → `#3498db` (ko'k) → 0.5s ichida silliq → `#e74c3c` (qizil)
2. Sichqoncha ketadi → `#e74c3c` (qizil) → 0.5s ichida silliq → `#3498db` (ko'k) ga **avtomatik** qaytadi

> Transition ikki tomonga ham ishlaydi — orqaga qaytish uchun alohida kod yozish shart emas!

**Agar `transition` bo'lmaganda nima bo'lardi?**
```css
/* transition YO'Q bo'lganda: */
.box-1 {
    /* transition yo'q */
}
.box-1:hover {
    background-color: #e74c3c; /* bir zumda o'zgaradi — qo'pol */
}
```

---

## 2-Quti: Bir nechta xususiyatga transition

### HTML:
```html
<div class="box box-2">Rang va Shakl<br>(0.5s ease)</div>
```

### CSS:
```css
/* 2. Bir nechta xususiyatlarga transition */
.box-2 {
    transition: background-color 0.5s ease, border-radius 0.5s ease;
}
.box-2:hover {
    background-color: #2ecc71;
    border-radius: 50%;
}
```

### Tahlil:

**`transition: background-color 0.5s ease, border-radius 0.5s ease;`**

Vergul (`,`) bilan bir nechta xususiyat yozildi. Har biri alohida boshqarilmoqda:

```
transition: background-color 0.5s ease,   ← birinchi xususiyat
            border-radius    0.5s ease;   ← ikkinchi xususiyat
```

| Xususiyat | Davomiylik | Tezlik | Natija |
|---|---|---|---|
| `background-color` | 0.5s | ease | Ko'k → Yashil |
| `border-radius` | 0.5s | ease | To'rtburchak → Doira |

**`.box-2:hover`:**
- `background-color: #2ecc71` — yashil rang
- `border-radius: 50%` — to'rtburchakdan doiraga o'tish (50% = to'liq doira)

**Nima sodir bo'ladi?**
Bir vaqtning o'zida ikkala o'zgarish birga sodir bo'ladi — ham rang, ham shakl 0.5s ichida silliq o'zgaradi.

**Nega `border-radius: 50%` doira hosil qiladi?**
```
Kvadrat (150px × 150px):
┌─────────┐
│         │        border-radius: 50% qo'shilganda:
│         │   →        (  )
│         │            (  )
└─────────┘
```
Har burchakdan 50% (ya'ni 75px) yumaloqlash — to'liq doira!

**Farqli davomiylik ham bersa bo'ladi:**
```css
/* Rang 0.3s da, shakl 1s da o'zgaradi */
transition: background-color 0.3s ease, border-radius 1s linear;
```

---

## 3-Quti: `all` va `cubic-bezier`

### HTML:
```html
<div class="box box-3">Barcha xususiyatlar<br>(all 0.8s)</div>
```

### CSS:
```css
/* 3. Barcha xususiyatlarga transition (all) */
.box-3 {
    transition: all 0.8s cubic-bezier(0.25, 0.8, 0.25, 1);
    border: 2px solid transparent;
}
.box-3:hover {
    background-color: #9b59b6;
    color: #fff;
    transform: translateY(-10px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.2);
    border: 2px solid #8e44ad;
}
```

### Tahlil:

**`transition: all 0.8s cubic-bezier(0.25, 0.8, 0.25, 1);`**

| Qism | Qiymati | Ma'nosi |
|---|---|---|
| `all` | barcha xususiyatlar | Qaysi xususiyat o'zgarsa — hammasi animatsiya |
| `0.8s` | davomiylik | 0.8 soniya — birinchi qutidan sekinroq |
| `cubic-bezier(...)` | tezlik grafigi | O'zim yasagan tezlik egri chizig'i |

**`border: 2px solid transparent;`** — boshlang'ich holat
- Chegara bor, lekin rangi shaffof (ko'rinmaydi)
- Hover da rangi o'zgarganda, chegara paydo bo'lgandek ko'rinadi — lekin aslida u allaqachon bor edi!
- Bu — o'lcham siltanishining (layout jump) oldini olish uchun qilingan aqlli yechim.

**`.box-3:hover` da 4 ta o'zgarish:**

```css
background-color: #9b59b6;                /* 1. Rang: ko'k → binafsha */
color: #fff;                              /* 2. Matn rangi (allaqachon oq, lekin aniq) */
transform: translateY(-10px);             /* 3. Yuqoriga 10px ko'tariladi */
box-shadow: 0 10px 20px rgba(0,0,0,0.2); /* 4. Soya paydo bo'ladi */
border: 2px solid #8e44ad;               /* 5. Chegara rangi: shaffof → binafsha */
```

`all` tufayli bularning **barchasi** 0.8s ichida birgalikda silliq o'zgaradi.

---

### `cubic-bezier` nima?

`ease`, `linear`, `ease-in` kabi tayyor qiymatlar yetarli bo'lmaganda, **o'z tezlik grafiging**ni yaratish uchun ishlatiladi.

```css
cubic-bezier(x1, y1, x2, y2)
              ↑   ↑   ↑   ↑
      Birinchi kontrol nuqta  Ikkinchi kontrol nuqta
```

Bu fayldagi qiymat: `cubic-bezier(0.25, 0.8, 0.25, 1)`

```
Tezlik:  ^
     1.0 |                    ___---
         |               ____/
         |          ____/
         |     ____/
     0.0 |____/
         +-------------------------> Vaqt
              0.25      0.8   1.0
```

Bu grafik: boshida sekin, keyin tezlashadi, oxirida juda tekis tugaydi — tabiiy his beradi.

**Standart qiymatlar bilan solishtirish:**

```css
ease:        cubic-bezier(0.25, 0.1,  0.25, 1.0)  /* o'xshash */
ease-in-out: cubic-bezier(0.42, 0.0,  0.58, 1.0)
linear:      cubic-bezier(0.0,  0.0,  1.0,  1.0)

/* O'yin effekti (ortga ketib oldinга) */
cubic-bezier(0.68, -0.55, 0.27, 1.55)
```

> **Qurol:** [cubic-bezier.com](https://cubic-bezier.com) — grafik ustida bosib qiymatlarni vizual ko'rish mumkin!

---

## Asosiy 4 ta xususiyat — qisqacha

`transition` shorthand aslida 4 ta alohida xususiyatning qisqa yozuvi:

```css
/* Bu ikki yozuv bir xil natija beradi: */

/* Shorthand: */
transition: background-color 0.5s ease 0s;

/* Alohida-alohida: */
transition-property:        background-color;
transition-duration:        0.5s;
transition-timing-function: ease;
transition-delay:           0s;
```

**Tartib muhim!**

```css
transition: [property] [duration] [timing-function] [delay]
              Nima?       Qancha?    Qanday?           Qachon?
```

Agar `delay` ishlatmasangiz, uni yozmasangiz ham bo'ladi (default `0s`):
```css
transition: background-color 0.5s ease; /* delay yo'q = darhol boshlanadi */
```

---

## `transition-timing-function` qiymatlari

`transition-timing-function` — animatsiya davomida **tezlikning qanday o'zgarishini** boshqaradi.

---

### `ease` — sekin boshlanadi, tezlashadi, sekin tugaydi (default)

> _"transition will start slow, then go fast, and end slow"_

```css
transition-timing-function: ease;
/* yoki shorthand da: */
transition: background-color 0.5s ease;
```

```
Tezlik:  ^
         |          ___
         |        /     \
         |      /         \
         |    /             \
         |___/               \___
         +-------------------------> Vaqt
           Sekin  Tez  Tez  Sekin
```

- Animatsiya **sekin** boshlanadi
- O'rtada **tezlashadi**
- Oxirida yana **sekinlashadi**
- Bu eng tabiiy his beradi — shuning uchun **default** qiymat
- Aksariyat hover effektlar uchun ideal

```css
/* Misol: */
.box-1 {
    transition: background-color 0.5s ease; /* index.html da ham ease ishlatilgan */
}
```

---

### `linear` — boshidan oxirigacha bir xil tezlik

> _"transition will keep the same speed from start to end"_

```css
transition-timing-function: linear;
transition: background-color 0.5s linear;
```

```
Tezlik:  ^
         |  ________________________
         | /                        \
         |/                          \
         +-------------------------> Vaqt
           Bir xil  Bir xil  Bir xil
```

- Boshidan oxirigacha **bir xil tezlik** — o'zgarmaydi
- Mexanik, sun'iy his beradi
- Tabiiy ko'rinmaydi (real hayotda narsalar shunday harakatlanmaydi)
- Faqat maxsus holatlarda ishlatiladi

```css
/* Qachon ishlatiladi: */
.progress-bar { transition: width 2s linear; }     /* yuklanish paneli */
.spinner      { transition: transform 1s linear; } /* aylanayotgan loading */
.clock-hand   { transition: transform 1s linear; } /* soat mili */
```

---

### `ease-in` — sekin boshlanadi (oxirida tezlashadi)

> _"transition will start slow"_

```css
transition-timing-function: ease-in;
transition: background-color 0.5s ease-in;
```

```
Tezlik:  ^
         |                    ______
         |                 __/
         |             ___/
         |          __/
         |_________/
         +-------------------------> Vaqt
           Juda sekin ...  Tez  Tez
```

- Animatsiya **juda sekin** boshlanadi
- Oxiriga borib **tezlashib** tugaydi
- Foydalanuvchiga biroz og'ir his beradi — chunki boshida "nima bo'lyapti?" deydi
- Odatda **element sahifadan chiqayotganda** ishlatiladi

```css
/* Qachon ishlatiladi: */
.modal.closing { transition: opacity 0.3s ease-in; } /* modal yopilish */
.card.removing { transition: transform 0.4s ease-in; } /* karta o'chirilish */
```

---

### `ease-out` — tez boshlanadi (oxirida sekinlashadi)

> _"transition will end slow"_

```css
transition-timing-function: ease-out;
transition: background-color 0.5s ease-out;
```

```
Tezlik:  ^
         |  ______
         | /      \___
         |/            \___
         |                  \___
         |                       \___
         +-------------------------> Vaqt
           Tez  Tez  ...  Sekin  Juda sekin
```

- Animatsiya **tez** boshlanadi
- Oxirida **sekinlashib** to'xtaydi
- Eng tabiiy his beradi — real hayotda narsalar ham shunday sekinlashadi
- **Element sahifaga kirayotganda** ideal

```css
/* Qachon ishlatiladi: */
.modal.opening    { transition: transform 0.4s ease-out; } /* modal ochilish */
.dropdown.opening { transition: opacity 0.3s ease-out; }   /* dropdown ochilish */
.toast            { transition: translateY 0.3s ease-out; } /* bildirishnoma */
```

---

### `ease-in-out` — sekin boshlanadi va sekin tugaydi

> _"transition will have a slow start and end"_

```css
transition-timing-function: ease-in-out;
transition: background-color 0.5s ease-in-out;
```

```
Tezlik:  ^
         |           ___
         |         /     \
         |       /         \
         |     /             \
         |____/               \____
         +-------------------------> Vaqt
          Sekin   Tez   Tez   Sekin
```

- `ease` ga o'xshaydi, lekin **ikki tomonda sekinlash kuchliroq**
- Juda silliq va professional his beradi
- Uzoqroq animatsiyalar uchun (0.5s dan yuqori) ideal

```css
/* ease vs ease-in-out farqi: */
transition: transform 0.3s ease;        /* qisqa animatsiyalarda yaxshi */
transition: transform 0.8s ease-in-out; /* uzoq animatsiyalarda yaxshi */

/* Qachon ishlatiladi: */
.drawer  { transition: transform 0.5s ease-in-out; } /* yon panel */
.carousel{ transition: transform 0.6s ease-in-out; } /* slayder */
```

---

### `cubic-bezier(n,n,n,n)` — o'z qiymatlaringni belgilab bera oladi

> _"lets you define your own values in a cubic-bezier function"_

```css
transition-timing-function: cubic-bezier(n, n, n, n);
/* index.html da: */
transition: all 0.8s cubic-bezier(0.25, 0.8, 0.25, 1);
```

Yuqoridagi barcha qiymatlar (`ease`, `linear`, va boshqalar) aslida `cubic-bezier` ning maxsus holatlaridir:

```css
ease:        cubic-bezier(0.25, 0.1,  0.25, 1.0)
linear:      cubic-bezier(0.0,  0.0,  1.0,  1.0)
ease-in:     cubic-bezier(0.42, 0.0,  1.0,  1.0)
ease-out:    cubic-bezier(0.0,  0.0,  0.58, 1.0)
ease-in-out: cubic-bezier(0.42, 0.0,  0.58, 1.0)
```

**4 ta son nimani bildiradi?**

```css
cubic-bezier(x1, y1, x2, y2)
```

- `x1, y1` — birinchi kontrol nuqta (0 dan 1 gacha)
- `x2, y2` — ikkinchi kontrol nuqta (0 dan 1 gacha)

**index.html dagi `cubic-bezier(0.25, 0.8, 0.25, 1)` qanday ishlaydi:**

```
Tezlik:  ^
     1.0 |                    ___---
         |               ____/
         |          ____/
         |     ____/
     0.0 |____/
         +-------------------------> Vaqt
              0.25      0.8   1.0
```

Natija: boshida sekin, keyin tezlashib, oxirida juda tekis to'xtaydi.

**Qiziq `cubic-bezier` qiymatlari:**

```css
/* Orqaga ketib, keyin oldinга (spring effect) */
cubic-bezier(0.68, -0.55, 0.27, 1.55)

/* Tez kirib, sekin chiqish */
cubic-bezier(0.4, 0, 0.2, 1)  /* Material Design standart */

/* "Bounce" hissi */
cubic-bezier(0.34, 1.56, 0.64, 1)
```

> **Qurol:** [cubic-bezier.com](https://cubic-bezier.com) — grafik ustida bosib qiymatlarni vizual sozlash mumkin!

---

### Qiymatlar qisqacha jadvali

| Qiymat | Ta'rif | Qachon ishlatish |
|---|---|---|
| `ease` | Sekin → Tez → Sekin **(default)** | Aksariyat hover effektlar |
| `linear` | Boshidan oxirigacha bir xil tezlik | Progress bar, loading, soat |
| `ease-in` | Sekin boshlanadi | Element sahifadan chiqayotganda |
| `ease-out` | Sekin tugaydi (tez boshlanadi) | Element sahifaga kirayotganda |
| `ease-in-out` | Sekin boshlanadi **va** tugaydi | Modal, drawer, slayder |
| `cubic-bezier()` | O'z qiymatlaringni belgilaysan | O'ziga xos animatsiya kerakda |

---

## Keng tarqalgan xatolar

### Xato 1: `transition` ni hover ga qo'yish

```css
/* XATO: Hover da berilsa, orqaga qaytish animatsiyasiz bo'ladi */
.box-1 {
    background-color: #3498db;
    /* transition yo'q */
}
.box-1:hover {
    background-color: #e74c3c;
    transition: background-color 0.5s ease; /* bu joy noto'g'ri! */
}
```

Natija: Kelishda silliq, ketishda bir zumda o'zgaradi.

```css
/* TO'G'RI: Asosiy holatda bering */
.box-1 {
    background-color: #3498db;
    transition: background-color 0.5s ease; /* to'g'ri joy */
}
.box-1:hover {
    background-color: #e74c3c;
}
```

---

### Xato 2: Animatsiya qilib bo'lmaydigan xususiyat

```css
/* Ishlamaydi: display animatsiya qilinmaydi */
.menu {
    display: none;
    transition: display 0.3s ease; /* bekor! */
}
.menu.active {
    display: block; /* bir zumda paydo bo'ladi */
}

/* TO'G'RI: opacity + visibility */
.menu {
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.3s ease, visibility 0.3s ease;
}
.menu.active {
    opacity: 1;
    visibility: visible;
}
```

---

### Xato 3: `border` qo'shish/olib tashlash (o'lcham siltanishi)

```css
/* XATO: Hover da border QO'SHILSA, element kattalashadi → siltanish */
.box {
    /* border yo'q */
}
.box:hover {
    border: 2px solid #8e44ad; /* element 4px kattalashadi! */
}

/* TO'G'RI (index.html da qilingan usul): Shaffof border oldindan berish */
.box-3 {
    border: 2px solid transparent; /* bor, lekin ko'rinmaydi */
}
.box-3:hover {
    border: 2px solid #8e44ad; /* faqat rangi o'zgaradi, o'lcham o'zgarmaydi */
}
```

---

## Animatsiya qilsa bo'ladigan va bo'lmaydigan xususiyatlar

**Bo'ladigan (raqamga ega xususiyatlar):**

```css
/* Ranglar */
background-color, color, border-color, box-shadow

/* O'lchamlar */
width, height, padding, margin, border-width, font-size

/* Ko'rinish */
opacity, transform

/* Joylashuv */
top, left, right, bottom
```

**Bo'lmaydigan (raqamsiz xususiyatlar):**

```css
display: none → block   /* bir zumda o'zgaradi */
position: fixed → static /* bir zumda o'zgaradi */
font-family             /* bir zumda o'zgaradi */
```

---

## Performance (ishlash tezligi)

Hamma xususiyat bir xil "narxda" animatsiya qilinmaydi:

**Tez (GPU tomonidan qayta chiziladi):**
```css
transform   /* translateY(-10px) — index.html da ishlatilgan */
opacity
```

**Sekin (butun sahifa layoutini qayta hisoblaydi):**
```css
width, height, margin, padding, top, left
```

Shuning uchun `index.html` da element ko'tarilishi uchun `top` emas, `transform: translateY(-10px)` ishlatilgan — bu to'g'ri yondashuv!

---

## Xulosa: Qachon nima ishlatish kerak?

| Vaziyat | Yechim | Misol (index.html dan) |
|---|---|---|
| Bitta xususiyat | aniq nom yozing | `.box-1` — faqat `background-color` |
| 2-3 ta xususiyat | vergul bilan ajrating | `.box-2` — rang va shakl |
| Ko'p o'zgarish | `all` ishlating | `.box-3` — 4 ta o'zgarish |
| O'ziga xos tezlik | `cubic-bezier()` | `.box-3` da ishlatilgan |
| Layout siltanmasin | shaffof border bering | `.box-3 { border: 2px solid transparent }` |

---

## Esda saqlash uchun

```css
/* Minimal (ishlaydi): */
transition: background-color 0.3s;

/* To'liq (barcha qismlar): */
transition: background-color 0.5s ease 0s;
/*          Nima?            Vaqt  Qanday? Qachon? */

/* Bir nechta (vergul bilan): */
transition: background-color 0.5s ease,
            border-radius    0.5s ease;

/* Hammasi uchun: */
transition: all 0.8s cubic-bezier(0.25, 0.8, 0.25, 1);
```
