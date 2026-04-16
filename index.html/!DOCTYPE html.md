**<!DOCTYPE html>**

**<html lang="en">**

**<head>**

&#x20; **<meta charset="UTF-8"/>**

&#x20; **<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"/>**

&#x20; **<title>Dragon Mine Predictor</title>**



&#x20; **<!-- Telegram Mini App SDK — REQUIRED for BotFather Mini Apps -->**

&#x20; **<script src="https://telegram.org/js/telegram-web-app.js"></script>**



&#x20; **<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@600;700\&family=Inter:wght@300;400;500\&display=swap" rel="stylesheet"/>**



&#x20; **<style>**

&#x20;   **:root {**

&#x20;     **--bg: #0f1117;**

&#x20;     **--bg2: #161b24;**

&#x20;     **--card: #1a2030;**

&#x20;     **--card2: #1f2535;**

&#x20;     **--border: #2a3348;**

&#x20;     **--green: #00ff6a;**

&#x20;     **--green-dim: #00cc55;**

&#x20;     **--green-glow: rgba(0,255,106,0.25);**

&#x20;     **--text: #e2e8f0;**

&#x20;     **--muted: #64748b;**

&#x20;     **--label: #94a3b8;**

&#x20;   **}**



&#x20;   **\* { box-sizing: border-box; margin: 0; padding: 0; -webkit-tap-highlight-color: transparent; }**



&#x20;   **html, body {**

&#x20;     **height: 100%;**

&#x20;     **overflow-x: hidden;**

&#x20;   **}**



&#x20;   **body {**

&#x20;     **background: var(--bg);**

&#x20;     **color: var(--text);**

&#x20;     **font-family: 'Inter', sans-serif;**

&#x20;     **min-height: 100vh;**

&#x20;     **display: flex;**

&#x20;     **flex-direction: column;**

&#x20;     **align-items: center;**

&#x20;     **padding: 16px 16px 40px;**

&#x20;     **background-image:**

&#x20;       **radial-gradient(ellipse at 50% 0%, rgba(0,255,106,0.05) 0%, transparent 55%),**

&#x20;       **radial-gradient(ellipse at 80% 90%, rgba(30,60,120,0.12) 0%, transparent 50%);**

&#x20;   **}**



&#x20;   **/\* ── Header ── \*/**

&#x20;   **header {**

&#x20;     **width: 100%;**

&#x20;     **max-width: 480px;**

&#x20;     **text-align: center;**

&#x20;     **padding: 20px 0 18px;**

&#x20;     **animation: fadeDown 0.6s ease both;**

&#x20;   **}**



&#x20;   **.logo {**

&#x20;     **width: 62px; height: 62px;**

&#x20;     **background: linear-gradient(135deg, #1a9c52, #00ff6a);**

&#x20;     **border-radius: 50%;**

&#x20;     **display: flex; align-items: center; justify-content: center;**

&#x20;     **font-size: 1.8rem;**

&#x20;     **margin: 0 auto 12px;**

&#x20;     **box-shadow: 0 0 24px var(--green-glow);**

&#x20;   **}**



&#x20;   **h1 {**

&#x20;     **font-family: 'Rajdhani', sans-serif;**

&#x20;     **font-size: 1.5rem;**

&#x20;     **font-weight: 700;**

&#x20;     **color: #fff;**

&#x20;     **letter-spacing: 0.05em;**

&#x20;     **text-transform: uppercase;**

&#x20;   **}**



&#x20;   **.subtitle {**

&#x20;     **font-size: 0.8rem;**

&#x20;     **color: var(--muted);**

&#x20;     **margin-top: 4px;**

&#x20;   **}**



&#x20;   **/\* ── Card ── \*/**

&#x20;   **.card {**

&#x20;     **background: var(--card);**

&#x20;     **border: 1px solid var(--border);**

&#x20;     **border-radius: 16px;**

&#x20;     **padding: 20px 18px 22px;**

&#x20;     **width: 100%;**

&#x20;     **max-width: 480px;**

&#x20;     **box-shadow: 0 12px 40px rgba(0,0,0,0.45);**

&#x20;     **animation: fadeUp 0.6s 0.1s ease both;**

&#x20;   **}**



&#x20;   **.card-title {**

&#x20;     **font-family: 'Rajdhani', sans-serif;**

&#x20;     **font-size: 1.15rem;**

&#x20;     **font-weight: 700;**

&#x20;     **color: #fff;**

&#x20;     **margin-bottom: 4px;**

