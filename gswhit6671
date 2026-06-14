/* ═══════════════════════════════════════════════════════
   IB REPORT CARD CHECKER  — app.js
   GitHub Pages static site (runs entirely in the browser)
════════════════<!DOCTYPE html>
<html lang="en"># IB Report Card Comment Checker
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --blue:      #1f4e79;
  --blue2:     #2f6fb0;
  --soft-blue: #e8f1ff;
  --red:       #c0392b;
  --red-bg:    #fde8e8;
  --amber:     #c47d00;
  --amber-bg:  #fff8e1;
  --green:     #176b34;
  --green-bg:  #e8f8ee;
  --border:    #d8e1f0;
  --text:      #1f2937;
  --muted:     #6b7280;
  --radius:    18px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  background: radial-gradient(circle at top left, rgba(47,111,176,0.14), transparent 38%),
              linear-gradient(135deg, #f7faff 0%, #eef3fb 100%);
  color: var(--text);
  min-height: 100vh;
  font-size: 15px;
  line-height: 1.5;
}

.page {
  width: min(1180px, 94%);
  margin: 0 auto;
  padding: 40px 0 60px;
  display: flex;
  flex-direction: column;
  gap: 22px;
}

/* ── HERO ──────────────────────────────────────────── */
.hero {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 22px;
  align-items: center;
}

.hero-card {
  background: rgba(255,255,255,0.94);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  box-shadow: 0 16px 48px rgba(31,78,121,0.11);
  padding: 36px;
}

.badge {
  display: inline-block;
  background: var(--soft-blue);
  color: var(--blue);
  font-weight: 700;
  font-size: 12px;
  padding: 6px 14px;
  border-radius: 99px;
  margin-bottom: 16px;
  letter-spacing: .02em;
}

h1 {
  font-size: clamp(30px, 4.5vw, 50px);
  color: #173b72;
  line-height: 1.08;
  letter-spacing: -1px;
  margin-bottom: 14px;
}

.subtitle {
  font-size: 16px;
  color: var(--muted);
  line-height: 1.6;
}

.mini-panel {
  background: linear-gradient(155deg, var(--blue), var(--blue2));
  border-radius: var(--radius);
  padding: 28px;
  color: #fff;
  box-shadow: 0 16px 48px rgba(31,78,121,0.2);
}

.mini-panel h2 { font-size: 17px; margin-bottom: 14px; }

.check-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.check-list li {
  background: rgba(255,255,255,0.13);
  border: 1px solid rgba(255,255,255,0.2);
  border-radius: 9px;
  padding: 8px 12px;
  font-size: 13px;
  line-height: 1.3;
}

/* ── CARDS ─────────────────────────────────────────── */
.card {
  background: rgba(255,255,255,0.94);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  box-shadow: 0 8px 28px rgba(31,78,121,0.08);
}

/* ── SETTINGS ──────────────────────────────────────── */
.settings-card { overflow: hidden; }

.settings-toggle {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background: none;
  border: none;
  cursor: pointer;
  font-size: 15px;
  font-weight: 700;
  color: var(--blue);
  text-align: left;
  border-radius: var(--radius);
  transition: background .15s;
}

.settings-toggle:hover { background: var(--soft-blue); }

.settings-arrow { font-size: 12px; transition: transform .2s; }
.settings-arrow.open { transform: rotate(180deg); }

.settings-body {
  padding: 0 24px 22px;
  border-top: 1px solid var(--border);
  margin-top: 0;
}

.settings-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  padding-top: 20px;
}

.setting-group { display: flex; flex-direction: column; gap: 10px; }

.setting-label {
  font-weight: 700;
  font-size: 13px;
  color: var(--blue);
  text-transform: uppercase;
  letter-spacing: .04em;
}

.setting-desc {
  font-size: 12px;
  color: var(--muted);
}

.radio-col { display: flex; flex-direction: column; gap: 8px; }

.radio-label {
  display: flex;
  align-items: baseline;
  gap: 8px;
  font-size: 14px;
  cursor: pointer;
}

.radio-label span:nth-child(2) { font-weight: 600; }

.setting-select {
  padding: 9px 12px;
  border: 1px solid var(--border);
  border-radius: 8px;
  font-size: 14px;
  background: white;
  color: var(--text);
  cursor: pointer;
}

.checkbox-col { display: flex; flex-direction: column; gap: 10px; }

.check-label {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 14px;
  cursor: pointer;
  line-height: 1.4;
}

/* ── UPLOAD CARD ───────────────────────────────────── */
.upload-card { padding: 28px; }

.upload-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 12px;
  margin-bottom: 20px;
}

