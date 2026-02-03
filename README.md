<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dimsum Berkah - Order Online</title>
    
    <!-- Import Font Quicksand agar terlihat lebih imut dan modern -->
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@500;700&display=swap" rel="stylesheet">

    <style>
        /* --- CSS VARIABLES (THEME CUTE) --- */
        :root {
            --primary-color: #ff9a9e;
            --secondary-color: #fad0c4;
            --accent-color: #ff6b6b;
            --text-color: #5d5d5d;
            --bg-color: #fff9f9;
            --white: #ffffff;
            --wa-green-start: #25D366;
            --wa-green-end: #128C7E;
        }

        /* --- GLOBAL STYLES --- */
        body {
            font-family: 'Quicksand', 'Segoe UI', sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--bg-color);
            color: var(--text-color);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        /* --- HEADER --- */
        header {
            background: linear-gradient(135deg, var(--primary-color) 0%, #fecfef 100%);
            color: var(--white);
            padding: 2.5rem 1rem;
            text-align: center;
            border-radius: 0 0 40px 40px; /* Lengkungan di bawah header */
            box-shadow: 0 4px 15px rgba(255, 154, 158, 0.3);
            margin-bottom: 30px;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        header h1 {
            margin: 0;
            font-size: 2.5rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
            transition: opacity 0.3s ease; /* Transisi untuk animasi ganti bahasa */
            opacity: 1;
        }

        /* Tombol Bahasa */
        .lang-switcher {
            margin-top: 15px;
            display: flex;
            justify-content: center;
            gap: 8px;
            flex-wrap: wrap;
        }

        .lang-btn {
            background: rgba(255, 255, 255, 0.3);
            border: 2px solid var(--white);
            padding: 6px 15px;
            cursor: pointer;
            border-radius: 20px;
            color: var(--white);
            font-weight: 700;
            transition: all 0.3s ease;
            backdrop-filter: blur(5px);
            font-family: 'Quicksand', sans-serif;
        }

        .lang-btn:hover, .lang-btn.active {
            background: var(--white);
            color: var(--primary-color);
            transform: scale(1.1);
        }

        /* --- CONTAINER & CARDS --- */
        .container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            padding: 0 20px 50px 20px;
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .card {
            background: var(--white);
            border-radius: 25px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
            width: 280px;
            overflow: hidden;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 4px solid var(--white);
            display: flex;
            flex-direction: column;
        }

        .card:hover {
            transform: translateY(-10px) rotate(1deg);
            box-shadow: 0 15px 30px rgba(255, 154, 158, 0.2);
        }

        .card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border-bottom: 4px solid var(--bg-color);
            background-color: #eee;
            transition: transform 0.5s ease;
        }

        .card:hover img {
            transform: scale(1.05);
        }

        .card-content {
            padding: 20px;
            text-align: center;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .card-content h3 {
            margin: 10px 0 5px 0;
            color: var(--accent-color);
            font-size: 1.3rem;
        }

        .card-content p {
            margin: 0 0 15px 0;
            font-size: 0.95rem;
            line-height: 1.4;
            color: #777;
        }

        .price {
            font-weight: 800;
            color: #ff8e53;
            font-size: 1.3rem;
            background: #fff5f5;
            display: inline-block;
            padding: 5px 15px;
            border-radius: 15px;
            margin: 10px 0;
            width: fit-content;
            align-self: center;
        }

        /* --- BUTTONS --- */
        .btn-wa {
            display: block;
            background: linear-gradient(135deg, var(--wa-green-start) 0%, var(--wa-green-end) 100%);
            color: white;
            padding: 12px 20px;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            box-shadow: 0 4px 10px rgba(37, 211, 102, 0.3);
            transition: transform 0.2s, box-shadow 0.2s;
            text-align: center;
            margin-top: auto;
        }

        .btn-wa:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(37, 211, 102, 0.4);
        }

        .btn-wa:active {
            transform: scale(0.95);
        }

        /* --- FOOTER --- */
        footer {
            text-align: center;
            padding: 20px;
            color: #aaa;
            font-size: 0.8rem;
            margin-top: auto;
        }

        /* Responsiveness untuk mobile */
        @media (max-width: 600px) {
            header h1 { font-size: 2rem; }
            .container { gap: 20px; }
            .card { width: 100%; max-width: 320px; }
        }
    </style>
</head>
<body>

<header>
    <h1 id="title">Dimsum Berkah ✨</h1>
    <div class="lang-switcher">
        <button class="lang-btn active" onclick="changeLang('id', this)">ID</button>
        <button class="lang-btn" onclick="changeLang('en', this)">EN</button>
        <button class="lang-btn" onclick="changeLang('zh', this)">ZH</button>
        <button class="lang-btn" onclick="changeLang('jp', this)">JP</button>
    </div>
</header>

<main class="container">
    <!-- Card 1: Dimsum -->
    <div class="card">
        <!-- Menggunakan Picsum dengan seed 'dimsum' agar gambar konsisten -->
        <img src="dimsum.jpg" alt="dimsum">
        <div class="card-content">
            <div>
                <h3 class="name-1">Dimsum</h3>
                <p class="desc-1">Dimsum yang lembut dengan saus pilihan.</p>
            </div>
            <div>
                <div class="price">Rp 20.000</div>
                <a href="#" class="btn-wa order-btn" onclick="sendWA('Dimsum')">Pesan Sekarang ✨</a>
            </div>
        </div>
    </div>

    <!-- Card 2: Hakau -->
    <div class="card">
        <img src="hakau.jpg" alt="hakau">
        <div class="card-content">
            <div>
                <h3 class="name-2">Hakau</h3>
                <p class="desc-2">Kulit transparan dengan isian daging di dalamnya.</p>
            </div>
            <div>
                <div class="price">Rp 25.000</div>
                <a href="#" class="btn-wa order-btn" onclick="sendWA('Hakau')">Pesan Sekarang ✨</a>
            </div>
        </div>
    </div>

    <!-- Card 3: Bakpao Telur Asin -->
    <div class="card">
        <img src="telurasin.jpg" alt="Bakpao Telur Asin">
        <div class="card-content">
            <div>
                <h3 class="name-3">Bakpao Telur Asin</h3>
                <p class="desc-3">Bakpao lembut dengan isian telur asin lumer.</p>
            </div>
            <div>
                <div class="price">Rp 22.000</div>
                <a href="#" class="btn-wa order-btn" onclick="sendWA('Bakpao Telur Asin')">Pesan Sekarang ✨</a>
            </div>
        </div>
    </div>
</main>

<footer>
    &copy; 2023 Dimsum Berkah. Made with ❤️
</footer>

<script>
    // Data Terjemahan
    const translations = {
        id: {
            title: "Dimsum Berkah ✨",
            n1: "Siomay Ayam", d1: "Siomay ayam lembut dengan saus pilihan.",
            n2: "Hakau Udang", d2: "Kulit transparan dengan udang utuh di dalamnya.",
            n3: "Bakpao Telur Asin", d3: "Bakpao lembut dengan isian telur asin lumer.",
            order: "Pesan Sekarang ✨",
            msg: "Halo Dimsum Berkah, saya ingin memesan "
        },
        en: {
            title: "Blessing Dimsum ✨",
            n1: "Chicken Siomay", d1: "Soft chicken dumplings with signature sauce.",
            n2: "Shrimp Hakau", d2: "Transparent skin with whole juicy shrimp.",
            n3: "Salted Egg Bun", d3: "Soft buns with melting salted egg filling.",
            order: "Order Now ✨",
            msg: "Hi Blessing Dimsum, I would like to order "
        },
        zh: {
            title: "福气点心 ✨",
            n1: "鸡肉烧卖", d1: "配有招牌酱汁的软鸡肉烧卖。",
            n2: "水晶虾饺", d2: "晶莹剔透的外皮包裹着整只鲜虾。",
            n3: "奶黄流沙包", d3: "口感柔软，内馅咸香流沙。",
            order: "现在下单 ✨",
            msg: "你好，我想订购 "
        },
        jp: {
            title: "福点心 ✨",
            n1: "鶏肉シューマイ", d1: "特製ソースを添えた柔らかい鶏肉のシューマイ。",
            n2: "海老ハカオ", d2: "まるごと海老が入った透明な皮の蒸し餃子。",
            n3: "カスタードまん", d3: "とろける塩卵フィリング入りのふわふわ饅頭。",
            order: "注文する ✨",
            msg: "こんにちは、注文したいのですが "
        }
    };

    let currentLang = 'id';

    // Fungsi Ganti Bahasa
    function changeLang(lang, btnElement) {
        currentLang = lang;
        const t = translations[lang];
        
        // Update UI Button Active State
        document.querySelectorAll('.lang-btn').forEach(btn => btn.classList.remove('active'));
        if(btnElement) btnElement.classList.add('active');

        // Animasi Fade pada Title
        const titleEl = document.getElementById('title');
        titleEl.style.opacity = 0;
        
        setTimeout(() => {
            // Update Konten
            titleEl.innerText = t.title;
            document.querySelector('.name-1').innerText = t.n1;
            document.querySelector('.desc-1').innerText = t.d1;
            document.querySelector('.name-2').innerText = t.n2;
            document.querySelector('.desc-2').innerText = t.d2;
            document.querySelector('.name-3').innerText = t.n3;
            document.querySelector('.desc-3').innerText = t.d3;
            
            document.querySelectorAll('.order-btn').forEach(btn => {
                btn.innerText = t.order;
            });

            // Fade In
            titleEl.style.opacity = 1;
        }, 200); // Waktu tunggu sesuai durasi transisi CSS
    }

    // Fungsi Kirim WhatsApp
    function sendWA(productName) {
        const phone = "6289524582843";
        const message = translations[currentLang].msg + "*" + productName + "*";
        const url = `https://wa.me/${phone}?text=${encodeURIComponent(message)}`;
        
        // Membuka di tab baru
        window.open(url, '_blank');
    }
</script>

</body>
</html>

