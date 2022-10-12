Синтаксис объявления переменной - знак $ перед именем и её значение после двоеточия.


________________________
width: 960px + 10%; // Ошибка!
  width: 960px + 30px; // 990px
  width: 960px + 30; // 990px
  width: 100% + 20%; // 120%
===============
  width: calc(100% - 20px);
  width: calc(5em + 20px);
  ________________________
  
  Всё ок -
  $gridItemMargin: 20px;

.box {
  margin: $gridItemMargin * 2;
}
=================
Но в случае когда SASS-переменная используется в функции calc(), во время компиляции её имя не заменяется на значение.
В таких случаях необходимо делать интерполяцию значения переменной используя специальную конструкцию #{$имя_переменной}.

$gridItemMargin: 20px;

.box {
  margin: calc(#{$gridItemMargin} * 2);
}
________________________

.box:hover .button {color: red;} 

=========

.button {
  .box:hover & {
    color: red;
  }
}

_____________________________

@import сначала файл с переменными, что б они были досупны в следующих 
_______________________

@mixin bordered($color: black, $type) { <!--  цвет по умолчаию юует чёрный -->
  border-top: 1px $type $color;
  border-bottom: 1px $type $color;
}

<!-- вызывать мексина параметры в порядке указаном в миксине -->
@include bordered(red, dashed)
<!-- если надо в другом порядке -->
@include bordered ($type: dashed)

_____________________________________
$social-icons: 'facebook', 'twitter';
$client-icons: 'client1', 'client2'; <!-- Создаём списки -->

@mixin iconGenerator ($iconList) { <!-- создаём миксин -->
  @each $iconName in $iconList { 
    .icon-#{$iconName} {
      background-image: url("../images/#{iconName}.svg")
    }
  }
}

@include iconGenerator($social-icons);
______________________
