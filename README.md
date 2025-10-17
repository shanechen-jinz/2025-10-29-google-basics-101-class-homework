# 2025-10-29-google-basics-101-class-homework
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>廣告活動策略師</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Noto+Sans+TC:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        body { 
            font-family: 'Inter', 'Noto Sans TC', sans-serif; 
            scroll-behavior: smooth;
        }
        .scenario-card {
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
        }
        .scenario-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
        }
        .feedback {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.7s ease-in-out, opacity 0.5s ease-in-out 0.2s;
            opacity: 0;
        }
        .feedback.show {
            max-height: 500px;
            opacity: 1;
        }
        .loader {
            border: 2px solid #f3f3f3;
            border-top: 2px solid #6366f1;
            border-radius: 50%;
            width: 16px;
            height: 16px;
            animation: spin 1s linear infinite;
            display: none; /* Hidden by default */
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <div class="container mx-auto p-4 md:p-8 max-w-7xl">
        <!-- Header -->
        <header class="text-center mb-10">
            <h1 class="text-3xl md:text-4xl font-bold text-gray-900 tracking-tight">廣告活動策略師</h1>
            <p class="mt-3 text-lg text-gray-600">根據下列商業情境，選擇最合適的 Google 廣告活動類型並說明你的策略。</p>
        </header>

        <!-- Scenarios Grid -->
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
            
            <!-- Scenario A: Pet Cafe -->
            <div id="card-a" class="scenario-card bg-white p-6 rounded-2xl shadow-md border border-gray-200 flex flex-col">
                <div class="flex-grow">
                    <div class="flex items-center mb-4">
                        <span class="bg-indigo-100 text-indigo-800 text-sm font-bold mr-3 px-3 py-1.5 rounded-full">情境 A</span>
                        <h2 class="text-xl font-bold text-gray-900">寵物咖啡廳</h2>
                    </div>
                    <p class="text-gray-600 mb-6">一家位於市區新開幕的寵物咖啡廳，希望增加店面來客數並提升在地知名度。</p>
                    
                    <form id="form-a" class="space-y-4">
                        <div>
                            <label for="campaign-a" class="block text-sm font-medium text-gray-700 mb-1">廣告活動類型</label>
                            <select id="campaign-a" name="campaign-a" class="w-full bg-gray-100 border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500">
                                <option value="">請選擇...</option>
                                <option value="最高成效">最高成效 (PMax)</option>
                                <option value="搜尋">搜尋</option>
                                <option value="多媒體">多媒體 (GDN)</option>
                                <option value="影片">影片</option>
                            </select>
                        </div>
                        <div>
                            <label for="reasoning-a" class="block text-sm font-medium text-gray-700 mb-1">策略理由</label>
                            <textarea id="reasoning-a" name="reasoning-a" rows="4" class="w-full bg-gray-100 border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500" placeholder="說明您選擇此廣告活動的原因..."></textarea>
                        </div>
                    </form>
                </div>
                <div class="mt-6">
                    <button id="button-a" onclick="getGeminiFeedback('a')" class="w-full bg-indigo-600 text-white font-semibold py-2 px-4 rounded-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 transition-colors flex items-center justify-center space-x-2">
                        <span>提交策略</span>
                        <div class="loader" id="loader-a"></div>
                    </button>
                    <div id="feedback-a" class="feedback mt-4 pt-4 border-t border-gray-200">
                        <h4 class="font-bold text-gray-900">🧠 Gemini 智慧分析</h4>
                        <p id="feedback-content-a" class="mt-2 text-sm text-gray-700 whitespace-pre-line"></p>
                    </div>
                </div>
            </div>

            <!-- Scenario B: E-commerce -->
            <div id="card-b" class="scenario-card bg-white p-6 rounded-2xl shadow-md border border-gray-200 flex flex-col">
                <div class="flex-grow">
                    <div class="flex items-center mb-4">
                        <span class="bg-teal-100 text-teal-800 text-sm font-bold mr-3 px-3 py-1.5 rounded-full">情境 B</span>
                        <h2 class="text-xl font-bold text-gray-900">線上電商</h2>
                    </div>
                    <p class="text-gray-600 mb-6">一個線上銷售客製化手機殼的電商網站，目標是提升網站的總銷售額，並希望廣告投資報酬率 (ROAS) 能達到 300%。</p>
                    
                     <form id="form-b" class="space-y-4">
                        <div>
                            <label for="campaign-b" class="block text-sm font-medium text-gray-700 mb-1">廣告活動類型</label>
                            <select id="campaign-b" name="campaign-b" class="w-full bg-gray-100 border-gray-300 rounded-md shadow-sm focus:ring-teal-500 focus:border-teal-500">
                                <option value="">請選擇...</option>
                                <option value="最高成效">最高成效 (PMax)</option>
                                <option value="購物">購物</option>
                                <option value="搜尋">搜尋</option>
                                <option value="多媒體">多媒體 (GDN)</option>
                            </select>
                        </div>
                        <div>
                            <label for="reasoning-b" class="block text-sm font-medium text-gray-700 mb-1">策略理由</label>
                            <textarea id="reasoning-b" name="reasoning-b" rows="4" class="w-full bg-gray-100 border-gray-300 rounded-md shadow-sm focus:ring-teal-500 focus:border-teal-500" placeholder="說明您選擇此廣告活動的原因..."></textarea>
                        </div>
                    </form>
                </div>
                <div class="mt-6">
                    <button id="button-b" onclick="getGeminiFeedback('b')" class="w-full bg-teal-600 text-white font-semibold py-2 px-4 rounded-md hover:bg-teal-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-teal-500 transition-colors flex items-center justify-center space-x-2">
                         <span>提交策略</span>
                         <div class="loader" id="loader-b"></div>
                    </button>
                    <div id="feedback-b" class="feedback mt-4 pt-4 border-t border-gray-200">
                        <h4 class="font-bold text-gray-900">🧠 Gemini 智慧分析</h4>
                        <p id="feedback-content-b" class="mt-2 text-sm text-gray-700 whitespace-pre-line"></p>
                    </div>
                </div>
            </div>

            <!-- Scenario C: Gym Event -->
            <div id="card-c" class="scenario-card bg-white p-6 rounded-2xl shadow-md border border-gray-200 flex flex-col">
                <div class="flex-grow">
                    <div class="flex items-center mb-4">
                        <span class="bg-rose-100 text-rose-800 text-sm font-bold mr-3 px-3 py-1.5 rounded-full">情境 C</span>
                        <h2 class="text-xl font-bold text-gray-900">健身房活動</h2>
                    </div>
                    <p class="text-gray-600 mb-6">一家健身房正推廣「夏日減重挑戰」活動，希望能吸引大量民眾填寫線上報名表單，獲取潛在客戶名單。</p>
                    
                    <form id="form-c" class="space-y-4">
                        <div>
                            <label for="campaign-c" class="block text-sm font-medium text-gray-700 mb-1">廣告活動類型</label>
                            <select id="campaign-c" name="campaign-c" class="w-full bg-gray-100 border-gray-300 rounded-md shadow-sm focus:ring-rose-500 focus:border-rose-500">
                                <option value="">請選擇...</option>
                                <option value="搜尋">搜尋</option>
                                <option value="需求開發">需求開發</option>
                                <option value="最高成效">最高成效 (PMax)</option>
                                <option value="影片">影片</option>
                            </select>
                        </div>
                        <div>
                            <label for="reasoning-c" class="block text-sm font-medium text-gray-700 mb-1">策略理由</label>
                            <textarea id="reasoning-c" name="reasoning-c" rows="4" class="w-full bg-gray-100 border-gray-300 rounded-md shadow-sm focus:ring-rose-500 focus:border-rose-500" placeholder="說明您選擇此廣告活動的原因..."></textarea>
                        </div>
                    </form>
                </div>
                <div class="mt-6">
                    <button id="button-c" onclick="getGeminiFeedback('c')" class="w-full bg-rose-600 text-white font-semibold py-2 px-4 rounded-md hover:bg-rose-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-rose-500 transition-colors flex items-center justify-center space-x-2">
                        <span>提交策略</span>
                        <div class="loader" id="loader-c"></div>
                    </button>
                    <div id="feedback-c" class="feedback mt-4 pt-4 border-t border-gray-200">
                        <h4 class="font-bold text-gray-900">🧠 Gemini 智慧分析</h4>
                        <p id="feedback-content-c" class="mt-2 text-sm text-gray-700 whitespace-pre-line"></p>
                    </div>
                </div>
            </div>

        </div>
    </div>

    <script>
        const feedbackGenerator = {
            a: { // Pet Cafe
                '最高成效': "您選擇了「最高成效」，這是一個非常好的策略！PMax 能自動觸及地圖和搜尋的用戶，對於增加實體店來客數非常有幫助。\n\n請記得在素材資源中提供高品質的店家照片和影片，並確保您的 Google 商家檔案資訊完整，這樣 AI 才能發揮最大效益！",
                '搜尋': "選擇「搜尋廣告」是個很精準的作法！鎖定『[地區] 寵物咖啡廳』等關鍵字，可以直接抓住有明確需求的顧客。\n\n建議您可以同時考慮運行一個小額預算的「最高成效」廣告活動，目標設定為「親臨門市」，兩者相輔相成，能有效擴大觸及在地的潛在客群。",
                '多媒體': "透過「多媒體廣告」來提升在地知名度是個不錯的方向，可以用吸睛的圖片觸及對寵物或咖啡有興趣的廣大受眾。\n\n不過，GDN 較偏向於品牌曝光，對於直接轉換為「來客數」的目標可能較為間接。建議可以將主要預算放在能更直接驅動線下行動的「最高成效」或「搜尋」廣告上。",
                '影片': "使用「影片廣告」能生動地展示店內環境與可愛的寵物，非常適合用來建立品牌形象與知名度！\n\n為了更直接地帶來客數，建議在影片中加入明確的地址資訊與行動呼籲，並可考慮搭配「最高成效」廣告活動，將影片素材納入其中，進行更全面的投放。"
            },
            b: { // E-commerce
                '最高成效': "您選擇了「最高成效」，完全是電商的標準答案！設定以 ROAS 為目標，讓 AI 為您尋找高價值的訂單，是達成 300% ROAS 目標最有效率的方式。\n\n請務必確保您的產品動態饋給 (Product Feed) 優化良好，提供清晰的圖片與標題，這會是 PMax 成功的關鍵。",
                '購物': "「購物廣告」是非常適合電商的選擇，它能直接在搜尋結果頁展示商品，轉換效果通常很好。\n\n在預算充足的情況下，可以考慮從標準購物升級到「最高成效」廣告活動，它會包含購物廣告的版位，並進一步拓展到 YouTube、Gmail 等渠道，有機會帶來更多訂單。",
                '搜尋': "「搜尋廣告」可以幫助您抓住正在尋找特定款式手機殼的顧客，是一個很直接的銷售渠道。\n\n然而，對於電商來說，使用者通常更喜歡看到商品圖片。建議您優先考慮「購物廣告」或「最高成效」，因為它們能以更吸睛的圖文格式呈現商品，通常能帶來更好的 ROAS 表現。",
                '多媒體': "「多媒體廣告」很適合用來對瀏覽過您網站的訪客進行「再行銷」，提醒他們回來完成購買。\n\n但若作為開發新客的主要管道，其轉換成效可能不如「最高成效」或「購物廣告」直接。建議將其定位為輔助角色，用來擴大品牌觸及與召回舊客。"
            },
            c: { // Gym Event
                '搜尋': "選擇「搜尋廣告」來獲取潛在客戶名單是個非常精準的策略！直接鎖定有「減重課程」、「健身挑戰」需求的用戶，轉換意願最高。\n\n為了讓成效最大化，請務必設計一個簡潔明瞭、易於填寫的登陸頁面 (Landing Page)，降低使用者在最後一步放棄的機率。",
                '需求開發': "您選擇了「需求開發」，這是一個很好的策略來『創造』需求！透過 YouTube 或探索等平台，用引人入勝的影片或圖片吸引那些對健康生活感興趣，但還沒下定決心的人。\n\n建議可以將「需求開發」與「搜尋廣告」結合，前者用來觸及更廣泛的潛在受眾，後者則用來承接已經產生明確需求的用戶，形成一個完整的行銷漏斗。",
                '最高成效': "「最高成效」在獲取潛在客戶名單上也能有不錯的表現，因為 AI 會自動尋找最可能完成表單填寫的用戶。\n\n不過，PMax 的運作較像一個黑盒子，對於希望精準控制受眾和關鍵字的「名單型」活動來說，有時「搜尋廣告」能提供更高的可控性。您可以先從搜尋廣告開始，待名單穩定後，再開一個 PMax 來擴大開發規模。",
                '影片': "「影片廣告」非常適合用來展示活動的精彩內容、教練的專業形象或過往學員的成功案例，能有效建立信任感並激發報名意願。\n\n建議將影片的最終行動呼籲導向您的報名表單，並可考慮投放給對「健身」、「健康飲食」等主題感興趣的 YouTube 受眾，以提升轉換率。"
            }
        };

        function getGeminiFeedback(scenario) {
            const campaignSelect = document.getElementById(`campaign-${scenario}`);
            const reasoningText = document.getElementById(`reasoning-${scenario}`).value;
            const selectedCampaign = campaignSelect.value;
            
            const feedbackDiv = document.getElementById(`feedback-${scenario}`);
            const feedbackContent = document.getElementById(`feedback-content-${scenario}`);
            const button = document.getElementById(`button-${scenario}`);
            const loader = document.getElementById(`loader-${scenario}`);

            if (!selectedCampaign) {
                alert('請先選擇一個廣告活動類型！');
                return;
            }

            // --- UI Changes for loading ---
            button.disabled = true;
            button.classList.add('opacity-75', 'cursor-not-allowed');
            loader.style.display = 'block';
            feedbackDiv.classList.remove('show');
            
            // --- Simulate AI thinking ---
            setTimeout(() => {
                let geminiResponse = `您選擇了「${selectedCampaign}」，`;

                if(reasoningText.trim().length > 5) {
                    geminiResponse += `並提出了很棒的觀點：「...${reasoningText.trim().slice(0, 20)}...」。\n\n`;
                } else {
                    geminiResponse += `這是一個值得考慮的方向。\n\n`;
                }
                
                const suggestion = feedbackGenerator[scenario][selectedCampaign] || "這是一個有趣的選擇，讓我們來看看其他可能性。";
                geminiResponse += suggestion;
                
                feedbackContent.innerText = geminiResponse;

                // --- UI Changes for showing result ---
                loader.style.display = 'none';
                feedbackDiv.classList.add('show');
                button.disabled = false;
                 button.classList.remove('opacity-75', 'cursor-not-allowed');

            }, 1200); // Simulate network delay and thinking time
        }
    </script>

</body>
</html>

