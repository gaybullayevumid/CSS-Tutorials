# 01. CSS Transition (O'tishlar)

`transition` xususiyati CSS yordamida elementning bir holatdan ikkinchi holatga silliq o'tishini ta'minlaydi. 

### Asosiy xususiyatlar:
- `transition-property`: Qaysi xususiyat o'zgarishi kerakligi (masalan, `background-color`, `transform` yoki hammasi uchun `all`).
- `transition-duration`: O'zgarish qancha vaqt davom etishi (masalan, `0.5s` yoki `500ms`).
- `transition-timing-function`: O'zgarish tezligining dinamikasi (`ease`, `linear`, `ease-in-out` kabi).
- `transition-delay`: O'zgarishni boshlashdan oldin qancha vaqt kutish kerakligi.

### Shorthand (Qisqa) Sintaksis:
```css
.box {
  /* property name | duration | timing function | delay */
  transition: all 0.3s ease-in-out 0s;
}
```

### Nima uchun muhim?
Transitionlar veb-saytni ko'zni charchatmaydigan, interaktiv va professional ko'rsatuvchi eng oddiy va qulay vositadir. Ayniqsa, tugmalar (buttons) ustiga sichqoncha olib borilganda (`:hover` holatida) keng qo'llaniladi.
