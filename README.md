<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Undangan Pernikahan</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
  <link href="style.css" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(to bottom, #fdf6f0, #f8e8e0);
      color: #333;
      text-align: center;
    }

    header {
      padding: 60px 20px;
      background: #d4a373;
      color: white;
    }

    header h1 {
      font-family: 'Playfair Display', serif;
      font-size: 40px;
      margin-bottom: 10px;
    }

    section {
      padding: 50px 20px;
    }

    .nama-mempelai {
      font-family: 'Playfair Display', serif;
      font-size: 28px;
      margin: 15px 0;
    }

    .divider {
      width: 80px;
      height: 3px;
      background: #d4a373;
      margin: 20px auto;
    }

    .card {
      background: white;
      padding: 25px;
      margin: 20px auto;
      max-width: 500px;
      border-radius: 12px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }

    .countdown {
      font-size: 20px;
      font-weight: 600;
      margin-top: 15px;
      color: #d4a373;
    }

    footer {
      background: #d4a373;
      color: white;
      padding: 20px;
      font-size: 14px;
    }

    @media (max-width: 600px) {
      header h1 {
        font-size: 28px;
      }

      .nama-mempelai {
        font-size: 22px;
      }
    }
  </style>
</head>
<body>

  <header>
    <h1>Undangan Pernikahan</h1>
    <p>Dengan memohon rahmat dan ridho Tuhan Yang Maha Esa</p>
  </header>

  <section>
    <p>Kami mengundang Bapak/Ibu/Saudara/i untuk menghadiri pernikahan:</p>

    <div class="divider"></div>

    <div class="nama-mempelai">Afzal</div>
    <p>Putra dari Bapak ... & Ibu ...</p>

    <div class="nama-mempelai">&</div>

    <div class="nama-mempelai">Nama Pasangan</div>
    <p>Putri dari Bapak ... & Ibu ...</p>
  </section>

  <section>
    <div class="card">
      <h2>Akad & Resepsi</h2>
      <p><strong>Hari/Tanggal:</strong> Minggu, 20 Desember 2026</p>
      <p><strong>Waktu:</strong> 09.00 WIB</p>
      <p><strong>Lokasi:</strong> Gedung Serbaguna Bahagia</p>
      <div class="countdown" id="countdown"></div>
    </div>
  </section>

  <section>
    <p>Merupakan suatu kehormatan dan kebahagiaan bagi kami apabila Bapak/Ibu/Saudara/i berkenan hadir dan memberikan doa restu.</p>
  </section>

  <footer>
    © 2026 Afzal & Pasangan
  </footer>

  <script>
    const weddingDate = new Date("December 20, 2026 09:00:00").getTime();
    const countdownElement = document.getElementById("countdown");

    const interval = setInterval(() => {
      const now = new Date().getTime();
      const distance = weddingDate - now;

      if (distance < 0) {
        clearInterval(interval);
        countdownElement.innerHTML = "Hari Bahagia Telah Tiba 💍";
        return;
      }

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      countdownElement.innerHTML =
        days + " Hari " +
        hours + " Jam " +
        minutes + " Menit " +
        seconds + " Detik";
    }, 1000);
  </script>

</body>
</html>
