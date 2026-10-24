<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2026 冬天大阪四天三夜旅行導覽</title>
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

        /* 頂端固定選單 */
        header {
            position: sticky;
            top: 0;
            background-color: var(--bg-color);
            border-bottom: var(--border);
            z-index: 100;
            padding: 12px 16px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.1rem;
            font-weight: 700;
            background: var(--yellow);
            padding: 4px 12px;
            border: var(--border);
            border-radius: var(--radius-sm);
            box-shadow: var(--shadow-sm);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 8px;
        }

        nav a {
            text-decoration: none;
            color: var(--line-color);
            font-size: 0.9rem;
            font-weight: 700;
            background: var(--white);
            padding: 4px 10px;
            border: var(--border);
            border-radius: var(--radius-sm);
            box-shadow: var(--shadow-sm);
            display: inline-block;
            transition: transform 0.1s, box-shadow 0.1s;
        }

        nav a:active {
            transform: translate(2px, 2px);
            box-shadow: none;
        }

        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 16px;
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
            font-size: 1.6rem;
            margin-bottom: 8px;
            font-weight: 700;
        }

        .hero p {
            font-size: 0.95rem;
            margin-bottom: 16px;
        }

        .countdown-box {
            display: inline-flex;
            gap: 8px;
            background: var(--white);
            border: var(--border);
            padding: 8px 16px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-sm);
            font-weight: 700;
            font-size: 0.9rem;
        }

        /* 更精緻的 SVG 複合動畫元件 */
        .scene-container {
            width: 100%;
            max-width: 280px;
            height: 120px;
            margin: 0 auto 10px auto;
            display: block;
        }

        /* 各部位獨立精緻動畫 */
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
            transform-origin: 40px 30px;
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
            gap: 8px;
            margin-bottom: 16px;
            overflow-x: auto;
            padding-bottom: 4px;
        }

        .day-tab {
            flex: 1;
            min-width: 75px;
            background: var(--white);
            border: var(--border);
            border-radius: var(--radius-sm);
            padding: 8px 4px;
            text-align: center;
            font-family: 'Zen Maru Gothic', sans-serif;
            font-weight: 700;
            font-size: 0.9rem;
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
            margin-bottom: 20px;
            background: var(--white);
            border: var(--border);
            border-radius: var(--radius);
            padding: 14px;
            box-shadow: var(--shadow-sm);
            transition: transform 0.2s;
        }

        .timeline-item:hover {
            transform: translateY(-2px);
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
            font-size: 1.2rem;
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

    <!-- 頂端固定選單 -->
    <header>
        <div class="logo">🐙 大阪四天三夜</div>
        <nav>
            <ul>
                <li><a href="#home">首頁</a></li>
                <li><a href="#itinerary">行程</a></li>
                <li><a href="#info">資訊</a></li>
            </ul>
        </nav>
    </header>

    <div class="container">

        <!-- 首頁區塊 -->
        <section id="home" class="card hero">
            <h1>大阪漫遊手帳 🎒</h1>
            <p>出發日期：2026/12/14 ｜逛街美食 ＋ 街區漫遊</p>
            
            <!-- 精緻大阪特色 SVG 插圖：太陽、大阪城、通天閣、雲朵、飛機 -->
            <svg class="scene-container" viewBox="0 0 280 120" fill="none" xmlns="http://www.w3.org/2000/svg">
                <!-- 溫暖背景太陽 -->
                <circle class="ani-sun" cx="45" cy="30" r="14" fill="#F6D27A" stroke="#3E3A39" stroke-width="3"/>
                
                <!-- 遠景雲朵 1 -->
                <g class="ani-cloud-1">
                    <path d="M200 25C195 25 190 28 190 33C190 38 195 40 200 40H225C230 40 233 36 231 32C235 26 228 20 221 23C217 18 208 19 207 25C203 23 198 24 200 25Z" fill="#FFFFFF" stroke="#3E3A39" stroke-width="2.5"/>
                </g>

                <!-- 大阪城剪影 -->
                <path d="M110 95V70H140V95H110Z" fill="#F6D27A" stroke="#3E3A39" stroke-width="3"/>
                <path d="M102 70H148V63H102V70Z" fill="#F2A497" stroke="#3E3A39" stroke-width="3"/>
                <path d="M118 63V50H132V63H118Z" fill="#A8D3E6" stroke="#3E3A39" stroke-width="3"/>
                <!-- 城頂裝飾 -->
                <path d="M123 50L125 43H127L129 50H123Z" fill="#3E3A39"/>

                <!-- 通天閣剪影 -->
                <path d="M175 95L180 45H200L205 95H175Z" fill="#B9DAA5" stroke="#3E3A39" stroke-width="3"/>
                <path d="M170 95H210V100H170V95Z" fill="#3E3A39"/>
                <circle cx="190" cy="55" r="4" fill="#F2A497" stroke="#3E3A39" stroke-width="2"/>

                <!-- 近景雲朵 2 -->
                <g class="ani-cloud-2">
                    <path d="M30 75C25 75 20 78 20 83C20 88 25 90 30 90H60C65 90 68 86 66 82C70 76 63 70 56 73C52 68 43 69 42 75C38 73 33 74 30 75Z" fill="#FFFFFF" stroke="#3E3A39" stroke-width="3"/>
                </g>

                <!-- 飛行中的可愛飛機 -->
                <g class="ani-plane">
                    <path d="M70 40L100 30L88 48L80 42L70 40Z" fill="#FFFFFF" stroke="#3E3A39" stroke-width="3" stroke-linejoin="round"/>
                    <path d="M85 39L94 34" stroke="#3E3A39" stroke-width="2.5" stroke-linecap="round"/>
                </g>
            </svg>

            <div class="countdown-box" id="countdown">
                載入倒數中...
            </div>
        </section>

        <!-- 航班與住宿資訊 -->
        <section id="info">
            <div class="card flight-card">
                <h2>✈️ 航班資訊</h2>
                <div class="flight-row">
                    <div><strong>去程：</strong> 桃園中正機場 → 大阪關西機場</div>
                    <div>07:30 - 11:00</div>
                </div>
                <div class="flight-row">
                    <div><strong>回程：</strong> 大阪關西機場 → 桃園中正機場</div>
                    <div>14:00 - 14:25</div>
                </div>
            </div>

            <div class="card hotel-card">
                <h2>🏨 住宿資訊</h2>
                <div class="flight-row" style="background: var(--white); display: block;">
                    <div><strong>Hotel Intergate Osaka Umeda</strong><br><small style="color: #666;">ホテルインターゲート大阪梅田（以梅田為中心，交通極便利）</small></div>
                    <div style="margin-top: 8px;">
                        <a class="hotel-link" href="https://www.google.com/maps/place/Hotel+Intergate+%E5%A4%A7%E9%98%AA+%E6%A2%85%E7%94%B0/@34.6981353,135.4906501,17z" target="_blank">📍 Google 地圖導覽與位置</a>
                    </div>
                </div>
            </div>
        </section>

        <!-- 每日行程區塊 -->
        <section id="itinerary" class="card" style="background-color: #FFFDF9;">
            <h2>📅 每日行程</h2>
            
            <!-- 日期切換按鈕 -->
            <div class="day-tabs">
                <button class="day-tab active" onclick="switchDay(1)">DAY 1</button>
                <button class="day-tab" onclick="switchDay(2)">DAY 2</button>
                <button class="day-tab" onclick="switchDay(3)">DAY 3</button>
                <button class="day-tab" onclick="switchDay(4)">DAY 4</button>
            </div>

            <!-- DAY 1 -->
            <div id="day-1" class="day-content active">
                <p style="font-size: 0.85rem; margin-bottom: 12px; font-weight: 700; color: #777;">📍 主題：梅田＋中崎町 (2026/12/14)</p>
                <div class="timeline">
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">下午 12:30</span>
                            <div><span class="tag-transport">地鐵</span><span class="tag-must">必去</span></div>
                        </div>
                        <div class="item-desc"><strong>梅田逛街血拼</strong><br>抵達梅田與入住飯店後，展開 LUCUA ／ Grand Front Osaka ／ 阪急梅田 ／ 大丸梅田 購物之旅！</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">下午 03:30</span>
                            <div><span class="tag-transport">步行</span><span class="tag-must">必去</span></div>
                        </div>
                        <div class="item-desc"><strong>中崎町散步漫遊</strong><br>穿梭老屋、古著店、手作小店與特色咖啡廳，感受復古文青氣息。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">傍晚 06:30</span>
                            <div><span class="tag-transport">步行</span></div>
                        </div>
                        <div class="item-desc"><strong>晚餐與夜景</strong><br>返回梅田享用美味晚餐，並欣賞璀璨的梅田夜景。</div>
                    </div>
                </div>
            </div>

            <!-- DAY 2 -->
            <div id="day-2" class="day-content">
                <p style="font-size: 0.85rem; margin-bottom: 12px; font-weight: 700; color: #777;">📍 主題：木津市場＋新世界＋心齋橋＋堀江 (2026/12/15)</p>
                <div class="timeline">
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">早上 09:00</span>
                            <div><span class="tag-transport">地鐵</span><span class="tag-must">必去</span></div>
                        </div>
                        <div class="item-desc"><strong>木津市場早市</strong><br>品嚐新鮮海鮮早餐，體驗道地的市場早晨風情[cite: 1]。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">上午 10:30</span>
                            <div><span class="tag-transport">步行</span></div>
                        </div>
                        <div class="item-desc"><strong>新世界與通天閣</strong><br>漫步懷舊新世界街區，打卡地標通天閣[cite: 1]。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">中午 12:00</span>
                            <div><span class="tag-transport">地鐵</span><span class="tag-must">必去</span></div>
                        </div>
                        <div class="item-desc"><strong>心齋橋拉麵午餐 & 商店街</strong><br>品嚐心齋橋人氣拉麵，隨後瘋狂掃貨心齋橋筋商店街與大丸心齋橋[cite: 1]。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">下午 03:00</span>
                            <div><span class="tag-transport">步行</span><span class="tag-must">必去</span></div>
                        </div>
                        <div class="item-desc"><strong>美國村 → 堀江 Orange Street</strong><br>穿插造訪個性小店、選物店與質感咖啡廳[cite: 1]。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">傍晚 05:30</span>
                            <div><span class="tag-transport">步行</span><span class="tag-must">必去</span></div>
                        </div>
                        <div class="item-desc"><strong>道頓堀與法善寺橫丁</strong><br>漫步道頓堀霓虹燈區，探訪寧靜的法善寺橫丁[cite: 1]。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">晚上 07:30</span>
                            <div><span class="tag-transport">步行</span></div>
                        </div>
                        <div class="item-desc"><strong>和牛晚餐</strong><br>享用精緻的和牛燒肉或和牛壽喜燒大餐[cite: 1]。</div>
                    </div>
                </div>
            </div>

            <!-- DAY 3 -->
            <div id="day-3" class="day-content">
                <p style="font-size: 0.85rem; margin-bottom: 12px; font-weight: 700; color: #777;">📍 主題：天神橋筋＋中崎町漫遊 (2026/12/16)</p>
                <div class="timeline">
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">上午 09:30</span>
                            <div><span class="tag-transport">地鐵</span><span class="tag-must">必去</span></div>
                        </div>
                        <div class="item-desc"><strong>天神橋筋商店街</strong><br>造訪日本最長商店街，邊走邊逛特色小店、品嚐在地小吃[cite: 1]。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">中午 12:00</span>
                            <div><span class="tag-transport">步行</span></div>
                        </div>
                        <div class="item-desc"><strong>午餐時光</strong><br>在巷弄中尋找喜愛的質感小店享用午餐[cite: 1]。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">下午 02:00</span>
                            <div><span class="tag-transport">步行</span><span class="tag-must">必去</span></div>
                        </div>
                        <div class="item-desc"><strong>中崎町慢活下午茶</strong><br>再次造訪中崎町，深入古著店、雜貨舖、選物店，享受悠閒甜點時光[cite: 1]。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">傍晚 06:00</span>
                            <div><span class="tag-transport">地鐵</span></div>
                        </div>
                        <div class="item-desc"><strong>梅田最後衝刺</strong><br>返回梅田進行最後採買與晚餐[cite: 1]。</div>
                    </div>
                </div>
            </div>

            <!-- DAY 4 -->
            <div id="day-4" class="day-content">
                <p style="font-size: 0.85rem; margin-bottom: 12px; font-weight: 700; color: #777;">📍 主題：梅田自由購物 ➔ 賦歸 (2026/12/17)</p>
                <div class="timeline">
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">早上 09:00</span>
                            <div><span class="tag-transport">步行</span></div>
                        </div>
                        <div class="item-desc"><strong>悠閒早餐</strong><br>於飯店享用美味早餐，整理行李與戰利品[cite: 1]。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">上午 10:00</span>
                            <div><span class="tag-transport">步行</span><span class="tag-must">必去</span></div>
                        </div>
                        <div class="item-desc"><strong>梅田自由購物與伴手禮</strong><br>最後機會補齊藥妝、伴手禮與心儀衣物[cite: 1]。</div>
                    </div>
                    <div class="timeline-item">
                        <div class="time-header">
                            <span class="time-badge">中午 11:30</span>
                            <div><span class="tag-transport">特急列車</span></div>
                        </div>
                        <div class="item-desc"><strong>前往關西機場</strong><br>回飯店拿行李，搭乘列車前往關西機場，準備搭乘 14:00 航班平安返台！</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 打勾待辦清單 -->
        <section class="card todo-card">
            <h2>📝 行李與行前待辦</h2>
            <ul class="todo-list">
                <li class="todo-item" onclick="toggleCheck(this)">
                    <input type="checkbox"> <span>護照與日幣現金／信用卡確認</span>
                </li>
                <li class="todo-item" onclick="toggleCheck(this)">
                    <input type="checkbox"> <span>Visit Japan Web 填寫完成</span>
                </li>
                <li class="todo-item" onclick="toggleCheck(this)">
                    <input type="checkbox"> <span>網卡／eSIM 啟用確認</span>
                </li>
                <li class="todo-item" onclick="toggleCheck(this)">
                    <input type="checkbox"> <span>Hotel Intergate Osaka Umeda 訂房確認</span>
                </li>
                <li class="todo-item" onclick="toggleCheck(this)">
                    <input type="checkbox"> <span>輕便好走的散步鞋 👟</span>
                </li>
            </ul>
        </section>

    </div>

    <script>
        // 日期切換功能
        function switchDay(dayNum) {
            const contents = document.querySelectorAll('.day-content');
            const tabs = document.querySelectorAll('.day-tab');

            contents.forEach(el => el.classList.remove('active'));
            tabs.forEach(el => el.classList.remove('active'));

            document.getElementById(`day-${dayNum}`).classList.add('active');
            event.currentTarget.classList.add('active');
        }

        // 待辦清單互動打勾
        function toggleCheck(item) {
            const checkbox = item.querySelector('input[type="checkbox"]');
            if (event.target !== checkbox) {
                checkbox.checked = !checkbox.checked;
            }
            if (checkbox.checked) {
                item.classList.add('checked');
            } else {
                item.classList.remove('checked');
            }
        }

        // 出發倒數計時器（依據資料設定 2026-12-14 07:30:00）
        function updateCountdown() {
            const departureDate = new Date('2026-12-14T07:30:00').getTime();
            const now = new Date().getTime();
            const distance = departureDate - now;

            const countdownEl = document.getElementById('countdown');
            if (distance < 0) {
                countdownEl.innerHTML = "🎉 旅程已經展開或圓滿結束囉！";
                return;
            }

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));

            countdownEl.innerHTML = `✈️ 距離 2026/12/14 出發還有：${days} 天 ${hours} 小時 ${minutes} 分鐘`;
        }

        updateCountdown();
        setInterval(updateCountdown, 60000);
    </script>
</body>
</html>
