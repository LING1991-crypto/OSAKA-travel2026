<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>大阪四天三夜悠哉散步手帳</title>
    <!-- Google Fonts: Zen Maru Gothic -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Zen+Maru+Gothic:wght@500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #FFFCF6;
            --line-color: #3E3A39;
            --pink: #F2A497;
            --yellow: #F6D27A;
            --blue: #A8D3E6;
            --green: #B9DAA5;
            --white: #FFFFFF;
            --shadow: 4px 4px 0px #3E3A39;
            --shadow-sm: 2px 2px 0px #3E3A39;
            --border: 3px solid #3E3A39;
            --radius: 20px;
            --radius-lg: 28px;
            --radius-sm: 12px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--line-color);
            font-family: 'Zen Maru Gothic', sans-serif;
            font-weight: 500;
            line-height: 1.6;
            padding-bottom: 80px;
        }

        /* 頂端固定選單：使用 CSS Grid 確保四個方塊完美水平置中與等高對齊 */
        header {
            position: sticky;
            top: 0;
            background-color: var(--bg-color);
            border-bottom: var(--border);
            z-index: 100;
            width: 100%;
            padding: 10px 16px;
        }

        .header-grid {
            width: 100%;
            max-width: 560px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1.8fr 1fr 1fr 1fr;
            gap: 6px;
            align-items: center;
        }

        .header-item {
            height: 42px;
            display: flex;
            align-items: center;
            justify-content: center;
            border: var(--border);
            border-radius: var(--radius-sm);
            box-shadow: var(--shadow-sm);
            font-weight: 700;
            font-size: 0.8rem;
            white-space: nowrap;
            text-decoration: none;
            color: var(--line-color);
            background: var(--white);
            transition: transform 0.1s, box-shadow 0.1s;
        }

        .header-item:active {
            transform: translate(2px, 2px);
            box-shadow: none;
        }

        .logo-box {
            background: var(--yellow);
            font-size: 0.85rem;
            padding: 0 6px;
        }

        /* 主容器：單欄置中、左右留白 */
        .container {
            width: 100%;
            max-width: 560px;
            margin: 16px auto 0 auto;
            padding: 0 16px;
        }

        /* 通用卡片樣式 */
        .card {
            background-color: var(--white);
            border: var(--border);
            border-radius: var(--radius-lg);
            box-shadow: var(--shadow);
            padding: 20px;
            margin-bottom: 24px;
        }

        /* 首頁區塊 */
        .hero {
            text-align: center;
            background-color: var(--blue);
            position: relative;
            overflow: hidden;
        }

        .hero h1 {
            font-size: 1.5rem;
            margin-bottom: 8px;
            font-weight: 700;
        }

        .hero p {
            font-size: 0.9rem;
            margin-bottom: 14px;
        }

        .countdown-box {
            display: inline-flex;
            gap: 6px;
            background: var(--white);
            border: var(--border);
            padding: 8px 14px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-sm);
            font-weight: 700;
            font-size: 0.85rem;
        }

        /* SVG 複合動畫元件 */
        .scene-container {
            width: 100%;
            max-width: 260px;
            height: 110px;
            margin: 0 auto 10px auto;
            display: block;
        }

        .ani-cloud-1 {
            animation: moveCloud1 6s ease-in-out infinite alternate;
        }
        .ani-cloud-2 {
            animation: moveCloud2 8s ease-in-out infinite alternate;
        }
        .ani-plane {
            animation: flyPlane 4s ease-in-out infinite;
            transform-origin: 50% 50%;
        }
        .ani-sun {
            animation: pulseSun 3s ease-in-out infinite;
            transform-origin: 45px 30px;
        }

        @keyframes moveCloud1 {
            0% { transform: translateX(-10px); }
            100% { transform: translateX(10px); }
        }
        @keyframes moveCloud2 {
            0% { transform: translateX(10px); }
            100% { transform: translateX(-15px); }
        }
        @keyframes flyPlane {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            50% { transform: translate(8px, -6px) rotate(-3deg); }
        }
        @keyframes pulseSun {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.08); }
        }

        /* 航班卡片 */
        .flight-card {
            background-color: var(--yellow);
        }

        .flight-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--white);
            border: var(--border);
            border-radius: var(--radius-sm);
            padding: 10px 14px;
            margin-bottom: 10px;
            box-shadow: var(--shadow-sm);
            font-size: 0.9rem;
            flex-wrap: wrap;
            gap: 6px;
        }

        .flight-row:last-child {
            margin-bottom: 0;
        }

        /* 住宿資訊 */
        .hotel-card {
            background-color: var(--green);
        }

        .hotel-link {
            color: var(--line-color);
            font-weight: 700;
            text-decoration: underline;
            word-break: break-all;
            font-size: 0.85rem;
        }

        /* 日期切換按鈕 */
        .day-tabs {
            display: flex;
            gap: 6px;
            margin-bottom: 16px;
        }

        .day-tab {
            flex: 1;
            background: var(--white);
            border: var(--border);
            border-radius: var(--radius-sm);
            padding: 8px 2px;
            text-align: center;
            font-family: 'Zen Maru Gothic', sans-serif;
            font-weight: 700;
            font-size: 0.85rem;
            cursor: pointer;
            box-shadow: var(--shadow-sm);
            transition: background 0.2s, transform 0.1s;
        }

        .day-tab:active {
            transform: scale(0.95);
        }

        .day-tab.active {
            background: var(--pink);
        }

        /* 行程時間軸與彈跳切換動畫 */
        .day-content {
            display: none;
        }

        .day-content.active {
            display: block;
            animation: bounceIn 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        @keyframes bounceIn {
            0% { opacity: 0; transform: scale(0.92) translateY(12px); }
            70% { opacity: 1; transform: scale(1.02) translateY(-3px); }
            100% { opacity: 1; transform: scale(1) translateY(0); }
        }

        .timeline {
            position: relative;
            padding-left: 20px;
            border-left: 3px dashed var(--line-color);
            margin-left: 10px;
        }

        .timeline-item {
            position: relative;
            margin-bottom: 18px;
            background: var(--white);
            border: var(--border);
            border-radius: var(--radius);
            padding: 14px;
            box-shadow: var(--shadow-sm);
            transition: transform 0.2s;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -27.5px;
            top: 16px;
            width: 12px;
            height: 12px;
            background: var(--yellow);
            border: var(--border);
            border-radius: 50%;
        }

        .time-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 6px;
            flex-wrap: wrap;
            gap: 6px;
        }

        .time-badge {
            font-weight: 700;
            font-size: 0.85rem;
            background: var(--bg-color);
            border: 2px solid var(--line-color);
            padding: 2px 8px;
            border-radius: 8px;
        }

        .tag-transport {
            background-color: var(--blue);
            font-size: 0.75rem;
            padding: 2px 8px;
            border: 2px solid var(--line-color);
            border-radius: 8px;
            font-weight: 700;
        }

        .tag-must {
            background-color: var(--pink);
            font-size: 0.75rem;
            padding: 2px 8px;
            border: 2px solid var(--line-color);
            border-radius: 8px;
            font-weight: 700;
            margin-left: 4px;
        }

        .item-desc {
            font-size: 0.9rem;
            color: #555;
        }

        /* 待辦清單 */
        .todo-card {
            background-color: var(--pink);
        }

        .todo-list {
            list-style: none;
        }

        .todo-item {
            display: flex;
            align-items: center;
            gap: 10px;
            background: var(--white);
            border: var(--border);
            padding: 10px 14px;
            border-radius: var(--radius-sm);
            margin-bottom: 8px;
            box-shadow: var(--shadow-sm);
            font-size: 0.9rem;
            cursor: pointer;
            transition: background 0.1s;
        }

        .todo-item input[type="checkbox"] {
            width: 18px;
            height: 18px;
            accent-color: var(--line-color);
            cursor: pointer;
        }

        .todo-item.checked span {
            text-decoration: line-through;
            color: #888;
        }

        h2 {
            font-size: 1.15rem;
            margin-bottom: 14px;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        /* 減少動態效果支援 (Accessibility) */
        @media (prefers-reduced-motion: reduce) {
            .ani-cloud-1,
            .ani-cloud-2,
            .ani-plane,
            .ani-sun,
            .day-content.active {
                animation: none !important;
                transform: none !important;
            }
        }
    </style>
</head>
<body>

    <!-- 頂端固定選單：使用 CSS Grid 網格對齊 -->
    <header>
        <div class="header-grid">
            <div class="header-item logo-box">🐙 大阪四天三夜</div>
            <a href="#home" class="header-item">首頁</a>
            <a href="#itinerary" class="header-item">行程</a>
            <a href="#info" class="header-item">資訊</a>
        </div>
    </header>

    <div class="container">

        <!-- 首頁區塊 -->
        <section id="home" class="card hero">
            <h1>大阪漫遊手帳 🎒</h1>
            <p>出發日期：2026/12/14 ｜ 80% 逛街美食 ＋ 20% 街區散步</p>
            
            <!-- 精緻大阪特色 SVG 插圖 -->
            <svg class="scene-container" viewBox="0 0 280 120" fill="none" xmlns="http://www.w3.org/2000/svg">
                <circle class="ani-sun" cx="45" cy="30" r="14" fill="#F6D27A" stroke="#3E3A39" stroke-width="3"/>
                
                <g class="ani-cloud-1">
                    <path d="M200 25C195 25 190 28 190 33C190 38 195 40 200 40H225C230 40 233 36 231 32C235 26 228 20 221 23C217 18 208 19 207 25C203 23 198 24 200 25Z" fill="#FFFFFF" stroke="#3E3A39" stroke-width="2.5"/>
                </g>

                <path d="M110 95V70H140V95H110Z" fill="#F6D27A" stroke="#3E3A39" stroke-width="3"/>
                <path d="M102 70H148V63H102V70Z" fill="#F2A497" stroke="#3E3A39" stroke-width="3"/>
                <path d="M118 63V50H132V63H118Z" fill="#A8D3E6" stroke="#3E3A39" stroke-width="3"/>
                <path d="M123 50L125 43H127L129 50H123Z" fill="#3E3A39"/>

                <path d="M175 95L180 45H200L205 95H175Z" fill="#B9DAA5" stroke="#3E3A39" stroke-width="3"/>
                <path d="M170 95H210V100H170V95Z" fill="#3E3A39"/>
                <circle cx="190" cy="55" r="4" fill="#F2A497" stroke="#3E3A39" stroke-width="2"/>

                <g class="ani-cloud-2">
                    <path d="M30 75C25 75 20 78 20 83C20 88 25 90 30 90H60C65 90 68 86 66 82C70 76 63 70 56 73C52 68 43 69 42 75C38 73 33 74 30 75Z" fill="#FFFFFF" stroke="#3E3A39" stroke-width="3"/>
                </g>

                <g class="ani-plane">
                    <path d="M70 40L100 30L88 48L80 42L70 40Z" fill="#FFFFFF" stroke="#3E3A39" stroke-width="3" stroke-linejoin="round"/>
                    <path d="M85 39L94 34" stroke="#3E3A39" stroke-width="2.5" stroke-linecap="round"/>
                </g>
            </svg>

            <!-- 倒數計時器 -->
            <div class