&#x20;   **}**



&#x20;   **.card-sub {**

&#x20;     **font-size: 0.78rem;**

&#x20;     **color: var(--muted);**

&#x20;     **margin-bottom: 18px;**

&#x20;     **line-height: 1.5;**

&#x20;   **}**



&#x20;   **/\* ── Fields ── \*/**

&#x20;   **.field { margin-bottom: 14px; }**



&#x20;   **.field-label {**

&#x20;     **display: flex; align-items: center; gap: 6px;**

&#x20;     **font-size: 0.68rem;**

&#x20;     **font-weight: 500;**

&#x20;     **letter-spacing: 0.11em;**

&#x20;     **text-transform: uppercase;**

&#x20;     **color: var(--label);**

&#x20;     **margin-bottom: 6px;**

&#x20;   **}**



&#x20;   **.field-label svg { width: 13px; height: 13px; opacity: 0.7; flex-shrink: 0; }**



&#x20;   **.input-wrap { position: relative; }**



&#x20;   **input {**

&#x20;     **width: 100%;**

&#x20;     **background: var(--bg2);**

&#x20;     **border: 1px solid var(--border);**

&#x20;     **border-radius: 10px;**

&#x20;     **color: var(--text);**

&#x20;     **font-family: 'Inter', monospace;**

&#x20;     **font-size: 0.9rem;**

&#x20;     **padding: 13px 44px 13px 14px;**

&#x20;     **outline: none;**

&#x20;     **transition: border-color 0.2s, box-shadow 0.2s;**

&#x20;     **-webkit-appearance: none;**

&#x20;   **}**



&#x20;   **input::placeholder { color: var(--muted); font-size: 0.85rem; }**

&#x20;   **input:focus { border-color: var(--green-dim); box-shadow: 0 0 0 3px var(--green-glow); }**



&#x20;   **.copy-btn {**

&#x20;     **position: absolute; right: 10px; top: 50%; transform: translateY(-50%);**

&#x20;     **background: none; border: none; cursor: pointer;**

&#x20;     **color: var(--muted); padding: 4px; border-radius: 4px;**

&#x20;     **transition: color 0.2s; display: flex; align-items: center;**

&#x20;   **}**

&#x20;   **.copy-btn:active { color: var(--green); }**

&#x20;   **.copy-btn svg { width: 15px; height: 15px; }**



&#x20;   **/\* ── Button ── \*/**

&#x20;   **.btn-init {**

&#x20;     **width: 100%;**

&#x20;     **padding: 15px;**

&#x20;     **background: var(--green);**

&#x20;     **border: none;**

&#x20;     **border-radius: 12px;**

&#x20;     **color: #061a0d;**

&#x20;     **font-family: 'Rajdhani', sans-serif;**

&#x20;     **font-size: 1rem;**

&#x20;     **font-weight: 700;**

&#x20;     **letter-spacing: 0.13em;**

&#x20;     **text-transform: uppercase;**

&#x20;     **cursor: pointer;**

&#x20;     **margin-top: 10px;**

&#x20;     **transition: background 0.2s, transform 0.12s, box-shadow 0.2s;**

&#x20;     **box-shadow: 0 4px 20px var(--green-glow);**

&#x20;     **touch-action: manipulation;**

&#x20;   **}**



&#x20;   **.btn-init:active:not(:disabled) {**

&#x20;     **transform: scale(0.97);**

&#x20;     **box-shadow: 0 2px 10px var(--green-glow);**

&#x20;   **}**



&#x20;   **.btn-init:disabled { opacity: 0.45; cursor: not-allowed; }**



&#x20;   **/\* ── Result ── \*/**

&#x20;   **.result-wrap {**

&#x20;     **width: 100%; max-width: 480px;**

&#x20;     **margin-top: 18px;**

&#x20;     **animation: fadeUp 0.5s ease both;**

&#x20;   **}**



&#x20;   **.result-card {**

&#x20;     **background: var(--card);**

&#x20;     **border: 1px solid var(--green-dim);**

&#x20;     **border-radius: 16px;**

&#x20;     **padding: 18px 16px 20px;**

&#x20;     **box-shadow: 0 0 20px var(--green-glow), 0 12px 40px rgba(0,0,0,0.4);**

&#x20;     **position: relative; overflow: hidden;**

&#x20;   **}**



&#x20;   **.result-card::before {**

&#x20;     **content: '';**

&#x20;     **position: absolute; top: 0; left: 0; right: 0; height: 2px;**

