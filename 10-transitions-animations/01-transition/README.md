# 01. CSS Transition (O'tishlar)

> **Amaliy fayl:** `index.html` ni brauzerda ochib, sichqonchani qutilar ustiga olib boring va animatsiyalarni jonli ko'ring!

---

## Transition nima? Nima uchun kerak?

Tasavvur qiling: siz tugmachaga sichqonchani olib borganingizda uning rangi **bir zumda** o'zgaradi - bu qo'pol va yoqimsiz ko'rinadi.  
Endi tasavvur qiling - rang asta-sekin, silliq tarzda o'zgaradi - bu esa professional va zamonaviy ko'rinadi.

Mana shu **"silliqlik"ni** ta'minlaydigan narsa - `transition`!

```
Transition (o'tish) = element A holatidan B holatiga o'tganda o'zgarishni VAQT ichida silliq amalga oshirish
```

Transition **bo'lmaganda:**
```
Holat: NORMAL (ko'k)  ----bir zumda----> Holat: HOVER (qizil)
```

Transition **bo'lganda:**
```
Holat: NORMAL (ko'k)  ----0.5 soniya ichida silliq----> Holat: HOVER (qizil)
```

---

## Asosiy 4 ta xususiyat

Transition 4 ta kichik xususiyatdan iborat:

### 1. `transition-property` — Nima o'zgarsin?
Animatsiya qilinishi kerak bo'lgan CSS xususiyatini ko'rsatadi.

```css
transition-property: background-color; /* faqat rang */
transition-property: transform;        /* faqat transform */
transition-property: all;              /* barcha o'zgarishlar */
```

### 2. `transition-duration` — Qancha vaqt?
O'zgarish qancha vaqt ichida sodir bo'lishini belgilaydi.

```css
transition-duration: 0.5s;   /* yarim soniya */
transition-duration: 500ms;  /* 500 millisekund (bir xil) */
transition-duration: 2s;     /* 2 soniya (sekin) */
```

### 3. `transition-timing-function` — Qanday tezlikda?
O'zgarishning boshlangani va tugashi orasidagi tezlik o'zgarishini boshqaradi.

```css
transition-timing-function: ease;        /* Sekin → Tez → Sekin (default) */
transition-timing-function: linear;      /* Har doim bir xil tezlik */
transition-timing-function: ease-in;     /* Sekin boshlanadi, tezlashadi */
transition-timing-function: ease-out;    /* Tez boshlanadi, sekinlashadi */
transition-timing-function: ease-in-out; /* Sekin → Tez → Sekin (kuchli) */
```

### 4. `transition-delay` — Qachon boshlansin?
O'zgarish boshlanishidan oldin qancha vaqt kutish kerakligini belgilaydi.

```css
transition-delay: 0s;    /* Darhol (default) */
transition-delay: 0.3s;  /* 300ms kutib so'ng boshlanadi */
```

---

## Shorthand — Hammasi bir qatorda

Har bir xususiyatni alohida yozish o'rniga, hammasi bitta `transition` xususiyatiga yig'ish mumkin:

```css
/* transition: property  duration  timing-function  delay; */
   transition: background-color  0.5s  ease  0s;
```

**Tartib muhim!** Har doim: `property → duration → timing-function → delay`

---

## index.html Misollar tahlili

Ushbu papkadagi `index.html` faylida 3 ta quti mavjud. Har birini batafsil ko'rib chiqamiz:

---

### 📦 1-Quti: Oddiy rang o'zgarishi

```html
<div class="box box-1">Rang o'zgarishi (0.5s ease)</div>
```

```css
/* Asosiy holat */
.box-1 {
    transition: background-color 0.5s ease;
    /*          ~~~~~~~~~~~~~~~~ ~~~~  ~~~~
                Nima o'zgarsin?  Vaqt  Tezlik grafigi  */
}

/* Hover holatida nimaga o'zgarishi */
.box-1:hover {
    background-color: #e74c3c; /* Ko'kdan → Qizilga */
}
```

