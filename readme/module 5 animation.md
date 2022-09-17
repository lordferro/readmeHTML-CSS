transition-property: <свойство> background-color, transform
transition-duration: <время> 500ms;
transition-timing-function: <функция распределения времени> linear
transition-delay: <задержка>

Краткая запись перехода transition: [property] [duration] [timing-function] [delay]

Если анимируется несколько свойств, то набор значений для каждого из них разделяется запятой. Необходимо обязательно указать свойство и время перехода, функцию времени и задержку можно не указывать, тогда для них будут использованы значения по умолчанию.

transition: background-color 500ms linear, transform 500ms ease-in-out;

Напишем простой сценарий перехода цвета фона и вращения блока. Сначала блок должен изменить цвет, и только после этого начать вращаться. 
transition: background-color 500ms linear, transform 500ms ease-in-out 500ms;