&#x20;     **background: linear-gradient(90deg, transparent, var(--green), transparent);**

&#x20;   **}**



&#x20;   **.result-label {**

&#x20;     **font-size: 0.67rem; font-weight: 600;**

&#x20;     **letter-spacing: 0.13em; text-transform: uppercase;**

&#x20;     **color: var(--green); margin-bottom: 14px;**

&#x20;     **display: flex; align-items: center; gap: 6px;**

&#x20;   **}**



&#x20;   **.result-label::after {**

&#x20;     **content: ''; flex: 1; height: 1px;**

&#x20;     **background: linear-gradient(90deg, var(--border), transparent);**

&#x20;   **}**



&#x20;   **/\* ── 5×5 Grid ── \*/**

&#x20;   **.mines-grid {**

&#x20;     **display: grid;**

&#x20;     **grid-template-columns: repeat(5, 1fr);**

&#x20;     **gap: 8px;**

&#x20;     **margin-bottom: 14px;**

&#x20;   **}**



&#x20;   **.mine-cell {**

&#x20;     **aspect-ratio: 1;**

&#x20;     **border-radius: 10px;**

&#x20;     **background: var(--bg2);**

&#x20;     **border: 2px solid var(--border);**

&#x20;     **display: flex; align-items: center; justify-content: center;**

&#x20;     **font-size: 1.4rem;**

&#x20;     **position: relative; overflow: hidden;**

&#x20;   **}**



&#x20;   **.mine-cell.safe {**

&#x20;     **background: linear-gradient(135deg, #0b4d25, #18844a);**

&#x20;     **border-color: var(--green);**

&#x20;     **box-shadow: 0 0 14px rgba(0,255,106,0.4), inset 0 1px 0 rgba(255,255,255,0.12);**

&#x20;     **animation: gemPop 0.38s ease both;**

&#x20;   **}**



&#x20;   **.mine-cell.safe::before {**

&#x20;     **content: '';**

&#x20;     **position: absolute; inset: 0;**

&#x20;     **background: linear-gradient(135deg, rgba(255,255,255,0.1) 0%, transparent 55%);**

&#x20;     **border-radius: 8px;**

&#x20;   **}**



&#x20;   **@keyframes gemPop {**

&#x20;     **0%   { transform: scale(0.65); opacity: 0; }**

&#x20;     **70%  { transform: scale(1.07); }**

&#x20;     **100% { transform: scale(1);    opacity: 1; }**

&#x20;   **}**



&#x20;   **.result-note {**

&#x20;     **font-size: 0.78rem; color: var(--muted);**

&#x20;     **text-align: center; line-height: 1.6;**

&#x20;   **}**

&#x20;   **.result-note span { color: var(--green); font-weight: 600; }**



&#x20;   **/\* ── Loader ── \*/**

&#x20;   **.loader { display: flex; justify-content: center; gap: 6px; padding: 14px 0; }**

&#x20;   **.loader span {**

&#x20;     **width: 7px; height: 7px; background: var(--green);**

&#x20;     **border-radius: 50%; animation: bounce 1s infinite ease-in-out;**

&#x20;   **}**

&#x20;   **.loader span:nth-child(2) { animation-delay: 0.15s; }**

&#x20;   **.loader span:nth-child(3) { animation-delay: 0.3s; }**



&#x20;   **.error-msg { color: #f87171; font-size: 0.88rem; }**



&#x20;   **/\* ── History ── \*/**

&#x20;   **.history-wrap {**

&#x20;     **width: 100%; max-width: 480px;**

&#x20;     **margin-top: 20px;**

&#x20;     **animation: fadeUp 0.5s ease both;**

&#x20;   **}**



&#x20;   **.history-title {**

&#x20;     **font-size: 0.67rem; font-weight: 600;**

&#x20;     **letter-spacing: 0.11em; text-transform: uppercase;**

&#x20;     **color: var(--muted); margin-bottom: 10px;**

&#x20;     **display: flex; align-items: center; gap: 8px;**

&#x20;   **}**

&#x20;   **.history-title::before, .history-title::after {**

&#x20;     **content: ''; flex: 1; height: 1px; background: var(--border);**

&#x20;   **}**



&#x20;   **.history-item {**

&#x20;     **background: var(--card2);**

&#x20;     **border: 1px solid var(--border);**

&#x20;     **border-radius: 10px;**

&#x20;     **padding: 10px 14px;**

&#x20;     **margin-bottom: 8px;**

