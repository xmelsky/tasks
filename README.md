# Tasks-check - чек-лист для проверки тасков RS School

Позволяет быстро подготовить форму проверки для любого таска, который оценивается по принципу: _указывается максимальное количество баллов за полностью реализованный пункт, снимается половина (50%) баллов, если пункт выполнен с ошибками, и не начисляются баллы вовсе, если пункт требований не реализован_

Структура списка объектов в массиве пунктов задания:

```javascript
    export const task = "Some task title"; // this will be rendered as page title

    export const criteria = [
{
    type: "title", // this will be rendered as sub header
    title: "Общие требования"
},
{
    text: "Some text here, also with HTML tags <strong>strong</strong>. You need escape HTML tags to use it as regular text (prevent HTML rendering)",
    max: 20, // max points amount for this subtask
},
{
    text: "Another subtask here",
    max: 10
},
{
    type: "title", // another sub header right above the other tasks
    title: "Новые требования"
},
{
    text: "Neque porro quisquam est qui dolorem ipsum quia dolor <strong>sit amet</strong>",
    max: 5}, // etc...
```


## Features:
 ### 1. Три состояния выполнения пункта задания:
    - green: пункт выполнен полностью (100% от оценки за этот пункт);
    - yellow: пункт выполнен с ошибками (50% от оценки за этот пункт);
    - red: пункт требований не реализован (0 баллов);

    Состояния каждого пункта задания при клике сменяются по кругу, начиная с зеленого

    При этом общий скор за задание меняется соответственно. Числа округляются до 1 знака после запятой.

### 2. Добавление отзыва/замечания к конкретному пункту задания:
    - При наведении на пункт задания появляется ссылка Add feedback
    - При клике на ссылку появляется textarea с фокусом на этом поле и выделенным текстом (в случае, если ранее текст был сохранен)
    - Используйте Ctrl + Enter чтобы сохранить отзыв
    - Используйте Esc  чтобы отменить ввод/правку отзыва

### 3. Для удобства и самопроверки ведется подсчет проверенных пунктов задания (нельзя вызвать форму отчета проверки, если не остались не проверенные пункты)
    - Чтобы сбросить текущий результат проверки нажмите кнопку Сброс. Форма вернется в изначальное состояние

### 4. Для удобства, чтобы случайно не переключить уже проверенный пункт, используйте Ctrl + left click по пункту задания, чтобы сделать его неактивным (зафиксировать). Используйте эту же комбинацию чтобы разблокировать пункт.
    - При блокировке и разблокировке флаг не переключается

### 5. Форма отчета проверки
    - Итоговая форма отчета проверки рендерит список проверенных пунктов с учетом трех разделов (выполненные пункты, частично выполненные и незасчитанные пункты).
    - Если на каком-либо пункте был оставлен отзыв, то он будет также сгенерирован под этим пунктом в финальном отчете (мелким шрифтом)
    - Используйте линк "Скопировать в буфер", чтобы быстро скопировать отчет. Текст копируется с соответствующими переносами строк



[Try it online](https://xmelsky.github.io/cross-check-singolo/)

