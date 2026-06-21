<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Силовые стандарты по весу тела</title>
  <style>
    :root {
      --bg: #f6f7fb;
      --card: #ffffff;
      --text: #182033;
      --muted: #697386;
      --line: #d9deea;
      --head: #eef2ff;
      --accent: #3957d8;
      --accent-soft: #e7ebff;
      --good: #0f766e;
      --shadow: 0 12px 35px rgba(24, 32, 51, 0.08);
      --radius: 18px;
    }

    * { box-sizing: border-box; }

    body {
      margin: 0;
      font-family: Inter, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Arial, sans-serif;
      background: radial-gradient(circle at top left, #ffffff 0, var(--bg) 42%, #eef1f8 100%);
      color: var(--text);
      line-height: 1.45;
    }

    .wrap {
      max-width: 1120px;
      margin: 0 auto;
      padding: 32px 18px 48px;
    }

    .hero {
      display: grid;
      grid-template-columns: 1.4fr 0.9fr;
      gap: 22px;
      align-items: stretch;
      margin-bottom: 22px;
    }

    .card {
      background: var(--card);
      border: 1px solid rgba(217, 222, 234, 0.8);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
    }

    .intro { padding: 28px; }

    h1 {
      margin: 0 0 10px;
      font-size: clamp(28px, 4vw, 44px);
      line-height: 1.05;
      letter-spacing: -0.04em;
    }

    .lead {
      max-width: 720px;
      margin: 0;
      color: var(--muted);
      font-size: 17px;
    }

    .controls {
      padding: 22px;
      display: grid;
      gap: 14px;
      align-content: start;
    }

    .input-row { display: grid; gap: 7px; }

    label {
      font-weight: 700;
      font-size: 14px;
    }

    input[type="number"] {
      width: 100%;
      font: inherit;
      font-size: 20px;
      font-weight: 700;
      padding: 13px 14px;
      border: 1px solid var(--line);
      border-radius: 12px;
      outline: none;
      background: #fff;
      color: var(--text);
    }

    input[type="number"]:focus {
      border-color: var(--accent);
      box-shadow: 0 0 0 4px var(--accent-soft);
    }

    .hint {
      color: var(--muted);
      font-size: 13px;
    }

    .table-card { overflow: hidden; }

    .table-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 14px;
      padding: 18px 22px;
      border-bottom: 1px solid var(--line);
      background: linear-gradient(90deg, #ffffff, #f7f8ff);
    }

    h2 {
      margin: 0;
      font-size: 19px;
      letter-spacing: -0.02em;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      border-radius: 999px;
      padding: 7px 10px;
      font-size: 13px;
      font-weight: 700;
      color: var(--accent);
      background: var(--accent-soft);
      white-space: nowrap;
    }

    .table-wrap {
      overflow-x: auto;
      -webkit-overflow-scrolling: touch;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      min-width: 760px;
      background: white;
    }

    th, td {
      padding: 13px 14px;
      border-bottom: 1px solid var(--line);
      text-align: center;
      vertical-align: middle;
    }

    th:first-child, td:first-child {
      text-align: left;
      position: sticky;
      left: 0;
      background: inherit;
      z-index: 1;
      min-width: 225px;
    }

    thead th {
      background: var(--head);
      font-size: 13px;
      text-transform: uppercase;
      letter-spacing: 0.04em;
      color: #36415c;
    }

    tbody tr:nth-child(even) td { background: #fbfcff; }
    tbody tr.section-gap td { border-bottom: 8px solid #f3f5fb; }

    td:first-child { font-weight: 700; color: #263049; }
    .value { font-weight: 800; font-variant-numeric: tabular-nums; }
    .text-value { font-weight: 700; }

    .note {
      margin-top: 16px;
      padding: 16px 18px;
      color: var(--muted);
      font-size: 14px;
      background: rgba(255, 255, 255, 0.72);
      border: 1px solid rgba(217, 222, 234, 0.9);
      border-radius: 14px;
    }

    .footer {
      margin-top: 18px;
      color: var(--muted);
      font-size: 13px;
      text-align: center;
    }

    @media (max-width: 820px) {
      .hero { grid-template-columns: 1fr; }
      .wrap { padding-top: 18px; }
      .intro, .controls { padding: 20px; }
      .table-top { align-items: flex-start; flex-direction: column; }
      th, td { padding: 11px 12px; }
    }

    @media print {
      body { background: #fff; }
      .card { box-shadow: none; }
      .controls { display: none; }
      .hero { grid-template-columns: 1fr; }
      .table-wrap { overflow: visible; }
      table { min-width: 0; }
    }
  </style>
</head>
<body>
  <main class="wrap">
    <section class="hero">
      <div class="card intro">
        <h1>Силовые стандарты по весу тела</h1>
        <p class="lead">Введите вес тела и рост — калькулятор пересчитает целевые показатели по уровням. Все расчёты выполняются локально в браузере. Ваши результаты видите только вы.</p>
      </div>

      <form class="card controls" onsubmit="return false;" aria-label="Параметры калькулятора">
        <div class="input-row">
          <label for="bodyWeight">Вес тела, кг</label>
          <input id="bodyWeight" type="number" inputmode="decimal" min="30" max="250" step="0.1" value="77" />
          <div class="hint">Используется для расчёта упражнений с весом.</div>
        </div>
        <div class="input-row">
          <label for="heightCm">Рост, см</label>
          <input id="heightCm" type="number" inputmode="decimal" min="120" max="230" step="0.1" value="178" />
          <div class="hint">Используется для прыжка в длину.</div>
        </div>
      </form>
    </section>

    <section class="card table-card">
      <div class="table-top">
        <h2>Нормативы</h2>
        <span class="badge" id="currentParams">77 кг · 178 см</span>
      </div>
      <div class="table-wrap">
        <table aria-describedby="tableNote">
          <thead>
            <tr>
              <th>Упражнение</th>
              <th>Начинающий<br><span class="hint">6 мес</span></th>
              <th>Продолжающий<br><span class="hint">2 года</span></th>
              <th>Оптимальный<br><span class="hint">3 года</span></th>
              <th>Фанат<br><span class="hint">4+ лет</span></th>
            </tr>
          </thead>
          <tbody id="standardsBody"></tbody>
        </table>
      </div>
    </section>

    <p id="tableNote" class="note">Силовые показатели указаны в килограммах. 1RM — примерный максимум на одно повторение, 5RM — примерный максимум на пять повторений. Значения со штангой округляются до ближайших 2,5 кг.</p>
    <div class="footer">Автономный HTML-калькулятор на основе силовых стандартов strengthlevel.com</div>
  </main>

  <script>
    const levels = ["beginner", "intermediate", "optimal", "fan"];

    const strengthRows = [
      { label: "Становая 1RM", multipliers: [1.00, 1.75, 2.25, 3.00] },
      { label: "Становая 5RM", multipliers: [0.87, 1.52, 1.96, 2.61], gap: true },
      { label: "Присед 1RM", multipliers: [0.80, 1.25, 1.75, 2.25] },
      { label: "Присед 5RM", multipliers: [0.70, 1.09, 1.52, 1.96], gap: true },
      { label: "Жим лёжа 1RM", multipliers: [0.60, 1.00, 1.50, 2.00] },
      { label: "Жим лёжа 5RM", multipliers: [0.52, 0.87, 1.30, 1.74], gap: true },
      { label: "Жим стоя 1RM", multipliers: [0.40, 0.65, 0.90, 1.10] },
      { label: "Жим стоя 5RM", multipliers: [0.35, 0.57, 0.78, 0.96], gap: true }
    ];

    const fixedRows = [
      { label: "Подтягивания", values: ["1–5", "8–12", "15–20", "25+"], gap: true },
      { label: "Отжимания", values: ["20", "40", "60", "80"], gap: true },
      { label: "VO₂max", values: ["40", "50", "60", "70"], gap: true },
      { label: "Пульс в покое", values: ["60", "50", "40", "30"], gap: true },
      { label: "Прыжок в длину (% роста)", jumpMultipliers: [1.10, 1.30, 1.50, 1.60], gap: true },
      { label: "Пистолетик (на каждую ногу)", values: ["Устойчивая стойка на одной ноге 30 сек", "5", "10", "10 с доп. весом"] }
    ];

    const body = document.getElementById("standardsBody");
    const bodyWeightInput = document.getElementById("bodyWeight");
    const heightInput = document.getElementById("heightCm");
    const currentParams = document.getElementById("currentParams");

    function roundToIncrement(value, increment = 2.5) {
      return Math.round(value / increment) * increment;
    }

    function formatKg(value) {
      const rounded = roundToIncrement(value);
      return Number.isInteger(rounded) ? String(rounded) : rounded.toFixed(1);
    }

    function formatCm(value) {
      const rounded = Math.round(value * 10) / 10;
      return Number.isInteger(rounded) ? String(rounded) : rounded.toFixed(1);
    }

    function makeCell(content, className = "value") {
      const td = document.createElement("td");
      td.className = className;
      td.textContent = content;
      return td;
    }

    function makeRow(label, values, gap = false) {
      const tr = document.createElement("tr");
      if (gap) tr.classList.add("section-gap");
      tr.appendChild(makeCell(label, "exercise"));
      values.forEach(value => tr.appendChild(makeCell(value, typeof value === "string" && value.length > 8 ? "text-value" : "value")));
      return tr;
    }

    function recalc() {
      const bodyWeight = Number(bodyWeightInput.value) || 0;
      const height = Number(heightInput.value) || 0;
      body.innerHTML = "";

      strengthRows.forEach(row => {
        const values = row.multipliers.map(multiplier => formatKg(bodyWeight * multiplier));
        body.appendChild(makeRow(row.label, values, row.gap));
      });

      fixedRows.forEach(row => {
        let values;
        if (row.jumpMultipliers) {
          values = row.jumpMultipliers.map(multiplier => formatCm(height * multiplier));
        } else {
          values = row.values;
        }
        body.appendChild(makeRow(row.label, values, row.gap));
      });

      currentParams.textContent = `${bodyWeight || "—"} кг · ${height || "—"} см`;
    }

    bodyWeightInput.addEventListener("input", recalc);
    heightInput.addEventListener("input", recalc);
    recalc();
  </script>
</body>
</html>
