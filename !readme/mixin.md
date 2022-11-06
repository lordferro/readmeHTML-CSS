@mixin имя {
    @media screen and (min-width: 480px) {
        @content; 
    }
}

использование

@include имя {
    width: ...
    height ...
}