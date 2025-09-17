<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Temp Cover — Demo Certificate Generator</title>
  <style>
    :root{--accent:#0057a6;--muted:#666}
    body{font-family:Inter,system-ui,Segoe UI,Roboto,Arial; margin:0;background:#f6f8fb;color:#111}
    .container{max-width:980px;margin:28px auto;padding:20px;background:#fff;border-radius:12px;box-shadow:0 6px 24px rgba(10,20,40,.06)}
    h1{color:var(--accent);margin:0 0 12px;font-size:22px}
    label{display:block;margin-top:10px;font-size:13px;color:var(--muted)}
    input,textarea,select{width:100%;padding:10px;border:1px solid #e3e8ef;border-radius:8px;margin-top:6px;box-sizing:border-box}
    .grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
    .actions{display:flex;gap:10px;align-items:center;margin-top:16px}
    button{background:var(--accent);color:#fff;padding:10px 14px;border-radius:8px;border:0;cursor:pointer}
    button.secondary{background:#e6eefc;color:var(--accent)}
    .preview{margin-top:18px;padding:12px;border:1px dashed #e3e8ef;border-radius:8px}
    small{color:var(--muted)}
    .foot{margin-top:18px;font-size:13px;color:#444}
  </style>
  <!-- jsPDF from CDN -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js" integrity="" crossorigin="anonymous"></script>
</head>
<body>
  <div class="container">
    <h1>Temporary Cover — Demo Certificate Generator</h1>
    <p><small>This is a <strong>demo</strong>. PDFs created are clearly stamped <em>SAMPLE — NOT VALID</em>. Not affiliated with any insurer.</small></p>

    <div>
      <div class="grid">
        <div>
          <label>Policyholder name</label>
          <input id="holder" value="Hamzah Ilyas" />
        </div>
        <div>
          <label>Vehicle registration</label>
          <input id="reg" value="MY54 ANA" />
        </div>

        <div>
          <label>Vehicle make & model</label>
          <input id="vehicle" value="MERCEDES-BENZ GLE 450" />
        </div>
        <div>
          <label>Start date & time (YYYY-MM-DD HH:MM)</label>
          <input id="start" value="2025-09-16 17:00" />
        </div>

        <div>
          <label>End date & time (YYYY-MM-DD HH:MM)</label>
          <input id="end" value="2025-09-17 17:00" />
        </div>
        <div>
          <label>Total paid (£)</label>
          <input id="paid" value="48.84" />
        </div>

        <div style="grid-column:1/3">
          <label>Additional notes (will appear on the certificate)</label>
          <textarea id="notes" rows="3">This is a demo certificate — not a real insurance document.</textarea>
        </div>
      </div>

      <div class="actions">
        <button id="generate">Generate PDF (Sample)</button>
        <button id="downloadPdf" class="secondary" style="display:none">Download latest</button>
        <button id="clear" class="secondary">Reset form</button>
        <div style="margin-left:auto"><small>Demo only — will not bind any real policy.</small></div>
      </div>

      <div class="preview" id="preview">
        <strong>Preview (text):</strong>
        <div id="previewText" style="margin-top:10px;font-family:monospace;white-space:pre-wrap"></div>
      </div>

      <div class="foot">
        <p><strong>Hosting:</strong> to make this accessible worldwide, host `index.html` on GitHub Pages, Vercel, or Netlify (instructions below).</p>
      </div>
    </div>
  </div>

  <script>
    // Simple client-side PDF generator (jsPDF)
    const { jsPDF } = window.jspdf;

    function updatePreview() {
      const holder = document.getElementById('holder').value;
      const reg = document.getElementById('reg').value;
      const vehicle = document.getElementById('vehicle').value;
      const start = document.getElementById('start').value;
      const end = document.getElementById('end').value;
      const paid = document.getElementById('paid').value;
      const notes = document.getElementById('notes').value;

      const text = `CERTIFICATE (SAMPLE ONLY)\n\nPolicyholder: ${holder}\nRegistration: ${reg}\nVehicle: ${vehicle}\nStart: ${start}\nEnd: ${end}\nTotal paid: £${paid}\n\nNotes: ${notes}\n\n--- THIS IS A DEMO SAMPLE - NOT A VALID INSURANCE CERTIFICATE ---`;
      document.getElementById('previewText').innerText = text;
    }

    document.querySelectorAll('input,textarea').forEach(el => el.addEventListener('input', updatePreview));
    updatePreview();

    let lastPdfBlobUrl = null;

    document.getElementById('generate').addEventListener('click', () => {
      const doc = new jsPDF({unit:'pt',format:'a4'});
      const margin = 40;
      const pageWidth = doc.internal.pageSize.getWidth();

      // Header
      doc.setFontSize(16);
      doc.setFont('helvetica','bold');
      doc.text('TEMPORARY COVER — DEMO CERTIFICATE', pageWidth/2, 60, {align:'center'});

      // Red watermark diagonal
      doc.setTextColor(200,20,20);
      doc.setFontSize(48);
      doc.saveGraphicsState && doc.saveGraphicsState();
      doc.rotate(-35, {origin: [pageWidth/2, 350]});
      doc.setGState && doc.setGState(new doc.GState({opacity:0.10}));
      doc.text('SAMPLE — NOT VALID', pageWidth/2, 350, {align:'center'});
      doc.rotate(35, {origin: [pageWidth/2, 350]});
      doc.setTextColor(0,0,0);

      doc.setFontSize(11);
      doc.setFont('helvetica','normal');

      // Fields
      const left = margin;
      let y = 110;
      const lineGap = 18;

      const fields = [
        ['Policyholder', document.getElementById('holder').value],
        ['Registration', document.getElementById('reg').value],
        ['Vehicle', document.getElementById('vehicle').value],
        ['Start', document.getElementById('start').value],
        ['End', document.getElementById('end').value],
        ['Total paid (£)', document.getElementById('paid').value],
      ];

      fields.forEach(([label,val])=>{
        doc.setFont('helvetica','bold');
        doc.text(label + ':', left, y);
        doc.setFont('helvetica','normal');
        doc.text(String(val), left + 140, y);
        y += lineGap;
      });

      y += 6;
      doc.setFont('helvetica','bold');
      doc.text('Notes:', left, y);
      y += lineGap;
      doc.setFont('helvetica','normal');
      const notes = document.getElementById('notes').value;
      doc.text(doc.splitTextToSize(notes, pageWidth - margin*2), left, y);

      // Footer text that reiterates sample status
      doc.setFontSize(9);
      doc.setTextColor(120);
      doc.text('This document is a demo sample only and does not provide any valid insurance cover.', margin, 770);

      // Save to blob and show download link
      const pdfBlob = doc.output('blob');
      if (lastPdfBlobUrl) URL.revokeObjectURL(lastPdfBlobUrl);
      lastPdfBlobUrl = URL.createObjectURL(pdfBlob);
      const dl = document.getElementById('downloadPdf');
      dl.style.display = 'inline-block';
      dl.onclick = () => { const a = document.createElement('a'); a.href = lastPdfBlobUrl; a.download = 'temp-cover-sample.pdf'; a.click(); };

      // open in new tab
      const openNew = confirm('Open generated PDF in a new tab? (It will be labeled SAMPLE)');
      if (openNew) window.open(lastPdfBlobUrl, '_blank');

      alert('Sample PDF generated. It is clearly marked SAMPLE — NOT VALID.');
    });

    document.getElementById('clear').addEventListener('click', ()=>{
      document.getElementById('holder').value = '';
      document.getElementById('reg').value = '';
      document.getElementById('vehicle').value = '';
      document.getElementById('start').value = '';
      document.getElementById('end').value = '';
      document.getElementById('paid').value = '';
      document.getElementById('notes').value = 'Demo certificate — not valid for insurance purposes.';
      updatePreview();
    });
  </script>
</body>
</html>
