<html lang="zh">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>翻牌网</title>
  <style>
    body {
      font-family: 'Helvetica Neue', sans-serif;
      background: #f6f7fb;
      margin: 0;
      padding: 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
    }

    h1 {
      margin-bottom: 2rem;
      color: #333;
      user-select: none;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 1.5rem;
      width: 100%;
      max-width: 720px;
    }

    .card {
      perspective: 1000px;
      width: 100%;
      aspect-ratio: 3 / 4;
      max-width: 180px;
      cursor: pointer;
      user-select: none;
    }

    .inner {
      position: relative;
      width: 100%;
      height: 100%;
      transition: transform 0.8s;
      transform-style: preserve-3d;
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
      user-select: none;
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
      user-select: none;
    }

    .nickname {
      font-weight: bold;
      margin-bottom: 0.5rem;
      font-size: 1.1rem;
      color: #222;
      user-select: none;
    }

    .intro {
      font-size: 0.9rem;
      color: #666;
      user-select: none;
    }

    /* 去除页面中所有链接默认蓝色样式 */
    a {
      color: inherit;
      text-decoration: none;
      cursor: default;
    }
  </style>
</head>
<body>

  <h1>翻牌交友网</h1>
  <div class="grid">
    <!-- 12张牌 -->
    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=11" alt="头像1" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=11" alt="头像1" />
          <div class="nickname">小兔几</div>
          <div class="intro">爱吃草莓，讨厌孤单</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=22" alt="头像2" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=22" alt="头像2" />
          <div class="nickname">浪味仙</div>
          <div class="intro">自由摄影师，浪到天涯</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=33" alt="头像3" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=33" alt="头像3" />
          <div class="nickname">北岛余光</div>
          <div class="intro">想和你聊聊宇宙和星光</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=44" alt="头像4" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=44" alt="头像4" />
          <div class="nickname">程序媛</div>
          <div class="intro">代码之外，还有热爱</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=55" alt="头像5" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=55" alt="头像5" />
          <div class="nickname">阿巴阿巴</div>
          <div class="intro">没事翻翻牌，有事也翻牌</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=66" alt="头像6" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=66" alt="头像6" />
          <div class="nickname">奶茶不加糖</div>
          <div class="intro">不甜的人也配喝奶茶</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=7" alt="头像7" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=7" alt="头像7" />
          <div class="nickname">海洋之心</div>
          <div class="intro">喜欢大海和安静的夜晚</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=8" alt="头像8" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=8" alt="头像8" />
          <div class="nickname">旅行家</div>
          <div class="intro">背包行走在世界的角落</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=9" alt="头像9" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=9" alt="头像9" />
          <div class="nickname">书虫</div>
          <div class="intro">沉迷于文字的海洋</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=10" alt="头像10" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=10" alt="头像10" />
          <div class="nickname">音乐控</div>
          <div class="intro">用旋律表达情感</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=12" alt="头像11" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=12" alt="头像11" />
          <div class="nickname">咖啡师</div>
          <div class="intro">每天一杯咖啡的仪式感</div>
        </div>
      </div>
    </div>

    <div class="card" onclick="flip(this)">
      <div class="inner">
        <div class="front"><img src="https://i.pravatar.cc/180?img=13" alt="头像12" /></div>
        <div class="back">
          <img src="https://i.pravatar.cc/180?img=13" alt="头像12" />
          <div class="nickname">影迷</div>
          <div class="intro">电影让我看到不一样的世界</div>
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
