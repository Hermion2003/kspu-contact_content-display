## 9-ИЙ ЕТАП
На цьому етапі за допомогою файлу script.js було реалізовано відображення даних про працівників на веб-сторінці. Скрипт динамічно завантажує інформацію з файлу data.js та генерує HTML-контент, який потім виводиться на сторінці.

script.js відповідає за маніпуляцію з DOM, що дозволяє створювати елементи списку, заповнювати їх відповідними даними (ім'я, посада, контактна інформація) і відображати на сторінці у вигляді структурованого списку або таблиці. Це дозволяє користувачам бачити актуальні дані про працівників університету без необхідності вручну оновлювати HTML.

```js
const container = document.querySelector("#contacts");

data.forEach(section => {
    let sectionHTML = '';
    if (section.title != null) {
        sectionHTML += `<div class="title"><h2>${section.title}</h2></div>`
    }
    sectionHTML += '  <div class="threeColumnContainer">'
    section.blocks.forEach(block => {
        sectionHTML += `
          
                <div class="smallBlueBlock">
                    <div class="innerBlock">
                        <div class="front">
                                <img alt="Herb" src="${section.img}">
                            <h3>${block.front}</h3>
                        </div>
                        <div class="back">
                            ${block.back}
                        </div>
                    </div>
                </div>
           
        `;
    });
    sectionHTML += ' </div>'
    container.innerHTML += sectionHTML;
});
