# AZ-website
HTML websites
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chromebook → Linux — Field Sheet</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg-color: #0F172A;
    --card-bg: #1E293B;
    --text-primary: #F1F5F9;
    --text-secondary: #94A3B8;
    --accent: #FF7A00;
    --accent-dim: rgba(255, 122, 0, 0.15);
    --border-color: #334155;
    --success: #34D399;
  }
  * { box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body {
    margin: 0;
    background-color: var(--bg-color);
    color: var(--text-primary);
    font-family: 'Inter', sans-serif;
    -webkit-font-smoothing: antialiased;
    line-height: 1.5;
  }
  ::selection { background: var(--accent); color: var(--bg-color); }
  a { color: var(--accent); text-decoration: none; transition: opacity 0.2s; }
  a:hover { opacity: 0.8; }
  
  .wrap {
    max-width: 800px;
    margin: 0 auto;
    padding: 60px 20px 100px;
  }

  /* HERO */
  header.hero {
    background: var(--card-bg);
    padding: 40px;
    border-radius: 16px;
    border: 1px solid var(--border-color);
    margin-bottom: 32px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.2);
  }
  .tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    color: var(--accent);
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 16px;
  }
  .tag::before {
    content: "";
    width: 8px; height: 8px;
    background-color: var(--accent);
    display: inline-block;
  }
  h1 {
    font-family: 'Inter', sans-serif;
    font-weight: 700;
    font-size: clamp(32px, 6vw, 48px);
    margin: 0 0 12px;
    color: var(--text-primary);
  }
  h1 span { color: var(--text-secondary); font-weight: 500; }
  .dek {
    font-size: 16px;
    color: var(--text-secondary);
    max-width: 60ch;
    margin: 0 0 24px;
  }
  .metarow {
    display: flex;
    flex-wrap: wrap;
    gap: 16px 24px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--text-secondary);
    background: rgba(0,0,0,0.2);
    padding: 12px 16px;
    border-radius: 8px;
  }
  .metarow b { color: var(--text-primary); }

  /* WARNING PANEL */
  .warn {
    background: var(--accent-dim);
    border-left: 4px solid var(--accent);
    padding: 20px 24px;
    display: flex;
    gap: 16px;
    align-items: flex-start;
    border-radius: 0 8px 8px 0;
    margin-bottom: 40px;
  }
  .warn .bolt {
    font-family: 'JetBrains Mono', monospace;
    font-weight: 700;
    color: var(--accent);
    font-size: 16px;
    padding-top: 2px;
  }
  .warn p { margin: 0; font-size: 15px; color: var(--text-primary); }
  .warn p + p { margin-top: 12px; }

  /* SECTION LABEL */
  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    font-weight: 600;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    color: var(--text-secondary);
    margin: 40px 0 20px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .section-label::after {
    content: "";
    flex: 1;
    height: 1px;
    background: var(--border-color);
  }

  /* KIT LIST */
  .kit {
    list-style: none;
    margin: 0;
    padding: 0;
    display: grid;
    gap: 12px;
  }
  .kit li {
    background: var(--card-bg);
    border: 1px solid var(--border-color);
    padding: 16px 20px;
    display: flex;
    align-items: center;
    gap: 16px;
    font-size: 15px;
    color: var(--text-primary);
    border-radius: 8px;
  }
  .kit li::before {
    content: "";
    width: 10px; height: 10px;
    background-color: var(--accent);
    flex: none;
  }

  /* STEPS */
  .steps {
    display: grid;
    gap: 24px;
  }
  .step {
    background: var(--card-bg);
    border: 1px solid var(--border-color);
    padding: 32px;
    position: relative;
    border-radius: 12px;
  }
  .step .node {
    position: absolute;
    left: 32px; top: -16px;
    width: 36px; height: 36px;
    background-color: var(--bg-color);
    border: 2px solid var(--accent);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'JetBrains Mono', monospace;
    font-weight: 600;
    font-size: 14px;
    color: var(--accent);
    border-radius: 50%;
  }
  .step.critical {
    border-color: var(--accent);
  }
  .step.critical .node {
    background-color: var(--accent);
    color: var(--bg-color);
  }
  .step h3 {
    font-family: 'Inter', sans-serif;
    font-weight: 600;
    font-size: 18px;
    margin: 8px 0 12px;
    color: var(--text-primary);
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 10px;
  }
  .step h3 .ref {
    color: var(--text-secondary);
    font-weight: 400;
    font-size: 13px;
    background: rgba(0,0,0,0.2);
    padding: 2px 6px;
    border-radius: 4px;
  }
  .step p {
    margin: 0 0 12px;
    font-size: 15px;
    color: var(--text-secondary);
  }
  .step p.tip {
    color: var(--success);
    font-size: 14px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .step p.tip::before { content: "→"; font-weight: bold; }

  code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    background: rgba(0,0,0,0.3);
    padding: 2px 6px;
    border-radius: 4px;
    color: #E2E8F0;
  }
  .cmdbox {
    background: #0B0F17;
    border: 1px solid var(--border-color);
    padding: 16px;
    margin: 16px 0;
    overflow-x: auto;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13.5px;
    color: var(--success);
    white-space: pre;
    border-radius: 8px;
  }

  .pon {
    display: inline-block;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--bg-color);
    background-color: var(--accent);
    padding: 4px 10px;
    border-radius: 4px;
    margin-bottom: 12px;
  }

  footer {
    margin-top: 80px;
    padding-top: 24px;
    border-top: 1px solid var(--border-color);
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--text-secondary);
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 16px;
  }

  @media (max-width: 600px) {
    .wrap { padding: 40px 16px 80px; }
    header.hero, .step { padding: 24px; }
    .step .node { left: 24px; }
  }
