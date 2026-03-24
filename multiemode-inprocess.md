<!DOCTYPE html>
<html lang="en" class="">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SEO Blog Architect | Full-Lifecycle Content Engine</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap');
        
        body { transition: background-color 0.3s ease, color 0.3s ease; }
        
        .glass-panel {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(226, 232, 240, 0.8);
        }
        .dark .glass-panel {
            background: rgba(30, 41, 59, 0.7);
            border: 1px solid rgba(51, 65, 85, 0.8);
        }

        .loader {
            border-top-color: #6366f1;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Preview Area Content Formatting */
        .prose-output h1 { font-size: 2.25rem; font-weight: 800; margin-bottom: 1.5rem; line-height: 1.2; }
        .prose-output h2 { font-size: 1.75rem; font-weight: 700; margin-top: 2rem; margin-bottom: 1rem; }
        .prose-output h3 { font-size: 1.35rem; font-weight: 600; margin-top: 1.5rem; margin-bottom: 0.75rem; }
        .prose-output p { font-size: 1.05rem; line-height: 1.75; margin-bottom: 1.25rem; }
        .prose-output ul, .prose-output ol { margin-bottom: 1.25rem; padding-left: 1.5rem; list-style-type: disc; }
        .prose-output blockquote { border-left: 4px solid #6366f1; padding-left: 1rem; font-style: italic; margin: 1.5rem 0; opacity: 0.8; }
        .prose-output a { color: #6366f1; text-decoration: underline; font-weight: 500; }
        
        .dark .prose-output h1, .dark .prose-output h2, .dark .prose-output h3 { color: #f1f5f9; }
        .dark .prose-output p, .dark .prose-output li { color: #cbd5e1; }
        .dark .prose-output a { color: #818cf8; }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 6px; height: 6px; }
        ::-webkit-scrollbar-track { background: transparent; }
        ::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 10px; }
        .dark ::-webkit-scrollbar-thumb { background: #475569; }
        ::-webkit-scrollbar-thumb:hover { background: #94a3b8; }

        .suggestion-chip {
            transition: all 0.2s ease;
            cursor: pointer;
        }
        .suggestion-chip:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1);
        }
    </style>
</head>
<body class="bg-slate-50 dark:bg-slate-950 min-h-screen text-slate-900 dark:text-slate-100 antialiased transition-colors duration-300">

    <div class="max-w-7xl mx-auto px-4 py-6 md:py-8 h-full flex flex-col">
        <!-- Header -->
        <header class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4 mb-8 shrink-0">
            <div class="flex items-center gap-3">
                <div class="bg-indigo-600 p-2.5 rounded-xl shadow-lg shadow-indigo-500/20">
                    <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 20H5a2 2 0 01-2-2V6a2 2 0 012-2h10l4 4v10a2 2 0 01-2 2z"></path></svg>
                </div>
                <div>
                    <h1 class="text-xl font-extrabold tracking-tight leading-none">SEO Blog Architect</h1>
                    <div id="env-tag" class="text-[10px] font-bold uppercase tracking-widest mt-1 opacity-60">Detecting...</div>
                </div>
            </div>
            
            <div class="flex items-center gap-3 w-full sm:w-auto">
                <div id="status-pill" class="hidden px-3 py-1.5 rounded-full text-[10px] font-bold uppercase tracking-widest bg-indigo-100 dark:bg-indigo-900/40 text-indigo-700 dark:text-indigo-300 animate-pulse">
                    Processing
                </div>
                <button id="theme-toggle" class="p-2.5 rounded-xl bg-white dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-slate-500 dark:text-slate-400 hover:bg-slate-50 dark:hover:bg-slate-700 transition-all ml-auto sm:ml-0 shadow-sm">
                    <svg id="sun-icon" class="hidden w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364-6.364l-.707.707M6.343 17.657l-.707.707M16.071 16.071l.707.707M7.929 7.929l.707.707M12 8a4 4 0 100 8 4 4 0 000-8z"></path></svg>
                    <svg id="moon-icon" class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"></path></svg>
                </button>
            </div>
        </header>

        <main class="grid grid-cols-1 lg:grid-cols-2 gap-6 lg:h-[calc(100vh-160px)] items-stretch">
            
            <!-- Left Side: Input & Settings -->
            <div class="flex flex-col gap-4 h-full overflow-y-auto pr-1 custom-scrollbar">
                
                <!-- Main Input Mode Selector -->
                <div class="glass-panel rounded-2xl p-4 shadow-sm flex items-center justify-between shrink-0">
                    <span class="text-[10px] font-bold text-slate-400 uppercase tracking-widest">Workflow Mode</span>
                    <div class="flex bg-slate-100 dark:bg-slate-800 p-1 rounded-xl">
                        <button id="mode-architect" class="px-4 py-1.5 text-[10px] font-bold rounded-lg transition-all bg-white dark:bg-slate-700 shadow-sm text-indigo-600 dark:text-indigo-400">ARCHITECT (Text)</button>
                        <button id="mode-draft" class="px-4 py-1.5 text-[10px] font-bold rounded-lg transition-all text-slate-400 hover:text-slate-600">DRAFTEE (Topic)</button>
                    </div>
                </div>

                <!-- Text Area / Topic Input -->
                <div class="glass-panel rounded-2xl p-5 shadow-sm flex flex-col shrink-0 min-h-[250px]">
                    <div class="flex justify-between items-center mb-3">
                        <h2 id="input-label" class="text-[10px] font-bold text-slate-400 uppercase tracking-widest">Input Raw Content</h2>
                        <button id="clear-btn" class="text-[10px] text-slate-400 hover:text-red-500 font-bold transition-colors">Clear</button>
                    </div>
                    <textarea 
                        id="raw-input" 
                        placeholder="Paste your unformatted content here..."
                        class="w-full flex-grow bg-transparent resize-none focus:outline-none text-slate-700 dark:text-slate-300 text-base leading-relaxed border-none p-0"
                    ></textarea>
                    
                    <!-- Suggestions Area (Hidden by default) -->
                    <div id="suggestions-area" class="hidden mt-4 pt-4 border-t border-slate-100 dark:border-slate-800">
                        <h4 class="text-[10px] font-bold text-indigo-500 uppercase tracking-widest mb-3">Suggested Gaps & Topics</h4>
                        <div id="suggestions-container" class="flex flex-wrap gap-2">
                            <!-- Chips injected here -->
                        </div>
                    </div>
                </div>

                <!-- API CONFIGURATION PANEL -->
                <div class="glass-panel rounded-2xl p-5 shadow-sm space-y-4 shrink-0">
                    <h3 class="text-[10px] font-bold text-slate-400 uppercase tracking-widest border-b border-slate-100 dark:border-slate-800 pb-2">Settings & SEO Engine</h3>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <label class="block text-[10px] font-bold text-slate-400 uppercase mb-1.5 ml-1">Base URL (API)</label>
                            <input type="text" id="base-url-input" class="w-full bg-white dark:bg-slate-800/50 border border-slate-200 dark:border-slate-700 rounded-xl px-4 py-2 text-sm focus:ring-2 focus:ring-indigo-500 outline-none transition-all">
                        </div>
                        <div>
                            <label class="block text-[10px] font-bold text-slate-400 uppercase mb-1.5 ml-1">Model Name</label>
                            <input type="text" id="model-input" class="w-full bg-white dark:bg-slate-800/50 border border-slate-200 dark:border-slate-700 rounded-xl px-4 py-2 text-sm focus:ring-2 focus:ring-indigo-500 outline-none transition-all">
                        </div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <label class="block text-[10px] font-bold text-slate-400 uppercase mb-1.5 ml-1">API Key</label>
                            <input type="password" id="api-key-input" placeholder="Secret Key" class="w-full bg-white dark:bg-slate-800/50 border border-slate-200 dark:border-slate-700 rounded-xl px-4 py-2 text-sm focus:ring-2 focus:ring-indigo-500 outline-none transition-all">
                        </div>
                        <div>
                            <label class="block text-[10px] font-bold text-slate-400 uppercase mb-1.5 ml-1">Conversion Tone</label>
                            <select id="tone-select" class="w-full bg-white dark:bg-slate-800/50 border border-slate-200 dark:border-slate-700 rounded-xl px-4 py-2 text-sm focus:ring-2 focus:ring-indigo-500 outline-none transition-all cursor-pointer">
                                <option value="professional, authoritative, and expert">Expert / Authoritative</option>
                                <option value="STRICT_HIERARCHY">Strict (H1 -> H2 -> H3s)</option>
                                <option value="conversational, friendly, and relatable">Conversational</option>
                                <option value="persuasive, sales-oriented, and high-energy">Sales / Persuasive</option>
                            </select>
                        </div>
                    </div>

                    <!-- SITEMAP LINKING FIELD -->
                    <div class="p-4 rounded-xl bg-indigo-50/50 dark:bg-indigo-900/10 border border-indigo-100 dark:border-indigo-900/30 space-y-3">
                        <div class="flex items-end gap-2">
                            <div class="flex-grow">
                                <label class="block text-[10px] font-bold text-indigo-400 dark:text-indigo-300 uppercase mb-1.5 ml-1">Sitemap URL (XML)</label>
                                <input type="text" id="sitemap-url-input" placeholder="https://example.com/sitemap.xml" class="w-full bg-white dark:bg-slate-800 border border-indigo-200 dark:border-indigo-900 rounded-xl px-4 py-2 text-sm focus:ring-2 focus:ring-indigo-500 outline-none transition-all">
                            </div>
                            <button id="brainstorm-btn" title="Analyze Sitemap for Gaps" class="bg-indigo-100 dark:bg-indigo-900 text-indigo-600 dark:text-indigo-400 p-2.5 rounded-xl hover:bg-indigo-200 transition-colors shrink-0">
                                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"></path></svg>
                            </button>
                        </div>
                    </div>

                    <div id="proxy-settings" class="p-3 rounded-xl border border-dashed border-slate-200 dark:border-slate-700 bg-slate-50/50 dark:bg-slate-900/30">
                        <label class="block text-[10px] font-bold text-slate-400 uppercase mb-2 flex justify-between">
                            CORS Proxy
                            <a href="https://cors-anywhere.herokuapp.com/corsdemo" target="_blank" class="text-indigo-600 dark:text-indigo-400 hover:underline lowercase font-normal italic">Enable Proxy Access</a>
                        </label>
                        <input type="text" id="proxy-input" placeholder="https://cors-anywhere.herokuapp.com/" class="w-full bg-white dark:bg-slate-800/50 border border-slate-200 dark:border-slate-700 rounded-xl px-4 py-2 text-sm focus:ring-2 focus:ring-indigo-500 outline-none transition-all">
                    </div>
                    
                    <button id="convert-btn" class="w-full bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-3.5 rounded-xl transition-all shadow-lg shadow-indigo-500/20 flex items-center justify-center gap-3 active:scale-[0.98]">
                        <span>Architect SEO HTML</span>
                        <div id="loading-spinner" class="hidden loader rounded-full border-2 border-t-2 border-white/30 h-4 w-4"></div>
                    </button>
                </div>
            </div>

            <!-- Right Side: Output -->
            <div class="flex flex-col h-full lg:min-h-0">
                <div class="glass-panel rounded-2xl shadow-sm flex flex-col flex-grow overflow-hidden">
                    <!-- Tabs Nav -->
                    <div class="flex items-center justify-between bg-white/50 dark:bg-slate-800/50 border-b border-slate-200 dark:border-slate-700 px-2 shrink-0">
                        <div class="flex">
                            <button id="tab-preview" class="px-5 py-4 text-xs font-bold border-b-2 border-indigo-600 text-indigo-600 transition-all">PREVIEW</button>
                            <button id="tab-code" class="px-5 py-4 text-xs font-bold border-b-2 border-transparent text-slate-400 dark:text-slate-500 hover:text-slate-600 transition-all">HTML SOURCE</button>
                        </div>
                        <button id="copy-btn" class="mr-2 bg-slate-100 dark:bg-slate-700 hover:bg-slate-200 dark:hover:bg-slate-600 text-slate-700 dark:text-slate-200 text-[10px] font-bold px-3 py-1.5 rounded-lg transition-all flex items-center gap-2">
                            <svg class="w-3 h-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 5H6a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2v-1M8 5a2 2 0 002 2h2a2 2 0 002-2M8 5a2 2 0 012-2h2a2 2 0 012 2m0 0h2a2 2 0 012 2v3m2 4H10m0 0l3-3m-3 3l3 3"></path></svg>
                            COPY
                        </button>
                    </div>

                    <!-- Output Container with Scroll -->
                    <div class="flex-grow overflow-y-auto bg-white dark:bg-slate-900/40 custom-scrollbar p-6 md:p-10" id="output-wrapper">
                        <div id="rendered-content" class="prose-output max-w-none">
                            <div class="flex flex-col items-center justify-center h-64 text-slate-300 dark:text-slate-700 italic">
                                <svg class="w-12 h-12 mb-3 opacity-20" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"></path></svg>
                                <p class="text-sm">Architected content will appear here.</p>
                            </div>
                        </div>
                        <div id="code-content" class="hidden font-mono text-[13px] text-indigo-700 dark:text-indigo-300 whitespace-pre-wrap leading-relaxed select-all"></div>
                    </div>
                </div>
            </div>

        </main>
    </div>

    <script>
        const rawInput = document.getElementById('raw-input');
        const apiKeyInput = document.getElementById('api-key-input');
        const baseUrlInput = document.getElementById('base-url-input');
        const modelInput = document.getElementById('model-input');
        const sitemapUrlInput = document.getElementById('sitemap-url-input');
        const proxyInput = document.getElementById('proxy-input');
        const envTag = document.getElementById('env-tag');
        const convertBtn = document.getElementById('convert-btn');
        const brainstormBtn = document.getElementById('brainstorm-btn');
        const clearBtn = document.getElementById('clear-btn');
        const toneSelect = document.getElementById('tone-select');
        const loadingSpinner = document.getElementById('loading-spinner');
        const statusPill = document.getElementById('status-pill');
        const renderedContent = document.getElementById('rendered-content');
        const codeContent = document.getElementById('code-content');
        const tabPreview = document.getElementById('tab-preview');
        const tabCode = document.getElementById('tab-code');
        const copyBtn = document.getElementById('copy-btn');
        const themeToggle = document.getElementById('theme-toggle');
        
        const modeArchitect = document.getElementById('mode-architect');
        const modeDraft = document.getElementById('mode-draft');
        const inputLabel = document.getElementById('input-label');
        const suggestionsArea = document.getElementById('suggestions-area');
        const suggestionsContainer = document.getElementById('suggestions-container');

        const DEFAULT_PROXY = "https://cors-anywhere.herokuapp.com/";
        const DEFAULT_URL = "https://integrate.api.nvidia.com/v1";
        const DEFAULT_MODEL = "openai/gpt-oss-120b";
        let isLocal = false;
        let currentMode = 'architect'; 

        // --- UI FUNCTIONS ---
        function setLoading(loading) {
            convertBtn.disabled = loading;
            brainstormBtn.disabled = loading;
            loadingSpinner.classList.toggle('hidden', !loading);
            statusPill.classList.toggle('hidden', !loading);
            
            const btnText = convertBtn.querySelector('span');
            if (loading) {
                btnText.innerText = currentMode === 'draft' ? "DRAFTING..." : "ARCHITECTING...";
            } else {
                btnText.innerText = currentMode === 'draft' ? "Draft & Architect Content" : "Architect SEO HTML";
            }
        }

        // Dark Mode Logic
        function initTheme() {
            const savedTheme = localStorage.getItem('theme');
            if (savedTheme === 'dark' || (!savedTheme && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
                document.documentElement.classList.add('dark');
                updateThemeIcons(true);
            } else {
                updateThemeIcons(false);
            }
        }

        function updateThemeIcons(isDark) {
            document.getElementById('sun-icon').classList.toggle('hidden', !isDark);
            document.getElementById('moon-icon').classList.toggle('hidden', isDark);
        }

        themeToggle.onclick = () => {
            const isDark = document.documentElement.classList.toggle('dark');
            localStorage.setItem('theme', isDark ? 'dark' : 'light');
            updateThemeIcons(isDark);
        };

        // Workflow Mode Handling
        modeArchitect.onclick = () => {
            currentMode = 'architect';
            inputLabel.innerText = "Input Raw Content";
            rawInput.placeholder = "Paste your unformatted content here...";
            modeArchitect.classList.add('bg-white', 'dark:bg-slate-700', 'shadow-sm', 'text-indigo-600', 'dark:text-indigo-400');
            modeArchitect.classList.remove('text-slate-400');
            modeDraft.classList.remove('bg-white', 'dark:bg-slate-700', 'shadow-sm', 'text-indigo-600', 'dark:text-indigo-400');
            modeDraft.classList.add('text-slate-400');
            convertBtn.querySelector('span').innerText = "Architect SEO HTML";
        };

        modeDraft.onclick = () => {
            currentMode = 'draft';
            inputLabel.innerText = "Target Topic / Keywords";
            rawInput.placeholder = "Enter a blog topic or seed keywords...";
            modeDraft.classList.add('bg-white', 'dark:bg-slate-700', 'shadow-sm', 'text-indigo-600', 'dark:text-indigo-400');
            modeDraft.classList.remove('text-slate-400');
            modeArchitect.classList.remove('bg-white', 'dark:bg-slate-700', 'shadow-sm', 'text-indigo-600', 'dark:text-indigo-400');
            modeArchitect.classList.add('text-slate-400');
            convertBtn.querySelector('span').innerText = "Draft & Architect Content";
        };

        // Preferences Persistence
        function loadPrefs() {
            apiKeyInput.value = localStorage.getItem('seo_arch_key') || '';
            baseUrlInput.value = localStorage.getItem('seo_arch_url') || DEFAULT_URL;
            modelInput.value = localStorage.getItem('seo_arch_model') || DEFAULT_MODEL;
            sitemapUrlInput.value = localStorage.getItem('seo_arch_sitemap_url') || '';
            proxyInput.value = localStorage.getItem('seo_arch_proxy') || '';
        }

        function savePrefs() {
            localStorage.setItem('seo_arch_key', apiKeyInput.value);
            localStorage.setItem('seo_arch_url', baseUrlInput.value);
            localStorage.setItem('seo_arch_model', modelInput.value);
            localStorage.setItem('seo_arch_sitemap_url', sitemapUrlInput.value);
            localStorage.setItem('seo_arch_proxy', proxyInput.value);
        }

        function detectEnv() {
            isLocal = window.location.hostname === "localhost" || 
                      window.location.hostname === "127.0.0.1" || 
                      window.location.protocol === "file:";
            
            if (isLocal) {
                envTag.innerText = "LOCAL / PROXY ACTIVE";
                envTag.classList.add('text-amber-500');
                if (!proxyInput.value) proxyInput.value = DEFAULT_PROXY;
            } else {
                envTag.innerText = "WEB / DIRECT MODE";
                envTag.classList.add('text-emerald-500');
            }
        }

        initTheme();
        loadPrefs();
        detectEnv();

        // Sitemap Fetch Helper
        async function getVerifiedUrls(sitemapUrl, proxy) {
            if (!sitemapUrl) return [];
            try {
                const finalUrl = proxy ? proxy + sitemapUrl : sitemapUrl;
                const response = await fetch(finalUrl);
                if (!response.ok) throw new Error("Could not reach sitemap.");
                const text = await response.text();
                const parser = new DOMParser();
                const xmlDoc = parser.parseFromString(text, "text/xml");
                const locs = xmlDoc.getElementsByTagName("loc");
                const urls = Array.from(locs).map(l => l.textContent.trim());
                return [...new Set(urls)].slice(0, 150);
            } catch (err) {
                console.error("Sitemap Fetch Error:", err);
                return [];
            }
        }

        // Universal API Fetcher
        async function fetchAPI(userPrompt, systemPrompt) {
            const userApiKey = apiKeyInput.value.trim();
            const baseUrl = baseUrlInput.value.trim();
            const modelName = modelInput.value.trim();
            const manualProxy = proxyInput.value.trim();
            
            let API_URL = baseUrl.endsWith('/') ? baseUrl + 'chat/completions' : baseUrl + '/chat/completions';
            if (isLocal || (manualProxy && manualProxy !== "")) {
                API_URL = manualProxy + API_URL;
            }

            const response = await fetch(API_URL, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                    'Authorization': `Bearer ${userApiKey}`
                },
                body: JSON.stringify({
                    model: modelName,
                    messages: [
                        { role: "system", content: systemPrompt },
                        { role: "user", content: userPrompt }
                    ],
                    temperature: currentMode === 'draft' ? 0.7 : 0.1,
                    max_tokens: 4096
                })
            });

            if (!response.ok) {
                const errData = await response.json().catch(() => ({}));
                throw new Error(errData.error?.message || errData.message || `API Error: ${response.status}`);
            }

            const data = await response.json();
            return data.choices[0].message.content;
        }

        // Brainstorming Logic
        brainstormBtn.onclick = async () => {
            const userApiKey = apiKeyInput.value.trim();
            const sitemapUrl = sitemapUrlInput.value.trim();
            if (!userApiKey || !sitemapUrl) return alert("Please enter API Key and Sitemap URL.");
            
            setLoading(true);
            statusPill.innerText = "BRAINSTORMING...";
            statusPill.classList.remove('hidden');

            try {
                const verifiedUrls = await getVerifiedUrls(sitemapUrl, proxyInput.value.trim() || (isLocal ? DEFAULT_PROXY : ""));
                
                const prompt = `Based on these existing URLs from my sitemap, suggest 5 trending blog topics that are highly relevant but not yet covered. Output ONLY the 5 titles, one per line. No numbers.
                
                URLS:
                ${verifiedUrls.join('\n')}`;

                const response = await fetchAPI(prompt, "You are an SEO Content Strategist.");
                const topics = response.split('\n').filter(t => t.trim().length > 1);

                suggestionsContainer.innerHTML = '';
                topics.forEach(topic => {
                    const chip = document.createElement('div');
                    chip.className = "suggestion-chip px-3 py-1.5 rounded-lg bg-indigo-100 dark:bg-indigo-900/40 text-indigo-700 dark:text-indigo-300 text-[10px] font-bold border border-indigo-200 dark:border-indigo-800";
                    chip.innerText = topic.replace(/^\d+\.\s*/, '').replace(/^-+\s*/, '');
                    chip.onclick = () => {
                        rawInput.value = chip.innerText;
                        modeDraft.click();
                        rawInput.focus();
                    };
                    suggestionsContainer.appendChild(chip);
                });
                suggestionsArea.classList.remove('hidden');
                statusPill.innerText = "STRATEGY READY";
                setTimeout(() => statusPill.classList.add('hidden'), 3000);
            } catch (err) {
                alert("Brainstorming failed: " + err.message);
            } finally {
                setLoading(false);
            }
        };

        // Tab Navigation
        tabPreview.onclick = () => {
            tabPreview.classList.add('border-indigo-600', 'text-indigo-600');
            tabPreview.classList.remove('border-transparent', 'text-slate-400');
            tabCode.classList.remove('border-indigo-600', 'text-indigo-600');
            tabCode.classList.add('border-transparent', 'text-slate-400');
            renderedContent.classList.remove('hidden');
            codeContent.classList.add('hidden');
        };

        tabCode.onclick = () => {
            tabCode.classList.add('border-indigo-600', 'text-indigo-600');
            tabCode.classList.remove('border-transparent', 'text-slate-400');
            tabPreview.classList.remove('border-indigo-600', 'text-indigo-600');
            tabPreview.classList.add('border-transparent', 'text-slate-400');
            codeContent.classList.remove('hidden');
            renderedContent.classList.add('hidden');
        };

        clearBtn.onclick = () => {
            rawInput.value = "";
            renderedContent.innerHTML = `<div class="flex flex-col items-center justify-center h-64 text-slate-300 dark:text-slate-700 italic"><p class="text-sm">Content cleared.</p></div>`;
            codeContent.innerText = "";
            currentHtml = "";
        };

        // Main Execution
        convertBtn.onclick = async () => {
            const text = rawInput.value.trim();
            if (!text) return alert("Please enter content or a topic first!");
            const userApiKey = apiKeyInput.value.trim();
            if (!userApiKey) return alert("API Key required.");

            setLoading(true);
            savePrefs();

            try {
                const sitemapUrl = sitemapUrlInput.value.trim();
                const verifiedUrls = sitemapUrl ? await getVerifiedUrls(sitemapUrl, proxyInput.value.trim() || (isLocal ? DEFAULT_PROXY : "")) : [];
                const currentTone = toneSelect.value;

                let systemPrompt = "";
                let userPrompt = text;

                // Mode-based System Instruction
                if (currentMode === 'draft') {
                    systemPrompt = `You are a professional SEO Content Writer. 
                    TASK: Write a comprehensive, long-form blog article based on the user's topic. 
                    TONE: You MUST write in a ${currentTone} tone.
                    STRUCTURE:
                    1. Use exactly ONE <h1> for the title. 
                    2. Use exactly ONE <h2> for the secondary main section.
                    3. Use multiple <h3> for specific sub-points.
                    4. Content must be 800+ words.
                    5. Output ONLY raw HTML (<p>, <ul>, <li>, <strong>, <blockquote>). No code blocks.`;
                } else {
                    systemPrompt = `You are an SEO Content Engineer. 
                    TASK: Transform the user's raw text into a professional HTML blog post.
                    TONE: Apply a ${currentTone} tone throughout.
                    ${currentTone === 'STRICT_HIERARCHY' ? 'STRICT RULE: 1-H1, 1-H2, multi-H3. VERBATIM words - no edits.' : ''}
                    FORMAT: Use tags like <p>, <ul>, <li>, <strong>, <blockquote>. No code blocks.`;
                }

                // INTERNAL LINKING LOGIC (Applied to both modes)
                if (verifiedUrls.length > 0) {
                    systemPrompt += `
                    
                    ### INTERNAL LINKING RULES (CRITICAL) ###
                    1. IDENTIFY 3-5 keywords in standard <p> paragraphs.
                    2. WRAP these keywords in <a href="URL">...</a> tags using ONLY the verified pool below.
                    3. STRICTURE: DO NOT use the same URL more than once. (No duplicates).
                    4. STRICTURE: NEVER add <a> tags inside <h1>, <h2>, or <h3> elements. Only within <p> or <li>.
                    5. ACCURACY: Match keywords contextually to the provided URLs.
                    
                    VERIFIED URL POOL:
                    ${verifiedUrls.join('\n')}`;
                }

                const result = await fetchAPI(userPrompt, systemPrompt);
                currentHtml = result.replace(/```html|```/g, '').trim();
                renderedContent.innerHTML = currentHtml;
                codeContent.innerText = currentHtml;
                tabPreview.click();
            } catch (err) {
                console.error(err);
                renderedContent.innerHTML = `<div class="p-6 bg-red-50 dark:bg-red-900/20 border border-red-200 dark:border-red-900/50 rounded-xl text-red-600 dark:text-red-400">Error: ${err.message}</div>`;
            } finally {
                setLoading(false);
            }
        };

        copyBtn.onclick = () => {
            if (!currentHtml) return;
            const temp = document.createElement('textarea');
            temp.value = currentHtml;
            document.body.appendChild(temp);
            temp.select();
            document.execCommand('copy');
            document.body.removeChild(temp);
            const originalText = copyBtn.innerHTML;
            copyBtn.innerHTML = '<span class="text-emerald-500 font-bold">COPIED!</span>';
            setTimeout(() => copyBtn.innerHTML = originalText, 2000);
        };
    </script>
</body>
</html>