**Nima sodir bo'ladi?**  
Sichqoncha quti ustiga kelganda `background-color` xususiyati 0.5 soniya ichida `#3498db` (ko'k) dan `#e74c3c` (qizil) ga **silliq** o'tadi.  
Sichqonchani olib ketganda esa **orqaga** (qizildan ko'kka) ham silliq qaytadi!

---

### 📦 2-Quti: Bir vaqtda bir nechta xususiyat

```html
<div class="box box-2">Rang va Shakl (0.5s ease)</div>
```

```css
.box-2 {
    transition: background-color 0.5s ease, border-radius 0.5s ease;
    /*          ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
                Vergul bilan ajratib, bir nechta xususiyat yozildi! */
}

.box-2:hover {
    background-color: #2ecc71; /* Ko'kdan → Yashilga */
    border-radius: 50%;        /* To'rtburchakdan → Doiraga */
}
```

**Nima sodir bo'ladi?**  
Quti bir vaqtning o'zida ham rangini (ko'k → yashil), ham shaklini (to'rtburchak → doira) **birgalikda silliq** o'zgartiradi.

> **Diqqat:** Vergul (`,`) bilan bir nechta xususiyat uchun har xil davomiylik va timing ham bersa bo'ladi:
> ```css
> transition: background-color 0.5s ease, border-radius 1s linear;
> /*          Rang 0.5s da,              Shakl 1s da o'zgaradi */
> ```

---

### 📦 3-Quti: `all` va `cubic-bezier`

```html
<div class="box box-3">Barcha xususiyatlar (all 0.8s)</div>
```

```css
.box-3 {
    transition: all 0.8s cubic-bezier(0.25, 0.8, 0.25, 1);
    /*          ~~~          ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
                Hammasi      Custom tezlik grafigi          */
    border: 2px solid transparent;
}

.box-3:hover {
    background-color: #9b59b6;                /* Rang o'zgaradi */
    transform: translateY(-10px);             /* Yuqoriga ko'tariladi */
    box-shadow: 0 10px 20px rgba(0,0,0,0.2); /* Soya paydo bo'ladi */
    border: 2px solid #8e44ad;               /* Chegara rangi o'zgaradi */
}
```

**Nima sodir bo'ladi?**  
Hover qilinganda `all` tufayli **barcha 4 ta o'zgarish** (rang, ko'tarilish, soya, chegara) birgalikda 0.8 soniyada silliq amalga oshadi.

**`cubic-bezier` nima?**  
Bu custom (o'z tomonimizdan yaratilgan) tezlik grafigi. `ease`, `linear` kabi tayyor qiymatlar yetarli bo'lmasa, `cubic-bezier` yordamida ixtiyoriy tezlik dinamikasini o'zingiz sozlaysiz.  
[cubic-bezier.com](https://cubic-bezier.com) saytida vizual tarzda sozlash mumkin.

---

## Xulosa: Qachon nima ishlatish kerak?

| Vaziyat | Yechim |
|---|---|
| Faqat bitta narsani animatsiya qilish | `transition: background-color 0.3s ease` |
| 2-3 ta narsani turli vaqtda animatsiya qilish | Vergul bilan ajratib yozish |
| Barcha o'zgarishlarni animatsiya qilish | `transition: all 0.3s ease` |
| `all` ishlatiladigan joyda sekinlashish kuzatilsa | Faqat kerakli xususiyatlarni yozing |

> ⚠️ **`all` ni ehtiyotkorlik bilan ishlating!** `all` ba'zan `width`, `height`, `opacity` kabi kutilmagan xususiyatlarga ham ta'sir qilib, ishlash tezligini (performance) pasaytirishi mumkin. Iloji bo'lsa, aniq xususiyat nomlarini yozing.

---

## Esda saqlash uchun

```
transition: [property] [duration] [timing-function] [delay]
            Nima?       Qancha?    Qanday?            Qachon?
```
