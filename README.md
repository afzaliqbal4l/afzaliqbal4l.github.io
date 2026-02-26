<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Undangan Pernikahan</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
  <link href="style.css" rel="stylesheet">
</head>
<body>

  <header>
    <h1>Undangan Pernikahan</h1>
    <p>Kepada Yth:</p>
    <h2 id="namaTamu"></h2>
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

    const params = new URLSearchParams(window.location.search);
const nama = params.get("to");

const namaTamuElement = document.getElementById("namaTamu");

if (nama) {
  namaTamuElement.textContent = decodeURIComponent(nama);
} else {
  namaTamuElement.textContent = "Tamu Undangan";
}
</script>

</body>
</html>
