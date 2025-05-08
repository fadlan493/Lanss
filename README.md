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
      background: linear-gradient(45deg, #1e3c72, #2a5298, #ff6a00, #ff0099);
      background-size: 400% 400%;
      animation: gradientAnimation 15s ease infinite;
      color: white;
      transition: background 0.3s ease;
    }

    header {
      text-align: center;
      padding: 2rem;
      background: rgba(0, 0, 0, 0.5);
    }

    header h1 {
      font-size: 3rem;
      margin: 0;
    }

    header p {
      font-size: 1.5rem;
      margin: 0.5rem 0 0;
    }

    .btn-hosting {
      display: inline-block;
      margin-top: 2rem;
      background: #00ff88;
      color: black;
      padding: 0.5rem 1rem;
      border-radius: 5px;
      text-decoration: none;
      font-weight: bold;
      cursor: pointer;
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

    @keyframes gradientAnimation {
      0% {
        background-position: 0% 50%;
      }
      50% {
        background-position: 100% 50%;
      }
      100% {
        background-position: 0% 50%;
      }
    }

    .dark-background {
      background: #000;
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
  </style>
</head>
<body>
  <header>
    <h1>LANSS STORE</h1>
    <p>HOSTING MINECRAFT JAVA/BEDROCK</p>
    <a href="javascript:void(0);" class="btn-hosting" onclick="showPaketList()">HOSTING MINECRAFT</a>
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
      // Ganti latar belakang
      document.body.classList.add('dark-background');

      // Tampilkan container
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

        // Tambahkan delay animasi satu per satu
        setTimeout(() => {
          el.classList.add('fade-in-up');
        }, index * 150);
      });
    }
  </script>
</body>
</html>
