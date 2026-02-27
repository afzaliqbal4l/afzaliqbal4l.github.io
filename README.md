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
  <div class="card">
    <h2>Lokasi Acara</h2>
    <div class="map-container">
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3966.7228318045686!2d106.8357914750373!3d-6.167857993819407!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e69f5c8f32236c7%3A0xb92a4e0c561e6630!2sDirektorat%20Sistem%20Informasi%20dan%20Teknologi%20Perbendaharaan!5e0!3m2!1sid!2sid!4v1772164547345!5m2!1sid!2sid" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"
        width="100%" 
        height="300" 
        style="border:0;" 
        allowfullscreen="" 
        loading="lazy">
      </iframe>
    </div>
  </div>
</section>

  <section>
    <p>Merupakan suatu kehormatan dan kebahagiaan bagi kami apabila Bapak/Ibu/Saudara/i berkenan hadir dan memberikan doa restu.</p>
  </section>

  <section>
  <div class="card">
    <h2>RSVP</h2>
    <form id="rsvpForm">
      <input type="text" id="nama" placeholder="Nama Anda" readonly><br><br>
      
      <select id="kehadiran" required>
        <option value="" disabled selected hidden>Konfirmasi Kehadiran</option>
        <option value="Hadir">Hadir</option>
        <option value="Tidak Hadir">Tidak Hadir</option>
      </select><br><br>
      
      <input type="number" id="jumlah" placeholder="Jumlah Tamu" min="1"><br><br>
      
      <textarea id="ucapan" placeholder="Ucapan & Doa"></textarea><br><br>
      
      <button type="submit">Kirim</button>
    </form>
    
    <p id="status"></p>
  </div>
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
const inputNama = document.getElementById("nama");

if (nama) {
  const decodedNama = nama; // URLSearchParams sudah decode otomatis
  
  namaTamuElement.textContent = decodedNama;
  inputNama.value = decodedNama;   // ← otomatis isi input
} else {
  namaTamuElement.textContent = "Tamu Undangan";
  inputNama.value = "";
}

const form = document.getElementById("rsvpForm");

form.addEventListener("submit", async function(e) {
  e.preventDefault();
  
  const data = {
    nama: document.getElementById("nama").value,
    kehadiran: document.getElementById("kehadiran").value,
    jumlah: document.getElementById("jumlah").value,
    ucapan: document.getElementById("ucapan").value
  };
  
  const response = await fetch("[YOUR_WEB_APP_URL](https://script.google.com/macros/s/AKfycby41dUVYN9x_BJjbmN9YO1xExP3rIjdxfxOLDfaC7P15ydB5vXdeGPEMgKqYr44-bC3dA/exec)", {
    method: "POST",
    body: JSON.stringify(data)
  });
  
  const result = await response.json();
  
  document.getElementById("status").textContent = "Terima kasih atas konfirmasi Anda.";
  
  form.reset();
});
  
</script>

</body>
</html>
