
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <meta name="theme-color" content="#0a0414">
  <title>ZetGames · Website Pindah</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,600;14..32,700;14..32,800;14..32,900&family=Orbitron:wght@500;700;900&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

    :root {
      --neon: #c026d3;
      --neon-bright: #e879f9;
      --neon-soft: #f0abfc;
      --violet: #8b5cf6;
      --violet-deep: #6d28d9;
      --purple: #a855f7;
      --bg-1: #05010a;
      --bg-2: #0a0414;
      --bg-3: #10061e;
      --text: #f5e8ff;
      --text-dim: #b8a3d6;
      --green: #4ade80;
      --red: #f87171;
      --amber: #fbbf24;

      --pad-x: clamp(1rem, 5vw, 2.8rem);
      --pad-y: clamp(1.6rem, 5vw, 3rem);
      --radius-card: clamp(1.8rem, 5vw, 3.5rem);
    }

    html { -webkit-text-size-adjust: 100%; }

    body {
      background:
        radial-gradient(ellipse at 20% 0%, rgba(192, 38, 211, 0.25), transparent 50%),
        radial-gradient(ellipse at 80% 100%, rgba(139, 92, 246, 0.22), transparent 55%),
        radial-gradient(ellipse at 50% 50%, rgba(109, 40, 217, 0.12), transparent 60%),
        linear-gradient(160deg, var(--bg-1) 0%, var(--bg-2) 50%, var(--bg-3) 100%);
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

    /* grid neon bergerak */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(192, 38, 211, 0.06) 1px, transparent 1px),
        linear-gradient(90deg, rgba(192, 38, 211, 0.06) 1px, transparent 1px);
      background-size: 50px 50px;
      mask-image: radial-gradient(ellipse at center, black 10%, transparent 75%);
      -webkit-mask-image: radial-gradient(ellipse at center, black 10%, transparent 75%);
      z-index: 0;
      pointer-events: none;
      animation: gridMove 20s linear infinite;
    }

    @keyframes gridMove {
      0%   { background-position: 0 0, 0 0; }
      100% { background-position: 50px 50px, 50px 50px; }
    }

    /* blob ungu kiri atas */
    body::after {
      content: '';
      position: fixed;
      width: clamp(280px, 50vw, 500px);
      height: clamp(280px, 50vw, 500px);
      border-radius: 50%;
      background: radial-gradient(circle, rgba(192, 38, 211, 0.35), transparent 70%);
      filter: blur(100px);
      top: -150px;
      left: -150px;
      z-index: 0;
      pointer-events: none;
      animation: blobFloat 12s ease-in-out infinite;
    }

    @keyframes blobFloat {
      0%, 100% { transform: translate(0, 0) scale(1); }
      50%      { transform: translate(80px, 60px) scale(1.15); }
    }

    .blob-2 {
      position: fixed;
      width: clamp(260px, 45vw, 460px);
      height: clamp(260px, 45vw, 460px);
      border-radius: 50%;
      background: radial-gradient(circle, rgba(139, 92, 246, 0.3), transparent 70%);
      filter: blur(100px);
      bottom: -150px;
      right: -150px;
      z-index: 0;
      pointer-events: none;
      animation: blobFloat2 14s ease-in-out infinite;
    }

    @keyframes blobFloat2 {
      0%, 100% { transform: translate(0, 0) scale(1); }
      50%      { transform: translate(-70px, -50px) scale(1.2); }
    }

    .announce-card {
      max-width: min(640px, 100%);
      width: 100%;
      background: linear-gradient(155deg, rgba(28, 10, 50, 0.88) 0%, rgba(15, 6, 28, 0.92) 100%);
      backdrop-filter: blur(24px);
      -webkit-backdrop-filter: blur(24px);
      border-radius: var(--radius-card);
      padding: var(--pad-y) var(--pad-x);
      box-shadow:
        0 0 0 1px rgba(192, 38, 211, 0.3),
        0 0 40px -5px rgba(192, 38, 211, 0.4),
        0 0 100px -20px rgba(139, 92, 246, 0.45),
        0 30px 80px -20px rgba(0, 0, 0, 0.95),
        inset 0 1px 0 rgba(255, 255, 255, 0.06);
      border: 1px solid rgba(192, 38, 211, 0.35);
      position: relative;
      z-index: 1;
      text-align: center;
      animation: cardGlow 4s ease-in-out infinite;
    }

    @keyframes cardGlow {
      0%, 100% {
        box-shadow:
          0 0 0 1px rgba(192, 38, 211, 0.3),
          0 0 40px -5px rgba(192, 38, 211, 0.4),
          0 0 100px -20px rgba(139, 92, 246, 0.45),
          0 30px 80px -20px rgba(0, 0, 0, 0.95),
          inset 0 1px 0 rgba(255, 255, 255, 0.06);
      }
      50% {
        box-shadow:
          0 0 0 1px rgba(192, 38, 211, 0.45),
          0 0 55px -5px rgba(192, 38, 211, 0.55),
          0 0 130px -20px rgba(139, 92, 246, 0.6),
          0 30px 80px -20px rgba(0, 0, 0, 0.95),
          inset 0 1px 0 rgba(255, 255, 255, 0.08);
      }
    }

    /* sudut neon */
    .announce-card::before,
    .announce-card::after {
      content: '';
      position: absolute;
      width: 55px;
      height: 55px;
      border: 2px solid var(--neon-bright);
      border-radius: 18px;
      pointer-events: none;
      filter: drop-shadow(0 0 8px var(--neon));
      opacity: 0.7;
    }
    .announce-card::before {
      top: 12px; left: 12px;
      border-right: none; border-bottom: none;
      border-top-left-radius: 26px;
    }
    .announce-card::after {
      bottom: 12px; right: 12px;
      border-left: none; border-top: none;
      border-bottom-right-radius: 26px;
    }

    /* ikon pindah */
    .move-icon {
      width: clamp(64px, 18vw, 88px);
      height: clamp(64px, 18vw, 88px);
      margin: 0 auto clamp(1.2rem, 3vw, 1.6rem);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(145deg, var(--neon) 0%, var(--violet) 55%, var(--neon-bright) 100%);
      box-shadow:
        0 0 30px var(--neon),
        0 0 60px rgba(192, 38, 211, 0.6),
        inset 0 2px 3px rgba(255,255,255,0.4),
        inset 0 -3px 6px rgba(0,0,0,0.35);
      font-size: clamp(1.8rem, 5vw, 2.5rem);
      color: #fff;
      animation: iconPulse 2.5s ease-in-out infinite;
      position: relative;
    }

    .move-icon i { animation: arrowFloat 2s ease-in-out infinite; }

    @keyframes iconPulse {
      0%, 100% {
        box-shadow: 0 0 30px var(--neon), 0 0 60px rgba(192,38,211,0.6),
                    inset 0 2px 3px rgba(255,255,255,0.4), inset 0 -3px 6px rgba(0,0,0,0.35);
      }
      50% {
        box-shadow: 0 0 45px var(--neon), 0 0 90px rgba(192,38,211,0.85),
                    inset 0 2px 3px rgba(255,255,255,0.5), inset 0 -3px 6px rgba(0,0,0,0.35);
      }
    }

    @keyframes arrowFloat {
      0%, 100% { transform: translateX(0); }
      50%      { transform: translateX(5px); }
    }

    /* badge pemberitahuan */
    .notice-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: linear-gradient(135deg, rgba(251, 191, 36, 0.15), rgba(192, 38, 211, 0.1));
      border: 1px solid rgba(251, 191, 36, 0.5);
      border-radius: 100px;
      padding: clamp(0.4rem, 1.2vw, 0.55rem) clamp(0.9rem, 2.5vw, 1.2rem);
      font-size: clamp(0.7rem, 1.9vw, 0.8rem);
      font-weight: 700;
      letter-spacing: 0.5px;
      color: #fde68a;
      margin-bottom: clamp(1.2rem, 3vw, 1.6rem);
      text-transform: uppercase;
      box-shadow: 0 0 20px -5px rgba(251, 191, 36, 0.5);
      text-shadow: 0 0 8px rgba(251, 191, 36, 0.6);
      font-family: 'Orbitron', sans-serif;
    }

    .notice-badge i {
      color: var(--amber);
      filter: drop-shadow(0 0 5px rgba(251, 191, 36, 0.7));
      animation: warnPulse 2s ease-in-out infinite;
    }

    @keyframes warnPulse {
      0%, 100% { transform: scale(1); }
      50%      { transform: scale(1.15); }
    }

    /* Judul */
    .announce-title {
      font-family: 'Orbitron', sans-serif;
      font-size: clamp(1.6rem, 6.5vw, 2.6rem);
      font-weight: 900;
      line-height: 1.15;
      letter-spacing: -0.01em;
      margin-bottom: clamp(0.8rem, 2vw, 1.1rem);
      background: linear-gradient(120deg, #ffffff 0%, var(--neon-soft) 40%, var(--neon-bright) 70%, #ffffff 100%);
      background-size: 200% auto;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      filter: drop-shadow(0 0 15px rgba(232, 121, 249, 0.5));
      animation: textShine 4s linear infinite;
      word-break: break-word;
    }

    @keyframes textShine {
      0%   { background-position: 0% center; }
      100% { background-position: 200% center; }
    }

    /* Deskripsi */
    .announce-desc {
      font-size: clamp(0.88rem, 2.4vw, 1.05rem);
      color: var(--text-dim);
      line-height: 1.65;
      margin-bottom: clamp(1.4rem, 4vw, 2rem);
      max-width: 480px;
      margin-left: auto;
      margin-right: auto;
    }

    .announce-desc strong {
      color: var(--neon-soft);
      font-weight: 700;
      text-shadow: 0 0 8px rgba(232, 121, 249, 0.4);
    }

    /* URL baru */
    .new-url {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: linear-gradient(135deg, rgba(192, 38, 211, 0.15), rgba(139, 92, 246, 0.1));
      border: 1px solid rgba(192, 38, 211, 0.4);
      border-radius: 100px;
      padding: clamp(0.45rem, 1.4vw, 0.6rem) clamp(0.95rem, 2.8vw, 1.3rem);
      font-size: clamp(0.72rem, 2vw, 0.85rem);
      color: var(--neon-soft);
      font-weight: 600;
      margin-bottom: clamp(1.6rem, 4.5vw, 2.2rem);
      word-break: break-all;
      box-shadow: 0 0 20px -6px rgba(192, 38, 211, 0.6), inset 0 0 10px rgba(192, 38, 211, 0.1);
      font-family: 'Courier New', monospace;
    }

    .new-url i {
      color: var(--neon-bright);
      filter: drop-shadow(0 0 5px var(--neon));
      flex-shrink: 0;
    }

    /* Tombol Get Script */
    .get-script-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.7rem;
      width: 100%;
      max-width: 400px;
      padding: clamp(0.95rem, 2.8vw, 1.2rem) clamp(1.5rem, 4vw, 2rem);
      border-radius: 100px;
      font-family: 'Orbitron', sans-serif;
      font-size: clamp(0.95rem, 2.5vw, 1.1rem);
      font-weight: 900;
      letter-spacing: 1px;
      text-transform: uppercase;
      text-decoration: none;
      color: #fff;
      background: linear-gradient(135deg, var(--neon) 0%, var(--violet) 50%, var(--neon-bright) 100%);
      background-size: 200% auto;
      border: 1px solid rgba(232, 121, 249, 0.7);
      box-shadow:
        0 0 30px rgba(192, 38, 211, 0.6),
        0 0 60px -10px rgba(139, 92, 246, 0.5),
        0 10px 30px -10px rgba(0, 0, 0, 0.9),
        inset 0 1px 2px rgba(255, 255, 255, 0.3),
        inset 0 -2px 4px rgba(0, 0, 0, 0.25);
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
      animation: btnShine 3s linear infinite;
    }

    @keyframes btnShine {
      0%   { background-position: 0% center; }
      100% { background-position: 200% center; }
    }

    .get-script-btn::before {
      content: '';
      position: absolute;
      top: 0; left: -100%;
      width: 100%; height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
      transition: left 0.6s ease;
    }

    .get-script-btn:hover::before { left: 100%; }

    .get-script-btn:hover {
      transform: translateY(-3px) scale(1.02);
      box-shadow:
        0 0 45px rgba(192, 38, 211, 0.9),
        0 0 90px -10px rgba(139, 92, 246, 0.8),
        0 15px 40px -10px rgba(0, 0, 0, 0.9),
        inset 0 1px 2px rgba(255, 255, 255, 0.4);
    }

    .get-script-btn:active { transform: scale(0.98); }

    .get-script-btn i {
      font-size: 1.1em;
      filter: drop-shadow(0 0 4px rgba(255,255,255,0.5));
    }

    /* info kecil di bawah tombol */
    .btn-hint {
      margin-top: clamp(0.9rem, 2.5vw, 1.2rem);
      font-size: clamp(0.7rem, 1.9vw, 0.8rem);
      color: var(--text-dim);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.4rem;
    }

    .btn-hint i {
      color: var(--neon-bright);
      font-size: 0.85rem;
      filter: drop-shadow(0 0 4px var(--neon));
    }

    /* divider */
    .divider {
      height: 1px;
      background: linear-gradient(90deg, transparent, rgba(232, 121, 249, 0.5), rgba(192, 38, 211, 0.4), transparent);
      margin: clamp(1.4rem, 4vw, 2rem) 0 clamp(1rem, 2.5vw, 1.2rem);
      box-shadow: 0 0 10px rgba(192, 38, 211, 0.4);
    }

    /* footer */
    .footer-note {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.4rem;
      font-size: clamp(0.65rem, 1.8vw, 0.76rem);
      color: var(--text-dim);
      opacity: 0.7;
    }

    .footer-note i {
      color: var(--neon-bright);
      filter: drop-shadow(0 0 4px var(--neon));
    }

    /* responsif extra kecil */
    @media (max-width: 340px) {
      .announce-card::before, .announce-card::after { width: 40px; height: 40px; }
      .new-url { font-size: 0.65rem; padding: 0.4rem 0.8rem; }
      .notice-badge { font-size: 0.62rem; padding: 0.35rem 0.7rem; }
    }

    @media (max-height: 480px) and (orientation: landscape) {
      body { align-items: flex-start; }
      .announce-card { margin: 0.5rem 0; padding-top: 1.5rem; padding-bottom: 1.5rem; }
      .move-icon { width: 56px; height: 56px; font-size: 1.5rem; margin-bottom: 0.9rem; }
    }

    @media (prefers-reduced-motion: reduce) {
      * { transition: none !important; animation: none !important; }
    }
  </style>
