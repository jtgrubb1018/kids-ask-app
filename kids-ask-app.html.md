#   
<!doctype html>  
<html lang="en">  
<head>  
  <meta charset="utf-8" />  
  <meta name="viewport" content="width=device-width, initial-scale=1" />  
  <title>Can I Ask? (Kids)</title>  
  <style>  
    :root { font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif; }  
    body { margin: 0; background:#0b1220; color:#eaf0ff; }  
    .wrap { max-width: 760px; margin: 0 auto; padding: 18px; }  
    h1 { margin: 6px 0 14px; font-size: 22px; }  
    .card { background:#121b30; border:1px solid #233055; border-radius: 14px; padding: 16px; margin: 12px 0; }  
    .row { display: grid; grid-template-columns: 1fr; gap: 10px; }  
    label { font-weight: 600; display:block; margin-bottom: 6px; }  
    select, input[type="checkbox"] {  
      font-size: 16px;  
    }  
    select {  
      width: 100%;  
      padding: 10px 12px;  
      border-radius: 10px;  
      border: 1px solid #2c3c6b;  
      background:#0d1426;  
      color:#eaf0ff;  
    }  
    .grid2 { display:grid; grid-template-columns: 1fr 1fr; gap: 12px; }  
    .hint { opacity: .85; font-size: 13px; margin-top: 4px; }  
    .result {  
      display:flex; align-items:center; justify-content:space-between; gap:12px;  
      padding: 14px; border-radius: 14px; border:1px solid #2c3c6b;  
      background: linear-gradient(180deg, #0d1426, #0b1220);  
    }  
    .badge { padding: 6px 10px; border-radius: 999px; font-weight: 800; }  
    .yes { background:#0d3; color:#041; }  
    .no { background:#f55; color:#300; }  
    .pct { font-size: 34px; font-weight: 900; }  
    .small { font-size: 13px; opacity: .9; }  
    button {  
      width:100%;  
      padding: 12px 14px;  
      border-radius: 12px;  
      border: 1px solid #2c3c6b;  
      background:#1a2750;  
      color:#eaf0ff;  
      font-size: 16px;  
      font-weight: 800;  
      cursor:pointer;  
    }  
    button:active { transform: scale(.99); }  
    .todo { margin: 10px 0 0; padding-left: 18px; }  
    .footer { opacity:.75; font-size: 12px; margin-top: 10px; }  
    .settings summary { cursor: pointer; font-weight: 800; }  
    .settings .card { margin-top: 10px; }  
    input[type="number"] {  
      width: 100%;  
      padding: 10px 12px;  
      border-radius: 10px;  
      border: 1px solid #2c3c6b;  
      background:#0d1426;  
      color:#eaf0ff;  
      font-size: 16px;  
    }  
  </style>  
</head>  
<body>  
  <div class="wrap">  
    <h1>✅ Can I Ask to Play / Hang Out?</h1>  
  
    <div class="card">  
      <div class="row">  
        <div>  
          <label for="kid">Who is asking?</label>  
          <select id="kid">  
            <option value="Eloise">Eloise</option>  
            <option value="Renly">Renly</option>  
            <option value="Gavin">Gavin</option>  
          </select>  
          <div class="hint">Optional — used only for fun messaging (and future tweaking).</div>  
        </div>  
      </div>  
    </div>  
  
    <div class="card">  
      <div class="row">  
        <div class="grid2">  
          <div>  
            <label for="roomClean">Is your room clean?</label>  
            <select id="roomClean">  
              <option value="yes">Yes</option>  
              <option value="kinda">Mostly</option>  
              <option value="no">No</option>  
            </select>  
          </div>  
          <div>  
            <label for="bathroomClean">Is your bathroom clean?</label>  
            <select id="bathroomClean">  
              <option value="yes">Yes</option>  
              <option value="kinda">Mostly</option>  
              <option value="no">No</option>  
            </select>  
          </div>  
        </div>  
  
        <div class="grid2">  
          <div>  
            <label for="toiletFlushed">Is the toilet flushed?</label>  
            <select id="toiletFlushed">  
              <option value="yes">Yes</option>  
              <option value="no">No</option>  
            </select>  
          </div>  
          <div>  
            <label for="clothesFloor">Any clothes on the floor?</label>  
            <select id="clothesFloor">  
              <option value="none">None</option>  
              <option value="some">A little</option>  
              <option value="lots">Yes, a lot</option>  
            </select>  
          </div>  
        </div>  
  
        <div class="grid2">  
          <div>  
            <label for="devotional">Devotional done today?</label>  
            <select id="devotional">  
              <option value="yes">Yes</option>  
              <option value="partial">Partly</option>  
              <option value="no">No</option>  
            </select>  
          </div>  
          <div>  
            <label for="exercise">Exercised today?</label>  
            <select id="exercise">  
              <option value="yes">Yes</option>  
              <option value="some">A little</option>  
              <option value="no">No</option>  
            </select>  
          </div>  
        </div>  
  
        <div>  
          <label for="played">Already played / hung out today?</label>  
          <select id="played">  
            <option value="0">None</option>  
            <option value="30">30 minutes</option>  
            <option value="60">1 hour</option>  
            <option value="120">2 hours</option>  
            <option value="180">3+ hours</option>  
          </select>  
          <div class="hint">More play time today lowers the chance of a “yes.”</div>  
        </div>  
  
        <button id="checkBtn">Check my chances</button>  
      </div>  
    </div>  
  
    <div class="card result" id="resultCard" aria-live="polite">  
      <div>  
        <div class="small">Chance parents say yes</div>  
        <div class="pct" id="pct">—</div>  
        <div class="small" id="ruleText">Fill it out and tap “Check my chances.”</div>  
      </div>  
      <div class="badge" id="badge">—</div>  
    </div>  
  
    <div class="card">  
      <div style="font-weight:900; margin-bottom:8px;">Next steps (if you’re below 60%)</div>  
      <ul class="todo" id="todo"></ul>  
      <div class="footer">This is a “pre-check.” Parents still have the final say 🙂</div>  
    </div>  
  
    <details class="settings">  
      <summary>⚙️ Parent Settings (optional)</summary>  
      <div class="card">  
        <div class="grid2">  
          <div>  
            <label for="threshold">Ask threshold (%)</label>  
            <input id="threshold" type="number" min="0" max="100" value="60" />  
          </div>  
          <div>  
            <label for="strictMode">Strict mode?</label>  
            <select id="strictMode">  
              <option value="off">Off (default)</option>  
              <option value="on">On (harder to reach 60%)</option>  
            </select>  
            <div class="hint">Strict mode reduces bonus points and increases penalties.</div>  
          </div>  
        </div>  
      </div>  
    </details>  
  </div>  
  
<script>  
  // --- Scoring model ---  
  // Start with a baseline "maybe yes" then add/subtract points.  
  // Finally clamp 0..100 and compare to threshold.  
  
  const el = (id) => document.getElementById(id);  
  
  function clamp(n, min, max){ return Math.max(min, Math.min(max, n)); }  
  
  function scoreAnswer(value, map) {  
    return map[value] ?? 0;  
  }  
  
  function buildTodo(answers) {  
    const todos = [];  
    if (answers.roomClean !== "yes") todos.push("Clean your room (floor, bed, trash, desk).");  
    if (answers.bathroomClean !== "yes") todos.push("Clean your bathroom (sink, counter, towels).");  
    if (answers.toiletFlushed !== "yes") todos.push("Flush the toilet and check it’s clean.");  
    if (answers.clothesFloor !== "none") todos.push("Pick up clothes and put them in hamper / drawers.");  
    if (answers.devotional !== "yes") todos.push("Do today’s devotional (and tell a parent what you learned).");  
    if (answers.exercise !== "yes") todos.push("Do 10–20 minutes of exercise (walk, pushups, sport, etc.).");  
    const playedMin = parseInt(answers.played, 10);  
    if (playedMin >= 60) todos.push("You’ve already had a decent play block — consider chores/reading first.");  
    if (todos.length === 0) todos.push("You’re in great shape — ask respectfully and accept the answer.");  
    return todos;  
  }  
  
  function computeProbability(answers, strictMode=false) {  
    // Baseline: starts at 45 (so they need some wins to pass 60)  
    let p = 45;  
  
    const strictBonus = strictMode ? 0.85 : 1.0;  
    const strictPenalty = strictMode ? 1.15 : 1.0;  
  
    // Cleanliness / responsibility (big drivers)  
    p += scoreAnswer(answers.roomClean,     { yes: 18, kinda: 8,  no: -18 }) * strictBonus;  
    p += scoreAnswer(answers.bathroomClean, { yes: 14, kinda: 6,  no: -14 }) * strictBonus;  
  
    // Toilet is "non-negotiable" vibe  
    p += scoreAnswer(answers.toiletFlushed, { yes: 8, no: -20 }) * (answers.toiletFlushed === "no" ? strictPenalty : strictBonus);  
  
    // Clothes on floor penalty  
    p += scoreAnswer(answers.clothesFloor,  { none: 10, some: -6, lots: -14 }) * strictPenalty;  
  
    // Devotional + exercise  
    p += scoreAnswer(answers.devotional,    { yes: 16, partial: 7, no: -10 }) * strictBonus;  
    p += scoreAnswer(answers.exercise,      { yes: 10, some: 4, no: -8 }) * strictBonus;  
  
    // Already played today — stepwise penalty  
    const played = parseInt(answers.played, 10);  
    if (played === 0) p += 8 * strictBonus;  
    else if (played === 30) p += 2 * strictBonus;  
    else if (played === 60) p -= 6 * strictPenalty;  
    else if (played === 120) p -= 14 * strictPenalty;  
    else p -= 22 * strictPenalty;  
  
    // Clamp to 0..100  
    return Math.round(clamp(p, 0, 100));  
  }  
  
  function readAnswers() {  
    return {  
      kid: el("kid").value,  
      roomClean: el("roomClean").value,  
      bathroomClean: el("bathroomClean").value,  
      toiletFlushed: el("toiletFlushed").value,  
      clothesFloor: el("clothesFloor").value,  
      devotional: el("devotional").value,  
      exercise: el("exercise").value,  
      played: el("played").value  
    };  
  }  
  
  function render() {  
    const answers = readAnswers();  
    const threshold = clamp(parseInt(el("threshold").value || "60", 10), 0, 100);  
    const strictMode = el("strictMode").value === "on";  
    const prob = computeProbability(answers, strictMode);  
  
    el("pct").textContent = prob + "%";  
  
    const allowed = prob >= threshold;  
    const badge = el("badge");  
    const ruleText = el("ruleText");  
  
    badge.textContent = allowed ? "✅ You may ask" : "⛔ Not yet";  
    badge.className = "badge " + (allowed ? "yes" : "no");  
    ruleText.textContent = allowed  
      ? `You’re at/above ${threshold}%. Ask respectfully, and accept the answer.`  
      : `You’re below ${threshold}%. Knock out the next steps first.`;  
  
    // Todo list  
    const todos = buildTodo(answers);  
    const todoEl = el("todo");  
    todoEl.innerHTML = "";  
    todos.forEach(t => {  
      const li = document.createElement("li");  
      li.textContent = t;  
      todoEl.appendChild(li);  
    });  
  }  
  
  el("checkBtn").addEventListener("click", render);  
  
  // Auto-update if they change settings after checking once  
  ["threshold","strictMode","kid","roomClean","bathroomClean","toiletFlushed","clothesFloor","devotional","exercise","played"]  
    .forEach(id => el(id).addEventListener("change", () => {  
      // only re-render if we've already computed at least once  
      if (el("pct").textContent !== "—") render();  
    }));  
</script>  
</body>  
</html>  
