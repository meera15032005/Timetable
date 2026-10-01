<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <meta name="theme-color" content="#0f172a" />
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />
  <meta name="mobile-web-app-capable" content="yes" />
  <meta name="application-name" content="Study Habit Tracker" />
  <meta name="apple-mobile-web-app-title" content="Study Tracker" />
  <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>📚</text></svg>" />
  <title>Study + Habit + Diary Pro Tracker</title>
  <style>
    :root {
      --bg: #0f172a;
      --card: #1e293b;
      --card2: #334155;
      --text: #f1f5f9;
      --muted: #94a3b8;
      --primary: #3b82f6;
      --primary-hover: #2563eb;
      --success: #22c55e;
      --warning: #f59e0b;
      --danger: #ef4444;
      --border: #334155;
      --radius: 16px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      -webkit-tap-highlight-color: transparent;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      padding-bottom: 85px;
      line-height: 1.5;
    }

    .header {
      background: linear-gradient(135deg, #1e293b, #0f172a);
      padding: 20px 16px 16px;
      position: sticky;
      top: 0;
      z-index: 100;
      border-bottom: 1px solid var(--border);
    }

    .header h1 {
      font-size: 1.35rem;
      font-weight: 700;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .header p {
      color: var(--muted);
      font-size: 0.85rem;
      margin-top: 2px;
    }

    .container {
      padding: 16px;
      max-width: 480px;
      margin: 0 auto;
    }

    .card {
      background: var(--card);
      border-radius: var(--radius);
      padding: 16px;
      margin-bottom: 14px;
      border: 1px solid var(--border);
    }

    .card h2 {
      font-size: 1rem;
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .stat-box {
      background: var(--card2);
      border-radius: 12px;
      padding: 14px;
      text-align: center;
    }

    .stat-box .value {
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--primary);
    }

    .stat-box .label {
      font-size: 0.75rem;
      color: var(--muted);
      margin-top: 2px;
    }

    .progress-bar {
      height: 10px;
      background: var(--card2);
      border-radius: 99px;
      overflow: hidden;
      margin: 8px 0;
    }

    .progress-fill {
      height: 100%;
      background: linear-gradient(90deg, var(--primary), #60a5fa);
      border-radius: 99px;
      transition: width 0.4s ease;
    }

    .progress-fill.success { background: linear-gradient(90deg, var(--success), #4ade80); }
    .progress-fill.warning { background: linear-gradient(90deg, var(--warning), #fbbf24); }

    input, select, textarea {
      width: 100%;
      background: var(--card2);
      border: 1px solid var(--border);
      color: var(--text);
      padding: 12px 14px;
      border-radius: 12px;
      font-size: 1rem;
      outline: none;
      margin-bottom: 10px;
    }

    input:focus, select:focus, textarea:focus {
      border-color: var(--primary);
    }

    label {
      display: block;
      font-size: 0.85rem;
      color: var(--muted);
      margin-bottom: 4px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      padding: 12px 18px;
      border: none;
      border-radius: 12px;
      font-size: 0.95rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.2s;
      width: 100%;
    }

    .btn-primary { background: var(--primary); color: white; }
    .btn-primary:active { background: var(--primary-hover); }
    .btn-success { background: var(--success); color: white; }
    .btn-danger { background: var(--danger); color: white; }
    .btn-outline { background: transparent; border: 1px solid var(--border); color: var(--text); }
    .btn-sm { padding: 8px 12px; font-size: 0.85rem; width: auto; }

    .btn-group { display: flex; gap: 8px; margin-top: 10px; }

    .habit-item {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 12px;
      background: var(--card2);
      border-radius: 12px;
      margin-bottom: 8px;
    }

    .habit-item .name { font-weight: 500; flex: 1; }
    .habit-item .streak { font-size: 0.8rem; color: var(--warning); margin-right: 10px; }

    .check-btn {
      width: 36px;
      height: 36px;
      border-radius: 50%;
      border: 2px solid var(--border);
      background: transparent;
      color: var(--text);
      font-size: 1.1rem;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
    }

    .check-btn.done {
      background: var(--success);
      border-color: var(--success);
      color: white;
    }

    .nav {
      position: fixed;
      bottom: 0;
      left: 0;
      right: 0;
      background: var(--card);
      border-top: 1px solid var(--border);
      display: flex;
      justify-content: space-around;
      padding: 8px 0 calc(8px + env(safe-area-inset-bottom));
      z-index: 100;
    }

    .nav-btn {
      background: none;
      border: none;
      color: var(--muted);
      font-size: 0.65rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 2px;
      padding: 6px 4px;
      cursor: pointer;
      flex: 1;
      min-width: 0;
    }

    .nav-btn.active { color: var(--primary); }
    .nav-btn span { font-size: 1.2rem; }

    .section { display: none; }
    .section.active { display: block; }

    .timer-display {
      font-size: 3.5rem;
      font-weight: 700;
      text-align: center;
      font-variant-numeric: tabular-nums;
      letter-spacing: 2px;
      margin: 20px 0;
    }

    .timer-controls {
      display: flex;
      gap: 12px;
      justify-content: center;
      margin-bottom: 16px;
    }

    .milestone {
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 10px;
      background: var(--card2);
      border-radius: 10px;
      margin-bottom: 8px;
      font-size: 0.9rem;
    }

    .milestone.achieved { border-left: 4px solid var(--success); }
    .milestone.locked { opacity: 0.5; }

    .toast {
      position: fixed;
      top: 20px;
      left: 50%;
      transform: translateX(-50%);
      background: var(--card2);
      color: white;
      padding: 12px 20px;
      border-radius: 12px;
      z-index: 999;
      box-shadow: 0 8px 24px rgba(0,0,0,0.4);
      opacity: 0;
      transition: opacity 0.3s;
      pointer-events: none;
      max-width: 90%;
      text-align: center;
    }

    .toast.show { opacity: 1; }

    .empty {
      text-align: center;
      color: var(--muted);
      padding: 30px 10px;
      font-size: 0.95rem;
    }

    /* Bar Charts for Weekly Report */
    .chart-container {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      height: 120px;
      padding-top: 20px;
      margin-top: 15px;
      border-bottom: 1px solid var(--border);
    }

    .chart-bar-group {
      display: flex;
      flex-direction: column;
      align-items: center;
      flex: 1;
    }

    .chart-bar {
      width: 14px;
      background: var(--primary);
      border-radius: 4px 4px 0 0;
      transition: height 0.3s ease;
      min-height: 4px;
    }

    .chart-bar.mobile {
      background: var(--warning);
      margin-left: 2px;
    }

    .chart-label {
      font-size: 0.65rem;
      color: var(--muted);
      margin-top: 6px;
    }

    .badge {
      display: inline-block;
      background: var(--primary);
      color: white;
      font-size: 0.7rem;
      padding: 2px 8px;
      border-radius: 99px;
      margin-left: 6px;
    }
  </style>
</head>
<body>
  <div class="header">
    <h1>📚 Study + Habit Tracker Pro</h1>
    <p id="today-date">Loading...</p>
  </div>

  <div class="container">
    <!-- DASHBOARD -->
    <div id="dashboard" class="section active">
      <div class="card">
        <h2>📊 Aaj ka Progress</h2>
        <div class="grid-2">
          <div class="stat-box">
            <div class="value" id="dash-study">0m</div>
            <div class="label">Study</div>
          </div>
          <div class="stat-box">
            <div class="value" id="dash-mobile">0m</div>
            <div class="label">Mobile Use</div>
          </div>
        </div>
        <div style="margin-top:14px">
          <div style="display:flex;justify-content:space-between;font-size:0.85rem">
            <span>Study Goal</span>
            <span id="dash-study-pct">0%</span>
          </div>
          <div class="progress-bar"><div class="progress-fill" id="dash-study-bar" style="width:0%"></div></div>
        </div>
        <div style="margin-top:10px">
          <div style="display:flex;justify-content:space-between;font-size:0.85rem">
            <span>Mobile Limit</span>
            <span id="dash-mobile-pct">0%</span>
          </div>
          <div class="progress-bar"><div class="progress-fill warning" id="dash-mobile-bar" style="width:0%"></div></div>
        </div>
      </div>

      <div class="card">
        <h2>🔥 Streaks & Milestones</h2>
        <div id="milestones-list"></div>
      </div>

      <div class="card">
        <h2>🕒 Agla Task (Timetable)</h2>
        <div id="dash-next-task"></div>
      </div>

      <div class="card">
        <h2>✅ Aaj ke Habits</h2>
        <div id="dash-habits"></div>
      </div>
    </div>

    <!-- GOALS -->
    <div id="goals" class="section">
      <div class="card">
        <h2>🎯 Daily Goals Set Karo</h2>
        <label>Study Goal (minutes)</label>
        <input type="number" id="goal-study" min="1" max="1440" placeholder="e.g. 120" />
        <label>Mobile Max Limit (minutes)</label>
        <input type="number" id="goal-mobile" min="0" max="1440" placeholder="e.g. 60" />
        <button class="btn btn-primary" onclick="saveGoals()">Save Goals</button>
      </div>

      <div class="card">
        <h2>📝 Aaj ka Log Submit Karo</h2>
        <label>Kitna padha? (minutes)</label>
        <input type="number" id="log-study" min="0" max="1440" placeholder="0" />
        <label>Mobile kitna use kiya? (minutes)</label>
        <input type="number" id="log-mobile" min="0" max="1440" placeholder="0" />
        <button class="btn btn-success" onclick="submitDailyLog()">Submit Aaj ka Data</button>
      </div>
    </div>

    <!-- HABITS -->
    <div id="habits" class="section">
      <div class="card">
        <h2>➕ Naya Habit Add Karo</h2>
        <input type="text" id="new-habit" placeholder="e.g. Subah 6 baje uthna" maxlength="50" />
        <button class="btn btn-primary" onclick="addHabit()">Add Habit</button>
      </div>

      <div class="card">
        <h2>📋 Mere Habits</h2>
        <div id="habits-list"></div>
      </div>
    </div>

    <!-- TIMER -->
    <div id="timer" class="section">
      <div class="card">
        <h2>⏱️ Study Timer</h2>
        <div class="timer-display" id="timer-display">25:00</div>
        <div style="display:flex;gap:10px;margin-bottom:16px">
          <input type="number" id="timer-minutes" min="1" max="180" value="25" style="margin:0" />
          <button class="btn btn-outline btn-sm" onclick="setTimerMinutes()" style="width:auto;padding:0 16px">Set</button>
        </div>
        <div class="timer-controls">
          <button class="btn btn-primary" id="timer-start" onclick="startTimer()" style="width:auto;min-width:100px">Start</button>
          <button class="btn btn-outline" id="timer-pause" onclick="pauseTimer()" style="width:auto;min-width:100px" disabled>Pause</button>
          <button class="btn btn-danger" onclick="resetTimer()" style="width:auto;min-width:100px">Reset</button>
        </div>
        <p style="text-align:center;color:var(--muted);font-size:0.85rem;margin-top:10px">
          Timer complete hote hi time automatic aapke study log me add ho jayega.
        </p>
        <button class="btn btn-outline" style="margin-top:12px" onclick="requestNotifPermission()">🔔 Notification Permission</button>
      </div>
    </div>

    <!-- TIMETABLE -->
    <div id="timetable" class="section">
      <div class="card">
        <h2>🕒 Time Table Banao</h2>
        <p style="color:var(--muted);font-size:0.85rem;margin-bottom:12px">
          Time + Task set karo. Time aate hi alarm tune / notification bajega.
        </p>
        <label>Time (24-hour)</label>
        <input type="time" id="tt-time" />
        <label>Task / Kaam</label>
        <input type="text" id="tt-task" placeholder="e.g. Maths chapter 5 padhna" maxlength="80" />
        <button class="btn btn-primary" onclick="addTimetableEntry()">➕ Add to Timetable</button>
      </div>

      <div class="card">
        <h2>📋 Aaj ka Time Table</h2>
        <div id="timetable-list"></div>
      </div>
    </div>

    <!-- PRIVATE DIARY -->
    <div id="diary" class="section">
      <div id="diary-lock" class="card" style="text-align:center; padding:30px 16px;">
        <span style="font-size:3rem">🔒</span>
        <h2 style="justify-content:center; margin-top:10px;">Personal Locked Diary</h2>
        <p style="color:var(--muted); font-size:0.85rem; margin-bottom:15px;" id="diary-lock-msg">
          Apni private daily diary dekhne ke liye 4-digit PIN enter karein.
        </p>
        <input type="password" id="diary-pin-input" maxlength="4" pattern="\d*" placeholder="****" style="text-align:center; font-size:1.5rem; letter-spacing:8px; max-width:180px; margin:0 auto 15px auto;" />
        <button class="btn btn-primary" onclick="unlockDiary()">Unlock / Set PIN</button>
      </div>

      <div id="diary-content" style="display:none;">
        <div class="card">
          <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:10px;">
            <h2>📖 Aaj ki Dincharya</h2>
            <button class="btn btn-outline btn-sm" onclick="lockDiary()">🔒 Lock</button>
          </div>
          <label>Date Select Karein</label>
          <input type="date" id="diary-date" onchange="loadDiaryEntry()" />
          <label>Aaj ka din kaisa raha? Apni dincharya likhein:</label>
          <textarea id="diary-text" rows="8" placeholder="Aaj maine kya-kya kiya, kya naya sikha..."></textarea>
          <button class="btn btn-success" onclick="saveDiaryEntry()">Save Diary Entry</button>
        </div>

        <div class="card">
          <h2>⚙️ Security Settings</h2>
          <button class="btn btn-outline btn-sm" style="color:var(--danger)" onclick="resetDiaryPin()">Reset PIN Code</button>
        </div>
      </div>
    </div>

    <!-- REPORT -->
    <div id="report" class="section">
      <div class="card">
        <h2>📅 Weekly Summary</h2>
        <div id="weekly-summary"></div>
        <div class="chart-container" id="weekly-chart"></div>
        <div style="display:flex; justify-content:center; gap:15px; margin-top:10px; font-size:0.75rem;">
          <span style="color:var(--primary)">■ Study</span>
          <span style="color:var(--warning)">■ Mobile</span>
        </div>
      </div>
      <div class="card">
        <h2>💾 Data Backup</h2>
        <div class="btn-group">
          <button class="btn btn-outline" onclick="exportData()">Export JSON</button>
          <button class="btn btn-outline" onclick="document.getElementById('import-file').click()">Import JSON</button>
        </div>
        <input type="file" id="import-file" accept=".json" style="display:none" onchange="importData(event)" />
      </div>
    </div>
  </div>

  <!-- BOTTOM NAV -->
  <div class="nav">
    <button class="nav-btn active" data-section="dashboard" onclick="showSection('dashboard')">
      <span>🏠</span> Home
    </button>
    <button class="nav-btn" data-section="goals" onclick="showSection('goals')">
      <span>🎯</span> Goals
    </button>
    <button class="nav-btn" data-section="habits" onclick="showSection('habits')">
      <span>✅</span> Habits
    </button>
    <button class="nav-btn" data-section="timetable" onclick="showSection('timetable')">
      <span>🕒</span> Plan
    </button>
    <button class="nav-btn" data-section="timer" onclick="showSection('timer')">
      <span>⏱️</span> Timer
    </button>
    <button class="nav-btn" data-section="diary" onclick="showSection('diary')">
      <span>🔒</span> Diary
    </button>
    <button class="nav-btn" data-section="report" onclick="showSection('report')">
      <span>📊</span> Report
    </button>
  </div>

  <div class="toast" id="toast"></div>

  <script>
    const STORAGE_KEY = 'study_habit_tracker_pro';

    function defaultData() {
      return {
        goals: { study: 120, mobile: 90 },
        habits: [],
        logs: {},
        timetable: [],
        diaryPin: null,
        lastAlarmTriggered: {},
        createdAt: new Date().toISOString()
      };
    }

    function loadData() {
      try {
        const raw = localStorage.getItem(STORAGE_KEY);
        if (!raw) return defaultData();
        const parsed = JSON.parse(raw);
        if (!parsed.goals || !parsed.habits || !parsed.logs) return defaultData();
        if (!parsed.timetable) parsed.timetable = [];
        if (!parsed.lastAlarmTriggered) parsed.lastAlarmTriggered = {};
        return parsed;
      } catch (e) {
        return defaultData();
      }
    }

    function saveData(data) {
      try {
        localStorage.setItem(STORAGE_KEY, JSON.stringify(data));
        return true;
      } catch (e) {
        showToast('Storage full! Data save nahi hua.');
        return false;
      }
    }

    let data = loadData();

    function playBeepSound() {
      try {
        const ctx = new (window.AudioContext || window.webkitAudioContext)();
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.type = 'sine';
        osc.frequency.setValueAtTime(587.33, ctx.currentTime);
        gain.gain.setValueAtTime(0.3, ctx.currentTime);
        osc.connect(gain);
        gain.connect(ctx.destination);
        osc.start();
        osc.stop(ctx.currentTime + 0.8);
      } catch(e){}
    }

    function todayKey() {
      const d = new Date();
      return d.getFullYear() + '-' + String(d.getMonth()+1).padStart(2,'0') + '-' + String(d.getDate()).padStart(2,'0');
    }

    function formatMinutes(m) {
      if (m < 60) return m + 'm';
      const h = Math.floor(m / 60);
      const mins = m % 60;
      return mins ? `${h}h ${mins}m` : `${h}h`;
    }

    function showToast(msg, duration = 2500) {
      const t = document.getElementById('toast');
      t.textContent = msg;
      t.classList.add('show');
      setTimeout(() => t.classList.remove('show'), duration);
    }

    function getLog(dateKey) {
      if (!data.logs[dateKey]) {
        data.logs[dateKey] = { study: 0, mobile: 0, habits: {}, diary: "", submitted: false };
      }
      return data.logs[dateKey];
    }

    function showSection(id) {
      document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
      document.getElementById(id).classList.add('active');
      document.querySelectorAll('.nav-btn').forEach(b => {
        b.classList.toggle('active', b.dataset.section === id);
      });
      if (id === 'dashboard') renderDashboard();
      if (id === 'habits') renderHabits();
      if (id === 'goals') renderGoalsForm();
      if (id === 'timetable') renderTimetable();
      if (id === 'diary'
