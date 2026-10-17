
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <meta name="theme-color" content="#0d0716">
  <title>ZetGames · Update V5.0</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

    :root {
      --purple: #a855f7;
      --purple-soft: #c084fc;
      --purple-deep: #7c3aed;
      --purple-glow: rgba(168, 85, 247, 0.45);
      --bg-1: #050308;
      --bg-2: #0d0716;
      --bg-3: #120a1f;
      --card: rgba(20, 12, 32, 0.72);
      --border: rgba(168, 85, 247, 0.22);
      --text: #ede9fe;
      --text-dim: #a99cc4;

      /* fluid spacing untuk semua device */
      --pad-x: clamp(1rem, 5vw, 2.6rem);
      --pad-y: clamp(1.4rem, 5vw, 2.8rem);
      --radius-card: clamp(1.6rem, 5vw, 3rem);
    }

    html { -webkit-text-size-adjust: 100%; }

    body {
      background:
        radial-gradient(circle at 15% 10%, rgba(124, 58, 237, 0.18), transparent 45%),
        radial-gradient(circle at 85% 90%, rgba(168, 85, 247, 0.14), transparent 50%),
        linear-gradient(160deg, var(--bg-1) 0%, var(--bg-2) 55%, var(--bg-3) 100%);
      min-height: 100vh;
      min-height: 100dvh;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Inter', sans-serif;
      padding: clamp(0.75rem, 3vw, 1.5rem);
      color: var(--text);
      position: relative;
      overflow-x: hidden;
      padding-top: max(0.75rem, env(safe-area-inset-top));
      padding-bottom: max(0.75rem, env(safe-area-inset-bottom));
    }

    body::before,
    body::after {
      content: '';
      position: fixed;
      width: clamp(220px, 40vw, 380px);
      height: clamp(220px, 40vw, 380px);
      border-radius: 50%;
      filter: blur(120px);
      z-index: 0;
      pointer-events: none;
    }
    body::before {
      background: rgba(124, 58, 237, 0.22);
      top: -120px;
      left: -100px;
    }
    body::after {
      background: rgba(168, 85, 247, 0.16);
      bottom: -140px;
      right: -120px;
    }

    .update-card {
      max-width: min(860px, 100%);
      width: 100%;
      background: var(--card);
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
      border-radius: var(--radius-card);
      padding: var(--pad-y) var(--pad-x);
      box-shadow:
        0 30px 60px -20px rgba(0, 0, 0, 0.9),
        0 0 0 1px rgba(168, 85, 247, 0.08),
        inset 0 1px 2px rgba(255, 255, 255, 0.05);
      border: 1px solid var(--border);
      position: relative;
      z-index: 1;
      transition: box-shadow 0.35s ease;
    }

    .update-card:hover {
      box-shadow:
        0 40px 70px -20px rgba(0, 0, 0, 0.95),
        0 0 40px -8px rgba(168, 85, 247, 0.15),
        inset 0 1px 2px rgba(255, 255, 255, 0.06);
    }

    /* ===== HEADER ===== */
    .header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: clamp(1.2rem, 3.5vw, 2.2rem);
      flex-wrap: wrap;
      gap: 0.8rem;
    }

    .badge { display: flex; align-items: center; gap: 0.7rem; }

    .badge-icon {
      width: clamp(36px, 8vw, 44px);
      height: clamp(36px, 8vw, 44px);
      border-radius: clamp(11px, 2.5vw, 14px);
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(145deg, var(--purple-deep), var(--purple));
      box-shadow: 0 0 22px var(--purple-glow), inset 0 1px 1px rgba(255,255,255,0.25);
      font-size: clamp(0.95rem, 2.2vw, 1.2rem);
      color: #fff;
      flex-shrink: 0;
    }

    .badge span {
      font-weight: 800;
      font-size: clamp(1rem, 2.5vw, 1.25rem);
      letter-spacing: 0.5px;
      background: linear-gradient(135deg, #f3e8ff, #c084fc);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .version-tag {
      font-size: clamp(0.7rem, 1.8vw, 0.88rem);
      background: rgba(168, 85, 247, 0.1);
      padding: clamp(0.4rem, 1.2vw, 0.55rem) clamp(0.8rem, 2.4vw, 1.3rem);
      border-radius: 100px;
      border: 1px solid var(--border);
      color: var(--purple-soft);
      font-weight: 600;
      letter-spacing: 0.4px;
      box-shadow: 0 0 18px -6px var(--purple-glow);
      white-space: nowrap;
    }

    /* ===== TITLE ===== */
    .title-section h1 {
      font-size: clamp(1.45rem, 5.5vw, 2.7rem);
      font-weight: 800;
      letter-spacing: -0.02em;
      line-height: 1.15;
      margin-bottom: clamp(0.35rem, 1vw, 0.5rem);
      background: linear-gradient(to right, #ffffff, #d8b4fe);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      text-shadow: 0 0 30px rgba(168, 85, 247, 0.25);
      word-break: break-word;
    }

    .title-section .sub {
      font-size: clamp(0.82rem, 2.2vw, 1rem);
      color: var(--text-dim);
      display: flex;
      align-items: center;
      gap: 0.55rem;
      margin-top: 0.6rem;
      flex-wrap: wrap;
    }

    .sub i { font-size: 0.95rem; color: var(--purple-soft); }

    .date-highlight {
      background: rgba(168, 85, 247, 0.1);
      padding: clamp(0.38rem, 1.2vw, 0.5rem) clamp(0.8rem, 2.4vw, 1.1rem);
      border-radius: 100px;
      font-weight: 600;
      color: #e9d5ff;
      border: 1px solid var(--border);
      font-size: clamp(0.75rem, 2vw, 0.9rem);
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      box-shadow: 0 0 16px -6px var(--purple-glow);
    }

    /* ===== COUNTDOWN ===== */
    .countdown-container { margin: clamp(1.5rem, 4vw, 2.4rem) 0 clamp(1.2rem, 3vw, 1.6rem); }

    .countdown-label {
      font-size: clamp(0.68rem, 1.8vw, 0.82rem);
      text-transform: uppercase;
      letter-spacing: clamp(1.5px, 0.4vw, 3px);
      font-weight: 600;
      color: #9c8ab8;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .countdown-label i { color: var(--purple-soft); }

    /* grid countdown fleksibel: 4 kolom di layar lebar, tetap 4 di mobile */
    .countdown-grid {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: clamp(0.45rem, 1.8vw, 1rem);
    }

    .countdown-item {
      background: rgba(12, 7, 20, 0.75);
      border: 1px solid rgba(168, 85, 247, 0.16);
      border-radius: clamp(0.9rem, 3.5vw, 1.8rem);
      padding: clamp(0.7rem, 2.4vw, 1.2rem) clamp(0.35rem, 1.4vw, 1.2rem);
      text-align: center;
      box-shadow: inset 0 1px 2px rgba(255,255,255,0.03), 0 8px 24px -10px rgba(0,0,0,0.8);
      transition: border-color 0.25s, box-shadow 0.25s, transform 0.25s;
      min-width: 0;
    }

    .countdown-item:hover {
      border-color: rgba(168, 85, 247, 0.5);
      box-shadow: 0 0 26px -8px var(--purple-glow), inset 0 1px 2px rgba(255,255,255,0.05);
      transform: translateY(-2px);
    }

    .countdown-number {
      font-size: clamp(1.5rem, 7.5vw, 3.1rem);
      font-weight: 800;
      line-height: 1;
      color: #f5f0ff;
      font-feature-settings: "tnum";
      letter-spacing: -0.02em;
      text-shadow: 0 0 24px rgba(168, 85, 247, 0.55);
      font-variant-numeric: tabular-nums;
    }

    .countdown-unit {
      font-size: clamp(0.55rem, 1.8vw, 0.72rem);
      text-transform: uppercase;
      letter-spacing: clamp(0.5px, 0.3vw, 1.8px);
      color: #a08cc0;
      margin-top: clamp(0.25rem, 1vw, 0.45rem);
      font-weight: 600;
      white-space: nowrap;
    }

    /* ===== WARNING ===== */
    .warning-box {
      display: flex;
      align-items: flex-start;
      gap: 0.9rem;
      background: linear-gradient(135deg, rgba(168, 85, 247, 0.08), rgba(124, 58, 237, 0.05));
      border: 1px solid rgba(168, 85, 247, 0.3);
      border-left: 3px solid var(--purple);
      border-radius: clamp(0.9rem, 3vw, 1.4rem);
      padding: clamp(0.85rem, 2.5vw, 1.1rem) clamp(0.9rem, 3vw, 1.3rem);
      margin-top: 1.2rem;
      box-shadow: 0 0 30px -12px var(--purple-glow);
    }

    .warning-box i {
      font-size: clamp(1rem, 3vw, 1.3rem);
      color: #d8b4fe;
      margin-top: 0.1rem;
      filter: drop-shadow(0 0 8px rgba(216, 180, 254, 0.6));
      flex-shrink: 0;
    }

    .warning-box p {
      font-size: clamp(0.78rem, 2.1vw, 0.9rem);
      color: #d8ccec;
      line-height: 1.55;
    }

    .warning-box strong { color: #f3e8ff; font-weight: 700; }
    .warning-box .hl { color: #c084fc; font-weight: 600; }

    /* ===== SECTION TITLE ===== */
    .section-title {
      display: flex;
      align-items: center;
      gap: 0.6rem;
      font-size: clamp(0.7rem, 1.9vw, 0.85rem);
      text-transform: uppercase;
      letter-spacing: clamp(1.5px, 0.4vw, 2.5px);
      font-weight: 700;
      color: #b9a6d6;
      margin: clamp(1.4rem, 4vw, 2rem) 0 1rem;
    }

    .section-title i { color: var(--purple-soft); }

    /* ===== COMMUNITY ===== */
    .community-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(min(100%, 240px), 1fr));
      gap: clamp(0.7rem, 2vw, 1rem);
    }

    .community-card {
      background: rgba(12, 7, 20, 0.65);
      border: 1px solid rgba(168, 85, 247, 0.18);
      border-radius: clamp(1rem, 3.5vw, 1.6rem);
      padding: clamp(0.9rem, 2.8vw, 1.2rem);
      display: flex;
      flex-direction: column;
      gap: clamp(0.65rem, 2vw, 0.9rem);
      transition: border-color 0.25s, box-shadow 0.25s, transform 0.25s;
      position: relative;
      overflow: hidden;
      min-width: 0;
    }

    .community-card:hover {
      border-color: rgba(168, 85, 247, 0.45);
      box-shadow: 0 0 30px -10px var(--purple-glow);
      transform: translateY(-2px);
    }

    .community-card.followed {
      border-color: rgba(74, 222, 128, 0.5);
      box-shadow: 0 0 30px -10px rgba(74, 222, 128, 0.35);
    }

    .community-head {
      display: flex;
      align-items: center;
      gap: 0.7rem;
      min-width: 0;
    }

    .community-icon {
      width: clamp(32px, 8vw, 38px);
      height: clamp(32px, 8vw, 38px);
      border-radius: clamp(9px, 2.2vw, 11px);
      background: linear-gradient(145deg, #1a0f2e, #2a1447);
      border: 1px solid rgba(168, 85, 247, 0.3);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #4ade80;
      font-size: clamp(0.9rem, 2.4vw, 1.05rem);
      flex-shrink: 0;
    }

    .community-name {
      font-size: clamp(0.8rem, 2.2vw, 0.9rem);
      font-weight: 700;
      color: #ede9fe;
      line-height: 1.3;
      word-break: break-word;
    }

    .community-sub {
      font-size: clamp(0.65rem, 1.8vw, 0.72rem);
      color: #9c8ab8;
      margin-top: 0.15rem;
      letter-spacing: 0.3px;
    }

    .follow-btn {
      border: none;
      cursor: pointer;
      border-radius: 100px;
      padding: clamp(0.5rem, 1.6vw, 0.62rem) clamp(0.8rem, 2.4vw, 1rem);
      font-family: 'Inter', sans-serif;
      font-size: clamp(0.72rem, 2vw, 0.82rem);
      font-weight: 700;
      letter-spacing: 0.3px;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.45rem;
      background: linear-gradient(135deg, var(--purple-deep), var(--purple));
      color: #fff;
      box-shadow: 0 6px 20px -6px var(--purple-glow);
      transition: transform 0.15s, box-shadow 0.25s, opacity 0.2s;
      text-decoration: none;
      width: 100%;
      text-align: center;
      white-space: nowrap;
    }

    .follow-btn:hover {
      box-shadow: 0 0 26px -4px var(--purple-glow);
      transform: translateY(-1px);
    }

    .follow-btn:active { transform: scale(0.97); }

    .follow-btn.followed {
      background: linear-gradient(135deg, #166534, #22c55e);
      box-shadow: 0 0 22px -6px rgba(34, 197, 94, 0.6);
      cursor: default;
    }

    /* ===== LOCKED NOTICE ===== */
    .locked-notice {
      display: flex;
      align-items: flex-start;
      gap: 0.7rem;
      background: rgba(168, 85, 247, 0.05);
      border: 1px dashed rgba(168, 85, 247, 0.35);
      border-radius: clamp(0.9rem, 3vw, 1.4rem);
      padding: clamp(0.8rem, 2.4vw, 1rem) clamp(0.9rem, 2.8vw, 1.2rem);
      margin-top: 1.4rem;
      font-size: clamp(0.75rem, 2vw, 0.85rem);
      color: #b9a6d6;
      line-height: 1.5;
      transition: opacity 0.3s;
    }

    .locked-notice i { color: var(--purple-soft); font-size: 1rem; margin-top: 0.15rem; flex-shrink: 0; }

    /* ===== SCRIPT SECTION ===== */
    .script-section {
      display: none;
      margin-top: clamp(1.2rem, 3.5vw, 1.8rem);
      animation: fadeUp 0.6s ease forwards;
    }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(16px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .script-header {
      display: flex;
      align-items: center;
      gap: 0.6rem;
      font-size: clamp(0.78rem, 2.1vw, 0.9rem);
      font-weight: 700;
      color: #d8b4fe;
      margin-bottom: 0.8rem;
      letter-spacing: 0.5px;
    }

    .script-header i { color: var(--purple-soft); }

    .script-box {
      position: relative;
      background: rgba(6, 3, 12, 0.92);
      border: 1px solid rgba(168, 85, 247, 0.35);
      border-radius: clamp(1rem, 3.2vw, 1.6rem);
      padding: clamp(0.9rem, 2.8vw, 1.2rem) clamp(0.9rem, 2.8vw, 1.4rem);
      padding-right: clamp(0.9rem, 2.8vw, 1.4rem);
      font-family: 'Courier New', monospace;
      font-size: clamp(0.7rem, 2vw, 0.85rem);
      color: #d8b4fe;
      word-break: break-all;
      line-height: 1.65;
      box-shadow: inset 0 1px 4px rgba(0,0,0,0.7), 0 0 30px -12px var(--purple-glow);
    }

    .script-box code { color: #86efac; white-space: pre-wrap; word-break: break-all; }

    /* tombol salin: absolute di desktop, full-width di mobile */
    .copy-btn {
      margin-top: 0.8rem;
      background: rgba(168, 85, 247, 0.16);
      border: 1px solid rgba(168, 85, 247, 0.45);
      color: #e9d5ff;
      border-radius: 100px;
      padding: clamp(0.5rem, 1.6vw, 0.55rem) clamp(0.9rem, 2.6vw, 1.05rem);
      font-family: 'Inter', sans-serif;
      font-size: clamp(0.72rem, 2vw, 0.82rem);
      font-weight: 700;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.45rem;
      transition: background 0.2s, transform 0.15s, border-color 0.2s;
      backdrop-filter: blur(6px);
      width: 100%;
    }

    .copy-btn:hover {
      background: rgba(168, 85, 247, 0.32);
      border-color: rgba(168, 85, 247, 0.75);
    }

    .copy-btn:active { transform: scale(0.97); }

    .copy-btn.copied {
      background: rgba(34, 197, 94, 0.22);
      border-color: rgba(34, 197, 94, 0.7);
      color: #bbf7d0;
    }

    .script-hint {
      margin-top: 0.6rem;
      font-size: clamp(0.68rem, 1.8vw, 0.78rem);
      color: #9c8ab8;
      display: flex;
      align-items: flex-start;
      gap: 0.4rem;
      line-height: 1.4;
    }

    .script-hint i { font-size: 0.72rem; margin-top: 0.15rem; flex-shrink: 0; }

    .divider {
      height: 1px;
      background: linear-gradient(90deg, transparent, rgba(168, 85, 247, 0.25), transparent);
      margin: clamp(1.2rem, 3.5vw, 1.8rem) 0 0.5rem;
    }

    .footer-note {
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 1rem;
      opacity: 0.6;
      font-size: clamp(0.65rem, 1.8vw, 0.76rem);
      color: #9c8ab8;
      text-align: center;
      gap: 0.4rem;
    }

    .footer-note i { margin-right: 4px; }

    /* ===== TABLET & DESKTOP: tombol salin kembali ke posisi absolute ===== */
    @media (min-width: 560px) {
      .script-box {
        padding-right: 6.5rem;
      }
      .copy-btn {
        position: absolute;
        top: 50%;
        right: 1rem;
        transform: translateY(-50%);
        margin-top: 0;
        width: auto;
      }
      .copy-btn:active { transform: translateY(-50%) scale(0.96); }
    }

    /* ===== HP SANGAT KECIL (<=340px) ===== */
    @media (max-width: 340px) {
      .countdown-grid { gap: 0.35rem; }
      .countdown-item { border-radius: 0.8rem; padding: 0.6rem 0.2rem; }
      .countdown-number { font-size: 1.35rem; }
      .countdown-unit { font-size: 0.5rem; letter-spacing: 0.3px; }
      .header { gap: 0.5rem; }
      .version-tag { font-size: 0.65rem; padding: 0.35rem 0.7rem; }
    }

    /* ===== LANDSCAPE HP PENDEK ===== */
    @media (max-height: 480px) and (orientation: landscape) {
      body { align-items: flex-start; }
      .update-card { margin: 0.5rem 0; }
    }

    /* ===== REDUCE MOTION ===== */
    @media (prefers-reduced-motion: reduce) {
      * { transition: none !important; animation: none !important; }
    }
  </style>
</head>
<body>
  <div class="update-card">
    <!-- HEADER -->
    <div class="header">
      <div class="badge">
        <div class="badge-icon"><i class="fas fa-cube"></i></div>
        <span>ZetGames</span>
      </div>
      <div class="version-tag">
        <i class="fas fa-code-branch" style="margin-right: 6px; font-size: 0.75rem;"></i> Update V5.0
      </div>
    </div>

    <!-- TITLE -->
    <div class="title-section">
      <h1>Informasi Update V5.0</h1>
      <div class="sub">
        <i class="fas fa-calendar-alt"></i>
        <span class="date-highlight">
          <i class="far fa-clock" style="font-size: 0.75rem;"></i>
          17 Oktober 2026 · 10:30 WIB
        </span>
        <span style="display: inline-flex; align-items: center; gap: 0.3rem;">
          <i class="fas fa-rocket" style="font-size: 0.9rem;"></i> segera hadir
        </span>
      </div>
    </div>

    <!-- COUNTDOWN -->
    <div class="countdown-container">
      <div class="countdown-label" id="countdownLabel">
        <i class="fas fa-hourglass-half"></i> hitung mundur update
      </div>
      <div class="countdown-grid">
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

    <!-- WARNING -->
    <div class="warning-box">
      <i class="fas fa-triangle-exclamation"></i>
      <p>
        <strong>Peringatan!</strong> Jika komunitas sepi dan hanya tersisa <span class="hl">2–4 orang</span>,
        maka <strong>Cheat ZetGames-AimlockFree akan dihentikan</strong> secara permanen.
        Bantu ramaikan komunitas agar update tetap berjalan!
      </p>
    </div>

    <!-- COMMUNITY -->
    <div class="section-title">
      <i class="fas fa-users"></i> Follow Komunitas (wajib 2/2)
    </div>
    <div class="community-grid">
      <div class="community-card" id="communityCard1">
        <div class="community-head">
          <div class="community-icon"><i class="fab fa-whatsapp"></i></div>
          <div>
            <div class="community-name">Komunitas ZetGames #1</div>
            <div class="community-sub">WhatsApp Channel</div>
          </div>
        </div>
        <a class="follow-btn" id="followBtn1" href="https://whatsapp.com/channel/0029Vb8STPh0VycODHqyol10" target="_blank" rel="noopener noreferrer">
          <i class="fas fa-plus"></i> Follow Komunitas 1
        </a>
      </div>

      <div class="community-card" id="communityCard2">
        <div class="community-head">
          <div class="community-icon"><i class="fab fa-whatsapp"></i></div>
          <div>
            <div class="community-name">Komunitas ZetGames #2</div>
            <div class="community-sub">WhatsApp Channel</div>
          </div>
        </div>
        <a class="follow-btn" id="followBtn2" href="https://whatsapp.com/channel/0029Vb8mYeDEVccFk7Vin01i" target="_blank" rel="noopener noreferrer">
          <i class="fas fa-plus"></i> Follow Komunitas 2
        </a>
      </div>
    </div>

    <!-- LOCKED NOTICE -->
    <div class="locked-notice" id="lockedNotice">
      <i class="fas fa-lock"></i>
      <span>Script akan terbuka setelah kamu follow <strong>kedua komunitas</strong> di atas.</span>
    </div>

    <!-- SCRIPT -->
    <div class="script-section" id="scriptSection">
      <div class="script-header">
        <i class="fas fa-code"></i> Script Update V5.0 — Terbuka!
      </div>
      <div class="script-box">
        <code id="scriptText">loadstring(game:HttpGet("https://fazxy-script.lovable.app/api/public/raw/Aimbot-Free-Fazxy"))()</code>
        <button class="copy-btn" id="copyBtn" type="button">
          <i class="fas fa-copy"></i> <span id="copyBtnText">Salin</span>
        </button>
      </div>
      <div class="script-hint">
        <i class="fas fa-info-circle"></i> Tekan tombol salin untuk menyalin script ke clipboard.
      </div>
    </div>

    <div class="divider"></div>
    <div class="footer-note">
      <i class="fas fa-shield-halved"></i> countdown real-time · ZetGames official
    </div>
  </div>

  <script>
    (function () {
      const targetDate = new Date(Date.UTC(2026, 9, 17, 3, 30, 0)); // 17 Okt 2026 10:30 WIB

      const daysEl = document.getElementById('days');
      const hoursEl = document.getElementById('hours');
      const minutesEl = document.getElementById('minutes');
      const secondsEl = document.getElementById('seconds');
      const countdownLabel = document.getElementById('countdownLabel');
      const scriptSection = document.getElementById('scriptSection');
      const lockedNotice = document.getElementById('lockedNotice');
      const copyBtn = document.getElementById('copyBtn');
      const copyBtnText = document.getElementById('copyBtnText');
      const followBtn1 = document.getElementById('followBtn1');
      const followBtn2 = document.getElementById('followBtn2');
      const communityCard1 = document.getElementById('communityCard1');
      const communityCard2 = document.getElementById('communityCard2');

      const SCRIPT_TEXT = 'loadstring(game:HttpGet("https://fazxy-script.lovable.app/api/public/raw/Aimbot-Free-Fazxy"))()';

      let followed1 = false;
      let followed2 = false;
      let countdownDone = false;
      let scriptRevealed = false;

      function padZero(num) { return num.toString().padStart(2, '0'); }

      function tryRevealScript() {
        if (scriptRevealed) return;
        if (countdownDone && followed1 && followed2) {
          scriptRevealed = true;
          lockedNotice.style.display = 'none';
          scriptSection.style.display = 'block';
          countdownLabel.innerHTML = '<i class="fas fa-check-circle" style="color:#4ade80;"></i> UPDATE TERSEDIA!';
        }
      }

      function updateCountdown() {
        const now = new Date();
        const diffMs = targetDate - now;

        if (diffMs <= 0) {
          daysEl.textContent = '00';
          hoursEl.textContent = '00';
          minutesEl.textContent = '00';
          secondsEl.textContent = '00';
          if (!countdownDone) {
            countdownDone = true;
            countdownLabel.innerHTML = '<i class="fas fa-check-circle" style="color:#4ade80;"></i> WAKTU UPDATE TIBA!';
            tryRevealScript();
          }
          return;
        }

        const totalSeconds = Math.floor(diffMs / 1000);
        daysEl.textContent = padZero(Math.floor(totalSeconds / 86400));
        hoursEl.textContent = padZero(Math.floor((totalSeconds % 86400) / 3600));
        minutesEl.textContent = padZero(Math.floor((totalSeconds % 3600) / 60));
        secondsEl.textContent = padZero(totalSeconds % 60);
      }

      followBtn1.addEventListener('click', function () {
        if (followed1) return;
        followed1 = true;
        followBtn1.classList.add('followed');
        followBtn1.innerHTML = '<i class="fas fa-check"></i> Sudah Difollow';
        communityCard1.classList.add('followed');
        updateLockedNotice();
        tryRevealScript();
      });

      followBtn2.addEventListener('click', function () {
        if (followed2) return;
        followed2 = true;
        followBtn2.classList.add('followed');
        followBtn2.innerHTML = '<i class="fas fa-check"></i> Sudah Difollow';
        communityCard2.classList.add('followed');
        updateLockedNotice();
        tryRevealScript();
      });

      function updateLockedNotice() {
        if (followed1 && followed2) {
          lockedNotice.style.display = 'none';
        } else {
          const count = (followed1 ? 1 : 0) + (followed2 ? 1 : 0);
          const remaining = 2 - count;
          lockedNotice.style.display = 'flex';
          lockedNotice.querySelector('span').innerHTML =
            'Script akan terbuka setelah kamu follow <strong>kedua komunitas</strong> di atas. ' +
            '(<strong>' + count + '/2</strong> selesai, kurang <strong>' + remaining + '</strong> lagi)';
        }
      }

      copyBtn.addEventListener('click', async function () {
        try {
          if (navigator.clipboard && window.isSecureContext) {
            await navigator.clipboard.writeText(SCRIPT_TEXT);
          } else {
            const textArea = document.createElement('textarea');
            textArea.value = SCRIPT_TEXT;
            textArea.style.position = 'fixed';
            textArea.style.opacity = '0';
            document.body.appendChild(textArea);
            textArea.focus();
            textArea.select();
            document.execCommand('copy');
            document.body.removeChild(textArea);
          }
          copyBtn.classList.add('copied');
          copyBtnText.textContent = 'Tersalin!';
          copyBtn.querySelector('i').className = 'fas fa-check';
          setTimeout(function () {
            copyBtn.classList.remove('copied');
            copyBtnText.textContent = 'Salin';
            copyBtn.querySelector('i').className = 'fas fa-copy';
          }, 2000);
        } catch (err) {
          copyBtnText.textContent = 'Gagal';
          setTimeout(function () { copyBtnText.textContent = 'Salin'; }, 2000);
        }
      });

      updateLockedNotice();
      updateCountdown();
      setInterval(updateCountdown, 1000);
    })();
  </script>
</body>
</html>
