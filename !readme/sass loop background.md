
 * SASS loop for background generation
 */
$colors: "#F44336", "#3F51B5", "#4CAF50", "#00BCD4", "#E91E63", "#009688";

@each $color in $colors {
  $idx: index($colors, $color);

  .element:nth-child(#{$idx}) {
    background-color: #{$color};
  }
}