.upload-header h2 { font-size: 21px; color: #173b72; }

.privacy-pill {
  background: var(--green-bg);
  color: var(--green);
  border: 1px solid #bde8ca;
  font-size: 12.5px;
  font-weight: 700;
  padding: 6px 12px;
  border-radius: 99px;
  white-space: nowrap;
}

.drop-zone {
  border: 2px dashed #a8bad9;
  background: #f8fbff;
  border-radius: 14px;
  padding: 30px 20px;
  text-align: center;
  transition: border-color .15s, background .15s, transform .12s;
  cursor: default;
}

.drop-zone.drag-over {
  border-color: var(--blue2);
  background: #eff5ff;
  transform: scale(1.01);
}

.drop-icon { font-size: 2.4rem; margin-bottom: 10px; }
.drop-zone p { color: var(--muted); margin-bottom: 10px; }

.file-name {
  font-weight: 700;
  color: var(--blue);
  font-size: 14px;
  margin-top: 10px;
  min-height: 1.2em;
}

.file-hint { font-size: 12.5px; color: var(--muted); margin-top: 6px; }

/* ── LEVEL ROW ─────────────────────────────────────── */
.level-row {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 12px;
  margin: 18px 0;
  font-size: 14px;
}

.level-row select {
  padding: 8px 12px;
  border: 1px solid var(--border);
  border-radius: 8px;
  font-size: 14px;
  background: white;
  color: var(--text);
  cursor: pointer;
}

.level-hint { color: var(--muted); font-size: 12.5px; }

/* ── BUTTONS ───────────────────────────────────────── */
.btn-primary {
  display: inline-block;
  background: linear-gradient(135deg, var(--blue), var(--blue2));
  color: #fff;
  border: none;
  border-radius: 10px;
  padding: 10px 20px;
  font-size: 14px;
  font-weight: 700;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
  transition: transform .13s, box-shadow .13s;
  box-shadow: 0 6px 18px rgba(31,78,121,0.22);
}

.btn-primary:hover:not(:disabled) {
  transform: translateY(-1px);
  box-shadow: 0 10px 26px rgba(31,78,121,0.28);
}

.btn-primary:disabled { opacity: .42; cursor: not-allowed; }

.btn-large {
  width: 100%;
  padding: 14px;
  font-size: 16px;
  margin-top: 4px;
  border-radius: 12px;
}

.btn-outline {
  background: white;
  border: 1.5px solid var(--blue);
  color: var(--blue);
  border-radius: 9px;
  padding: 8px 16px;
  font-size: 13.5px;
  font-weight: 700;
  cursor: pointer;
  transition: background .13s;
}

.btn-outline:hover { background: var(--soft-blue); }

/* ── SPINNER ───────────────────────────────────────── */
.spinner {
  display: flex;
  align-items: center;
  gap: 14px;
  padding: 18px 0 0;
  color: var(--muted);
  font-size: 14px;
}

.spin {
  width: 26px; height: 26px; flex-shrink: 0;
  border: 3px solid var(--border);
  border-top-color: var(--blue);
  border-radius: 50%;
  animation: spin .65s linear infinite;
}

@keyframes spin { to { transform: rotate(360deg); } }

/* ── FEATURES ──────────────────────────────────────── */
.features {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 16px;
}

.feature-card { padding: 22px; }
.feature-icon { font-size: 1.8rem; margin-bottom: 10px; }
.feature-card h3 { font-size: 15px; color: #173b72; margin-bottom: 6px; }
.feature-card p  { font-size: 13px; color: var(--muted); line-height: 1.5; }

/* ── RESULTS ───────────────────────────────────────── */
.results-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 14px;
  flex-wrap: wrap;
  gap: 10px;
}

.results-header h2 { font-size: 22px; color: #173b72; }

.download-row { display: flex; gap: 10px; flex-wrap: wrap; }

.summary-bar {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
  margin-bottom: 16px;
}

.summary-pill {
  flex: 1;
  min-width: 100px;
  text-align: center;
  border-radius: 12px;
  padding: 12px 10px;
  font-size: 13px;
  font-weight: 700;
}

.summary-pill span {
  display: block;
  font-size: 27px;
  font-weight: 800;
  line-height: 1;
  margin-bottom: 4px;
}

.pill-red   { background: var(--red-bg);   color: var(--red);   border: 1px solid #f5c6c6; }
.pill-amber { background: var(--amber-bg); color: var(--amber); border: 1px solid #ffe082; }
.pill-blue  { background: var(--soft-blue);color: var(--blue);  border: 1px solid #c3d7f5; }
.pill-green { background: var(--green-bg); color: var(--green); border: 1px solid #bde8ca; }

/* ── TABLE ─────────────────────────────────────────── */
.table-wrap {
  overflow-x: auto;
  border-radius: 12px;
  border: 1px solid var(--border);
  box-shadow: 0 4px 14px rgba(31,78,121,0.07);
}

table {
  width: 100%;
  border-collapse: collapse;
  background: white;
  font-size: 13px;
}

thead th {
  background: var(--blue);
  color: white;
  padding: 11px 14px;
  text-align: left;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: .04em;
  white-space: nowrap;
}

tbody tr:hover td { background: #f9fafd; }

tbody td {
  padding: 10px 14px;
  border-bottom: 1px solid #edf0f7;
  vertical-align: top;
  line-height: 1.45;
}

tbody tr:last-child td { border-bottom: none; }

/* Priority badges inside table */
.badge-high   { background: var(--red-bg);   color: var(--red);   border: 1px solid #f5c6c6; }
.badge-medium { background: var(--amber-bg); color: var(--amber); border: 1px solid #ffe082; }
.badge-low    { background: var(--soft-blue);color: var(--blue);  border: 1px solid #c3d7f5; }
.badge-ok     { background: var(--green-bg); color: var(--green); border: 1px solid #bde8ca; }

.badge-pill {
  display: inline-block;
  padding: 3px 10px;
  border-radius: 99px;
  font-size: 11.5px;
  font-weight: 700;
  white-space: nowrap;
}

/* Report area tag */
.area-tag {
  display: inline-block;
  background: #f0f4ff;
  color: #2d5099;
  border: 1px solid #c5d5f5;
  border-radius: 6px;
  font-size: 11px;
  font-weight: 700;
  padding: 2px 8px;
  white-space: nowrap;
}

.found-cell { font-style: italic; color: #374151; }
.found-cell em { color: var(--muted); }

.results-note {
  margin-top: 14px;
  font-size: 13px;
  color: #725000;
  background: var(--amber-bg);
  border: 1px solid #ffe082;
  padding: 10px 14px;
  border-radius: 10px;
}

/* ── RESPONSIVE ────────────────────────────────────── */
@media (max-width: 1000px) {
  .settings-grid { grid-template-columns: 1fr 1fr; }
}

@media (max-width: 860px) {
  .hero     { grid-template-columns: 1fr; }
  .features { grid-template-columns: repeat(2, 1fr); }
  .settings-grid { grid-template-columns: 1fr; }
}

@media (max-width: 560px) {
  .features     { grid-template-columns: 1fr; }
  .upload-header{ flex-direction: column; align-items: flex-start; }
  .level-row    { flex-direction: column; align-items: flex-start; }
  .summary-bar  { display: grid; grid-template-columns: repeat(2, 1fr); }
  .download-row { flex-direction: column; }
}

A private, browser-based tool for IB PYP teachers to check report card comments before submission.

## What it checks

- Grammar, spelling & punctuation
- Wrong student name or pronoun mix-up (copy-paste detection)
- Negative or informal tone
- Missing next step or target
- IB Learner Profile & ATL skills (in UOI and Student as Learner comments)
- EAL clarity: long sentences, stacked clauses, idioms, vague phrases
- Vague language (not actionable for parents)
- Level mismatch (comment doesn't match the student's grade level)
- **Auto-detects Report Area**: UOI, Student as Learner, Mathematics, Language Arts, Science, Specialist, General

## Privacy

All processing happens in your browser. No file is ever uploaded to any server. Student data never leaves your device.

## How to use

1. Go to the website (GitHub Pages URL)
2. Optionally expand **Settings** to choose strictness, comment type, and which checks to run
3. Upload a `.pdf` or `.docx` report card file
4. Optionally select the student level to enable level-match checking
5. Click **Check Comments**
6. Review the table and download as `.html` or `.csv`

## How to publish to GitHub Pages

1. Create a new GitHub repository (e.g. `rc-checker`)
2. Upload all these files to the repository
3. Go to **Settings → Pages**
4. Under **Source**, choose **GitHub Actions**
5. The deploy workflow runs automatically on every push to `main`
6. Your site will be live at `https://yourusername.github.io/rc-checker/`

## Files

| File | Purpose |
|------|---------|
| `index.html` | Main page structure and UI |
| `style.css` | Professional styling |
| `app.js` | All checking logic (runs in browser) |
| `.github/workflows/deploy.yml` | Auto-deploy to GitHub Pages |

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>IB Report Card Checker</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>

<div class="page">

  <!-- HERO -->
  <header class="hero">
    <div class="hero-card">
      <div class="badge">&#127758; IB PYP Tool &nbsp;&middot;&nbsp; Runs in your browser &nbsp;&middot;&nbsp; No data uploaded</div>
      <h1>Report Card<br>Comment Checker</h1>
      <p class="subtitle">Upload a PDF or Word file containing report card comments. Get a clear feedback table showing what to fix, why, and how — instantly, privately, in your browser.</p>
    </div>
    <aside class="mini-panel">
      <h2>What it checks</h2>
      <ul class="check-list">
        <li>&#10003; Grammar, spelling &amp; punctuation</li>
        <li>&#10003; Wrong student name or pronoun mix-up</li>
        <li>&#10003; Negative or informal tone</li>
        <li>&#10003; Missing next step or target</li>
        <li>&#10003; IB Learner Profile &amp; ATL language</li>
        <li>&#10003; EAL parent–friendly wording</li>
        <li>&#10003; Vague language &amp; clichés</li>
        <li>&#10003; Level mismatch (optional)</li>
        <li>&#10003; Report area auto-detection</li>
      </ul>
    </aside>
  </header>

  <!-- SETTINGS PANEL -->
  <section class="card settings-card">
    <button class="settings-toggle" id="settingsToggle" aria-expanded="false">
      <span>&#9881;&#65039; Settings</span>
      <span class="settings-arrow" id="settingsArrow">&#9660;</span>
    </button>
    <div class="settings-body" id="settingsBody" hidden>
      <div class="settings-grid">

        <div class="setting-group">
          <div class="setting-label">Strictness</div>
          <div class="radio-col">
            <label class="radio-label">
              <input type="radio" name="strictness" value="light" />
              <span>Light</span>
              <span class="setting-desc">High-priority issues only</span>
            </label>
            <label class="radio-label">
              <input type="radio" name="strictness" value="balanced" checked />
              <span>Balanced</span>
              <span class="setting-desc">Default — high &amp; medium issues</span>
            </label>
            <label class="radio-label">
              <input type="radio" name="strictness" value="detailed" />
              <span>Detailed</span>
              <span class="setting-desc">Show all suggestions including minor style</span>
            </label>
          </div>
        </div>

        <div class="setting-group">
          <label class="setting-label" for="reportTypeSelect">Comment type</label>
          <select id="reportTypeSelect" class="setting-select">
            <option value="auto">Auto-detect from text</option>
            <option value="sal">Student as a Learner</option>
            <option value="uoi">Unit of Inquiry</option>
            <option value="subject">Subject comment (Maths, Language, etc.)</option>
            <option value="general">General comment</option>
          </select>
          <div class="setting-desc" style="margin-top:6px">
            Auto-detect reads keywords in each comment to classify it.
          </div>
        </div>

        <div class="setting-group">
          <div class="setting-label">Include suggestions for</div>
          <div class="checkbox-col">
            <label class="check-label">
              <input type="checkbox" id="chkIB" checked />
              IB / PYP language (Learner Profile &amp; ATL skills)
            </label>
            <label class="check-label">
              <input type="checkbox" id="chkEAL" checked />
              EAL clarity (long sentences, idioms, vague phrases)
            </label>
            <label class="check-label">
              <input type="checkbox" id="chkStyle" />
              Minor style (wordiness, sentence variety)
            </label>
          </div>
        </div>

      </div><!-- settings-grid -->
    </div><!-- settings-body -->
  </section>

  <!-- UPLOAD CARD -->
  <section class="card upload-card">
    <div class="upload-header">
      <h2>Upload your report card file</h2>
      <span class="privacy-pill">&#128274; Processed locally — never uploaded</span>
    </div>

    <div class="drop-zone" id="dropZone">
      <div class="drop-icon">&#128196;</div>
      <p><strong>Drag &amp; drop a file here</strong>, or</p>
      <label class="btn-primary" for="fileInput">Choose file</label>
      <input type="file" id="fileInput" accept=".pdf,.docx,.doc" hidden />
      <p class="file-name" id="fileName"></p>
      <p class="file-hint">Accepts .pdf and .docx &nbsp;&middot;&nbsp; For .doc files, save as .docx in Word first</p>
    </div>

    <div class="level-row">
      <label for="levelSelect"><strong>Optional:</strong> Student level in this file</label>
      <select id="levelSelect">
        <option value="none">Not selected (skip level check)</option>
        <option value="emerging">Emerging / High support</option>
        <option value="developing">Developing</option>
        <option value="secure">Secure / Meeting expectations</option>
        <option value="extending">Extending / Exceeding</option>
      </select>
      <span class="level-hint">If set, comments that don't match this level will be flagged.</span>
    </div>

    <button class="btn-primary btn-large" id="checkBtn" disabled>
      &#128270; Check Comments
    </button>

    <div class="spinner" id="spinner" hidden>
      <div class="spin"></div>
      <p>Reading file and checking comments&hellip;</p>
    </div>
  </section>

  <!-- FEATURES ROW -->
  <section class="features">
    <div class="card feature-card">
      <div class="feature-icon">&#128195;</div>
      <h3>Report Area column</h3>
      <p>Auto-detects whether each comment is for UOI, Student as Learner, Maths, Language, or General — IB checks only run where relevant.</p>
    </div>
    <div class="card feature-card">
      <div class="feature-icon">&#127758;</div>
      <h3>IB language aware</h3>
      <p>Checks for Learner Profile attributes (Inquirer, Reflective…) and ATL skills in UOI and SAL comments only.</p>
    </div>
    <div class="card feature-card">
      <div class="feature-icon">&#128101;</div>
      <h3>EAL parent friendly</h3>
      <p>Flags long sentences, stacked clauses, idioms and vague phrases that may be confusing for parents.</p>
    </div>
    <div class="card feature-card">
      <div class="feature-icon">&#128274;</div>
      <h3>Private by design</h3>
      <p>All checking happens in your browser. No student data is ever sent to any server.</p>
    </div>
  </section>

  <!-- RESULTS SECTION -->
  <section id="resultsSection" hidden>
    <div class="results-header">
      <h2>Results</h2>
      <div class="download-row">
        <button class="btn-outline" id="downloadHtmlBtn" hidden>&#11015; Download (.html)</button>
        <button class="btn-outline" id="downloadCsvBtn" hidden>&#11015; Download (.csv)</button>
      </div>
    </div>

    <div class="summary-bar" id="summary"></div>

    <div class="table-wrap">
      <table id="resultsTable">
        <thead>
          <tr>
            <th>Student / Section</th>
            <th>Report Area</th>
            <th>Priority</th>
            <th>Category</th>
            <th>Text Found</th>
            <th>Why It Matters</th>
            <th>Suggested Fix</th>
          </tr>
        </thead>
        <tbody id="tableBody"></tbody>
      </table>
    </div>

    <p class="results-note">&#9888;&#65039; Automated first-pass only. Always apply your professional judgement before making changes.</p>
  </section>

</div><!-- .page -->

<!-- CDN LIBRARIES -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/mammoth/1.6.0/mammoth.browser.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.min.js"></script>
<script>
  if (typeof pdfjsLib !== 'undefined') {
    pdfjsLib.GlobalWorkerOptions.workerSrc =
      'https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.worker.min.js';
  }
</script>
<script src="app.js"></script>

</body>
</html>
═══════════════════════════════════════ */

/* ── IB CONSTANTS ─────────────────────────────────────────── */
const LP_ATTRS = [
  'inquirer','knowledgeable','thinker','communicator','principled',
  'open-minded','caring','risk-taker','balanced','reflective'
];

const ATL_SKILLS = [
  'thinking skills','research skills','communication skills',
  'social skills','self-management skills'
];

const LP_SUGGESTIONS = {
  uoi: [
    'During the Unit of Inquiry, ___ demonstrated strong {attr} skills by…',
    'As a {attr} learner, ___ asked thoughtful questions about…',
    '___ showed the Learner Profile attribute of {attr} when…'
  ],
  sal: [
    '___ shows the attributes of a {attr} learner by…',
    'As a {attr} learner, ___ consistently…',
    '___ demonstrates the IB Learner Profile attribute of {attr} through…'
  ]
};

/* ── FILE READING ─────────────────────────────────────────── */
function readDocx(file) {
  return new Promise((resolve, reject) => {
    const reader = new FileReader();
    reader.onload = e => {
      mammoth.extractRawText({ arrayBuffer: e.target.result })
        .then(r => resolve(r.value))
        .catch(reject);
    };
    reader.onerror = reject;
    reader.readAsArrayBuffer(file);
  });
}

async function readPdf(file) {
  const arrayBuffer = await file.arrayBuffer();
  const pdf = await pdfjsLib.getDocument({ data: arrayBuffer }).promise;
  const pageTexts = [];

  for (let i = 1; i <= pdf.numPages; i++) {
    const page = await pdf.getPage(i);
    const content = await page.getTextContent();

    // Group items by Y position to reconstruct lines
    const lineMap = new Map();
    content.items.forEach(item => {
      const y = Math.round(item.transform[5]);
      if (!lineMap.has(y)) lineMap.set(y, []);
      lineMap.get(y).push(item.str);
    });

    const lines = [...lineMap.entries()]
      .sort((a, b) => b[0] - a[0])
      .map(([, parts]) => parts.join(' ').trim())
      .filter(l => l.length > 0);

    pageTexts.push(lines.join('\n'));
  }

  return pageTexts.join('\n\n');
}

/* ── SECTION SPLITTING ────────────────────────────────────── */
function splitIntoSections(fullText) {
  // Split on blank lines
  let sections = fullText
    .split(/\n{2,}/)
    .map(s => s.trim())
    .filter(s => s.length >= 80);

  if (sections.length < 2) {
    // Fallback: split on name-like patterns at start of line
    sections = fullText
      .split(/\n(?=[A-Z][a-z]+ [A-Z][a-z]+\s*[:\-\n])/)
      .map(s => s.trim())
      .filter(s => s.length >= 80);
  }

  if (sections.length < 1) sections = [fullText.trim()];
  return sections;
}

function guessStudentName(text) {
  const patterns = [
    /^([A-Z][a-z]+(?:\s[A-Z][a-z]+)?)\s+(?:is|has|can|demonstrates|shows|continues|works|enjoys)/m,
    /^([A-Z][a-z]+(?:\s[A-Z][a-z]+)?)\s*[:\-]/m,
    /Student(?:\s+Name)?:\s*([A-Z][a-z]+(?:\s[A-Z][a-z]+)?)/i,
  ];
  for (const p of patterns) {
    const m = text.match(p);
    if (m) return m[1].trim();
  }
  return null;
}

/* ── REPORT AREA DETECTION ────────────────────────────────── */
function detectReportArea(text, override) {
  if (override && override !== 'auto') {
    const map = { sal: 'Student as Learner', uoi: 'Unit of Inquiry', subject: 'Subject', general: 'General' };
    return map[override] || 'General';
  }

  const t = text.toLowerCase();

  if (/unit of inquiry|central idea|line of inquiry|\buoi\b|inquiry unit/.test(t))
    return 'Unit of Inquiry';
  if (/student as a? learner|\bsal\b|learner profile|atl skill|approaches to learning/.test(t))
    return 'Student as Learner';
  if (/\bmath(s|ematics)?\b|\bnumeracy\b/.test(t))
    return 'Mathematics';
  if (/\blanguage arts?\b|\bliteracy\b|\breading\b|\bwriting\b|\bphonics\b/.test(t))
    return 'Language Arts';
  if (/\bscience\b|\bscientific inquiry\b/.test(t))
    return 'Science';
  if (/visual arts?\b|\bmusic\b|\bdrama\b|\bphysical education\b|\bpe\b/.test(t))
    return 'Specialist';

  return 'General';
}

/* ── LEVEL DETECTION ──────────────────────────────────────── */
function detectLevelInText(text) {
  const t = text.toLowerCase();
  if (/\bextend(ing|s|ed)?\b|exceeds? expectations|beyond grade level|highly advanced/.test(t))
    return 'extending';
  if (/\bsecure\b|meeting expectations|at grade level|on grade level|consistently demonstrates/.test(t))
    return 'secure';
  if (/\bdeveloping\b|making progress|with some support|with guidance|sometimes demonstrates/.test(t))
    return 'developing';
  if (/\bemerging\b|beginning to|not yet|with support|with consistent support|struggles to/.test(t))
    return 'emerging';
  return null;
}

/* ══════════════════════════════════════════════════════════
   CHECK FUNCTIONS
   Each returns an array of { priority, category, found, why, fix }
══════════════════════════════════════════════════════════ */

function checkGrammar(text) {
  const issues = [];

  const patterns = [
    { re: /\b(he|she|they)\s+(is|are)\s+a\s+(girl|boy|student)\s+who\s+(is|are)\b/i,
      found: m => m[0], why: 'Redundant construction.', fix: 'Remove "who is" — e.g. "She is a curious learner."' },
    { re: /\bthe\s+the\b/i,
      found: m => m[0], why: 'Duplicated word.', fix: 'Remove one "the".' },
    { re: /\b(a)\s+([aeiou])/i,
      check: m => !/\b(a)\s+unique\b/i.test(m[0]),
      found: m => m[0], why: 'Use "an" before vowel sounds.', fix: 'Change "a" to "an".' },
    { re: /\bshould of\b|\bcould of\b|\bwould of\b/i,
      found: m => m[0], why: 'Common grammar error.', fix: 'Use "should have", "could have", or "would have".' },
    { re: /\btheir\s+is\b|\bthere\s+are\s+a\b/i,
      found: m => m[0], why: 'Likely grammar error (their/there confusion).', fix: 'Check "there is" vs "their".' },
    { re: /\bstudents\s+whom\b|\bchild\s+whom\b/i,
      found: m => m[0], why: '"Whom" may be incorrect here.', fix: 'Consider "who" instead of "whom" after a noun subject.' },
  ];

  for (const p of patterns) {
    const m = text.match(p.re);
    if (m && (!p.check || p.check(m))) {
      issues.push({ priority: 'High', category: 'Grammar', found: p.found(m), why: p.why, fix: p.fix });
    }
  }
  return issues;
}

function checkSpelling(text) {
  const issues = [];
  const common = [
    ['recieve','receive'], ['acheive','achieve'], ['occured','occurred'],
    ['seperately','separately'], ['accomodate','accommodate'], ['begining','beginning'],
    ['beleive','believe'], ['calender','calendar'], ['definately','definitely'],
    ['enviroment','environment'], ['goverment','government'], ['grammer','grammar'],
    ['independant','independent'], ['knowlege','knowledge'], ['neccessary','necessary'],
    ['occassion','occasion'], ['perseverence','perseverance'], ['priviledge','privilege'],
    ['reccommend','recommend'], ['responsibilty','responsibility'], ['succesful','successful'],
    ['untill','until'], ['writting','writing'], ['comunication','communication'],
    ['colaborate','collaborate'], ['colaboration','collaboration'],
  ];
  for (const [wrong, right] of common) {
    const re = new RegExp(`\\b${wrong}\\b`, 'i');
    const m = text.match(re);
    if (m) {
      issues.push({
        priority: 'High', category: 'Spelling',
        found: m[0], why: 'Misspelled word.', fix: `Change to "${right}".`
      });
    }
  }
  return issues;
}

function checkPunctuation(text) {
  const issues = [];

  if (/[a-z]\s{0,1}$/.test(text.trimEnd()) && !/[.!?]$/.test(text.trimEnd())) {
    issues.push({
      priority: 'Medium', category: 'Punctuation',
      found: '(comment does not end with punctuation)',
      why: 'Comments should end with a full stop or other terminal punctuation.',
      fix: 'Add a period at the end of the comment.'
    });
  }

  const doublePunct = text.match(/[.!?,]{2,}/);
  if (doublePunct) {
    issues.push({
      priority: 'Low', category: 'Punctuation',
      found: doublePunct[0],
      why: 'Double punctuation marks look like a typo.',
      fix: 'Remove the extra punctuation mark.'
    });
  }

  return issues;
}

function checkWrongName(text, studentName) {
  const issues = [];
  if (!studentName) return issues;

  const nameRe = /\b([A-Z][a-z]{2,})\b/g;
  let m;
  const namesFound = new Set();
  while ((m = nameRe.exec(text)) !== null) {
    const word = m[1];
    if (word === studentName) continue;
    if (/^(The|This|These|They|Their|There|When|While|With|During|Through|After|Before|In|At|He|She|It|And|But|Or|For|An|Also|By|To|As|All|Both|Each|Such|That|Which|Who|What|Where|How|His|Her|Its|My|Our)$/.test(word)) continue;
    if (LP_ATTRS.map(a => a.charAt(0).toUpperCase() + a.slice(1)).includes(word)) continue;
    namesFound.add(word);
  }

  if (namesFound.size > 1) {
    const extras = [...namesFound].filter(n => n !== studentName);
    if (extras.length) {
      issues.push({
        priority: 'High', category: 'Wrong Name / Copy-Paste',
        found: extras.slice(0, 3).join(', '),
        why: 'Multiple student names detected. This comment may have been copied from another student.',
        fix: `Check that the comment is written for ${studentName} only.`
      });
    }
  }

  return issues;
}

function checkPronouns(text) {
  const issues = [];
  const heMatches  = (text.match(/\bhe\b|\bhim\b|\bhis\b/gi) || []).length;
  const sheMatches = (text.match(/\bshe\b|\bher\b|\bhers\b/gi) || []).length;
  const theyMatches= (text.match(/\bthey\b|\bthem\b|\btheir\b/gi) || []).length;

  let sets = 0;
  if (heMatches > 0) sets++;
  if (sheMatches > 0) sets++;
  if (theyMatches > 0) sets++;

  if (sets > 1) {
    issues.push({
      priority: 'High', category: 'Pronoun Mix-up',
      found: `Mixed pronouns detected (he/him: ${heMatches}, she/her: ${sheMatches}, they/them: ${theyMatches})`,
      why: 'Switching pronouns suggests the comment was copied from another student\'s report.',
      fix: 'Check and correct all pronouns to match the student.'
    });
  }
  return issues;
}

function checkNegativeTone(text) {
  const issues = [];
  const phrases = [
    { re: /\brefuses? to\b/i, fix: 'Use "is working on" or "is developing confidence to".' },
    { re: /\bnever (listens?|pays? attention|tries?|completes?)\b/i, fix: 'Replace "never" with a specific, measurable observation.' },
    { re: /\balways (disrupts?|distracts?|forgets?|fails?)\b/i, fix: 'Replace "always" — use "sometimes" or a specific example.' },
    { re: /\bcan'?t\b|\bcannot\b/i, fix: 'Reframe as a next step: "is working towards…" or "is developing the skill of…".' },
    { re: /\blazy\b|\bindifferent\b|\bapathetic\b/i, fix: 'Describe the observed behaviour, not a character trait.' },
    { re: /\bpoor\b(?!\s+performance is improving)/i, fix: 'Replace "poor" with a specific description of what needs development.' },
    { re: /\bdisruptive\b|\bbehaves? badly\b/i, fix: 'Describe the behaviour specifically without judging character.' },
    { re: /\bfails? to\b|\bfailed? to\b/i, fix: 'Use "is working on" or describe the current level of skill.' },
  ];

  for (const p of phrases) {
    const m = text.match(p.re);
    if (m) {
      issues.push({
        priority: 'High', category: 'Negative Tone',
        found: m[0], why: 'This language may upset parents and is not aligned with IB report card conventions.',
        fix: p.fix
      });
    }
  }
  return issues;
}

function checkMissingTarget(text) {
  const issues = [];
  const hasTarget = /next step|working (towards|on)|goal|aim(s)? to|will continue|should (focus|practise|try|explore)|to improve|in order to|by the end|target/i.test(text);
  const wordCount = text.split(/\s+/).length;

  if (!hasTarget && wordCount > 30) {
    issues.push({
      priority: 'Medium', category: 'Missing Next Step',
      found: '(no next step or target found)',
      why: 'IB report comments should include a forward-looking next step so parents know what to support.',
      fix: 'Add a sentence like: "___ will continue to work on… by…" or "A next step for ___ is to…"'
    });
  }
  return issues;
}

function checkVagueness(text) {
  const issues = [];
  const patterns = [
    { re: /\ba (good|great|lovely|nice|wonderful|fantastic|awesome) (student|learner|worker|child)\b/i,
      fix: 'Be specific: name a strength and an example — "___ consistently shows curiosity by asking detailed questions."' },
    { re: /\bworks (very )?hard\b/i,
      fix: 'What do they work hard at? "Works hard to explain their thinking in writing" is more useful.' },
    { re: /\benjoyed (this|the) (term|year|unit|topic)\b/i,
      fix: 'Say what specifically they enjoyed and why it mattered.' },
    { re: /\bis a (pleasure|joy) to (have|teach)\b/i,
      fix: 'Warm phrase, but add a specific example of the quality you\'re describing.' },
    { re: /\bkeep(s)? (up the )?good work\b/i,
      fix: 'What good work? Name the specific skill or behaviour.' },
    { re: /\bmust try harder\b|\bneeds to try harder\b/i,
      fix: 'Be specific: "needs to read for 15 minutes each night" or "needs to show working in Maths."' },
    { re: /\bincredible|\bamazing\b|\bfabulous\b/i,
      fix: 'These words are vague positives. Replace with a specific achievement or skill.' },
  ];

  for (const p of patterns) {
    const m = text.match(p.re);
    if (m) {
      issues.push({
        priority: 'Medium', category: 'Vague Language',
        found: m[0], why: 'This phrase doesn\'t give parents actionable information.', fix: p.fix
      });
    }
  }
  return issues;
}

function checkRepeatedPhrases(text) {
  const issues = [];
  const words = text.toLowerCase().split(/\s+/);
  const counted = {};
  words.forEach(w => {
    const clean = w.replace(/[^a-z]/g, '');
    if (clean.length >= 5) counted[clean] = (counted[clean] || 0) + 1;
  });

  const stop = new Set(['their','student','shows','which','during','about','skills','learning',
    'continues','consistently','always','further','develop','using','through','often','other',
    'areas','work','with','this','that','they','them','when','also','able','more','unit','well']);
  const repeated = Object.entries(counted)
    .filter(([w, c]) => c >= 3 && !stop.has(w))
    .sort((a, b) => b[1] - a[1])
    .slice(0, 2);

  if (repeated.length) {
    issues.push({
      priority: 'Low', category: 'Repeated Words',
      found: repeated.map(([w, c]) => `"${w}" (×${c})`).join(', '),
      why: 'Repeating the same word multiple times can make a comment feel less polished.',
      fix: 'Use synonyms or restructure sentences to vary word choice.'
    });
  }
  return issues;
}

function checkIncompleteSentences(text) {
  const issues = [];
  const sentences = text.match(/[^.!?]+[.!?]/g) || [];
  sentences.forEach(s => {
    const trimmed = s.trim();
    if (trimmed.split(/\s+/).length < 4 && trimmed.length > 2) {
      issues.push({
        priority: 'Medium', category: 'Incomplete Sentence',
        found: trimmed,
        why: 'This sentence is very short — it may be incomplete or a fragment.',
        fix: 'Expand into a full sentence with a subject, verb, and detail.'
      });
    }
  });
  return issues.slice(0, 1);
}

function checkWordiness(text) {
  const issues = [];
  const wordy = [
    { re: /\bdue to the fact that\b/i, fix: 'Replace with "because".' },
    { re: /\bin order to\b/i, fix: 'Replace with "to".' },
    { re: /\bat this point in time\b/i, fix: 'Replace with "now".' },
    { re: /\bfor the purpose of\b/i, fix: 'Replace with "to".' },
    { re: /\bwith regard to\b/i, fix: 'Replace with "about" or "regarding".' },
    { re: /\bprior to\b/i, fix: 'Replace with "before".' },
    { re: /\bsubsequent to\b/i, fix: 'Replace with "after".' },
  ];

  for (const p of wordy) {
    const m = text.match(p.re);
    if (m) {
      issues.push({
        priority: 'Low', category: 'Wordiness',
        found: m[0], why: 'A simpler phrase is easier to read, especially for EAL parents.', fix: p.fix
      });
    }
  }
  return issues;
}

/* ── EAL CLARITY CHECKS ───────────────────────────────────── */
function checkEALClarity(text) {
  const issues = [];

  // Long sentences
  const sentences = text.split(/(?<=[.!?])\s+/);
  sentences.forEach(s => {
    const wordCount = s.trim().split(/\s+/).length;
    if (wordCount > 35) {
      issues.push({
        priority: 'Low', category: 'EAL Clarity — Long Sentence',
        found: s.trim().substring(0, 90) + (s.trim().length > 90 ? '…' : ''),
        why: `This sentence has ~${wordCount} words. EAL parents may find it hard to follow.`,
        fix: 'Split into two shorter sentences.'
      });
    }
  });

  // Stacked clauses
  sentences.forEach(s => {
    const clauseCount = (s.match(/\bbecause\b|\bwhich\b|\bwhile\b|\balthough\b|\bhowever\b|\bwhereby\b/gi) || []).length;
    if (clauseCount >= 2) {
      issues.push({
        priority: 'Low', category: 'EAL Clarity — Stacked Clauses',
        found: s.trim().substring(0, 90) + '…',
        why: 'Multiple connecting clauses in one sentence can be difficult to follow.',
        fix: 'Break into shorter sentences and use simpler connectives.'
      });
    }
  });

  // Vague phrases
  const vagueList = [
    [/\bdo better\b/i, 'Say what specifically needs to improve.'],
    [/\btry harder\b/i, 'Specify what to try: "practise adding fractions daily" or "read for 10 minutes each night".'],
    [/\bgood attitude\b/i, 'Be specific: "always ready to learn" or "volunteers ideas in group discussions".'],
    [/\bneeds (to )?improvement\b/i, 'Name the area and the next step.'],
    [/\bhas potential\b/i, 'Describe what you\'ve seen and what the next step is.'],
    [/\bcould do more\b/i, 'Say specifically what: "could attempt extension tasks" or "could read for 15 minutes nightly".'],
  ];

  for (const [re, fix] of vagueList) {
    const m = text.match(re);
    if (m) {
      issues.push({
        priority: 'Medium', category: 'Vague Language',
        found: m[0], why: 'This phrase is too vague to be actionable for parents.', fix
      });
    }
  }

  // Idioms
  const idiomList = [
    [/\bstep up\b/i, 'Replace with "take more responsibility" or be specific about what that looks like.'],
    [/\bkeep on track\b/i, 'Replace with "maintain their current progress" or "continue to complete work on time".'],
    [/\bgo the extra mile\b/i, 'Replace with "put in extra effort" — specify what that effort looks like.'],
    [/\bthink outside the box\b/i, 'Replace with "explore creative solutions" or "try new approaches".'],
    [/\bon the right track\b/i, 'Replace with "making good progress" or be specific.'],
    [/\bpull (their|his|her) weight\b/i, 'Replace with "contribute equally to group work".'],
    [/\bshoot for the stars\b/i, 'Replace with "aim high and set ambitious goals".'],
  ];

  for (const [re, fix] of idiomList) {
    const m = text.match(re);
    if (m) {
      issues.push({
        priority: 'Low', category: 'EAL Clarity — Idiom',
        found: m[0], why: 'This idiom may confuse parents who speak English as an additional language.', fix
      });
    }
  }

  return issues;
}

/* ── LEVEL MATCH CHECK ────────────────────────────────────── */
function checkLevelMatch(text, selectedLevel) {
  const issues = [];
  const detected = detectLevelInText(text);
  const level = selectedLevel !== 'none' ? selectedLevel : detected;
  if (!level) return issues;

  const positive = (text.match(/\bexcellent\b|\boutstanding\b|\bexceptional\b|\bimpressive\b|\bstrength\b|\bshines?\b|\bbrilliant\b|\bsuperb\b|\btalented?\b/gi) || []).length;
  const negative = (text.match(/\bstruggles?\b|\bdifficulty\b|\bchallenging\b|\bneeds? to\b|\bnot yet\b|\bhardy\b|\brarely\b|\bhesitant\b|\binconsistent\b/gi) || []).length;

  if ((level === 'emerging' || level === 'developing') && positive > 3 && negative === 0) {
    issues.push({
      priority: 'Medium', category: 'Level Mismatch',
      found: `Grade level: ${level}, but comment contains only positive language`,
      why: 'A comment for a student at this level should include a clear next step, not only strengths.',
      fix: 'Add a specific, forward-looking next step so parents understand where to focus support.'
    });
  }

  if ((level === 'secure' || level === 'extending') && negative > positive + 2) {
    issues.push({
      priority: 'Medium', category: 'Level Mismatch',
      found: `Grade level: ${level}, but comment reads mostly negatively`,
      why: 'A student at this level should have clear strengths acknowledged before areas for growth.',
      fix: 'Lead with a specific strength before discussing next steps.'
    });
  }

  // Specific descriptor contradiction
  if (level === 'developing' && /consistently exceeds?|exceeds? expectations|above grade level|highly advanced/i.test(text)) {
    issues.push({
      priority: 'High', category: 'Level Mismatch',
      found: 'Comment says "consistently exceeds" but grade level is Developing',
      why: 'The comment language directly contradicts the grade level assigned.',
      fix: 'Use language aligned with Developing — save "exceeds expectations" for Extending.'
    });
  }

  if (level === 'extending' && /not yet|struggles? to|with support|with guidance|beginning to/i.test(text)) {
    issues.push({
      priority: 'High', category: 'Level Mismatch',
      found: 'Comment uses "not yet / struggles" language but grade level is Extending',
      why: 'Extending-level students should not be described with emerging-level language.',
      fix: 'Check the grade level or revise the comment to reflect genuine strengths.'
    });
  }

  return issues;
}

/* ── IB LANGUAGE CHECK ────────────────────────────────────── */
function checkIBLanguage(text, reportArea) {
  const issues = [];
  if (reportArea !== 'Unit of Inquiry' && reportArea !== 'Student as Learner') return issues;

  const t = text.toLowerCase();
  const hasLP  = LP_ATTRS.some(a => t.includes(a));
  const hasATL = ATL_SKILLS.some(s => t.includes(s));

  if (reportArea === 'Unit of Inquiry' && !hasLP && !hasATL) {
    const exampleAttr = LP_ATTRS[Math.floor(LP_ATTRS.length / 2)];
    issues.push({
      priority: 'Medium', category: 'IB Language — Missing',
      found: '(no Learner Profile attribute or ATL skill mentioned)',
      why: 'UOI comments should connect learning to IB Learner Profile attributes or ATL skills.',
      fix: `Add an IB connection, e.g. "During the Unit of Inquiry, ___ demonstrated the ${exampleAttr} attribute by…"`
    });
  } else if (reportArea === 'Student as Learner' && !hasLP) {
    issues.push({
      priority: 'Medium', category: 'IB Language — Missing',
      found: '(no Learner Profile attribute mentioned)',
      why: 'Student as Learner comments should reference at least one IB Learner Profile attribute.',
      fix: '___ shows the attributes of a reflective and caring learner by…'
    });
  }

  return issues;
}

/* ══════════════════════════════════════════════════════════
   ORCHESTRATOR — runs all checks on one section
══════════════════════════════════════════════════════════ */
function checkSection(text, studentName, selectedLevel, settings) {
  const { strictness, reportTypeOverride, includeIB, includeEAL, includeStyle } = settings;
  const reportArea = detectReportArea(text, reportTypeOverride);

  let issues = [
    ...checkGrammar(text),
    ...checkSpelling(text),
    ...checkPunctuation(text),
    ...checkWrongName(text, studentName),
    ...checkPronouns(text),
    ...checkNegativeTone(text),
    ...checkMissingTarget(text),
    ...checkVagueness(text),
    ...checkIncompleteSentences(text),
    ...checkLevelMatch(text, selectedLevel),
  ];

  if (includeStyle) {
    issues = issues.concat(checkWordiness(text), checkRepeatedPhrases(text));
  }

  if (includeEAL) {
    issues = issues.concat(checkEALClarity(text));
  }

  if (includeIB) {
    issues = issues.concat(checkIBLanguage(text, reportArea));
  }

  // Apply strictness filter
  if (strictness === 'light') {
    issues = issues.filter(i => i.priority === 'High');
  } else if (strictness === 'balanced') {
    issues = issues.filter(i => i.priority !== 'Low');
  }
  // 'detailed' = show all

  // Deduplicate by category (keep first)
  const seenCats = new Set();
  issues = issues.filter(i => {
    const key = i.category + '|' + i.found.substring(0, 20);
    if (seenCats.has(key)) return false;
    seenCats.add(key);
    return true;
  });

  // Non-nitpicky cap: max 5 per section (always show all High, fill to 5 with Medium/Low)
  const high   = issues.filter(i => i.priority === 'High');
  const medium = issues.filter(i => i.priority === 'Medium');
  const low    = issues.filter(i => i.priority === 'Low');

  let capped = [...high];
  if (capped.length < 5) capped = capped.concat(medium.slice(0, 5 - capped.length));
  if (capped.length < 5) capped = capped.concat(low.slice(0, 5 - capped.length));

  if (capped.length === 0) {
    capped = [{ priority: 'OK', category: 'No issues found', found: '', why: 'This comment looks good!', fix: '' }];
  }

  return { reportArea, issues: capped };
}

/* ══════════════════════════════════════════════════════════
   RENDER RESULTS
══════════════════════════════════════════════════════════ */
function priorityClass(p) {
  if (p === 'High')   return 'badge-high';
  if (p === 'Medium') return 'badge-medium';
  if (p === 'Low')    return 'badge-low';
  return 'badge-ok';
}

function renderResults(allResults) {
  const tbody = document.getElementById('tableBody');
  const summaryEl = document.getElementById('summary');
  tbody.innerHTML = '';

  let highCount = 0, medCount = 0, lowCount = 0, okCount = 0;
  let sectionCount = 0;

  allResults.forEach(({ name, reportArea, issues }) => {
    sectionCount++;
    const firstIssue = issues[0];

    issues.forEach((issue, idx) => {
      if (issue.priority === 'High')   highCount++;
      else if (issue.priority === 'Medium') medCount++;
      else if (issue.priority === 'Low')    lowCount++;
      else okCount++;

      const tr = document.createElement('tr');
      tr.innerHTML = `
        <td>${idx === 0 ? `<strong>${escHtml(name)}</strong>` : ''}</td>
        <td>${idx === 0 ? `<span class="area-tag">${escHtml(reportArea)}</span>` : ''}</td>
        <td><span class="badge-pill ${priorityClass(issue.priority)}">${escHtml(issue.priority)}</span></td>
        <td>${escHtml(issue.category)}</td>
        <td class="found-cell">${issue.found ? `"${escHtml(issue.found)}"` : '<em>—</em>'}</td>
        <td>${escHtml(issue.why)}</td>
        <td>${escHtml(issue.fix)}</td>
      `;
      tbody.appendChild(tr);
    });
  });

  // Summary pills
  summaryEl.innerHTML = `
    <div class="summary-pill pill-red">  <span>${highCount}</span>High priority</div>
    <div class="summary-pill pill-amber"><span>${medCount}</span>Medium priority</div>
    <div class="summary-pill pill-blue"> <span>${lowCount}</span>Low priority</div>
    <div class="summary-pill pill-green"><span>${okCount}</span>Sections OK</div>
  `;

  document.getElementById('resultsSection').hidden = false;
  document.getElementById('downloadHtmlBtn').hidden = false;
  document.getElementById('downloadCsvBtn').hidden = false;
  document.getElementById('resultsSection').scrollIntoView({ behavior: 'smooth' });

  // Store for download
  window._lastResults = allResults;
}

function escHtml(str) {
  return String(str || '').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
}

/* ══════════════════════════════════════════════════════════
   DOWNLOAD — HTML REPORT
══════════════════════════════════════════════════════════ */
function downloadHtml(allResults, filename) {
  const rows = allResults.flatMap(({ name, reportArea, issues }) =>
    issues.map((issue, idx) => `
      <tr>
        <td>${idx === 0 ? `<strong>${escHtml(name)}</strong>` : ''}</td>
        <td>${idx === 0 ? `<span style="background:#f0f4ff;color:#2d5099;border:1px solid #c5d5f5;border-radius:4px;padding:2px 7px;font-size:11px;font-weight:700">${escHtml(reportArea)}</span>` : ''}</td>
        <td><span style="padding:3px 9px;border-radius:99px;font-size:12px;font-weight:700;${priorityStyle(issue.priority)}">${escHtml(issue.priority)}</span></td>
        <td>${escHtml(issue.category)}</td>
        <td style="font-style:italic;color:#374151">${issue.found ? `"${escHtml(issue.found)}"` : '—'}</td>
        <td>${escHtml(issue.why)}</td>
        <td>${escHtml(issue.fix)}</td>
      </tr>`)
  ).join('');

  const html = `<!DOCTYPE html>
<html lang="en"><head><meta charset="UTF-8"><title>Report Card Feedback</title>
<style>
  body{font-family:Arial,sans-serif;margin:0;padding:30px;background:#f5f7fb;color:#1f2937;font-size:13px}
  h1{color:#1f4e79;font-size:28px;margin:0 0 6px}
  p{color:#6b7280;margin:0 0 20px}
  table{width:100%;border-collapse:collapse;background:#fff;border-radius:10px;overflow:hidden;box-shadow:0 4px 14px rgba(31,78,121,.1)}
  thead th{background:#1f4e79;color:#fff;padding:10px 13px;text-align:left;font-size:11.5px;letter-spacing:.04em;white-space:nowrap}
  tbody td{padding:9px 13px;border-bottom:1px solid #edf0f7;vertical-align:top;line-height:1.4}
  tbody tr:last-child td{border-bottom:none}
  tbody tr:hover td{background:#f9fafd}
  .note{margin-top:18px;background:#fff8e1;border:1px solid #ffe082;color:#725000;padding:10px 14px;border-radius:8px;font-size:12px}
</style>
</head><body>
<h1>Report Card Feedback</h1>
<p>Generated by IB Report Card Checker &nbsp;|&nbsp; ${new Date().toLocaleDateString()}</p>
<table>
<thead><tr>
  <th>Student / Section</th><th>Report Area</th><th>Priority</th>
  <th>Category</th><th>Text Found</th><th>Why It Matters</th><th>Suggested Fix</th>
</tr></thead>
<tbody>${rows}</tbody>
</table>
<p class="note">&#9888;&#65039; Automated first-pass only. Apply professional judgement before making changes.</p>
</body></html>`;

  const blob = new Blob([html], { type: 'text/html;charset=utf-8' });
  triggerDownload(blob, filename.replace(/\.[^.]+$/, '') + '_feedback.html');
}

function priorityStyle(p) {
  if (p === 'High')   return 'background:#fde8e8;color:#c0392b;border:1px solid #f5c6c6';
  if (p === 'Medium') return 'background:#fff8e1;color:#c47d00;border:1px solid #ffe082';
  if (p === 'Low')    return 'background:#e8f1ff;color:#1f4e79;border:1px solid #c3d7f5';
  return 'background:#e8f8ee;color:#176b34;border:1px solid #bde8ca';
}

/* ── DOWNLOAD — CSV ───────────────────────────────────────── */
function downloadCsv(allResults, filename) {
  const headers = ['Student/Section','Report Area','Priority','Category','Text Found','Why It Matters','Suggested Fix'];
  const rows = allResults.flatMap(({ name, reportArea, issues }) =>
    issues.map(issue => [name, reportArea, issue.priority, issue.category, issue.found, issue.why, issue.fix])
  );
  const csv = [headers, ...rows]
    .map(row => row.map(cell => `"${String(cell || '').replace(/"/g, '""')}"`).join(','))
    .join('\n');

  const blob = new Blob([csv], { type: 'text/csv;charset=utf-8' });
  triggerDownload(blob, filename.replace(/\.[^.]+$/, '') + '_feedback.csv');
}

function triggerDownload(blob, name) {
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = name;
  a.click();
  setTimeout(() => URL.revokeObjectURL(url), 3000);
}

/* ══════════════════════════════════════════════════════════
   MAIN PROCESS
══════════════════════════════════════════════════════════ */
async function processFile(file) {
  const ext = file.name.split('.').pop().toLowerCase();

  if (ext === 'doc') {
    alert('.doc files are not supported. Please open the file in Word or Google Docs, then save/download it as .docx and try again.');
    return;
  }

  let fullText;
  try {
    if (ext === 'docx') {
      fullText = await readDocx(file);
    } else if (ext === 'pdf') {
      fullText = await readPdf(file);
    } else {
      alert('Unsupported file type. Please upload a .pdf or .docx file.');
      return;
    }
  } catch (err) {
    alert('Could not read the file. Make sure it is not password-protected and try again.\n\nError: ' + err.message);
    return;
  }

  if (!fullText || fullText.trim().length < 50) {
    alert('The file appears to be empty or could not be read. If it is a scanned PDF, text extraction will not work.');
    return;
  }

  const sections = splitIntoSections(fullText);

  // Gather settings
  const settings = {
    strictness: document.querySelector('input[name="strictness"]:checked')?.value || 'balanced',
    reportTypeOverride: document.getElementById('reportTypeSelect').value,
    includeIB:    document.getElementById('chkIB').checked,
    includeEAL:   document.getElementById('chkEAL').checked,
    includeStyle: document.getElementById('chkStyle').checked,
  };
  const selectedLevel = document.getElementById('levelSelect').value;

  const allResults = sections.map((sec, idx) => {
    const name = guessStudentName(sec) || `Section ${idx + 1}`;
    const { reportArea, issues } = checkSection(sec, name, selectedLevel, settings);
    return { name, reportArea, issues };
  });

  renderResults(allResults);

  // Wire downloads
  document.getElementById('downloadHtmlBtn').onclick = () => downloadHtml(allResults, file.name);
  document.getElementById('downloadCsvBtn').onclick  = () => downloadCsv(allResults, file.name);
}

/* ══════════════════════════════════════════════════════════
   EVENT LISTENERS
══════════════════════════════════════════════════════════ */
document.addEventListener('DOMContentLoaded', () => {
  const fileInput  = document.getElementById('fileInput');
  const dropZone   = document.getElementById('dropZone');
  const fileNameEl = document.getElementById('fileName');
  const checkBtn   = document.getElementById('checkBtn');
  const spinner    = document.getElementById('spinner');
  const settingsToggle = document.getElementById('settingsToggle');
  const settingsBody   = document.getElementById('settingsBody');
  const settingsArrow  = document.getElementById('settingsArrow');

  let chosenFile = null;

  function setFile(f) {
    chosenFile = f;
    fileNameEl.textContent = f ? f.name : '';
    checkBtn.disabled = !f;
  }

  // Settings toggle
  settingsToggle.addEventListener('click', () => {
    const open = !settingsBody.hidden;
    settingsBody.hidden = open;
    settingsToggle.setAttribute('aria-expanded', String(!open));
    settingsArrow.classList.toggle('open', !open);
  });

  // File input
  fileInput.addEventListener('change', () => setFile(fileInput.files[0] || null));

  // Drag and drop
  dropZone.addEventListener('dragover', e => { e.preventDefault(); dropZone.classList.add('drag-over'); });
  dropZone.addEventListener('dragleave', () => dropZone.classList.remove('drag-over'));
  dropZone.addEventListener('drop', e => {
    e.preventDefault();
    dropZone.classList.remove('drag-over');
    const f = e.dataTransfer.files[0];
    if (f) setFile(f);
  });

  // Check button
  checkBtn.addEventListener('click', async () => {
    if (!chosenFile) return;
    checkBtn.disabled = true;
    spinner.hidden = false;
    document.getElementById('resultsSection').hidden = true;

    try {
      await processFile(chosenFile);
    } finally {
      spinner.hidden = true;
      checkBtn.disabled = false;
    }
  });
});
