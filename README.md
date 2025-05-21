<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>翻牌交友网</title>
  <style>
    body {
      font-family: 'Helvetica Neue', sans-serif;
      background: #f6f7fb;
      margin: 0;
      padding: 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    h1 {
      margin-bottom: 2rem;
      color: #333;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
    }

    .card {
      perspective: 1000px;
      width: 180px;
      height: 240px;
    }

    .inner {
      position: relative;
      width: 100%;
      height: 100%;
      transition: transform 0.8s;
      transform-style: preserve-3d;
      cursor: pointer;
    }

    .flipped {
      transform: rotateY(180deg);
    }

    .front, .back {
      position: absolute;
      width: 100%;
      height: 100%;
      backface-visibility: hidden;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    }

    .front {
      background-color: #ddd;
    }

    .front img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      filter: blur(6px);
    }

    .back {
      background: white;
      transform: rotateY(180deg);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 1rem;
      text-align: center;
    }

    .back img {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      margin-bottom: 1rem;
    }

    .nickname {
      font-weight: bold;
      margin-bottom: 0.5rem;
      font-size: 1.1rem;
    }

    .intro {
      font-size: 0.9rem;
      color: #666;
    }
  </style>
</head>
<body>

  <h1>翻牌交友网</h1>
  <div class="grid">
    <!-- 卡片1 -->
    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front">
          <img src="https://i.pravatar.cc/180?img=11" />
        </div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=11" />
          <div class="nickname">小兔几</div>
          <div class="intro">爱吃草莓，讨厌孤单</div>
        </div>
      </div>
    </div>

    <!-- 卡片2 -->
    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front">
          <img src="https://i.pravatar.cc/180?img=22" />
        </div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=22" />
          <div class="nickname">浪味仙</div>
          <div class="intro">自由摄影师，浪到天涯</div>
        </div>
      </div>
    </div>

    <!-- 卡片3 -->
    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front">
          <img src="https://i.pravatar.cc/180?img=33" />
        </div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=33" />
          <div class="nickname">北岛余光</div>
          <div class="intro">想和你聊聊宇宙和星光</div>
        </div>
      </div>
    </div>

    <!-- 卡片4 -->
    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front">
          <img src="https://i.pravatar.cc/180?img=44" />
        </div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=44" />
          <div class="nickname">程序媛</div>
          <div class="intro">代码之外，还有热爱</div>
        </div>
      </div>
    </div>

    <!-- 卡片5 -->
    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front">
          <img src="https://i.pravatar.cc/180?img=55" />
        </div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=55" />
          <div class="nickname">阿巴阿巴</div>
          <div class="intro">没事翻翻牌，有事也翻牌</div>
        </div>
      </div>
    </div>

    <!-- 卡片6 -->
    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front">
          <img src="https://i.pravatar.cc/180?img=66" />
        </div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=66" />
          <div class="nickname">奶茶不加糖</div>
          <div class="intro">不甜的人也配喝奶茶</div>
        </div>
      </div>
    </div>

  </div>

  <script>
    function flip(card) {
      const inner = card.querySelector('.inner');
      inner.classList.toggle('flipped');
    }
  </script>
</body>
</html>
