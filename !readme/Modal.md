pointer-events: none; - пропускает клики мышкой сквозь себя

Сосед кнопке что открывает модальное окно - создаём

 <div data-modal class="backdrop is-hidden">
            <div class="modal">
              <button data-modal-close class="modal-button button">
                <svg width="18" height="18">
                  <use href="./img/icons.svg#icon-close"></use>
                </svg>
              </button>
            </div>
 </div>



.backdrop {
  position: fixed;
  top: 0;
  left: 0;
 
  width: 100%;
  height: 100%;

  background-color: rgba(0, 0, 0, 0.2);
  overflow-y: scroll; <!-- add to scroll modal -->
}

.modal {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  width: 528px;
  height: 581px;

  background-color: #FFFFFF;
  box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.12), 0px 1px 1px rgba(0, 0, 0, 0.14), 0px 2px 1px rgba(0, 0, 0, 0.2);
  border-radius: 4px;
}

.backdrop.is-hidden {
  opacity: 0;
  pointer-events: none;
}

.modal-button {
  position: absolute;
  top: 8px;
  right: 8px;
  display: flex;  
  justify-content: center;
  align-items: center;

  padding: 0;

  background: #FFFFFF;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 50%;
}


_________________
Открытие/закрытие модального окна
Модальное окно с формой заявки открывается по клику на кнопку "Заказать услугу". Для того чтобы скрипт сработал необходимо добавить в разметку специальные атрибуты, по которым скрипт ищет элементы:

data-modal-open - на кнопку открытия модального окна.
data-modal-close - на кнопку закрытия модального окна.
data-modal - на бекдроп модального окна.
После чего, перед закрывающим тегом body добавить тег script со ссылкой на файл скрипта для модально окна. Можно посмотреть видео-инструкцию.

<body>
  <!-- Вся твоя разметка, включая разметку модалки -->

  <!-- Ставим перед закрывающим тегом body -->
  <script src="./js/modal.js"></script>
</body>

Скрипт который необходимо скопировать и вставить в файл modal.js.

(() => {
  const refs = {
    openModalBtn: document.querySelector("[data-modal-open]"),
    closeModalBtn: document.querySelector("[data-modal-close]"),
    modal: document.querySelector("[data-modal]"),
  };

  refs.openModalBtn.addEventListener("click", toggleModal);
  refs.closeModalBtn.addEventListener("click", toggleModal);

  function toggleModal() {
    document.body.classList.toggle('modal-open');
    refs.modal.classList.toggle("is-hidden");
  }
})();


_________________
<!-- add to avoid scrolling of page while modal open -->
body.modal-open {
  overflow: hidden;
}