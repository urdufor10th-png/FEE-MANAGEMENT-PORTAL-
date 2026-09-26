<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>FEE-MANAGEMENT-PORTAL</title>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700;900&display=swap" rel="stylesheet">
  
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Roboto', sans-serif;
    }
    body {
      background-color: #f1f5f9;
      color: #0f172a;
      padding: 25px 12px;
    }

    .main-wrapper {
      max-width: 900px;
      margin: 0 auto;
    }

    .portal-title-top {
      font-size: 20px;
      font-weight: 900;
      color: #004b87;
      margin-bottom: 12px;
      letter-spacing: 0.5px;
    }

    .portal-card {
      background: #ffffff;
      border: 1.5px solid #003366;
      border-radius: 0px;
      padding: 24px;
      box-shadow: 0 4px 15px rgba(0, 34, 68, 0.08);
    }

    .inst-header {
      text-align: center;
      margin-bottom: 20px;
      border-bottom: 1px solid #e2e8f0;
      padding-bottom: 15px;
    }
    .inst-header h1 {
      font-size: 24px;
      font-weight: 900;
      color: #000000;
      letter-spacing: 0.5px;
      text-transform: uppercase;
    }
    .inst-header p {
      font-size: 13px;
      color: #475569;
      font-weight: 600;
      margin-top: 4px;
    }

    .badge-strip {
      background: #dc2626;
      color: #ffffff;
      font-size: 12px;
      font-weight: 800;
      padding: 6px 14px;
      display: inline-block;
      margin-top: 10px;
      letter-spacing: 0.5px;
      text-transform: uppercase;
    }

    .section-title {
      font-size: 13px;
      font-weight: 900;
      color: #003366;
      border-left: 4px solid #003366;
      padding-left: 8px;
      margin: 18px 0 12px;
      text-transform: uppercase;
    }

    .form-grid-3 {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 14px;
      margin-bottom: 12px;
    }

    .form-field {
      display: flex;
      flex-direction: column;
    }
    .form-field label {
      font-size: 11.5px;
      font-weight: 700;
      color: #334155;
      margin-bottom: 5px;
    }
    .form-field input, .form-field select {
      width: 100%;
      padding: 10px 11px;
      font-size: 14px;
      border: 1.5px solid #cbd5e1;
      border-radius: 0px;
      outline: none;
      background: #ffffff;
      color: #0f172a;
      font-weight: 600;
    }
    .form-field input:focus, .form-field select:focus {
      border-color: #0284c7;
      background: #f8fafc;
    }

    .dropdown-large {
      background: #f0fdf4 !important;
      border: 1.5px solid #003366 !important;
      font-weight: 800 !important;
      color: #003366 !important;
      cursor: pointer;
    }

    /* SUMMARY BAR */
    .balance-bar {
      background: #f8fafc;
      border: 1.5px solid #003366;
      border-radius: 0px;
      padding: 12px 14px;
      margin: 16px 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 10px;
    }
    .balance-bar .math-text {
      font-size: 12.5px;
      color: #334155;
      font-weight: 700;
    }
    .balance-bar .total-box {
      text-align: right;
    }
    .balance-bar .total-box span {
      font-size: 10.5px;
      font-weight: 800;
      color: #003366;
      display: block;
      text-transform: uppercase;
    }
    .balance-bar .total-box strong {
      font-size: 22px;
      color: #dc2626;
      font-weight: 900;
    }

    /* BUTTONS ROW */
    .btn-row-3 {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      gap: 10px;
      margin-top: 14px;
    }

    .action-btn {
      width: 100%;
      border: none;
      border-radius: 0px;
      padding: 12px 6px;
      font-size: 13px;
      font-weight: 900;
      cursor: pointer;
      text-transform: uppercase;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      color: #ffffff;
      transition: all 0.1s ease;
    }

    .btn-print { background: #003366; }
    .btn-print:hover { background: #002244; }

    .btn-whatsapp { background: #16a34a; }
    .btn-whatsapp:hover { background: #15803d; }

    .btn-sms { background: #0284c7; }
    .btn-sms:hover { background: #0369a1; }

    /* PRINT RECEIPT LAYOUT */
    #receiptPrintArea { display: none; }

    @media print {
      body * { visibility: hidden; }
      #receiptPrintArea, #receiptPrintArea * { visibility: visible; }
      #receiptPrintArea {
        display: block !important;
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        padding: 20px;
        background: #ffffff;
        color: #000000;
      }
      .receipt-paper {
        border: 2px solid #000000;
        padding: 20px;
        max-width: 620px;
        margin: 0 auto;
      }
      .rcpt-head {
        text-align: center;
        border-bottom: 2px solid #000000;
        padding-bottom: 8px;
        margin-bottom: 12px;
      }
      .rcpt-head h2 { font-size: 22px; text-transform: uppercase; font-weight: 900; margin-bottom: 3px; }
      .rcpt-head p { font-size: 12px; }
      .rcpt-meta {
        display: flex;
        justify-content: space-between;
        font-size: 12.5px;
        font-weight: bold;
        margin-bottom: 12px;
        border-bottom: 1px dashed #000;
        padding-bottom: 5px;
      }
      .rcpt-table {
        width: 100%;
        border-collapse: collapse;
        margin-bottom: 12px;
      }
      .rcpt-table th, .rcpt-table td {
        border: 1px solid #000000;
        padding: 8px 10px;
        font-size: 12.5px;
        text-align: left;
      }
      .rcpt-table th { background: #f8fafc; width: 40%; }
      .rcpt-footer {
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        margin-top: 35px;
      }
      .rcpt-sign {
        border-top: 1.5px solid #000000;
        width: 160px;
        text-align: center;
        font-size: 11px;
        font-weight: bold;
      }
    }

    @media (max-width: 768px) {
      .form-grid-3, .btn-row-3 { grid-template-columns: 1fr; }
      .balance-bar { flex-direction: column; align-items: flex-start; }
      .balance-bar .total-box { text-align: left; }
    }
  </style>
</head>
<body>

  <div class="main-wrapper">
    <div class="portal-title-top">FEE-MANAGEMENT-PORTAL.</div>

    <div class="portal-card">
      <div class="inst-header">
        <h1>LUCENT COACHING CENTRE</h1>
        <p>Near Mithila Eye Hospital, Musrighari, Samastipur (Bihar) | Helpline: +91 8789524958</p>
        <div class="badge-strip">✦ OFFICIAL STUDENT FEE RECEIPT &amp; MANAGEMENT ✦</div>
      </div>

      <!-- 1. STUDENT INFORMATION -->
      <div class="section-title">1. Student Information (छात्र विवरण)</div>
      <div class="form-grid-3">
        <!-- Student Dropdown -->
        <div class="form-field">
          <label>छात्र चुनें (Dropdown List) *</label>
          <select id="studentSelect" class="dropdown-large" onchange="onStudentSelectChange()">
            <option value="">-- छात्र का नाम चुनें --</option>
          </select>
        </div>
        <div class="form-field">
          <label>Student Full Name (छात्र का नाम) *</label>
          <input type="text" id="studentName" placeholder="उदा. Rahul Kumar" oninput="calculateTotal()">
        </div>
        <div class="form-field">
          <label>Parents Mobile Number (WhatsApp/SMS) *</label>
          <input type="tel" id="parentPhone" placeholder="10 digit number">
        </div>
      </div>

      <div class="form-grid-3">
        <div class="form-field">
          <label>Class / Batch *</label>
          <input type="text" id="studentClass" value="12th" oninput="calculateTotal()">
        </div>
        <!-- Month Dropdown -->
        <div class="form-field">
          <label>Fee Month (फीस का महीना चुनें) *</label>
          <select id="feeMonth" class="dropdown-large" onchange="calculateTotal()">
            <option value="January 2026">January 2026</option>
            <option value="February 2026">February 2026</option>
            <option value="March 2026">March 2026</option>
            <option value="April 2026">April 2026</option>
            <option value="May 2026">May 2026</option>
            <option value="June 2026">June 2026</option>
            <option value="July 2026">July 2026</option>
            <option value="August 2026">August 2026</option>
            <option value="September 2026" selected>September 2026</option>
            <option value="October 2026">October 2026</option>
            <option value="November 2026">November 2026</option>
            <option value="December 2026">December 2026</option>
          </select>
        </div>
        <div class="form-field">
          <label>Payment Date (भुगतान तारीख चुनें) *</label>
          <input type="date" id="paymentDate" onchange="calculateTotal()">
        </div>
      </div>

      <!-- 2. FEE DETAILS & PAYMENT -->
      <div class="section-title">2. Fee Details &amp; Payment (जमा व रसीद विवरण)</div>
      <div class="form-grid-3">
        <div class="form-field">
          <label>Previous Due (पिछला बकाया ₹)</label>
          <input type="number" id="prevDues" value="0" min="0" oninput="calculateTotal()">
        </div>
        <div class="form-field">
          <label>Current Month Fee (चालू शुल्क ₹) *</label>
          <input type="number" id="currFee" value="450" min="0" oninput="calculateTotal()">
        </div>
        <div class="form-field">
          <label>Amount Paid Now (जमा की गई राशि ₹) *</label>
          <input type="number" id="paidAmount" value="450" min="0" oninput="calculateTotal()">
        </div>
      </div>

      <div class="form-grid-3">
        <div class="form-field">
          <label>Payment Mode (भुगतान माध्यम) *</label>
          <select id="payMode" onchange="calculateTotal()">
            <option value="Cash (नकद)">Cash (नकद)</option>
            <option value="Online (PhonePe/UPI)">Online (PhonePe/UPI)</option>
          </select>
        </div>
        <div class="form-field" style="grid-column: span 2;">
          <label>Receipt Remarks / Note (रसीद रिमार्क)</label>
          <input type="text" id="receiptNote" value="फीस सफलतापूर्वक प्राप्त हुई।" oninput="calculateTotal()">
        </div>
      </div>

      <!-- Balance Summary Box -->
      <div class="balance-bar">
        <div class="math-text" id="mathBreakdown">
          कुल शुल्क: ₹450 (बकाया ₹0 + चालू ₹450) | जमा: ₹450 | शेष: ₹0
        </div>
        <div class="total-box">
          <span>Remaining Balance (शेष बकाया)</span>
          <strong id="balanceDisplay">₹ 0</strong>
        </div>
      </div>

      <!-- Action Buttons -->
      <div class="btn-row-3">
        <button type="button" class="action-btn btn-print" onclick="printReceipt()">
          <span>🖨️</span> रसीद प्रिंट / PDF
        </button>
        <button type="button" class="action-btn btn-whatsapp" onclick="sendPaidReceipt('whatsapp')">
          <span>💬</span> WhatsApp रसीद भेजें
        </button>
        <button type="button" class="action-btn btn-sms" onclick="sendPaidReceipt('sms')">
          <span>✉️</span> Normal SMS रसीद भेजें
        </button>
      </div>
    </div>
  </div>

  <!-- PRINTABLE PAPER RECEIPT -->
  <div id="receiptPrintArea">
    <div class="receipt-paper">
      <div class="rcpt-head">
        <h2>LUCENT COACHING CENTRE</h2>
        <p>Near Mithila Eye Hospital, Musrighari, Samastipur (Bihar) | Ph: +91 8789524958</p>
        <div style="font-weight: bold; margin-top: 5px; font-size: 13px;">★ OFFICIAL FEE PAYMENT RECEIPT ★</div>
      </div>

      <div class="rcpt-meta">
        <div>रसीद सं.: <span id="rcptNo">LCC-1021</span></div>
        <div>भुगतान दिनांक: <span id="rcptDate">26/09/2026</span></div>
      </div>

      <table class="rcpt-table">
        <tr>
          <th>विद्यार्थी का नाम:</th>
          <td id="rcptStudentName">Rahul Kumar</td>
        </tr>
        <tr>
          <th>कक्षा / बैच (Class):</th>
          <td id="rcptClass">12th</td>
        </tr>
        <tr>
          <th>मोबाइल नंबर:</th>
          <td id="rcptPhone">9876543210</td>
        </tr>
        <tr>
          <th>फीस का महीना:</th>
          <td id="rcptMonth">September 2026</td>
        </tr>
        <tr>
          <th>पिछला बकाया (Previous Due):</th>
          <td id="rcptPrevDue">₹0</td>
        </tr>
        <tr>
          <th>चालू माह शुल्क (Monthly Fee):</th>
          <td id="rcptMonthFee">₹450</td>
        </tr>
        <tr style="background: #f8fafc; font-weight: bold;">
          <th>जमा की गई राशि (Amount Paid):</th>
          <td id="rcptPaid" style="font-size: 14px;">₹450</td>
        </tr>
        <tr>
          <th>भुगतान माध्यम (Payment Mode):</th>
          <td id="rcptMode">Cash (नकद)</td>
        </tr>
        <tr>
          <th>शेष बकाया (Balance Due):</th>
          <td id="rcptBal">₹0</td>
        </tr>
      </table>

      <div style="font-size: 11px; margin-top: 6px; color: #333;">
        * नोट: यह एक आधिकारिक कम्प्यूटरीकृत रसीद है। फीस जमा करने के लिए धन्यवाद।
      </div>

      <div class="rcpt-footer">
        <div style="font-size: 11px;">Verified by: Lucent Office</div>
        <div class="rcpt-sign">हस्ताक्षर / प्राधिकृत मुहर</div>
      </div>
    </div>
  </div>

  <script>
    // Complete Student List
    const studentsData = [
      { name: "AMJAD ALAM", phone: "9955684664" },
      { name: "ANAMIKA KRI", phone: "7257054499" },
      { name: "ANJALI KRI 25", phone: "9661935200" },
      { name: "Anjali Kumari 55", phone: "8102799207" },
      { name: "ANSHU KUMARI-9", phone: "7352082956" },
      { name: "Anshu kri-42", phone: "" },
      { name: "ANUPAM KRI", phone: "9241417455" },
      { name: "BEAUTY KUMARI", phone: "6200783994" },
      { name: "DHIRAJ KUMAR", phone: "6204035295" },
      { name: "DURGA KRI", phone: "9204523024" },
      { name: "GAUTAM KR", phone: "7352494184" },
      { name: "GOLU KR.", phone: "7654872555" },
      { name: "Jamila 12th", phone: "9341643733" },
      { name: "JASMIN PARWEEN", phone: "9693402311" },
      { name: "JULY KRI", phone: "8130457073" },
      { name: "KARINA KUMARI", phone: "7324983282" },
      { name: "KHUSHBOO KRI", phone: "7764836893" },
      { name: "Md Dilsan", phone: "9942833704" },
      { name: "MD MERAJ-17", phone: "9330773998" },
      { name: "MD MERAJ-41", phone: "7091859037" },
      { name: "MD SAJID", phone: "9204687474" },
      { name: "MD SIRAJ", phone: "7549898828" },
      { name: "MD WASIM", phone: "9102763861" },
      { name: "MEHAR KALI", phone: "6299956098" },
      { name: "MEHJABIN PARWEEN", phone: "9990688776" },
      { name: "MONIKA KRI", phone: "6201578087" },
      { name: "MUSARRAT PRAWEEN", phone: "7079910638" },
      { name: "MUSKAN BEGUM", phone: "9330942019" },
      { name: "NEHA KHATOON", phone: "9709587061" },
      { name: "NISHU KRI 30", phone: "8210975252" },
      { name: "NISHU KRI-45", phone: "8475868000" },
      { name: "PARITOSH KUMAR", phone: "9142869790" },
      { name: "PRITY KRI", phone: "7079598875" },
      { name: "PRIYANKA KRI", phone: "9155206202" },
      { name: "Priyanshu kr", phone: "7004128721" },
      { name: "RADHA KRI", phone: "9534005894" },
      { name: "RAGINI KRI", phone: "6201389319" },
      { name: "Raja kr", phone: "9296503161" },
      { name: "RAJ NANDINI KRI", phone: "8873126752" },
      { name: "RANJAN KUMAR", phone: "9709864426" },
      { name: "RAUSHNI KRI", phone: "9534758058" },
      { name: "RIMJHIM KRI", phone: "9570170325" },
      { name: "ROKHSANA KHATUN", phone: "9709658472" },
      { name: "RUPA KRI", phone: "9661273871" },
      { name: "SAHIN PARWEEN", phone: "7372035346" },
      { name: "SAMA AFREEN", phone: "9110989890" },
      { name: "SANDHNA KRI", phone: "8002000873" },
      { name: "SANIYA PARWEEN", phone: "7654162435" },
      { name: "SAVITA KRI", phone: "7544842569" },
      { name: "SHAHNAWAZ HUSSAIN", phone: "8102643833" },
      { name: "SHIVANI KRI", phone: "7563912052" },
      { name: "SNEHA KUMARI", phone: "7295997451" },
      { name: "SUDHA KRI", phone: "9931051192" },
      { name: "SUMAN KUMARI", phone: "9560726946" },
      { name: "SUNITA KRI", phone: "8252764123" },
      { name: "VERSA KRI", phone: "7255032487" }
    ];

    function setDefaultDate() {
      const today = new Date();
      const yyyy = today.getFullYear();
      const mm = String(today.getMonth() + 1).padStart(2, '0');
      const dd = String(today.getDate()).padStart(2, '0');
      document.getElementById('paymentDate').value = `${yyyy}-${mm}-${dd}`;
    }

    function getFormattedSelectedDate() {
      const val = document.getElementById('paymentDate').value;
      if (!val) return "";
      const p = val.split('-');
      return `${p[2]}/${p[1]}/${p[0]}`;
    }

    function populateDropdown() {
      const select = document.getElementById('studentSelect');
      select.innerHTML = '<option value="">-- छात्र का नाम चुनें --</option>';
      studentsData.forEach((st, idx) => {
        const opt = document.createElement('option');
        opt.value = idx;
        opt.textContent = `${st.name} (${st.phone || 'No Phone'})`;
        select.appendChild(opt);
      });
    }

    function onStudentSelectChange() {
      const select = document.getElementById('studentSelect');
      const val = select.value;
      if (val !== "") {
        const student = studentsData[val];
        document.getElementById('studentName').value = student.name;
        document.getElementById('parentPhone').value = student.phone || "";
        document.getElementById('prevDues').value = 0;
        document.getElementById('paidAmount').value = 450;
      }
      calculateTotal();
    }

    function calculateTotal() {
      const prev = parseFloat(document.getElementById('prevDues').value) || 0;
      const curr = parseFloat(document.getElementById('currFee').value) || 0;
      const paid = parseFloat(document.getElementById('paidAmount').value) || 0;

      const totalFee = prev + curr;
      let remaining = totalFee - paid;
      if (remaining < 0) remaining = 0;

      document.getElementById('mathBreakdown').innerText = 
        `कुल शुल्क: ₹${totalFee} (बकाया ₹${prev} + चालू ₹${curr}) | जमा: ₹${paid} | शेष: ₹${remaining}`;
      document.getElementById('balanceDisplay').innerText = `₹ ${remaining}`;

      return { totalFee, paid, remaining, prev, curr };
    }

    function printReceipt() {
      const name = document.getElementById('studentName').value.trim();
      const phone = document.getElementById('parentPhone').value.trim();
      const sClass = document.getElementById('studentClass').value.trim();
      const month = document.getElementById('feeMonth').value;
      const mode = document.getElementById('payMode').value;
      const calc = calculateTotal();
      const pDate = getFormattedSelectedDate();

      if (!name) {
        alert("कृपया पहले छात्र का नाम चुनें!");
        return;
      }

      document.getElementById('rcptNo').innerText = 'LCC-' + Math.floor(1000 + Math.random() * 9000);
      document.getElementById('rcptDate').innerText = pDate;
      document.getElementById('rcptStudentName').innerText = name;
      document.getElementById('rcptClass').innerText = sClass;
      document.getElementById('rcptPhone').innerText = phone || 'N/A';
      document.getElementById('rcptMonth').innerText = month;
      document.getElementById('rcptPrevDue').innerText = `₹${calc.prev}`;
      document.getElementById('rcptMonthFee').innerText = `₹${calc.curr}`;
      document.getElementById('rcptPaid').innerText = `₹${calc.paid}`;
      document.getElementById('rcptMode').innerText = mode;
      document.getElementById('rcptBal').innerText = `₹${calc.remaining}`;

      window.print();
    }

    function sendPaidReceipt(channel) {
      const name = document.getElementById('studentName').value.trim();
      let 
