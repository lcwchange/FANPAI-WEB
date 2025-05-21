<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>翻牌网</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      font-family: 'Helvetica Neue', sans-serif;
      background: #f2f4f8;
      margin: 0;
      padding: 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
    }

    h1 {
      margin-bottom: 1rem;
      color: #333;
    }

    .btn {
      padding: 0.6rem 1.2rem;
      font-size: 1rem;
      background: #007aff;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      margin-bottom: 1.5rem;
    }

    .btn:disabled {
      background: #aaa;
      cursor: not-allowed;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 1.5rem;
      width: 100%;
      max-width: 800px;
    }

    .card {
      perspective: 1000px;
      cursor: pointer;
    }

    .inner {
      width: 100%;
      aspect-ratio: 3 / 4;
      position: relative;
      transition: transform 0.6s;
      transform-style: preserve-3d;
    }

    .card:hover .inner {
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
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
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    }

    .front {
      background: #ccc;
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
      font-size: 1.1rem;
      margin-bottom: 0.5rem;
      color: #222;
    }

    .intro {
      font-size: 0.9rem;
      color: #666;
    }
  </style>
</head>
<body>
  <h1>翻牌网</h1>
  <button class="btn" onclick="simulatePayment()" id="payBtn">💳 支付9.9元 解锁翻牌</button>
  <div class="grid" id="cardGrid"></div>

  <script>
    let isPaid = false;

    const data = [
      { img: 11, name: '小兔几', intro: '爱吃草莓，讨厌孤单' },
      { img: 22, name: '浪味仙', intro: '自由摄影师，浪到天涯' },
      { img: 33, name: '北岛余光', intro: '想和你聊聊宇宙和星光' },
      { img: 44, name: '程序媛', intro: '代码之外，还有热爱' },
      { img: 55, name: '阿巴阿巴', intro: '没事翻翻牌，有事也翻牌' },
      { img: 66, name: '奶茶不加糖', intro: '不甜的人也配喝奶茶' },
    ];

    const grid = document.getElementById('cardGrid');

    data.forEach(person => {
      const card = document.createElement('div');
      card.className = 'card';
      card.innerHTML = `
        <div class="inner" onclick="handleFlip(this)">
          <div class="front">
            <img src="https://i.pravatar.cc/180?img=${person.img}" alt="头像" />
          </div>
          <div class="back">
            <img src="https://i.pravatar.cc/180?img=${person.img}" alt="头像" />
            <div class="nickname">${person.name}</div>
            <div class="intro">${person.intro}</div>
          </div>
        </div>
      `;
      grid.appendChild(card);
    });

    function handleFlip(innerEl) {
      if (!isPaid) {
        alert("请先支付 9.9 元解锁全部翻牌功能");
        return;
      }
      innerEl.classList.toggle('flipped');
    }

    function simulatePayment() {
      isPaid = true;
      document.getElementById('payBtn').disabled = true;
      document.getElementById('payBtn').innerText = "✅ 已支付，尽情翻牌";
      alert("支付成功，您已解锁所有翻牌内容！");
    }
  </script>
</body>
</html>
