[index.html](https://github.com/user-attachments/files/32854575/index.html)
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>منصة نبض مصر الإخبارية</title>
  <style>
    :root {
      --bg-color: #fdfdfd;
      --text-color: #222222;
      --card-bg: #f8f9fa;
      --border-color: #e2e8f0;
      --accent: #d32f2f;
    }

    body.dark-mode {
      --bg-color: #121212;
      --text-color: #e0e0e0;
      --card-bg: #1e1e1e;
      --border-color: #333333;
      --accent: #ff5252;
    }

    body {
      margin: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      background-color: var(--bg-color);
      color: var(--text-color);
      transition: background-color 0.3s, color 0.3s;
    }

    /* 1. شريط عاجل */
    .breaking-news-bar {
      display: flex;
      align-items: center;
      background: #1a1a1a;
      color: #ffffff;
      height: 44px;
      overflow: hidden;
      font-size: 14px;
    }

    .breaking-label {
      background: var(--accent);
      color: #ffffff;
      font-weight: bold;
      padding: 0 16px;
      height: 100%;
      display: flex;
      align-items: center;
      z-index: 2;
    }

    .ticker-wrap {
      flex-grow: 1;
      overflow: hidden;
      white-space: nowrap;
    }

    .ticker-move {
      display: inline-block;
      padding-right: 100%;
      animation: ticker 25s linear infinite;
    }

    @keyframes ticker {
      0% { transform: translate3d(0, 0, 0); }
      100% { transform: translate3d(100%, 0, 0); }
    }

    .theme-btn {
      background: transparent;
      border: none;
      font-size: 20px;
      cursor: pointer;
      padding: 0 16px;
    }

    /* 2. أزرار المشاركة العائمة */
    .floating-share {
      position: fixed;
      bottom: 24px;
      left: 24px;
      display: flex;
      flex-direction: column;
      gap: 10px;
      z-index: 999;
    }

    .share-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 10px 16px;
      border-radius: 50px;
      color: #ffffff;
      font-size: 13px;
      text-decoration: none;
      font-weight: bold;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }

    .share-btn.wa { background: #25d366; }
    .share-btn.fb { background: #1877f2; }

    /* 3. بطاقة الكاتب */
    .container {
      max-width: 800px;
      margin: 40px auto;
      padding: 0 20px;
    }

    .author-card {
      display: flex;
      align-items: center;
      gap: 20px;
      background: var(--card-bg);
      border: 1px solid var(--border-color);
      border-right: 4px solid var(--accent);
      padding: 24px;
      border-radius: 10px;
      margin-top: 40px;
    }

    .author-avatar img {
      width: 95px;
      height: 95px;
      border-radius: 50%;
      object-fit: cover;
      border: 2px solid var(--accent);
    }

    .author-details h3 {
      margin: 0 0 8px;
      font-size: 20px;
      color: var(--accent);
    }

    .author-titles {
      list-style: none;
      padding: 0;
      margin: 0 0 10px;
      font-size: 14px;
      line-height: 1.6;
    }

    .author-bio {
      font-size: 13.5px;
      margin: 0;
      line-height: 1.6;
      opacity: 0.85;
    }

    @media (max-width: 600px) {
      .author-card {
        flex-direction: column;
        text-align: center;
      }
    }
  </style>
</head>
<body>

  <!-- شريط الأخبار العاجلة وزر الوضع الليلي -->
  <div class="breaking-news-bar">
    <div class="breaking-label">عاجل</div>
    <div class="ticker-wrap">
      <div class="ticker-move">
        <span>مرحباً بكم في منصة نبض مصر الإخبارية • تغطية شاملة ومصداقية ترصد نبض الشارع لحظة بلحظة</span>
      </div>
    </div>
    <button id="theme-toggle" class="theme-btn" title="تبديل الوضع الليلي">🌙</button>
  </div>

  <!-- أزرار المشاركة العائمة -->
  <div class="floating-share">
    <a href="#" id="share-wa" target="_blank" class="share-btn wa">مشاركة واتساب</a>
    <a href="#" id="share-fb" target="_blank" class="share-btn fb">مشاركة فيسبوك</a>
  </div>

  <!-- حاوية المقال وبطاقة الكاتب الصحفي -->
  <div class="container">
    <article>
      <h1>عنوان المقال الإخباري هنا</h1>
      <p>نص المقال والتحليل الصحفي يبدأ من هنا...</p>
    </article>

    <!-- بطاقة التعريف بالكاتب -->
    <div class="author-card">
      <div class="author-avatar">
        <img src="https://ui-avatars.com/api/?name=Mohamed+Galal&background=d32f2f&color=fff&size=120" alt="أستاذ محمد جلال">
      </div>
      <div class="author-details">
        <h3>بقلم: أستاذ / محمد جلال</h3>
        <ul class="author-titles">
          <li>• محرر صحفي بجريدة الأنباء العربية الأفريقية الدولية</li>
          <li>• مسؤول الاتصال والإعلام بجريدة صوت الناس الحر</li>
          <li>• مراسل صحفي بأخبار مصر اليوم</li>
        </ul>
        <p class="author-bio">تغطيات ومقالات وتحليلات صحفية ترصد قضايا الوطن ونبض الشارع بمصداقية ومهنية.</p>
      </div>
    </div>
  </div>

  <!-- سكريبت التشغيل التلقائي والروابط والوضع الليلي -->
  <script>
    // تفعيل وتخزين الوضع الليلي
    const themeToggle = document.getElementById('theme-toggle');
    if (localStorage.getItem('theme') === 'dark') {
      document.body.classList.add('dark-mode');
      themeToggle.textContent = '☀️';
    }

    themeToggle.addEventListener('click', () => {
      document.body.classList.toggle('dark-mode');
      const isDark = document.body.classList.contains('dark-mode');
      themeToggle.textContent = isDark ? '☀️' : '🌙';
      localStorage.setItem('theme', isDark ? 'dark' : 'light');
    });

    // تجهيز روابط المشاركة على السوشيال ميديا
    const currentUrl = encodeURIComponent(window.location.href);
    const currentTitle = encodeURIComponent(document.title);
    document.getElementById('share-wa').href = `https://api.whatsapp.com/send?text=${currentTitle}%20${currentUrl}`;
    document.getElementById('share-fb').href = `https://www.facebook.com/sharer/sharer.php?u=${currentUrl}`;
  </script>
</body>
</html>
