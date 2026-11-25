<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
  <meta name="description" content="รวม 10 สถานที่เที่ยวอุดรธานี พร้อมที่พักและร้านอาหารใกล้ ๆ">
  <title>เที่ยวอุดรธานี 10 จุด พร้อมที่พักและร้านอาหาร</title>

  <style>
    /* ========== 1. สีและธีม (แก้สีได้ที่นี่) ========== */
    :root {
      --bg: #fffaf7;      /* พื้นหลังหน้าเว็บ */
      --card: #ffffff;    /* พื้นการ์ด */
      --text: #25202a;    /* สีตัวหนังสือ */
      --muted: #6b6270;   /* ตัวหนังสือรอง */
      --accent: #c2185b;  /* สีหลัก (ชมพูบัวแดง) */
      --accent2: #00796b; /* สีรอง (เขียว) */
      --border: #eadfe3;
      --header: #8e1451;

      box-sizing: border-box;
      padding-top: env(safe-area-inset-top, 0px);
      padding-bottom: env(safe-area-inset-bottom, 0px);
    }

    /* โหมดมืด (ตามเครื่อง) */
    @media (prefers-color-scheme: dark) {
      :root:not([data-theme="light"]) {
        --bg: #17131a; --card: #221c26; --text: #f3ecf4; --muted: #b3a8b8;
        --accent: #f06292; --accent2: #4db6ac; --border: #37303b; --header: #4a1030;
      }
    }
    :root[data-theme="dark"] {
      --bg: #17131a; --card: #221c26; --text: #f3ecf4; --muted: #b3a8b8;
      --accent: #f06292; --accent2: #4db6ac; --border: #37303b; --header: #4a1030;
    }

    /* ========== 2. โครงหน้า ========== */
    html { scroll-padding-top: env(safe-area-inset-top, 0px); }
    * { box-sizing: border-box; }

    body {
      margin: 0;
      background: var(--bg);
      color: var(--text);
      font-family: 'Noto Sans Thai', 'Sarabun', system-ui, sans-serif;
      line-height: 1.65;
    }

    header {
      background: linear-gradient(135deg, var(--header), #c2185b);
      color: #fff;
      padding: 36px 20px 28px;
      text-align: center;
    }
    header h1 { margin: 0 0 6px; font-size: 1.9rem; }
    header p  { margin: 0; opacity: .92; }

    nav {
      position: sticky;
      top: env(safe-area-inset-top, 0px);
      z-index: 5;
      padding: 12px 16px;
      background: var(--bg);
      border-bottom: 1px solid var(--border);
    }
    nav:empty { display: none; }
    nav a {
      display: inline-block;
      padding: 4px 12px;
      border: 1px solid var(--border);
      border-radius: 20px;
      background: var(--card);
      color: var(--accent);
      font-size: .85rem;
      text-decoration: none;
    }

    main { max-width: 760px; margin: 0 auto; padding: 16px; }

    footer {
      padding: 20px 16px 30px;
      text-align: center;
      color: var(--muted);
      font-size: .8rem;
    }

    /* ========== 3. หน้าแรก: การ์ดรายการสถานที่ ========== */
    .hint { margin: 4px 0 12px; color: var(--muted); }

    .card {
      display: flex;
      align-items: center;
      gap: 12px;
      margin: 10px 0;
      padding: 12px 14px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 14px;
      color: var(--text);
      text-decoration: none;
      transition: transform .15s;
    }
    .card:active { transform: scale(.97); }
    .card .no {
      flex: none;
      width: 34px; height: 34px;
      line-height: 34px;
      text-align: center;
      font-weight: bold;
      color: #fff;
      background: var(--accent);
      border-radius: 50%;
    }
    .card .info { flex: 1; }
    .card b     { display: block; }
    .card small { display: block; color: var(--muted); font-size: .8rem; }
    .card .arrow { font-size: 1.6rem; color: var(--accent); }

    /* ========== 4. หน้ารายละเอียด ========== */
    .spot {
      margin: 16px 0;
      padding: 18px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
    }
    .spot h2 { margin: 0 0 2px; font-size: 1.25rem; color: var(--accent); }
    .spot h2 span {
      display: inline-block;
      width: 28px; height: 28px;
      margin-right: 8px;
      line-height: 28px;
      text-align: center;
      font-size: .9rem;
      color: #fff;
      background: var(--accent);
      border-radius: 50%;
    }
    .spot h3 { margin: 14px 0 6px; font-size: 1rem; color: var(--accent2); }
    .location { margin-bottom: 8px; color: var(--muted); font-size: .85rem; }

    .tip {
      margin: 8px 0;
      padding: 6px 10px;
      font-size: .9rem;
      background: rgba(0, 121, 107, .1);
      border-left: 3px solid var(--accent2);
      border-radius: 6px;
    }

    .btn {
      display: inline-block;
      margin: 6px 0;
      padding: 8px 14px;
      font-size: .9rem;
      color: #fff;
      background: var(--accent2);
      border-radius: 10px;
      text-decoration: none;
    }

    /* รายการที่พัก / ร้านอาหาร */
    .item { padding: 8px 0; border-top: 1px dashed var(--border); }
    .item b     { display: block; }
    .item small { color: var(--muted); }
    .item a     { margin-right: 10px; color: var(--accent); font-size: .85rem; }

    /* ปุ่มสถานที่ก่อนหน้า / ถัดไป */
    .pager { display: flex; justify-content: space-between; gap: 8px; margin: 8px 0; }
    .pager a { color: var(--accent); font-size: .9rem; text-decoration: none; }

    /* ========== 5. เอฟเฟกต์หยดน้ำ ========== */
    .drop {
      position: fixed;
      z-index: 99;
      width: 24px; height: 24px;
      margin: -12px 0 0 -12px;
      border-radius: 50%;
      border: 2px solid rgba(194, 24, 91, .55);
      background: radial-gradient(circle, rgba(194,24,91,.28) 0%, rgba(0,121,107,.2) 60%, transparent 70%);
      pointer-events: none;
      transform: scale(0);
      opacity: .9;
      animation: drop .7s cubic-bezier(.2, .6, .3, 1) forwards;
    }
    .drop::after {          /* วงน้ำชั้นใน */
      content: "";
      position: absolute;
      inset: 6px;
      border-radius: 50%;
      border: 2px solid rgba(0, 121, 107, .5);
    }
    @keyframes drop { 60% { opacity: .6; } to { transform: scale(150); opacity: 0; } }

    /* หน้าใหม่ค่อย ๆ ชัดขึ้น */
    #app.enter { animation: enter .55s cubic-bezier(.2, .7, .3, 1); }
    @keyframes enter {
      from { opacity: 0; transform: scale(.95) translateY(8px); filter: blur(6px); }
      to   { opacity: 1; transform: none; filter: blur(0); }
    }

    /* คนที่ปิดแอนิเมชันในเครื่อง */
    @media (prefers-reduced-motion: reduce) {
      .drop { display: none; }
      #app.enter { animation: none; }
    }
  </style>
</head>

<body>
  <header>
    <h1>🌸 เที่ยวอุดรธานี</h1>
    <p>10 จุดเที่ยว พร้อมที่พักและร้านอาหาร/คาเฟ่ใกล้ ๆ</p>
  </header>

  <nav id="nav"></nav>
  <main id="app"></main>

  <footer>
    คะแนนและข้อมูลที่พัก/ร้านมาจาก Google Maps ราคา เวลาเปิด-ปิดอาจเปลี่ยน<br>
    โทรสอบถามหรือเช็กก่อนเดินทางทุกครั้ง
  </footer>

  <script>
    /* ========== 1. ข้อมูล ========== */

    // สร้างข้อมูลที่พัก/ร้าน 1 รายการ (ชื่อ, คะแนน, เบอร์โทร, ละติจูด, ลองจิจูด, หมายเหตุ)
    // เบอร์ "—" = ไม่มีเบอร์
    const place = (name, rating, phone, lat, lng, note) =>
      ({ name, rating, phone, lat, lng, note });

    // สถานที่ท่องเที่ยว: name ชื่อ / area พื้นที่ / desc คำอธิบาย / tip เคล็ดลับ
    //                   stays ที่พัก / eats ร้านอาหารและคาเฟ่
    const SPOTS = [
      {
        name: "ทะเลบัวแดง (หนองหานกุมภวาปี)",
        area: "อ.กุมภวาปี",
        desc: "ทะเลสาบดอกบัวแดงสุดฮิตของอุดรฯ นั่งเรือชมบัวบานยามเช้า",
        tip: "ไปเช้าตรู่ ช่วงบัวบานราวเดือนธันวาคมถึงกุมภาพันธ์ จองเรือล่วงหน้าผ่านที่พักได้",
        stays: [
          place("Bua Daeng Resort บัวแดง รีสอร์ท", "4.8", "083 614 0916", 17.231218, 103.0182742, "รีวิวบอกห่างทะเลบัวแดงราว 3–5 นาที มีสระว่ายน้ำ"),
          place("Kitisuwan Villa", "4.7", "088 218 4986", 17.1251779, 103.0320198, "ใกล้ท่าเรือ ห้องสะอาด ราคาประหยัด"),
        ],
        eats: [
          place("บ้านข้าวหอม", "4.7", "094 664 4662", 17.3637992, 103.1069825, "ร้านข้าวซอย ในอ.หนองหาน (ปิดวันอาทิตย์)"),
          place("ร้านอาหารที่ มาเดอบัว (Ma Der Bua)", "4.1", "088 573 0364", 17.2125416, 103.0337317, "อยู่ติดท่าเรือชมบัวแดง"),
        ],
      },
      {
        name: "วัดคำชะโนด",
        area: "อ.บ้านดุง",
        desc: "สถานที่ศักดิ์สิทธิ์ชื่อดังของอีสาน เกาะลอยน้ำตามความเชื่อพญานาค",
        tip: "คนเยอะมากช่วงวันหยุดและวันพระ แต่งกายสุภาพ",
        stays: [
          place("บ้านต้นปาล์ม คำชะโนด โฮมสเตย์", "4.6", "094 872 8546", 17.7411316, 103.3583619, "อยู่ตรงข้ามวัด เดินถึง มีอาหารเช้า"),
          place("ดรีมฟอเรส รีสอร์ท", "4.9", "099 142 9142", 17.7404298, 103.2917758, "บังกะโลเดี่ยว ห้องสะอาด"),
        ],
        eats: [
          place("วาสนา คาเฟ่ คำชะโนด", "4.7", "—", 17.7411535, 103.2909073, "คาเฟ่ใหญ่ ตกแต่งธีมพญานาค มีอาหารด้วย"),
          place("วาสนาปาร์ค รีสอร์ทและร้านอาหาร", "4.5", "061 160 4766", 17.7409433, 103.2899893, "ร้านอาหาร สระปลาให้อาหาร"),
        ],
      },
      {
        name: "ศาลเจ้าปู่-ย่า",
        area: "ตัวเมืองอุดรธานี",
        desc: "ศาลเจ้าจีนสีสันสดใส มังกรขาวขนาดใหญ่ด้านหลัง ติดหนองประจักษ์",
        tip: "ไปช่วงเย็นถึงค่ำ ไฟโคมแดงสวยมาก",
        stays: [
          place("Charoen Hotel (โรงแรมเจริญ)", "4.3", "042 248 155", 17.4013135, 102.8005099, "โรงแรมเก่าแต่ทำเลดี มีสระ ห้องประชุมเยอะ"),
          place("Surada Guesthouse", "4.3", "042 245 769", 17.3977153, 102.8052407, "เกสต์เฮาส์ราคาประหยัด เดินจากสถานีรถไฟได้"),
        ],
        eats: [
          place("ร้านชาผิงอันและติ่มซำ", "4.6", "082 707 0666", 17.3991717, 102.807026, "ติ่มซำราคาประมาณ 35 บาทต่อจาน ในศาลเจ้า (9:00–18:00)"),
          place("Brunch & Munch", "4.5", "061 396 9988", 17.4022405, 102.8047207, "สเต็ก พาสต้า ในย่านยูดีทาวน์"),
        ],
      },
      {
        name: "สวนสาธารณะหนองประจักษ์ศิลปาคม",
        area: "ตัวเมืองอุดรธานี",
        desc: "สวนกลางเมืองริมบึง เดินเล่น ปั่นจักรยาน ชมพระอาทิตย์ตก",
        tip: "เช้าและเย็นอากาศดี คนออกกำลังกายเยอะ",
        stays: [
          place("VELA Dhi Udon Thani Hotel", "4.8", "042 219 219", 17.4166662, 102.7999798, "โรงแรมใหม่ มีสระ ฟิตเนส ซาวน่า"),
          place("The Old Inn Udonthani", "4.2", "095 646 6147", 17.405362, 102.8016143, "โรงแรมสไตล์ลอฟต์ ใกล้ร้านอาหารและเซ็นทรัล"),
        ],
        eats: [
          place("Lost in the Forest Cafe", "4.5", "095 456 9655", 17.4132072, 102.770175, "คาเฟ่สวนร่มรื่น เมนูไทยและตะวันตก"),
          place("UD TOWN Food Center", "4.5", "062 789 2456", 17.4031117, 102.8043095, "ศูนย์อาหาร หลายร้าน มีดนตรีสด"),
        ],
      },
      {
        name: "ยูดีทาวน์ (UD Town) และย่านใจกลางเมือง",
        area: "ตัวเมืองอุดรธานี",
        desc: "แหล่งช้อปปิ้ง กินดื่ม และตลาดกลางคืนใจกลางเมือง",
        tip: "ศูนย์อาหารต้องเติมเงินในบัตรก่อนซื้อ เหลือเงินคืนได้ที่เคาน์เตอร์",
        stays: [
          place("Centara Udon", "4.4", "042 343 555", 17.4065879, 102.8005834, "ติดห้างเซ็นทรัล มีสปา ฟิตเนส"),
          place("Kavinburi Green Hotel", "4.1", "042 326 888", 17.404045, 102.8018865, "สระดาดฟ้า เดินถึงตลาดกลางคืน"),
        ],
        eats: [
          place("UD TOWN Food Center", "4.5", "062 789 2456", 17.4031117, 102.8043095, "เปิดถึงเที่ยงคืน (10:30–24:00)"),
          place("Brunch & Munch", "4.5", "061 396 9988", 17.4022405, 102.8047207, "เปิด 7:00–22:00 เหมาะมื้อสาย"),
        ],
      },
      {
        name: "บ้านเชียง (แหล่งมรดกโลก)",
        area: "อ.หนองหาน",
        desc: "แหล่งโบราณคดียุคก่อนประวัติศาสตร์ อายุราว 5,000 ปี ขึ้นทะเบียนมรดกโลกปี 1992",
        tip: "ตรวจสอบเวลาเปิดพิพิธภัณฑ์ก่อนไป ในหมู่บ้านมีรถรางนำเที่ยว",
        stays: [
          place("เฮือนปลายนา@บ้านเชียง", "4.5", "084 628 0716", 17.3993403, 103.23108, "บังกะโลวิวทุ่งนา ราคาประมาณ 600 บาท"),
          place("โฮมสเตย์เฮือนพรประไกร (บ้านเชียง)", "4.6", "081 485 1864", 17.4038772, 103.2371843, "สะอาด เงียบ เหมาะครอบครัว"),
        ],
        eats: [
          place("Wanadee’s Homestay & Restaurant", "4.9", "087 605 4666", 17.3993473, 103.2211065, "ผัดกะเพราเนื้อเป็นเมนูเด่น มีสระและบาร์"),
          place("เฮือนปลายนา (ร้านอาหารในที่พัก)", "4.5", "084 628 0716", 17.3993403, 103.23108, "ส้มตำ ไส้กรอกอีสาน ครัวปิด 21:00"),
        ],
      },
      {
        name: "วัดป่าบ้านตาด",
        area: "อ.เมืองอุดรธานี",
        desc: "วัดป่าสายพระกรรมฐาน ร่มรื่น สงบ เหมาะทำบุญและเดินเงียบ ๆ",
        tip: "แต่งกายสุภาพ รักษาความสงบ",
        stays: [
          place("Triple M Resort", "4.9", "081 116 5442", 17.3101005, 102.7914603, "รีสอร์ทใหม่ ห้องใหญ่ มีร้านอาหารและเครื่องดื่มในที่พัก"),
        ],
        eats: [
          place("ร้านอาหารใน Triple M Resort", "4.9", "081 116 5442", 17.3101005, 102.7914603, "เมนูหลากหลาย รอนานได้ในบางช่วง"),
        ],
      },
      {
        name: "วัดถ้ำสหาย (หนองวัวซอ)",
        area: "อ.หนองวัวซอ",
        desc: "วัดถ้ำในเขตธรรมชาติ บรรยากาศสงบ ใกล้ลำธาร",
        tip: "ที่พักบางแห่งรับจัดเตรียมใส่บาตรให้ ถามเจ้าของก่อน",
        stays: [
          place("213 ที่นี่ผาสิงห์ Cafe Resort & Camping", "4.8", "091 867 6265", 17.1919082, 102.6563641, "ติดลำธาร มีคาเฟ่และลานกางเต็นท์"),
          place("หลงภู@ผาสิงห์", "4.6", "088 793 5804", 17.1946126, 102.6599948, "แคมป์ปิ้ง บังกะโล มีร้านอาหารและคาเฟ่"),
        ],
        eats: [
          place("บ้านสวนคุณย่า Garden & Farmstay", "4.6", "062 348 8320", 17.195629, 102.6587514, "ฟาร์มสเตย์และคาเฟ่ อาจเก็บค่าเข้าสำหรับผู้ไม่พัก"),
          place("หลงภู@ผาสิงห์ (ร้านอาหาร)", "4.6", "088 793 5804", 17.1946126, 102.6599948, "อาหารราคาประหยัด มีมุมปิ้งย่าง"),
        ],
      },
      {
        name: "วัดป่านาคำน้อย",
        area: "อ.นายูง",
        desc: "วัดป่าชื่อดังทางภาคอีสานตอนบน บรรยากาศภูเขาเย็นสบาย",
        tip: "อยู่ห่างตัวเมืองพอสมควร เหมาะค้างคืน ถนนบางช่วงต้องขับระวัง",
        stays: [
          place("บ้านสวนมีสุข ที่พักนายูงรีสอร์ท", "4.7", "096 160 4302", 17.9226377, 102.2125019, "บรรยากาศสวนร่มรื่น เจ้าของใจดี"),
          place("Thongkoon Homestay", "4.8", "091 373 4816", 17.9138213, 102.1733789, "กระท่อมสะอาด ตรงข้ามมีเซเว่น"),
        ],
        eats: [
          place("เพียงพอดี", "4.3", "092 696 4222", 17.9253876, 102.2154735, "รับสั่งอาหารถวายพระ ร้านกาแฟและร้านอาหารที่เดียว"),
          place("ครัวจำปาสี่ต้น", "4.5", "064 154 4451", 17.9261786, 102.1857143, "อาหารตามสั่งสไตล์ครอบครัว (ปิดวันศุกร์)"),
        ],
      },
      {
        name: "อีสานบ้านเฮาฟาร์ม",
        area: "อ.บ้านดุง",
        desc: "แหล่งเรียนรู้วิถีอีสาน ขี่ม้า นั่งเกวียน ทอผ้า กินอาหารพื้นบ้าน",
        tip: "รีวิวบอกเข้าชมฟรี ไม่คิดค่าขี่ม้าและเกวียน รายได้มาจากที่พักและอาหาร",
        stays: [
          place("ที่พักบ้านไม้สไตล์อีสานในฟาร์ม", "4.4", "098 708 8245", 17.6081665, 103.336998, "บ้านอีสานดัดแปลงทันสมัย มีแอร์"),
        ],
        eats: [
          place("ร้านอาหารในฟาร์ม", "4.4", "098 708 8245", 17.6081665, 103.336998, "เมนูอีสานหลากหลาย มีกาแฟและเครื่องดื่ม (8:00–17:00)"),
        ],
      },
    ];

    /* ========== 2. ฟังก์ชันช่วย ========== */

    const $ = id => document.getElementById(id);

    // ลิงก์ Google Maps จากพิกัด
    const mapByCoords = (lat, lng) =>
      `https://www.google.com/maps/search/?api=1&query=${lat},${lng}`;

    // ลิงก์ Google Maps จากชื่อสถานที่
    const mapByName = name =>
      `https://www.google.com/maps/search/?api=1&query=${encodeURIComponent(name + " อุดรธานี")}`;

    // HTML ของที่พัก/ร้าน 1 รายการ
    function itemHTML(p) {
      const phoneLink = p.phone === "—"
        ? ""
        : `<a href="tel:${p.phone.replace(/\s/g, "")}">โทร ${p.phone}</a>`;
      return `
        <div class="item">
          <b>${p.name}</b>
          <small>★ ${p.rating} · ${p.note}</small>
          <div>
            ${phoneLink}
            <a href="${mapByCoords(p.lat, p.lng)}" target="_blank" rel="noopener">แผนที่</a>
          </div>
        </div>`;
    }

    /* ========== 3. หน้าแรก (รายการสถานที่) ========== */

    function showHome() {
      $("nav").innerHTML = "";
      $("app").innerHTML =
        `<p class="hint">แตะที่สถานที่เพื่อดูรายละเอียด ที่พัก และร้านอาหารใกล้ ๆ</p>` +
        SPOTS.map((s, i) => `
          <a class="card" href="#spot-${i + 1}">
            <span class="no">${i + 1}</span>
            <div class="info">
              <b>${s.name}</b>
              <small>📍 ${s.area}</small>
              <small>🛏 ${s.stays.length} ที่พัก · 🍜 ${s.eats.length} ร้าน/คาเฟ่</small>
            </div>
            <span class="arrow">›</span>
          </a>`).join("");
    }

    /* ========== 4. หน้ารายละเอียด ========== */

    function showDetail(i) {
      const s = SPOTS[i];
      const prev = SPOTS[i - 1];
      const next = SPOTS[i + 1];
      const shortName = spot => spot.name.split(" ")[0];

      $("nav").innerHTML = `<a href="#">← กลับหน้ารวม</a>`;
      $("app").innerHTML = `
        <section class="spot">
          <h2><span>${i + 1}</span>${s.name}</h2>
          <div class="location">📍 ${s.area}</div>
          <p>${s.desc}</p>
          <div class="tip">💡 ${s.tip}</div>
          <a class="btn" href="${mapByName(s.name)}" target="_blank" rel="noopener">🗺 เปิดสถานที่นี้ใน Google Maps</a>

          <h3>🛏 ที่พักใกล้ ๆ</h3>
          ${s.stays.map(itemHTML).join("")}

          <h3>🍜 ร้านอาหาร / คาเฟ่</h3>
          ${s.eats.map(itemHTML).join("")}
        </section>

        <div class="pager">
          ${prev ? `<a href="#spot-${i}">‹ ${shortName(prev)}</a>` : "<span></span>"}
          ${next ? `<a href="#spot-${i + 2}">${shortName(next)} ›</a>` : "<span></span>"}
        </div>`;
    }

    /* ========== 5. สลับหน้าตาม URL (#spot-1, #spot-2, ...) ========== */

    function route() {
      const match = location.hash.match(/^#spot-(\d+)$/);
      const index = match ? Number(match[1]) - 1 : -1;

      if (SPOTS[index]) showDetail(index);
      else showHome();

      scrollTo(0, 0);

      // เล่นแอนิเมชันหน้าใหม่ใหม่ทุกครั้ง
      const app = $("app");
      app.classList.remove("enter");
      void app.offsetWidth;
      app.classList.add("enter");
    }

    /* ========== 6. เอฟเฟกต์หยดน้ำตอนแตะลิงก์ภายในหน้า ========== */

    document.addEventListener("click", e => {
      const link = e.target.closest('a[href^="#"]');
      if (!link) return;
      e.preventDefault();

      // วางวงน้ำตรงจุดที่แตะ (ถ้าใช้คีย์บอร์ดให้อยู่กลางปุ่ม)
      const box = link.getBoundingClientRect();
      const drop = document.createElement("div");
      drop.className = "drop";
      drop.style.left = (e.clientX || box.left + box.width / 2) + "px";
      drop.style.top  = (e.clientY || box.top + box.height / 2) + "px";
      document.body.appendChild(drop);

      // รอให้เห็นวงน้ำก่อน แล้วค่อยเปลี่ยนหน้า
      setTimeout(() => { location.hash = link.getAttribute("href").slice(1); }, 240);
      setTimeout(() => drop.remove(), 800);
    });

    addEventListener("hashchange", route);
    route();
  </script>
</body>
</html>