</style>
</head>
<body>
<div class="wrap">

  <header class="hero">
    <div class="tag">Field Sheet · Hardware Mod</div>
    <h1>Chromebook <span>→</span> Linux</h1>
    <p class="dek">A condensed route from stock ChromeOS to a fully unlocked Linux laptop — flash write‑protect off, install open firmware, boot real Linux from USB.</p>
    <div class="metarow">
      <span><b>Time</b> ~1 hr</span>
      <span><b>Difficulty</b> Moderate</span>
      <span><b>Reversible</b> Partial — see P5</span>
      <span><b>Not for</b> ARM‑based Chromebooks</span>
    </div>
  </header>

  <div class="warn">
    <div class="bolt">!!</div>
    <div>
      <p><b>ARM Chromebooks aren't supported.</b> The flashing script fails on ARM boards — if that's you, look up your model on the <a href="https://cb-linux.github.io/breath/" target="_blank" rel="noopener">breath</a> project instead.</p>
      <p>Step 5 has a genuine point of no return. Past it, ChromeOS is gone from that device for good unless you took a backup.</p>
    </div>
  </div>

  <div class="section-label">Kit</div>
  <ul class="kit">
    <li>2× USB sticks, 8GB+ (one for the Linux image, one optional backup of the stock ChromeOS firmware)</li>
    <li>A Linux ISO — Lubuntu LTS is the well‑trodden path</li>
    <li>USB imaging tool — Etcher, or the Chromebook Recovery Utility as a fallback</li>
    <li>Small screwdriver set, if your model gates write‑protect behind a physical screw or switch</li>
  </ul>

  <div class="section-label">Route</div>

  <div class="steps">

    <div class="step">
      <div class="node">1</div>
      <h3>Build your install media</h3>
      <p>Download a Lubuntu LTS (or your flavor of choice) image, then burn it to a USB stick with Etcher. If Etcher isn't available, the Chromebook Recovery Utility works too — rename the ISO to end in <code>.bin</code>, choose "Use local image" under the gear icon, and it'll <code>dd</code> it for you.</p>
      <p class="tip">You can do this step on any second computer, or from a crouton chroot on the Chromebook itself.</p>
    </div>

    <div class="step critical">
      <div class="node">2</div>
      <h3>Disable write‑protect <span class="ref">hardware</span></h3>
      <p>This is model‑specific and usually means cracking the case: a physical two‑position switch, or a write‑protect screw to remove from the motherboard. Search your exact model — the mechanism differs by manufacturer and even by revision.</p>
      <p>Case is open anyway, so it's a sensible moment to upgrade RAM or swap in a larger SSD if your board allows it. Reassemble carefully, then boot back into ChromeOS.</p>
    </div>

    <div class="step">
      <div class="node">3</div>
      <h3>Decide: wipe or dual‑boot</h3>
      <p>Some boards support an <b>RW_LEGACY</b> option that keeps ChromeOS alongside Linux. Most older units don't. Dual‑boot also eats more storage — if you're not sure you need ChromeOS anymore, plan for a clean wipe instead.</p>
    </div>

    <div class="step">
      <div class="node">4</div>
      <h3>Open the shell</h3>
      <p>On the Chromebook, press <code>Ctrl</code> + <code>Alt</code> + <code>T</code> to reach crosh, then type <code>shell</code> and hit enter to drop into a full Linux shell.</p>
      <div class="cmdbox">cd; curl -LO https://mrchromebox.tech/firmware-util.sh && sudo bash firmware-util.sh</div>
      <p>That pulls down and runs the community firmware utility used to reflash the board.</p>
    </div>

    <div class="step critical">
      <div class="node">5</div>
      <h3>Flash UEFI firmware</h3>
      <span class="pon">Point of no return</span>
      <p>The script detects your hardware and presents a menu. Choose the option to flash a full UEFI‑capable ROM. You'll be offered a chance to back up the stock ChromeOS ROM first — take it if you kept that second USB stick.</p>
      <p>When it finishes, power off, plug in your Linux install USB, and boot. From there it installs like any ordinary UEFI laptop. Check the <a href="https://mrchromebox.tech/#faq" target="_blank" rel="noopener">mrchromebox FAQ</a> for the UEFI boot‑order specifics.</p>
    </div>

    <div class="step">
      <div class="node">6</div>
      <h3>Settle in</h3>
      <p>Once Linux boots clean, treat it like any fresh install — pull in the desktop environment and utilities you like. A dock app such as cairo‑dock is a common first add.</p>
    </div>

  </div>

  <div class="section-label">Notes from the field</div>
  <ul class="kit">
    <li>Newer Chromebooks increasingly lock write‑protect behind firmware rather than a physical switch — coverage for those models is thinner.</li>
    <li>If your device is too new for this script but is on the supported list for <a href="https://cb-linux.github.io/breath/" target="_blank" rel="noopener">breath</a>, that's currently the safer path.</li>
  </ul>

  <footer>
    <span>Condensed from an iFixit community guide</span>
    <span>Original: 6 steps · 26 completions logged</span>
  </footer>

</div>
</body>
</html>
