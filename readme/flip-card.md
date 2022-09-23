<body> 
  <div class="scene scene--card">
    <div class="card">
      <div class="card__face card__face--front">front</div>
      <div class="card__face card__face--back">back</div>
    </div>
  </div>
  <p>Click card to flip.</p>
</body>



.scene {
    background-color: transparent;
    width: 300px;
    height: 200px;
    border: 1px solid #f1f1f1;
    perspective: 1000px;
}
.card {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.8s;
    transform-style: preserve-3d;
}

.scene:hover .card {
    transform: rotateY(180deg);
}

.card__face {
    position: absolute;
    width: 100%;
    height: 100%;    
    backface-visibility: hidden;
}

.card__face--front {
  background-color: red;
}

.card__face--back {
    background-color: dodgerblue;
    color: white;
    transform: rotateY(180deg);
}