&#x20;     **display: flex; align-items: center; gap: 12px;**

&#x20;   **}**



&#x20;   **.history-meta {**

&#x20;     **color: var(--muted); font-size: 0.72rem;**

&#x20;     **margin-bottom: 5px;**

&#x20;   **}**



&#x20;   **.mini-grid {**

&#x20;     **display: grid;**

&#x20;     **grid-template-columns: repeat(5, 12px);**

&#x20;     **gap: 2px; flex-shrink: 0;**

&#x20;   **}**



&#x20;   **.mini-cell { width: 12px; height: 12px; border-radius: 2px; background: var(--border); }**

&#x20;   **.mini-cell.safe { background: var(--green-dim); }**



&#x20;   **.history-info { flex: 1; }**

&#x20;   **.history-count { font-size: 0.8rem; color: var(--green); font-weight: 600; }**



&#x20;   **/\* ── Animations ── \*/**

&#x20;   **@keyframes fadeDown {**

&#x20;     **from { opacity: 0; transform: translateY(-14px); }**

&#x20;     **to   { opacity: 1; transform: translateY(0); }**

&#x20;   **}**

&#x20;   **@keyframes fadeUp {**

&#x20;     **from { opacity: 0; transform: translateY(14px); }**

&#x20;     **to   { opacity: 1; transform: translateY(0); }**

&#x20;   **}**

&#x20;   **@keyframes bounce {**

&#x20;     **0%, 80%, 100% { transform: scale(0.55); opacity: 0.35; }**

&#x20;     **40%            { transform: scale(1);    opacity: 1; }**

&#x20;   **}**

&#x20; **</style>**

**</head>**

**<body>**



**<header>**

&#x20; **<div class="logo">🐉</div>**

&#x20; **<h1>Dragon Mine Predictor</h1>**

&#x20; **<p class="subtitle">AI-powered safe cell prediction</p>**

**</header>**



**<div class="card">**

&#x20; **<div class="card-title">Configuration</div>**

&#x20; **<p class="card-sub">Enter your current game seeds to calibrate the AI predictor.</p>**



&#x20; **<div class="field">**

&#x20;   **<div class="field-label">**

&#x20;     **<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">**

&#x20;       **<circle cx="12" cy="12" r="3"/>**

&#x20;       **<path d="M12 1v4M12 19v4M4.22 4.22l2.83 2.83M16.95 16.95l2.83 2.83M1 12h4M19 12h4M4.22 19.78l2.83-2.83M16.95 7.05l2.83-2.83"/>**

&#x20;     **</svg>**

&#x20;     **Active Client Seed**

&#x20;   **</div>**

&#x20;   **<div class="input-wrap">**

&#x20;     **<input type="text" id="seed" placeholder="Ex: HcHSwy62Lq" autocomplete="off" autocorrect="off" spellcheck="false"/>**

&#x20;     **<button class="copy-btn" onclick="copyField('seed')" title="Copy">**

&#x20;       **<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">**

&#x20;         **<rect x="9" y="9" width="13" height="13" rx="2"/>**

&#x20;         **<path d="M5 15H4a2 2 0 01-2-2V4a2 2 0 012-2h9a2 2 0 012 2v1"/>**

&#x20;       **</svg>**

&#x20;     **</button>**

&#x20;   **</div>**

&#x20; **</div>**



&#x20; **<div class="field">**

&#x20;   **<div class="field-label">**

&#x20;     **<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">**

&#x20;       **<rect x="2" y="6" width="20" height="12" rx="2"/>**

&#x20;       **<path d="M6 10h.01M10 10h.01M14 10h.01"/>**

&#x20;     **</svg>**

&#x20;     **Active Server Seed (Hashed)**

&#x20;   **</div>**

&#x20;   **<div class="input-wrap">**

&#x20;     **<input type="text" id="phrase" placeholder="Ex: 5ac99db755..." autocomplete="off" autocorrect="off" spellcheck="false"/>**

&#x20;     **<button class="copy-btn" onclick="copyField('phrase')" title="Copy">**

&#x20;       **<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">**

&#x20;         **<rect x="9" y="9" width="13" height="13" rx="2"/>**

&#x20;         **<path d="M5 15H4a2 2 0 01-2-2V4a2 2 0 012-2h9a2 2 0 012 2v1"/>**

&#x20;       **</svg>**

&#x20;     **</button>**

&#x20;   **</div>**

&#x20; **</div>**



