# goit-markup-hw-05

Для всех эффектов ховера и фокуса сделаны переходы. Время - 250ms, функция распределения времени - cubic-bezier(0.4, 0, 0.2, 1).
В главной навигации, при помощи псевдоэлемента, сделано подчёркивание текущей ссылки.
В секции Чем мы занимаемся текст спозиционирован поверх изображения.
В секции Портфолио, синий оверлей с текстом поверх изображения выезжает снизу изображения.
Есть разметка и оформление модального окна и его бекдропа (тёмного полупрозрачного фона).
Изначально модальное окно скрыто при помощи класса is-hidden (свойства visibility, opacity и pointer-events). Если класс убрать - модалка появляется.
Появление и скрытие модального окна анимированы при помощи перехода с произвольным эффектом, например scale или translate, и opacity.
Модальное окно с формой заявки открывается по клику на кнопку "Заказать услугу". 
Добавkены в разметку специальные атрибуты, по которым скрипт ищет элементы:
  data-modal-open - на кнопку открытия модального окна
  data-modal-close - на кнопку закрытия модального окна
  data-modal - на бекдроп модального окна
После чего, перед закрывающим тегом body добавлен тег script со ссылкой на файл скрипта для модально окна.
  <body>
  <!-- Вся твоя разметка, включая разметку модалки -->

  <!-- Ставим перед закрывающим тегом body -->
  <script src="./js/modal.js"></script>
  </body>
  
 modal.js
  (() => {
  const refs = {
    openModalBtn: document.querySelector('[data-modal-open]'),
    closeModalBtn: document.querySelector('[data-modal-close]'),
    modal: document.querySelector('[data-modal]'),
  };

  refs.openModalBtn.addEventListener('click', toggleModal);
  refs.closeModalBtn.addEventListener('click', toggleModal);

  function toggleModal() {
    refs.modal.classList.toggle('is-hidden');
  }
  })();