</head>
<body>
  <div class="blob-2"></div>

  <div class="announce-card">
    <!-- Badge pemberitahuan -->
    <div class="notice-badge">
      <i class="fas fa-bullhorn"></i> Pemberitahuan
    </div>

    <!-- Ikon pindah -->
    <div class="move-icon">
      <i class="fas fa-arrow-right-from-bracket"></i>
    </div>

    <!-- Judul -->
    <h1 class="announce-title">Website Telah Pindah!</h1>

    <!-- Deskripsi -->
    <p class="announce-desc">
      Mulai sekarang, <strong>ZetGames</strong> resmi berpindah ke website baru.
      Semua update, script, dan informasi terbaru bisa kamu akses di sana.
      Klik tombol di bawah untuk langsung menuju website baru.
    </p>

    <!-- URL baru -->
    <div class="new-url">
      <i class="fas fa-link"></i>
      <span>https://get-script-aimbot.vercel.app/</span>
    </div>

    <!-- Tombol Get Script -->
    <a class="get-script-btn" href="https://get-script-aimbot.vercel.app/" target="_blank" rel="noopener noreferrer">
      <i class="fas fa-download"></i>
      Get Script
      <i class="fas fa-arrow-right"></i>
    </a>

    <!-- Hint -->
    <div class="btn-hint">
      <i class="fas fa-info-circle"></i>
      Tombol akan membuka website baru di tab baru
    </div>

    <div class="divider"></div>

    <div class="footer-note">
      <i class="fas fa-shield-halved"></i> ZetGames official · 2026
    </div>
  </div>
</body>
</html>