&#x20; **<button class="btn-init" id="predictBtn" onclick="predict()">⚡ Initialize AI</button>**

**</div>**



**<div id="resultWrap" class="result-wrap" style="display:none;"></div>**

**<div id="historyWrap" class="history-wrap" style="display:none;"></div>**



**<script>**

&#x20; **// ── Telegram Mini App Init ──**

&#x20; **const tg = window.Telegram?.WebApp;**

&#x20; **if (tg) {**

&#x20;   **tg.ready();**

&#x20;   **tg.expand();**

&#x20;   **// Use Telegram theme colors if available**

&#x20;   **if (tg.colorScheme === 'light') {**

&#x20;     **document.documentElement.style.setProperty('--bg', '#f0f2f5');**

&#x20;     **document.documentElement.style.setProperty('--bg2', '#ffffff');**

&#x20;     **document.documentElement.style.setProperty('--card', '#ffffff');**

&#x20;     **document.documentElement.style.setProperty('--text', '#111827');**

&#x20;     **document.documentElement.style.setProperty('--muted', '#6b7280');**

&#x20;   **}**

&#x20; **}**



&#x20; **const gameHistory = \[];**



&#x20; **function copyField(id) {**

&#x20;   **const val = document.getElementById(id).value;**

&#x20;   **if (!val) return;**

&#x20;   **navigator.clipboard.writeText(val).catch(() => {**

&#x20;     **// fallback for older Telegram WebView**

&#x20;     **const el = document.createElement('textarea');**

&#x20;     **el.value = val;**

&#x20;     **document.body.appendChild(el);**

&#x20;     **el.select();**

&#x20;     **document.execCommand('copy');**

&#x20;     **document.body.removeChild(el);**

&#x20;   **});**

&#x20;   **if (tg) tg.HapticFeedback?.notificationOccurred('success');**

&#x20; **}**



&#x20; **function escapeHtml(str) {**

&#x20;   **return String(str)**

&#x20;     **.replace(/\&/g,'\&amp;').replace(/</g,'\&lt;')**

&#x20;     **.replace(/>/g,'\&gt;').replace(/"/g,'\&quot;');**

&#x20; **}**



&#x20; **function renderGrid(safeCells) {**

&#x20;   **let html = '<div class="mines-grid">';**

&#x20;   **for (let i = 0; i < 25; i++) {**

&#x20;     **const isSafe = safeCells.includes(i);**

&#x20;     **const delay = isSafe ? `animation-delay:${safeCells.indexOf(i) \* 75}ms` : '';**

&#x20;     **html += `<div class="mine-cell${isSafe ? ' safe' : ''}" style="${delay}">${isSafe ? '💎' : ''}</div>`;**

&#x20;   **}**

&#x20;   **return html + '</div>';**

&#x20; **}**



&#x20; **function renderMiniGrid(safeCells) {**

&#x20;   **let html = '<div class="mini-grid">';**

&#x20;   **for (let i = 0; i < 25; i++) {**

&#x20;     **html += `<div class="mini-cell${safeCells.includes(i) ? ' safe' : ''}"></div>`;**

&#x20;   **}**

&#x20;   **return html + '</div>';**

&#x20; **}**



&#x20; **async function predict() {**

&#x20;   **const seed   = document.getElementById('seed').value.trim();**

&#x20;   **const phrase = document.getElementById('phrase').value.trim();**



&#x20;   **if (!seed || !phrase) {**

&#x20;     **if (tg) tg.HapticFeedback?.notificationOccurred('error');**

&#x20;     **alert('Please enter both a Client Seed and a Server Seed.');**

&#x20;     **return;**

&#x20;   **}**



&#x20;   **const btn = document.getElementById('predictBtn');**

&#x20;   **btn.disabled = true;**

&#x20;   **if (tg) tg.HapticFeedback?.impactOccurred('medium');**



&#x20;   **const resultWrap = document.getElementById('resultWrap');**

&#x20;   **resultWrap.style.display = 'block';**

&#x20;   **resultWrap.innerHTML = `**

&#x20;     **<div class="result-card">**

&#x20;       **<div class="result-label">🔮 AI is calculating safe cells…</div>**

&#x20;       **<div class="loader"><span></span><span></span><span></span></div>**

&#x20;     **</div>`;**



&#x20;   **// Smooth scroll to result on mobile**

&#x20;   **setTimeout(() => resultWrap.scrollIntoView({ behavior: 'smooth', block: 'start' }), 100);**



&#x20;   **try {**

