# rbse-95
RBSE Class 12 AI Study Website
<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RBSE 12th PCB: Mission 95% Strategy + AI Guru</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Devanagari:wght@400;600;700&display=swap" rel="stylesheet">
    
    <!-- Chosen Palette: Academic Excellence -->
    <!-- Primary: #1E3A8A (Deep Blue) -->
    <!-- Secondary: #7C3AED (Purple - AI Sparkle) -->
    <!-- Background: #F1F5F9 (Soft Slate) -->

    <style>
        body {
            font-family: 'Noto Sans Devanagari', sans-serif;
            background-color: #f1f5f9;
            color: #1e293b;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 500px;
            height: 300px;
            margin: 0 auto;
        }
        .subject-btn.active {
            background-color: #1e3a8a;
            color: white;
            border-color: #1e3a8a;
        }
        .ai-tool-card {
            background: white;
            transition: all 0.3s ease;
            border: 1px solid #e2e8f0;
        }
        .ai-tool-card:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 15px -3px rgba(124, 58, 237, 0.1);
            border-color: #ddd6fe;
        }
        .custom-scroll::-webkit-scrollbar {
            width: 6px;
        }
        .custom-scroll::-webkit-scrollbar-track {
            background: #f1f1f1; 
        }
        .custom-scroll::-webkit-scrollbar-thumb {
            background: #cbd5e1; 
            border-radius: 4px;
        }
        .loader {
            border: 2px solid #f3f3f3;
            border-top: 2px solid #7c3aed;
            border-radius: 50%;
            width: 16px;
            height: 16px;
            animation: spin 1s linear infinite;
            display: inline-block;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .glow-text {
            text-shadow: 0 0 10px rgba(124, 58, 237, 0.3);
        }
    </style>
</head>
<body class="min-h-screen flex flex-col">

    <!-- Application Structure Plan:
         1. Header: Branding and AI Status.
         2. Subject Tabs: Navigation between PCB + Hindi/English.
         3. AI Mega-Hub (New): A 4-grid tool section for personalized learning.
            - Study Planner (Updated)
            - Doubt Solver (Updated)
            - ✨ Answer Checker (New)
            - ✨ Viva Mock Test (New)
         4. Content Sections: Blueprint visualization and Golden Topics.
         5. Footer: Credits and Disclaimer.
    -->

    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->

    <header class="bg-white border-b border-gray-200 sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 py-4 sm:px-6 lg:px-8 flex justify-between items-center">
            <div class="flex items-center space-x-3">
                <div class="bg-blue-900 text-white p-2 rounded-lg font-bold text-xl">95%</div>
                <div>
                    <h1 class="text-xl font-bold text-gray-900">RBSE 12th PCB AI-स्मार्ट रणनीति</h1>
                    <p class="text-xs text-gray-500">Mission Merit List • ✨ Gemini AI Guru Integrated</p>
                </div>
            </div>
            <div class="hidden sm:block">
                <span class="inline-flex items-center px-3 py-1 rounded-full text-xs font-medium bg-purple-100 text-purple-800 border border-purple-200">
                    ✨ AI असिस्टेंट एक्टिव
                </span>
            </div>
        </div>
    </header>

    <main class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-6">
        
        <!-- Subject Selection -->
        <div class="flex flex-wrap justify-center gap-2 mb-8" id="subject-nav"></div>

        <!-- AI Mega Hub -->
        <section class="mb-10">
            <div class="flex items-center gap-2 mb-4">
                <h2 class="text-xl font-bold text-gray-800">✨ AI स्मार्ट टूल्स</h2>
                <div class="h-px flex-grow bg-purple-200"></div>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
                <!-- Tool 1: Planner -->
                <div class="ai-tool-card p-4 rounded-xl shadow-sm flex flex-col">
                    <div class="text-2xl mb-2">📅</div>
                    <h4 class="font-bold text-sm text-gray-800">स्टडी प्लानर</h4>
                    <p class="text-xs text-gray-500 mb-4">चुने हुए विषय के लिए 7-दिन का कस्टमाइज़्ड शेड्यूल।</p>
                    <button onclick="generateAI('plan')" id="planBtn" class="mt-auto bg-purple-600 hover:bg-purple-700 text-white py-2 rounded-lg text-xs font-bold transition">✨ प्लान बनाएं</button>
                </div>

                <!-- Tool 2: Doubt Solver -->
                <div class="ai-tool-card p-4 rounded-xl shadow-sm flex flex-col">
                    <div class="text-2xl mb-2">❓ डाउट सॉल्वर</div>
                    <input type="text" id="doubtInput" placeholder="टॉपिक लिखें..." class="text-xs p-2 border border-gray-200 rounded mb-2">
                    <button onclick="generateAI('doubt')" id="doubtBtn" class="bg-indigo-600 hover:bg-indigo-700 text-white py-2 rounded-lg text-xs font-bold transition">✨ डाउट क्लियर करें</button>
                </div>

                <!-- Tool 3: Answer Improver -->
                <div class="ai-tool-card p-4 rounded-xl shadow-sm flex flex-col">
                    <div class="text-2xl mb-2">📝 आंसर चेक</div>
                    <p class="text-xs text-gray-500 mb-2">अपना आंसर पेस्ट करें, AI उसे '95% लायक' बनाएगा।</p>
                    <button onclick="openModal('answerModal')" class="mt-auto bg-emerald-600 hover:bg-emerald-700 text-white py-2 rounded-lg text-xs font-bold transition">✨ आंसर सुधारें</button>
                </div>

                <!-- Tool 4: Viva Prep -->
                <div class="ai-tool-card p-4 rounded-xl shadow-sm flex flex-col">
                    <div class="text-2xl mb-2">🔬 प्रैक्टिकल Viva</div>
                    <p class="text-xs text-gray-500 mb-4">प्रैक्टिकल परीक्षा के लिए संभावित प्रश्न पूछें।</p>
                    <button onclick="generateAI('viva')" id="vivaBtn" class="mt-auto bg-amber-600 hover:bg-amber-700 text-white py-2 rounded-lg text-xs font-bold transition">✨ Viva प्रश्न पूछें</button>
                </div>
            </div>

            <!-- AI Output Section -->
            <div id="aiOutputArea" class="hidden mt-6 bg-white rounded-2xl shadow-xl border border-purple-100 overflow-hidden animate-fade-in">
                <div class="bg-purple-50 px-6 py-3 border-b border-purple-100 flex justify-between items-center">
                    <span class="text-sm font-bold text-purple-800 flex items-center gap-2">
                        <span id="outputIcon">✨</span> <span id="outputHeader">AI Response</span>
                    </span>
                    <button onclick="closeOutput()" class="text-gray-400 hover:text-gray-600 font-bold">बंद करें &times;</button>
                </div>
                <div id="outputText" class="p-6 text-sm text-gray-700 leading-relaxed max-h-[500px] overflow-y-auto custom-scroll whitespace-pre-line prose prose-sm">
                    AI कंटेंट यहाँ दिखेगा...
                </div>
            </div>
        </section>

        <!-- Main Dashboard Content -->
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
            <!-- Left: Blueprint -->
            <div class="lg:col-span-5 space-y-6">
                <div class="bg-white rounded-2xl shadow-sm p-6 border border-gray-100">
                    <h3 class="text-lg font-bold text-gray-800 mb-4 flex justify-between">
                        <span>अंक विभाजन (Blueprint)</span>
                        <span class="text-xs text-blue-600 bg-blue-50 px-2 py-1 rounded">2024-25</span>
                    </h3>
                    <div class="chart-container">
                        <canvas id="blueprintChart"></canvas>
                    </div>
                    <div id="chart-legend" class="mt-6 grid grid-cols-1 gap-2 text-xs text-gray-600 max-h-48 overflow-y-auto custom-scroll"></div>
                </div>

                <div class="bg-gradient-to-br from-blue-900 to-indigo-950 text-white rounded-2xl p-6 shadow-lg">
                    <h3 class="text-lg font-bold mb-4">💡 स्मार्ट स्कोरिंग टिप्स</h3>
                    <div id="strategy-tips" class="space-y-4 text-sm text-blue-100"></div>
                </div>
            </div>

            <!-- Right: Content -->
            <div class="lg:col-span-7">
                <div class="bg-white rounded-2xl shadow-sm p-6 border border-gray-100">
                    <div class="flex items-center justify-between mb-6">
                        <h3 class="text-lg font-bold text-gray-800">🔥 गोल्डन टॉपिक्स (Target 95%)</h3>
                        <span id="subjectLabel" class="text-xs font-bold py-1 px-3 rounded-full bg-gray-100 text-gray-600 uppercase tracking-widest">Physics</span>
                    </div>
                    <p class="text-sm text-gray-500 mb-6">इन टॉपिक्स को बिल्कुल न छोड़ें, ये हर साल बोर्ड परीक्षा में रिपीट होते हैं।</p>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4" id="topic-checklist"></div>
                </div>

                <!-- Motivation Area -->
                <div class="mt-6 p-6 bg-amber-50 rounded-2xl border border-amber-100 flex items-center gap-4">
                    <div class="text-3xl">🎯</div>
                    <div>
                        <p class="text-sm font-bold text-amber-900">याद रखें!</p>
                        <p class="text-xs text-amber-700">RBSE बोर्ड में आपकी राइटिंग और डायग्राम की साफ़-सफाई आपके मार्क्स 5-10% बढ़ा सकती है।</p>
                    </div>
                </div>
            </div>
        </div>

    </main>

    <!-- Modal for Answer Improver -->
    <div id="answerModal" class="fixed inset-0 bg-black/50 hidden z-[60] flex items-center justify-center p-4">
        <div class="bg-white rounded-2xl w-full max-w-2xl shadow-2xl overflow-hidden">
            <div class="p-6 border-b border-gray-100 flex justify-between items-center">
                <h3 class="text-lg font-bold text-gray-800">✨ आंसर सुधारें (Answer Improver)</h3>
                <button onclick="closeModal('answerModal')" class="text-gray-400 hover:text-gray-800 text-2xl">&times;</button>
            </div>
            <div class="p-6">
                <label class="block text-sm font-medium text-gray-700 mb-2">अपना लिखा हुआ उत्तर यहाँ पेस्ट करें:</label>
                <textarea id="answerInput" rows="8" class="w-full border-gray-200 rounded-xl text-sm focus:ring-purple-500 focus:border-purple-500 p-4" placeholder="उदाहरण के लिए, 'लेंस मेकर फार्मूला' का उत्तर यहाँ लिखें..."></textarea>
                <div class="mt-6 flex justify-end gap-3">
                    <button onclick="closeModal('answerModal')" class="px-6 py-2 text-sm font-bold text-gray-500 hover:text-gray-700">कैंसिल</button>
                    <button onclick="generateAI('improve')" id="improveBtn" class="px-6 py-2 bg-purple-600 hover:bg-purple-700 text-white rounded-xl text-sm font-bold transition">✨ चेक करें</button>
                </div>
            </div>
        </div>
    </div>

    <footer class="bg-white border-t border-gray-200 py-10 mt-12">
        <div class="max-w-7xl mx-auto px-4 text-center">
            <p class="text-sm font-bold text-gray-800">RBSE Board Class 12th Hindi Medium PCB</p>
            <p class="text-xs text-gray-500 mt-1">© 2024 Exam Prep Hub. Designed for 95% + Success.</p>
        </div>
    </footer>

    <script>
        // --- Gemini API Logic ---
        const apiKey = ""; // Runtime provides this

        async function callGemini(prompt, systemPrompt) {
            const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`;
            const payload = {
                contents: [{ parts: [{ text: prompt }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] }
            };

            let delay = 1000;
            for (let i = 0; i < 5; i++) {
                try {
                    const response = await fetch(url, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });
                    if (!response.ok) throw new Error('API Error');
                    const data = await response.json();
                    return data.candidates?.[0]?.content?.parts?.[0]?.text || "Response error.";
                } catch (error) {
                    if (i === 4) throw error;
                    await new Promise(r => setTimeout(r, delay));
                    delay *= 2;
                }
            }
        }

        // --- Data ---
        const subjectsData = {
            physics: {
                label: "Physics",
                name: "भौतिक विज्ञान",
                blueprint: [
                    { label: "स्थिर वैद्युतिकी", marks: 7 },
                    { label: "धारा विद्युत", marks: 5 },
                    { label: "चुंबकीय प्रभाव", marks: 5 },
                    { label: "EMI & AC", marks: 7 },
                    { label: "किरण प्रकाशिकी (Optics)", marks: 9 },
                    { label: "आधुनिक भौतिकी (Modern)", marks: 11 },
                    { label: "अर्धचालक (Semiconductors)", marks: 6 }
                ],
                topics: ["गॉस का नियम", "किरचॉफ के नियम", "AC जनित्र", "YDSE प्रयोग", "प्रकाश विद्युत प्रभाव", "PN संधि डायोड"],
                tips: ["Derivations को लिखकर याद करें।", "Units (V, A, T) का विशेष ध्यान रखें।", "Pencil से साफ़ डायग्राम बनाएं।"]
            },
            chemistry: {
                label: "Chemistry",
                name: "रसायन विज्ञान",
                blueprint: [
                    { label: "विलयन", marks: 6 },
                    { label: "विद्युतरसायन", marks: 6 },
                    { label: "बलगतिकी", marks: 5 },
                    { label: "d & f ब्लॉक", marks: 5 },
                    { label: "उपसहसंयोजन", marks: 5 },
                    { label: "ऑर्गेनिक केमिस्ट्री (Full)", marks: 21 },
                    { label: "जैव अणु", marks: 4 }
                ],
                topics: ["Name Reactions (Wurtz, etc.)", "Raoult's Law", "Nernst Equation", "IUPAC Nomenclature", "Lanthanoid Contraction", "SN1/SN2 Mechanism"],
                tips: ["Reaction mechanism को लिखकर अभ्यास करें।", "Reasoning questions (क्यों?) पर फोकस करें।", "Organic conversions रोज़ाना करें।"]
            },
            biology: {
                label: "Biology",
                name: "जीव विज्ञान",
                blueprint: [
                    { label: "जनन", marks: 14 },
                    { label: "आनुवंशिकी", marks: 18 },
                    { label: "मानव कल्याण", marks: 14 },
                    { label: "Biotech", marks: 10 },
                    { label: "पारिस्थितिकी", marks: 14 }
                ],
                topics: ["Double Fertilization", "Menstrual Cycle", "Mendel's Laws", "DNA Replication", "PCR Technique", "In-situ & Ex-situ Conservation"],
                tips: ["डायग्राम साफ़ और नामांकित (Labelled) हों।", "उत्तर Points में लिखें, पैराग्राफ में नहीं।", "एग्जांपल्स (Examples) हमेशा दें।"]
            },
            hindi: {
                label: "Hindi",
                name: "हिंदी अनिवार्य",
                blueprint: [
                    { label: "अपठित बोध", marks: 12 },
                    { label: "रचनात्मक लेखन", marks: 12 },
                    { label: "व्यावहारिक व्याकरण", marks: 8 },
                    { label: "आरोह", marks: 32 },
                    { label: "वितान", marks: 12 }
                ],
                topics: ["पत्र लेखन (निविदा, विज्ञप्ति)", "फीचर व आलेख", "कवि परिचय (तुलसीदास, आदि)", "सिल्वर वेडिंग", "व्याकरण के नियम"],
                tips: ["लेखन प्रारूप (Format) सही रखें।", "मात्राओं की गलती से बचें।", "प्रस्तुतिकरण पर ध्यान दें।"]
            },
            english: {
                label: "English",
                name: "English Compulsory",
                blueprint: [
                    { label: "Reading", marks: 15 },
                    { label: "Writing", marks: 15 },
                    { label: "Grammar", marks: 8 },
                    { label: "Flamingo", marks: 28 },
                    { label: "Vistas", marks: 14 }
                ],
                topics: ["Notice & Ad writing", "Job Application", "Flamingo Poetry Themes", "The Last Lesson", "The Third Level Analysis"],
                tips: ["Stick to word limits.", "Practice phrasal verbs.", "Learn poem summaries."]
            }
        };

        // --- State ---
        let currentSubject = 'physics';
        let currentChart = null;

        // --- Navigation ---
        function renderNav() {
            const nav = document.getElementById('subject-nav');
            Object.keys(subjectsData).forEach(key => {
                const btn = document.createElement('button');
                btn.className = `subject-btn px-4 py-2 rounded-full border border-gray-200 text-xs font-bold transition hover:bg-gray-100 ${key === currentSubject ? 'active' : 'bg-white text-gray-600'}`;
                btn.textContent = subjectsData[key].name;
                btn.onclick = () => switchSubject(key, btn);
                nav.appendChild(btn);
            });
        }

        function switchSubject(key, btn) {
            currentSubject = key;
            document.querySelectorAll('.subject-btn').forEach(b => {
                b.classList.remove('active', 'bg-blue-900', 'text-white');
                b.classList.add('bg-white', 'text-gray-600');
            });
            btn.classList.add('active');
            loadSubjectData(key);
            closeOutput();
        }

        // --- Dashboard Loader ---
        function loadSubjectData(key) {
            const data = subjectsData[key];
            document.getElementById('subjectLabel').textContent = data.label;

            // Chart
            if (currentChart) currentChart.destroy();
            const ctx = document.getElementById('blueprintChart').getContext('2d');
            currentChart = new Chart(ctx, {
                type: 'doughnut',
                data: {
                    labels: data.blueprint.map(b => b.label),
                    datasets: [{
                        data: data.blueprint.map(b => b.marks),
                        backgroundColor: ['#1e3a8a', '#4338ca', '#7c3aed', '#db2777', '#dc2626', '#d97706', '#059669'],
                        borderWidth: 2
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: { legend: { display: false } }
                }
            });

            // Legend
            const legend = document.getElementById('chart-legend');
            legend.innerHTML = data.blueprint.map((b, i) => `
                <div class="flex justify-between items-center bg-gray-50 p-2 rounded">
                    <span>${b.label}</span>
                    <span class="font-bold text-gray-800">${b.marks} अंक</span>
                </div>
            `).join('');

            // Tips
            document.getElementById('strategy-tips').innerHTML = data.tips.map(t => `
                <div class="flex items-start gap-3">
                    <span class="text-blue-400 mt-1">▶</span>
                    <p>${t}</p>
                </div>
            `).join('');

            // Topics
            document.getElementById('topic-checklist').innerHTML = data.topics.map(t => `
                <label class="flex items-center gap-3 p-3 bg-white border border-gray-100 rounded-xl hover:border-blue-200 cursor-pointer transition">
                    <input type="checkbox" class="h-4 w-4 rounded border-gray-300 text-blue-600 focus:ring-blue-500">
                    <span class="text-xs font-semibold text-gray-700">${t}</span>
                </label>
            `).join('');
        }

        // --- AI Actions ---
        async function generateAI(type) {
            const sub = subjectsData[currentSubject];
            let prompt = "";
            let btnId = "";
            let icon = "✨";
            let header = "";

            if (type === 'plan') {
                btnId = "planBtn";
                header = "7-Day AI Study Plan";
                prompt = `Subject: ${sub.name}. Current Topics: ${sub.topics.join(", ")}. Create a 7-day revision schedule for RBSE Board class 12 Hindi medium student to score 95%. Break it down daily. Write in Hindi.`;
            } else if (type === 'doubt') {
                const query = document.getElementById('doubtInput').value;
                if (!query) return;
                btnId = "doubtBtn";
                header = "AI Doubt Solver";
                prompt = `In Subject ${sub.name}, explain this topic in simple Hindi for class 12 RBSE: ${query}. Focus on exam definition and key points.`;
            } else if (type === 'improve') {
                const answer = document.getElementById('answerInput').value;
                if (!answer) return;
                btnId = "improveBtn";
                header = "Answer Quality Review";
                prompt = `Review this student answer for RBSE class 12 ${sub.name}: "${answer}". How to improve it to get full marks? Suggest points, underlining, and diagrams in Hindi.`;
                closeModal('answerModal');
            } else if (type === 'viva') {
                btnId = "vivaBtn";
                header = "Practical Viva Questions";
                prompt = `For RBSE class 12 ${sub.name} practical exams, list 10 most common Viva-voce questions with short answers in Hindi.`;
            }

            const btn = document.getElementById(btnId);
            const originalText = btn.innerHTML;
            btn.disabled = true;
            btn.innerHTML = `<span class="loader"></span>`;

            document.getElementById('aiOutputArea').classList.remove('hidden');
            document.getElementById('outputText').innerHTML = "✨ Gemini Guru आपके लिए कंटेंट तैयार कर रहा है...";
            document.getElementById('outputHeader').textContent = header;

            const system = "You are an expert RBSE (Rajasthan Board) teacher for Class 12 Hindi Medium. Your goal is to help students score 95%+ by providing clear, exam-oriented, and structured advice in Hindi.";

            try {
                const result = await callGemini(prompt, system);
                document.getElementById('outputText').innerHTML = result;
                document.getElementById('aiOutputArea').scrollIntoView({ behavior: 'smooth' });
            } catch (err) {
                document.getElementById('outputText').textContent = "Error: कंटेंट जनरेट नहीं हो सका। कृपया दोबारा प्रयास करें।";
            } finally {
                btn.disabled = false;
                btn.innerHTML = originalText;
            }
        }

        // --- UI Utilities ---
        function openModal(id) { document.getElementById(id).classList.remove('hidden'); }
        function closeModal(id) { document.getElementById(id).classList.add('hidden'); }
        function closeOutput() { document.getElementById('aiOutputArea').classList.add('hidden'); }

        window.onload = () => {
            renderNav();
            loadSubjectData(currentSubject);
        };
    </script>
</body>
</html>
