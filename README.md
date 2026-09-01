# GPS Photo EXIF Extractor & Map Visualizer (SPA)

เว็บแอปพลิเคชัน Single Page Application (SPA) สำหรับอ่านข้อมูลพิกัด GPS (EXIF Metadata) และวันเวลาถ่ายภาพจากรูปภาพ แสดงผลบนตารางและแผนที่ Interactive (Leaflet.js / OpenStreetMap) พร้อมการส่งออกไฟล์ CSV รองรับภาษาไทย (UTF-8 BOM)

---

## 🌟 ฟังก์ชันและคุณสมบัติเด่น

1. **Client-Side 100% (Privacy & Security)**
   - รูปภาพทั้งหมดถูกประมวลผลบนเบราว์เซอร์ของผู้ใช้โดยตรง ไม่มีการส่งไฟล์ไปยังเซิร์ฟเวอร์ภายนอก ปลอดภัย รวดเร็ว และทำงานแบบ Offline ได้

2. **การอัปโหลดไฟล์ (Multi-Upload & Mobile Friendly)**
   - ปุ่ม **"เลือกรูปภาพทั้งหมด"** และ **"เลือกทั้งโฟลเดอร์"** (ใช้ `webkitdirectory`)
   - รองรับไฟล์รูปภาพหลากหลายฟอร์แมต: `.JPG`, `.JPEG`, `.PNG`, `.WebP`, `.TIFF`
   - รองรับไฟล์ **`.HEIC` / `.HEIF`** จาก iPhone / iPad / Android
   - พื้นที่ **Dropzone** ขนาดใหญ่ รองรับการลากวางไฟล์ (Drag & Drop)

3. **การประมวลผล EXIF Metadata**
   - อ่านพิกัด `Latitude` และ `Longitude` พร้อมแปลงจาก DMS เป็น Decimal Degrees (เช่น `16.432215, 102.823412`) อัตโนมัติด้วยไลบรารี `exifr`
   - ดึงวันที่และเวลาถ่ายภาพ (`DateTimeOriginal`)
   - **Progress Bar**: แสดงความคืบหน้าแบบ Real-time เปอร์เซ็นต์ และจำนวนรูปที่สแกนสำเร็จ

4. **การแสดงผลข้อมูลและแผนที่ (Interactive Dashboard)**
   - **Interactive Map (Leaflet.js & OpenStreetMap)**:
     * ปักหมุดพิกัดของรูปภาพทั้งหมดลงบนแผนที่
     * Popup แสดงรูปพรีวิว, ชื่อไฟล์, วันเวลาถ่ายภาพ, พิกัด และลิงก์เปิดดูใน Google Maps
     * ปุ่ม **Focus Map**: ปรับมุมมองแผนที่ให้ครอบคลุมทุกหมุดโดยอัตโนมัติ
     * ฟังก์ชัน **Zoom to Pin**: คลิกจากตารางเพื่อวูมไปยังตำแหน่งหมุดในแผนที่
   - **Data Table**:
     * รูป Thumbnail พรีวิว (คลิกเปิด Modal ดูรูปขนาดใหญ่)
     * ชื่อไฟล์, ขนาดไฟล์ (KB/MB), วันที่ถ่ายภาพ
     * พิกัด GPS พร้อมปุ่ม **"คัดลอกพิกัด"** ด้วยคลิกเดียว
     * ลิงก์ตรงเปิดดูตำแหน่งบน **Google Maps**
     * ช่องค้นหา (Search) ตามชื่อไฟล์หรือวันที่ และตัวกรอง (Filter) แสดงเฉพาะรูปที่มี/ไม่มี GPS

5. **ส่งออกข้อมูล CSV (UTF-8 with BOM)**
   - ปุ่ม **Export CSV** สำหรับนำข้อมูลไปใช้งานต่อใน Microsoft Excel หรือ Google Sheets
   - ใส่ **UTF-8 BOM (`\uFEFF`)** ป้องกันปัญหาภาษาไทยกลายเป็นภาษาต่างดาว
   - คอลัมน์ที่ส่งออก: `File Name`, `Latitude`, `Longitude`, `Full Coordinates`, `Date Taken`, `File Size`, `Google Maps Link`

---

## 📱 วิธีเปิดใช้งาน (คอมพิวเตอร์ และ มือถือ Android / iOS)

### 1. เปิดใช้งานบน คอมพิวเตอร์ (Windows / Mac)
- สามารถดับเบิลคลิกเปิดไฟล์ **`GPS_EXIF_Map_Extractor.html`** หรือ **`GPS_Photo_Extractor/index.html`** ด้วยเว็บเบราว์เซอร์ใดก็ได้ (Chrome, Edge, Firefox, Safari)

### 2. เปิดใช้งานบน มือถือ (Android / iPhone / iPad)
- เปิดไฟล์ `index.html` ผ่านเว็บเบราว์เซอร์บนมือถือ
- กดปุ่ม **"เลือกรูปภาพทั้งหมด"** เพื่อเลือกรูปภาพหลาย ๆ รูปจากคลังภาพ (Photos Album) ในครั้งเดียว

---

## 🛠️ เทคโนโลยีที่ใช้ (Libraries via CDN)
- **HTML5 & Modern Vanilla JavaScript (ES6+)**
- **Tailwind CSS v3**: สำหรับดีไซน์ UI Responsive & Modern Clean Style
- **Leaflet.js v1.9.4 & OpenStreetMap**: สำหรับแผนที่และระบบปักหมุด
- **exifr v7.1.3**: สำหรับอ่าน EXIF Metadata (GPS & Date)
- **heic2any v0.0.4**: สำหรับแปลงพรีวิวไฟล์ HEIC/HEIF บนเบราว์เซอร์
- **FontAwesome v6 font icons**: สำหรับไอคอน UI