&#x20;     **const response = await fetch("https://api.anthropic.com/v1/messages", {**

&#x20;       **method: "POST",**

&#x20;       **headers: { "Content-Type": "application/json" },**

&#x20;       **body: JSON.stringify({**

&#x20;         **model: "claude-sonnet-4-20250514",**

&#x20;         **max\_tokens: 400,**

&#x20;         **system: `You are a Mines game AI predictor. Given a client seed and a hashed server seed, predict which cells are SAFE on a 5x5 grid (25 cells, numbered 0–24, left to right, top to bottom).**



**Use the character values and structure of both seeds as entropy to select 5–10 safe cell indices.**



**Respond ONLY with valid JSON — no markdown, no explanation outside JSON:**

**{"safe":\[0,3,7,12,18,22],"reason":"One sentence on how the seeds determined this pattern."}**



**Rules: "safe" must have 5–10 unique integers from 0–24.`,**

&#x20;         **messages: \[{**

&#x20;           **role: "user",**

&#x20;           **content: `Client Seed: ${seed}\\nServer Seed (Hashed): ${phrase}\\n\\nPredict safe cells.`**

&#x20;         **}]**

&#x20;       **})**

&#x20;     **});**



&#x20;     **const data = await response.json();**

&#x20;     **const rawText = data.content?.map(b => b.text || '').join('') || '';**



&#x20;     **let parsed;**

&#x20;     **try {**

&#x20;       **parsed = JSON.parse(rawText.replace(/```json|```/g, '').trim());**

&#x20;     **} catch {**

&#x20;       **throw new Error('Unexpected AI response format. Try again.');**

&#x20;     **}**



&#x20;     **const safeCells = (parsed.safe || \[]).filter(n => Number.isInteger(n) \&\& n >= 0 \&\& n < 25).slice(0, 10);**

&#x20;     **const reason    = parsed.reason || '';**



&#x20;     **if (safeCells.length === 0) throw new Error('AI could not determine safe cells. Try again.');**



&#x20;     **resultWrap.innerHTML = `**

&#x20;       **<div class="result-card">**

&#x20;         **<div class="result-label">💎 Safe Cells — AI Prediction</div>**

&#x20;         **${renderGrid(safeCells)}**

&#x20;         **<div class="result-note">**

&#x20;           **<span>${safeCells.length} safe cells</span> predicted from your seeds.<br>${escapeHtml(reason)}**

&#x20;         **</div>**

&#x20;       **</div>`;**



&#x20;     **if (tg) tg.HapticFeedback?.notificationOccurred('success');**



&#x20;     **gameHistory.unshift({ seed, safeCells, reason });**

&#x20;     **renderHistory();**



&#x20;   **} catch (err) {**

&#x20;     **resultWrap.innerHTML = `**

&#x20;       **<div class="result-card">**

&#x20;         **<div class="result-label">⚠ Error</div>**

&#x20;         **<p class="error-msg">${escapeHtml(err.message)}</p>**

&#x20;       **</div>`;**

&#x20;     **if (tg) tg.HapticFeedback?.notificationOccurred('error');**

&#x20;   **}**



&#x20;   **btn.disabled = false;**

&#x20; **}**



&#x20; **function renderHistory() {**

&#x20;   **if (gameHistory.length === 0) return;**

&#x20;   **const wrap = document.getElementById('historyWrap');**

&#x20;   **wrap.style.display = 'block';**

&#x20;   **wrap.innerHTML = '<div class="history-title">Past Predictions</div>' +**

&#x20;     **gameHistory.slice(0, 5).map(h => `**

&#x20;       **<div class="history-item">**

&#x20;         **${renderMiniGrid(h.safeCells)}**

&#x20;         **<div class="history-info">**

&#x20;           **<div class="history-meta">${escapeHtml(h.seed.substring(0, 20))}${h.seed.length > 20 ? '…' : ''}</div>**

&#x20;           **<div class="history-count">${h.safeCells.length} safe cells predicted</div>**

&#x20;         **</div>**

&#x20;       **</div>`).join('');**

&#x20; **}**



&#x20; **document.getElementById('seed').addEventListener('keydown', e => {**

&#x20;   **if (e.key === 'Enter') document.getElementById('phrase').focus();**

&#x20; **});**

&#x20; **document.getElementById('phrase').addEventListener('keydown', e => {**

&#x20;   **if (e.key === 'Enter') predict();**

&#x20; **});**

**</script>**

**</body>**

**</html>**



