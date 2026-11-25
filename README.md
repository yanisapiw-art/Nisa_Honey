# Honey House

เว็บไซต์ร้านน้ำผึ้งสไตล์ natural พัฒนาด้วย HTML, CSS และ JavaScript แบบ Static พร้อมตะกร้าสินค้า และ Google Apps Script สำหรับบันทึกคำสั่งซื้อใน Google Sheets

## สินค้าตัวอย่าง
- HH-001 น้ำผึ้งดอกลำไย 250 กรัม — 159 บาท (สต็อกเริ่มต้น 50)
- HH-002 น้ำผึ้งป่า 500 กรัม — 279 บาท (สต็อกเริ่มต้น 35)

## เชื่อม Google Sheets
1. เปิด Google Sheets ของโปรเจกต์
2. เลือก Extensions → Apps Script
3. คัดลอกเนื้อหาไฟล์ `google-apps-script/Code.gs` ไปวางใน Apps Script แล้ว Save
4. เลือกฟังก์ชัน `setupSheets` แล้วกด Run และอนุญาตสิทธิ์ ระบบจะสร้างชีต Products และ Orders
5. เลือก Deploy → New deployment → Web app
6. ตั้ง Execute as: Me และ Who has access: Anyone แล้ว Deploy
7. คัดลอก Web app URL แล้วใส่ใน `CONFIG.API_URL` ในไฟล์ `app.js`
8. Commit การแก้ไข `app.js` ขึ้น GitHub เพื่อให้ Vercel deploy ใหม่

## Vercel
Repository นี้เป็น Static HTML ไม่ต้องใช้ framework หรือ build command
- Framework Preset: Other
- Build Command: เว้นว่าง
- Output Directory: .

## สิ่งที่ยังต้องตั้งค่าก่อนใช้งานจริง
- Apps Script Web App URL ยังไม่ได้ใส่ใน `app.js`
- LINE URL ใน `index.html` ยังเป็นลิงก์ทั่วไป ต้องเปลี่ยนเป็นลิงก์ LINE Official Account ของร้าน
- หน้าผู้ดูแลแบบใช้งานจริง, การยืนยันตัวตน, ระบบหยิบ/แพ็กที่อัปเดตสถานะในชีต และใบจ่าหน้าพัสดุของบริษัทขนส่ง ยังต้องพัฒนาต่อ
- ระบบตัวอย่างนี้ยังไม่มีการชำระเงินออนไลน์

**ข้อควรระวัง:** ทดสอบการสร้างออเดอร์และการตัดสต็อกด้วยออเดอร์ทดลองก่อนเปิดขายจริง และอย่าใส่รหัสผ่านหรือ token ลับไว้ใน JavaScript ฝั่งหน้าเว็บ
