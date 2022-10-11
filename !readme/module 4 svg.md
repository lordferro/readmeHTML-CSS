
fill для заливки внутри контура;
stroke для цвета самого контура.

Для наследования цвета текста родителя используют свойство fill со значением currentColor

.item {
  margin: 0.25rem;
  display: block;
  padding: 0.5rem;
  border-radius: 50%;
  background-color: var(--primary);
  <!-- задали цвет текста, которого нету. -->
    color: var(--accent);
}
.icon {
    <!-- Иконка наследует цвет текста, которого нету, теперь иконка цвета Accent -->
--icon-color: currentColor;
}
.item:hover {
    <!-- при ховере иконка и фон меняются цветами -->
  background-color: var(--accent);
    color: var(--primary);
}

_____________________________
<!-- ховер над ссылкой круглой -->
.social-link:hover,
.social-link:focus,
<!-- при ховере изменится и fill у icon -->
.social-link:hover .icon,
.social-link:focus .icon {
    background-color: var(--accent-color);
    fill: var(--white-color);
}