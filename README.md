<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Flipper BadUSB Payload Generator</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header>
    <h1>Flipper BadUSB Payload Generator</h1>
    <p>Build .txt BadUSB scripts quickly for Flipper Zero (extended DuckyScript).</p>
  </header>

  <main>
    <section class="controls">
      <div class="field">
        <label for="idField">ID (VID:PID Manufacturer:Product)</label>
        <input id="idField" placeholder="e.g. 1234:abcd Flipper Devices:Flipper Zero" />
      </div>
      <div class="field">
        <label for="defaultDelay">DEFAULT_DELAY (ms)</label>
        <input id="defaultDelay" type="number" min="0" placeholder="e.g. 100" />
      </div>
      <div class="field">
        <label for="filename">Filename (.txt)</label>
        <input id="filename" value="payload.txt" />
      </div>

      <div class="toolbar">
        <div class="cmd-group">
          <button data-insert="STRING " class="cmd">STRING</button>
          <button data-insert="ENTER" class="cmd">ENTER</button>
          <button data-insert="DELAY " class="cmd">DELAY</button>
          <button data-insert="DEFAULT_DELAY " class="cmd">DEFAULT_DELAY</button>
          <button data-insert="REPEAT " class="cmd">REPEAT</button>
        </div>
        <div class="cmd-group">
          <button data-insert="ALTSTRING " class="cmd">ALTSTRING</button>
          <button data-insert="ALTCHAR " class="cmd">ALTCHAR</button>
          <button data-insert="REM " class="cmd">REM</button>
          <button data-insert="TAB" class="cmd">TAB</button>
          <button data-insert="GUI " class="cmd">GUI</button>
        </div>
      </div>

      <div class="actions">
        <button id="loadSample">Load sample payload</button>
        <button id="clearEditor">Clear</button>
        <button id="downloadBtn" class="primary">Download .txt</button>
      </div>
    </section>

    <section class="editor">
      <label for="editorArea">Script editor</label>
      <textarea id="editorArea" placeholder="Type your commands here..."></textarea>
    </section>

    <section class="preview">
      <label>Preview / Script generated</label>
      <pre id="previewArea" aria-live="polite"></pre>
    </section>

    <section class="notes">
      <h3>Notes</h3>
      <ul>
        <li>If you fill the ID field it will be placed as the first line of the file (executed in preload).</li>
        <li>If DEFAULT_DELAY is filled and no DEFAULT_DELAY line exists in the script it will be inserted after the ID line.</li>
        <li>Download creates a UTF-8 .txt file with \n line endings (both are supported on Flipper).</li>
      </ul>
    </section>
  </main>

  <footer>
    <small>Based on Flipper BadUSB (DuckyScript) syntax. See documentation for command details.</small>
  </footer>

  <script src="app.js"></script>
</body>
</html>
