<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ZetGames · Update Countdown</title>
  <!-- Font elegan & modern -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <!-- Font Awesome untuk ikon halus -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #0b0f1c 0%, #141b2b 100%);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Inter', sans-serif;
      padding: 1.5rem;
      color: #eef2ff;
    }

    /* kartu utama — lembut, rounded, shadow elegan */
    .update-card {
      max-width: 820px;
      width: 100%;
      background: rgba(22, 28, 46, 0.75);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border-radius: 3.5rem;
      padding: 2.8rem 2.5rem;
      box-shadow: 
        0 30px 50px -15px rgba(0, 0, 0, 0.6),
        inset 0 1px 2px rgba(255, 255, 255, 0.06);
      border: 1px solid rgba(110, 130, 200, 0.2);
      transition: transform 0.25s ease, box-shadow 0.3s ease;
    }

    .update-card:hover {
      box-shadow: 
        0 40px 60px -18px rgba(0, 0, 0, 0.8),
        inset 0 1px 3px rgba(255, 255, 255, 0.08);
      transform: scale(1.003);
    }

    /* header dengan aksen lembut */
    .header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 2.2rem;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .badge {
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .badge i {
      font-size: 2rem;
      color: #7d9bff;
      filter: drop-shadow(0 0 8px rgba(125, 155, 255, 0.5));
    }

    .badge span {
      font-weight: 600;
      font-size: 1.2rem;
      letter-spacing: 0.5px;
      background: linear-gradient(135deg, #b7c8ff, #8aa3ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .version-tag {
      font-size: 0.9rem;
      background: rgba(125, 155, 255, 0.12);
      padding: 0.5rem 1.3rem;
      border-radius: 100px;
      border: 1px solid rgba(125, 155, 255, 0.25);
      color: #b7c8ff;
      font-weight: 500;
      backdrop-filter: blur(4px);
      letter-spacing: 0.3px;
    }

    /* judul besar */
    .title-section h1 {
      font-size: 2.8rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      line-height: 1.2;
      margin-bottom: 0.4rem;
      background: linear-gradient(to right, #f0f4ff, #c2d0ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .title-section .sub {
      font-size: 1.1rem;
      color: #9aa9cf;
      display: flex;
      align-items: center;
      gap: 0.6rem;
      margin-top: 0.5rem;
      flex-wrap: wrap;
    }

    .sub i {
      font-size: 1rem;
      color: #7d9bff;
      opacity: 0.9;
    }

    .date-highlight {
      background: rgba(125, 155, 255, 0.1);
      padding: 0.5rem 1.1rem;
      border-radius: 100px;
      font-weight: 600;
      color: #c6d4ff;
      border: 1px solid rgba(125, 155, 255, 0.25);
      font-size: 0.95rem;
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
    }

    /* Countdown */
    .countdown-container {
      margin: 2.5rem 0 1.8rem;
    }

    .countdown-label {
      font-size: 0.9rem;
      text-transform: uppercase;
      letter-spacing: 3px;
      font-weight: 500;
      color: #8f9fca;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .countdown-label i {
      font-size: 0.9rem;
      color: #7d9bff;
    }

    .countdown-grid {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .countdown-item {
      background: rgba(18, 24, 40, 0.7);
      backdrop-filter: blur(4px);
      border: 1px solid rgba(125, 155, 255, 0.15);
      border-radius: 2rem;
      padding: 1.2rem 1.3rem;
      flex: 1 1 100px;
      text-align: center;
      box-shadow: 0 8px 20px -8px rgba(0, 0, 0, 0.6), inset 0 1px 1px rgba(255, 255, 255, 0.03);
      transition: border 0.2s, box-shadow 0.2s;
    }

    .countdown-item:hover {
      border-color: rgba(125, 155, 255, 0.4);
      box-shadow: 0 10px 24px -8px #1f2b4b, inset 0 1px 2px rgba(255, 255, 255, 0.05);
    }

    .countdown-number {
      font-size: 3.2rem;
      font-weight: 700;
      line-height: 1;
      color: #edf2ff;
      font-feature-settings: "tnum";
      letter-spacing: -0.02em;
      text-shadow: 0 0 20px rgba(125, 155, 255, 0.3);
    }

    .countdown-unit {
      font-size: 0.8rem;
      text-transform: uppercase;
      letter-spacing: 1.5px;
      color: #99a9d4;
      margin-top: 0.4rem;
      font-weight: 500;
    }

    /* info tambahan */
    .update-note {
      display: flex;
      align-items: center;
      gap: 1rem;
      background: rgba(255, 255, 255, 0.02);
      border-radius: 2rem;
      padding: 1.2rem 1.5rem;
      margin-top: 1.5rem;
      border: 1px solid rgba(125, 155, 255, 0.1);
      flex-wrap: wrap;
    }

    .update-note i {
      font-size: 1.6rem;
      color: #7d9bff;
      opacity: 0.8;
    }

    .update-note p {
      font-size: 1rem;
      color: #b9c6ec;
      font-weight: 400;
      line-height: 1.5;
    }

    .update-note strong {
      color: #d6e0ff;
      font-weight: 600;
    }

    /* garis pemisah halus */
    .divider {
      height: 1px;
      background: linear-gradient(90deg, transparent, rgba(125, 155, 255, 0.2), transparent);
      margin: 1.8rem 0 0.5rem;
    }

    /* responsif */
    @media (max-width: 580px) {
      .update-card {
        padding: 2rem 1.5rem;
        border-radius: 2.5rem;
      }
      .title-section h1 {
        font-size: 2rem;
      }
      .countdown-number {
        font-size: 2.4rem;
      }
      .countdown-item {
        padding: 1rem 0.6rem;
        border-radius: 1.5rem;
      }
      .countdown-grid {
        gap: 0.7rem;
      }
      .update-note {
        padding: 1rem 1.2rem;
      }
      .badge i {
        font-size: 1.6rem;
      }
      .badge span {
        font-size: 1rem;
      }
      .version-tag {
        font-size: 0.8rem;
        padding: 0.4rem 1rem;
      }
    }

    @media (max-width: 400px) {
      .countdown-number {
        font-size: 2rem;
      }
      .countdown-unit {
        font-size: 0.65rem;
        letter-spacing: 1px;
      }
      .title-section h1 {
        font-size: 1.8rem;
      }
    }

    /* efek halus untuk link/icon */
    i {
      transition: color 0.2s;
    }
  </style>
</head>
<body>
  <div class="update-card">
    <!-- Header: ZetGames & versi -->
    <div class="header">
      <div class="badge">
        <i class="fas fa-cube"></i>
        <span>ZetGames</span>
      </div>
      <div class="version-tag">
        <i class="fas fa-code-branch" style="margin-right: 6px; font-size: 0.8rem;"></i> v2.4.0 · major update
      </div>
    </div>

    <!-- Judul + info tanggal -->
    <div class="title-section">
      <h1>Informasi Update</h1>
      <div class="sub">
        <i class="fas fa-calendar-alt"></i>
        <span class="date-highlight">
          <i class="far fa-clock" style="font-size: 0.8rem;"></i> 
          17 Oktober 2026 · 10:00 WIB
        </span>
        <span style="display: inline-flex; align-items: center; gap: 0.3rem;">
          <i class="fas fa-rocket" style="font-size: 0.9rem;"></i> segera hadir
        </span>
      </div>
    </div>

    <!-- Countdown -->
    <div class="countdown-container">
      <div class="countdown-label">
        <i class="fas fa-hourglass-half"></i> hitung mundur update
      </div>
      <div class="countdown-grid" id="countdown">
        <div class="countdown-item">
          <div class="countdown-number" id="days">00</div>
          <div class="countdown-unit">Hari</div>
        </div>
        <div class="countdown-item">
          <div class="countdown-number" id="hours">00</div>
          <div class="countdown-unit">Jam</div>
        </div>
        <div class="countdown-item">
          <div class="countdown-number" id="minutes">00</div>
          <div class="countdown-unit">Menit</div>
        </div>
        <div class="countdown-item">
          <div class="countdown-number" id="seconds">00</div>
          <div class="countdown-unit">Detik</div>
        </div>
      </div>
    </div>

    <!-- Catatan tambahan -->
    <div class="update-note">
      <i class="fas fa-bolt"></i>
      <p>
        <strong>ZetGames v2.4.0</strong> — peningkatan performa, fitur baru, dan pengalaman bermain yang lebih mulus. 
        <span style="display: inline-block; background: rgba(125,155,255,0.15); border-radius: 60px; padding: 0.2rem 0.8rem; margin-left: 8px; font-size: 0.85rem;">
          <i class="fas fa-sync-alt" style="margin-right: 4px;"></i> siap diunduh
        </span>
      </p>
    </div>

    <!-- garis dekoratif -->
    <div class="divider"></div>
    <div style="display: flex; justify-content: flex-end; margin-top: 1rem; opacity: 0.6; font-size: 0.8rem; color: #8f9fca;">
      <i class="fas fa-shield-alt" style="margin-right: 8px;"></i> countdown real-time · ZetGames official
    </div>
  </div>

  <script>
    (function() {
      // Target: 17 Oktober 2026, 10:00 WIB (UTC+7)
      // Kita set dalam UTC: 17 Oct 2026 10:00 WIB = 17 Oct 2026 03:00 UTC
      const targetDate = new Date(Date.UTC(2026, 9, 17, 3, 0, 0)); // bulan 9 = Oktober

      const daysEl = document.getElementById('days');
      const hoursEl = document.getElementById('hours');
      const minutesEl = document.getElementById('minutes');
      const secondsEl = document.getElementById('seconds');

      function padZero(num) {
        return num.toString().padStart(2, '0');
      }

      function updateCountdown() {
        const now = new Date();
        const diffMs = targetDate - now;

        if (diffMs <= 0) {
          // Jika sudah lewat / tepat waktu
          daysEl.textContent = '00';
          hoursEl.textContent = '00';
          minutesEl.textContent = '00';
          secondsEl.textContent = '00';
          // Opsional: tampilkan pesan update tersedia
          document.querySelector('.countdown-label').innerHTML = '<i class="fas fa-check-circle" style="color:#7dff9b;"></i> UPDATE TERSEDIA!';
          return;
        }

        const totalSeconds = Math.floor(diffMs / 1000);
        const days = Math.floor(totalSeconds / 86400);
        const hours = Math.floor((totalSeconds % 86400) / 3600);
        const minutes = Math.floor((totalSeconds % 3600) / 60);
        const seconds = totalSeconds % 60;

        daysEl.textContent = padZero(days);
        hoursEl.textContent = padZero(hours);
        minutesEl.textContent = padZero(minutes);
        secondsEl.textContent = padZero(seconds);
      }

      // panggil pertama kali
      updateCountdown();
      // update tiap detik
      setInterval(updateCountdown, 1000);
    })();
  </script>
</body>
</html>
