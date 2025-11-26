# Nhu
<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Profile của Nu</title>

  <!-- Tùy chọn: load font từ Google (bỏ nếu không muốn) -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">

  <style>
    :root{
      --accent: #ff6b6b;
      --glass-bg: rgba(255,255,255,0.12);
      --glass-border: rgba(255,255,255,0.18);
      --text: #ffffff;
      --muted: rgba(255,255,255,0.85);
      --max-width: 1000px;
    }

    /* Reset cơ bản */
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      color:var(--text);
      line-height:1.4;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      background: #111; /* fallback */
    }

    /* Background tràn viền: cover toàn màn hình */
    .hero-bg{
      position:relative;
      min-height:100vh;
      width:100%;
      background-image: url('background.jpg'); /* <-- đổi file này */
      background-size: cover;
      background-position: center;
      background-attachment: fixed; /* optional */
      display:flex;
      align-items:center;
      justify-content:center;
    }

    /* overlay tối để chữ dễ đọc */
    .hero-bg::before{
      content:"";
      position:absolute;
      inset:0;
      background: linear-gradient(180deg, rgba(0,0,0,0.35) 0%, rgba(0,0,0,0.55) 100%);
      pointer-events:none;
    }

    /* Card chứa thông tin (semi glass) */
    .profile-card{
      position:relative;
      width:calc(100% - 40px);
      max-width:var(--max-width);
      display:flex;
      gap:28px;
      align-items:center;
      padding:44px;
      border-radius:16px;
      backdrop-filter: blur(8px) saturate(120%);
      background: linear-gradient(180deg, rgba(255,255,255,0.06), rgba(255,255,255,0.03));
      border: 1px solid var(--glass-border);
      box-shadow: 0 10px 30px rgba(2,6,23,0.6);
      z-index:1;
    }

    /* Avatar - nằm so le, nổi lên trên background */
    .avatar-wrap{
      flex: 0 0 170px;
      display:flex;
      align-items:center;
      justify-content:center;
      margin-top: -90px; /* tạo cảm giác avatar nổi lên */
    }
    .avatar{
      width:170px;
      height:170px;
      border-radius:50%;
      overflow:hidden;
      border:6px solid rgba(255,255,255,0.9);
      box-shadow: 0 12px 28px rgba(0,0,0,0.5), 0 2px 6px rgba(0,0,0,0.25);
      background:linear-gradient(135deg, rgba(255,255,255,0.06), rgba(255,255,255,0.02));}
      .avatar img{
      width:100%;
      height:100%;
      object-fit:cover;
      display:block;
      transform:translateZ(0);
    }

    /* Nội dung profile */
    .profile-body{
      flex:1;
      min-width:0;
    }
    .name-row{
      display:flex;
      align-items:baseline;
      gap:14px;
      flex-wrap:wrap;
    }
    .name{
      font-size:1.8rem;
      font-weight:700;
      letter-spacing: -0.02em;
      margin:0;
    }
    .role{
      font-size:0.95rem;
      color:var(--muted);
      margin:0;
    }

    .bio{
      margin-top:12px;
      color:var(--muted);
      font-size:0.98rem;
    }

    .meta{
      margin-top:18px;
      display:flex;
      gap:12px;
      flex-wrap:wrap;
    }
    .pill{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding:8px 12px;
      border-radius:999px;
      font-size:0.9rem;
      background: rgba(255,255,255,0.03);
      border:1px solid rgba(255,255,255,0.04);
    }

    /* Buttons */
    .actions{
      margin-top:20px;
      display:flex;
      gap:12px;
      flex-wrap:wrap;
    }
    .btn{
      padding:10px 16px;
      border-radius:10px;
      border:0;
      cursor:pointer;
      font-weight:600;
      font-size:0.95rem;
      background: linear-gradient(90deg, var(--accent), #ff8a8a);
      color:white;
      box-shadow: 0 6px 18px rgba(255,107,107,0.18);
      transition: transform .15s ease, box-shadow .15s ease;
    }
    .btn:active{ transform: translateY(1px); }
    .btn.ghost{
      background:transparent;
      border:1px solid rgba(255,255,255,0.12);
      color:var(--muted);
      box-shadow:none;
    }

    /* small screens */
    @media (max-width:720px){
      .profile-card{
        padding:24px;
        gap:16px;
        flex-direction:column;
        align-items:center;
        text-align:center;
      }
      .avatar-wrap{ margin-top:-90px; }
      .avatar{ width:140px; height:140px; }
      .name{ font-size:1.4rem; }
    }
  </style>
</head>
<body>
  <main class="hero-bg" role="main" aria-label="Background profile của Nu">
    <article class="profile-card" aria-labelledby="name">
      <!-- Avatar -->
      <div class="avatar-wrap" aria-hidden="false">
        <div class="avatar">
          <!-- đổi avatar.jpg bằng link ảnh của Nu -->
          <img src="avatar.jpg" alt="Ảnh đại diện của Nu">
        </div>
      </div>

      <!-- Nội dung chính -->
      <div class="profile-body">
        <div class="name-row">
          <h1 id="name" class="name">Nu — Tên đầy đủ</h1>
          <p class="role">Học sinh • Yêu tin học • Thích thiết kế</p>
        </div>

        <p class="bio">
          Mô tả ngắn: Nu là người thích học lập trình, làm web và hay giúp bạn bè. Đây là mô tả ngắn gọn để khách
          truy cập biết Nu làm gì. Nu có thể thay đoạn này bằng vài dòng ấn tượng.
        </p>

        <div class="meta" aria-hidden="false">
          <span class="pill">📍 Bến Tre</span>
          <span class="pill">💻 iphone / HTML & CSS</span>
          <span class="pill">🎨 Thiết kế UI</span>
        </div>

        <div class="actions">
          <button class="btn" onclick="window.location.href='#contact'">Liên hệ</button>
          <button class="btn ghost" onclick="window.location.href='https://github.com/USERNAME'">GitHub</button>
        </div>
      </div>
    </article>
  </main>

  <!-- (Optional) Chân trang nhỏ -->
  <footer style="position:fixed;right:12px;bottom:12px;color:rgba(255,255,255,0.6);font-size:12px;">
    © <span id="year"></span> Nu
  </footer>

  <script>
    // JavaScript nhỏ: cập nhật năm tự động
    document.getElementById('year').textContent = new Date().getFullYear();
      </script>
</body>
</html>
      
