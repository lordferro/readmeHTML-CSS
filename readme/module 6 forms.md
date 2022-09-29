<form>
  <label for="user_email">Email</label>
  <input type="email" name="email" id="user_email" />
Если элемент формы, например поле ввода, вкладывается в <label>, связь создаётся браузером автоматически. Клик по тексту «Email» или «Password» поставит фокус в соотвествующее поле ввода.
<form>
  <label>
    Email
    <input type="email" name="email" />
  </label>
  ________________________

Атрибут autofocus
Поле ввода, которому задан этот атрибут, автоматически получит фокус при загрузке страницы, и в нём можно сразу набирать текст.
 <input type="text" name="username" autofocus />

 _____________________
 Атрибут placeholder
Позволяет отображать текст-подсказку о том, какие данные необходимо ввести в поле, когда элемент <input> пуст. 

!!!!!!!!!!!!!Из-за наличия пробельного символа между открывающим и закрывающим тегом textarea содержимое атрибута placeholder не отображается.
_____________________________
Радио-кнопки (переключатели)
Если задать атрибуту type значение radio - инпут превратится в переключатель (радио-кнопку, radio button). Радио-кнопки всегда идут группами, что позволяет пользователю выбрать одно из множества предопределенных значений.
Каждой радио-кнопке в группе задаётся одинаковое значение атрибута name, иначе браузер не будет знать, что это группа.
В отличие от текстовых полей, в радио-кнопки нельзя вводить данные, поэтому каждой из них необходимо указать значение в атрибуте value. Это значение, которое будет передано на сервер когда пользователь отправит форму.
Логический атрибут checked указывает какой переключатель будет выбран (отмечен) по умолчанию. В группе радио-кнопок в состоянии checked может быть только один элемент.
<form>
  <p>Choose a color:</p>
  <label>
    <input type="radio" name="color" value="red" checked />
    Red
  </label>
  <label>
    <input type="radio" name="color" value="white" />
    White
  </label>
</form>
_____________________________
Чекбоксы name должны быть одинаковые
<form>
  <p>What are your hobbies?</p>
  <ul class="hobby">
    <li>
      <label>
        <input type="checkbox" name="hobby" value="music" checked />
        Music
      </label>
    </li>
    <li>
      <label>
        <input type="checkbox" name="hobby" value="sports" checked />
        Sports
      </label>
    </li>
    <li>
      <label>
        <input type="checkbox" name="hobby" value="reading" />
        Reading
      </label>
    </li>
  </ul>
</form>

.hobby input[type='checkbox'] - selector

!!!!!!!!!!!!Имеет смысл обернуть их в ul
___________________
Числа

Weight with 0.1 step value:
  <input type="number" name="weight" min="0" max="150" step="0.1" value="0" />
  __________________
  Ползунки

    <input
    type="range"
    name="interest_rate"
    value="40"
    min="0"
    max="100"
    step="20"
  />
  ____________________
  Date
    <input type="date" min="1920-01-01" max="2020-01-01" />
  Time
    <input type="time" />
  Date and time
    <input type="datetime-local" min="1920-01-01T00:00" max="2020-01-01T00:00" />

__________________________
 <textarea name="feedback" rows="5" placeholder="Type your message here..."></textarea>
  </label>
  Атрибут rows устанавливает количество строк (высоту), а cols - колонок (ширину). На практике указывается только rows, а ширина элемента контролируется через CSS.
По умолчанию элемент <textarea> можно растягивать по горизонтали и вертикали. Для того чтобы контролировать возможность изменения размера пользователем, в CSS есть свойство resize.
resize: both | horizontal | vertical | none
____________________
Выпадающие списки

value - содержит значение для выбора (если отсутствует, то значение берут из текста);

<select name="month">
  <optgroup label="Summer">
    <option value="s6">June</option>
    <option value="s7">July</option>
    <option value="s8">August</option>
  </optgroup>

  <optgroup label="Autumn">
    <option value="s9">September</option>
    <option value="s10">October</option>
    <option value="s11">November</option>
  </optgroup>
</select>
__________________________
Data list
<label for="fav">Browser selection</label>
<input list="browsers" name="fav" id="fav" />

<datalist id="browsers">
  <option>Edge</option>
  <option>Firefox</option>
  <option>Chrome</option>
  <option>Opera</option>
  <option>Safari</option>
</datalist>
________________________________
Элементы <fieldset> и <legend>

!!!!!!!!!!!!!!!!!Не работает с флекс боксом, пользуем <div role="group"> что б читалка сказала - Это группа элементов, а не input input input

Элемент <fieldset> это контейнер для группировки нескольких связанных элементов в форме, а вложенный <legend> выполянет роль заголовка группы. Связанные радио-кнопки и чекбоксы всегда должны быть сгруппированы, другие типы полей группируются по необходимости.
<fieldset>
    <legend>Enter your contact details</legend>
    <label>
      Name
      <input type="text" name="username" />
    </label>
    <label>
      Email
      <input type="email" name="email" />
    </label>
  </fieldset>
  _________________________________
  Группировка с возможностью оформления
Элементы <fieldset> и <legend> имеют отличную семантику, но ограниченные возможности оформления. В большинстве случаев для группировки элементов формы используется <div> с атрибутами доступности role и aria-labelledby.
Атрибут role="group" указывает на то, что элементы внутри этого <div> являются частью группы.
Атрибут aria-labelledby="contact-details-head" содержит идентификатор элемента с описанием группы.
<div class="form-group" role="group" aria-labelledby="contact-details-head">
    <p id="contact-details-head">Enter your contact details</p>
    <label>
      Name
      <input type="text" name="username" />
    </label>
    <label>
      Email
      <input type="email" name="email" />
    </label>
  </div>
  _____________________________
  Два правила, которые необходимо запомнить для использования элемента form:

Нельзя размещать form внутри другого элемента form.
Внутри одной веб-страницы нельзя размещать более одного элемента input вне элемента form.
Часто используемые атрибуты элемента form:

autocomplete со значением on/off;
method - способ отправки данных браузером (в большинстве случаев для безопасности используется значение POST).
Атрибут action используется редко. Однако на момент верстки, для того чтобы предотвратить обработку (отправку данных) браузером, для формы создают заглушку в виде
атрибута action со значением # (или javascript:void(0);). В результате браузер игнорирует нажатие кнопки type="submit".

Кнопка - элемент button или input с атрибутом type="submit".

Также иногда для сложных форм используют кнопку с атрибутом type="reset" для удаления из input всего, что было введено в пределах элемента form.

______________________________
