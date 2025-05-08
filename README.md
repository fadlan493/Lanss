<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>LANSS STORE</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 0;
      background: linear-gradient(to bottom, #1e003e, #2e004f);
      background-size: cover;
      color: white;
    }

    .navbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: #2a004d;
      padding: 10px 20px;
    }

    .nav-left {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .logo {
      width: 40px;
      height: 40px;
      border-radius: 50%;
    }

    .brand {
      color: #c600ff;
      font-size: 20px;
      font-weight: bold;
    }

    .hamburger {
      font-size: 26px;
      color: white;
      cursor: pointer;
    }

    header.main {
      text-align: center;
      padding: 3rem 1rem;
    }

    header.main h1 {
      font-size: 2.5rem;
      margin: 0;
      font-weight: bold;
    }

    header.main h1 span {
      color: #c600ff;
    }

    header.main p {
      margin-top: 1rem;
      font-size: 1.1rem;
      line-height: 1.6;
    }

    .buttons {
      margin-top: 2rem;
      display: flex;
      justify-content: center;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .btn {
      padding: 0.75rem 1.5rem;
      border-radius: 8px;
      font-weight: bold;
      cursor: pointer;
      border: none;
      text-decoration: none;
      font-size: 1rem;
    }

    .btn-primary {
      background: #a100ff;
      color: white;
    }

    .btn-outline {
      background: transparent;
      border: 2px solid #a100ff;
      color: #a100ff;
    }

    .paket-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1rem;
      padding: 2rem;
      display: none;
    }

    .paket {
      background: rgba(255, 255, 255, 0.1);
      border-radius: 10px;
      padding: 1.5rem;
      text-align: center;
      opacity: 0;
      transform: translateY(30px);
    }

    .paket h2 {
      font-size: 1.5rem;
    }

    .paket p {
      margin: 0.5rem 0;
      font-family: monospace;
      white-space: pre-wrap;
    }

    .paket a {
      display: inline-block;
      margin-top: 1rem;
      background: #00ff88;
      color: black;
      padding: 0.5rem 1rem;
      border-radius: 5px;
      text-decoration: none;
      font-weight: bold;
    }

    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .fade-in-up {
      animation: fadeInUp 0.6s ease forwards;
    }

    .dark-background {
      background: #000;
    }
  </style>
</head>
<body>
  <div class="navbar">
    <div class="nav-left">
      <img src="https://i.ibb.co/Xj0Q8tD/pp.jpg" alt="Logo" class="logo" />
      <div class="brand">LANSS STORE</div>
    </div>
    <div class="hamburger">&#9776;</div>
  </div>

  <header class="main">
    <h1>Selamat <br> Datang di <br> <span>LANSS STORE</span></h1>
    <p>Menyediakan kebutuhan Minecraft terbaik dengan kualitas premium<br>
    dan harga terjangkau. Hosting Minecraft, VPS Digital Ocean, Server Siap Pakai, dan banyak lagi!</p>
    <div class="buttons">
      <a href="javascript:void(0);" class="btn btn-primary" onclick="showPaketList()">LIHAT PRODUK</a>
      <a href="https://wa.me/6282142570902" class="btn btn-outline" target="_blank">HUBUNGI KAMI</a>
    </div>
  </header>

  <div class="paket-container" id="paketList"></div>

  <script>
    const paketContainer = document.getElementById('paketList');
    const paketList = [
      { ram: 1, storage: 2, cpu: 200, backup: 2, port: 1 },
      { ram: 2, storage: 4, cpu: 200, backup: 2, port: 1 },
      { ram: 3, storage: 6, cpu: 200, backup: 2, port: 1 },
      { ram: 4, storage: 8, cpu: 200, backup: 2, port: 1 },
      { ram: 5, storage: 10, cpu: 400, backup: 2, port: 1 },
      { ram: 6, storage: 12, cpu: 400, backup: 2, port: 1 },
      { ram: 7, storage: 14, cpu: 400, backup: 2, port: 1 },
      { ram: 8, storage: 16, cpu: 400, backup: 2, port: 1 },
      { ram: 9, storage: 18, cpu: 400, backup: 2, port: 1 },
      { ram: 10, storage: 20, cpu: 400, backup: 2, port: 1 },
      { ram: 11, storage: 22, cpu: 400, backup: 2, port: 1 },
      { ram: 12, storage: 24, cpu: 400, backup: 2, port: 1 },
    ];

    function formatRupiah(angka) {
      return 'Rp' + angka.toString().replace(/\B(?=(\d{3})+(?!\d))/g, '.');
    }

    function showPaketList() {
      document.body.classList.add('dark-background');
      paketContainer.style.display = 'grid';
      paketContainer.innerHTML = '';

      paketList.forEach((paket, index) => {
        const harga = paket.ram * 4000000;
        const el = document.createElement('div');
        el.className = 'paket';
        el.innerHTML = `
          <h2>𝙿𝙰𝙺𝙴𝚃 #${index + 1}</h2>
          <p>
𝚁𝚊𝚖      : ${paket.ram}𝙶𝙱
𝚂𝚝𝚘𝚛𝚊𝚐𝚎 : ${paket.storage}𝙶𝙱
𝙲𝚙𝚞     : ${paket.cpu}%
𝙱𝚊𝚌𝚔𝚞𝚙   : ${paket.backup}
𝙿𝚘𝚛𝚝     : ${paket.port}
          </p>
          <p><strong>Harga: ${formatRupiah(harga)}</strong></p>
          <a href="https://wa.me/6282142570902?text=SAYA%20MAU%20BELI%20PAKET%20${index + 1}" target="_blank">Beli</a>
        `;
        paketContainer.appendChild(el);
        setTimeout(() => {
          el.classList.add('fade-in-up');
        }, index * 150);
      });
    }
  </script>
</body>
</html>    
