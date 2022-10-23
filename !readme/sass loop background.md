
 * SASS loop for background generation
 */


@mixin colorize($colors,$baseSelector) {
  @each $color in $colors {
  $idx: index($colors, $color);
  <!-- index($list, $value)
Returns the position of a value within a list -->

  $baseSelector:nth-child(#{$idx}) {
    background-color: #{$color};
  }
}
}


$colors: "#F44336", "#3F51B5", "#4CAF50", "#00BCD4", "#E91E63", "#009688";

@include colorize($colors, ".имя селектора");


___________________

    @mixin colorize($colors,$baseSelector) {
      @each $color in $colors {
      $idx: index($colors, $color);      
    
      #{$baseSelector}:nth-child(#{$idx}) {
        background-color: #{$color};
      }
    }
    }
  .features-item {
    min-width: 320px;
    max-width: 1200px;
    border: 1px solid black;



  }
  $colors: "#F44336", "#3F51B5", "#4CAF50", "#00BCD4", "#E91E63", "#009688";

  @include colorize($colors, ".features-item");