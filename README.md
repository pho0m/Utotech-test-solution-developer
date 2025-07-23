# 📦 Utotech Test: Developer Solution

**ระบบนำเข้า ตรวจสอบ และจัดการข้อมูลแบบ Responsive**
Tech Stack: `Next.js + TypeScript + Tailwind CSS + Shadcn UI`

---

## 🚀 เทคโนโลยีที่ใช้

- ⚙️ **Frontend**: [Next.js](https://nextjs.org/) (TypeScript)
- 🎨 **UI Framework**: [Shadcn UI](https://ui.shadcn.com/) + [Tailwind CSS](https://tailwindcss.com/)
- 🧠 **State Management**: React Context API / Local Storage
- 📤 **Export Format**: Excel (.xls), CSV (.csv)

---

## 🧭 Flow การทำงานของระบบ

### 1. 📥 Import Data

- ผู้ใช้สามารถอัปโหลดไฟล์ข้อมูลผ่านหน้าเว็บ
- ข้อมูลที่อัปโหลดจะถูกจัดเก็บไว้ใน `Context` หรือ `Local Storage` เพื่อใช้งานต่อเนื่อง
- ใช้ข้อมูลจากไฟล์ data-for-test-new-employee.xlsx

---

### 2. 🧹 ตรวจสอบและเตรียมข้อมูล (Pre-Data Processing)

ระบบจะแสดงข้อมูลพร้อมตรวจสอบความถูกต้อง:

#### 🔴 Missing Value

- แสดงด้วย **สีแดง**
- ตัวเลือก:
  - ❌ ลบทั้ง record
  - 🔄 แทนค่าด้วยข้อมูลสุ่มจาก column เดียวกัน
  - ✍️ กรอกข้อมูลด้วยตนเอง

#### 🟡 Null Value

- แสดงด้วย **สีเหลือง**
- ตัวเลือก:
  - 🟨 คงค่า null เดิมไว้
  - 🔄 แทนค่าด้วยข้อมูลสุ่มจาก column เดียวกัน
  - ✍️ กรอกข้อมูลด้วยตนเอง

#### 🔵 Duplicate Records

- แสดงด้วย **สีน้ำเงิน**
- ตัวเลือก:
  - ❌ ลบ record ที่ซ้ำ
  - 🔍 เปรียบเทียบแล้วเลือกเก็บ record ที่มีข้อมูลมากกว่า
    (เช่น A, B, C, D ดีกว่า A, B, D)

---

### 3. 🆔 การสร้าง RefCode อัตโนมัติ

หลังตรวจสอบข้อมูลจะมีการสร้างคอลัมน์ใหม่: `RefCode`

> รูปแบบ: `YYMMXXX` เช่น `2501010`

- `25` = ปี (พ.ศ.) จากคอลัมน์วันที่สร้าง
- `01` = เดือน
- `010` = ลำดับที่ในเดือนนั้น

---

### 4. 📊 การแสดงผลข้อมูลเป็นกราฟ

แสดงข้อมูลเป็นกราฟสรุปรายเดือน:

- จำนวน record ต่อเดือน
- รองรับการแยกประเภท (หากมี)

---

### 5. 📤 การส่งออกข้อมูล

ผู้ใช้สามารถดาวน์โหลดข้อมูลหลังประมวลผลในรูปแบบ:

- `.xls` (Excel)
- `.csv` (CSV)

---

## 📌 การส่งงาน

โปรด Fork และทำการ Pull Request เข้ามาที่ branch: demo

📁 ตัวอย่าง: `develop-jojo`

---

## 🙌 หมายเหตุ

- โฟกัสที่ความเข้าใจใน data flow และการจัดการ UI/UX
- โค้ดควรแยก component อย่างเป็นระบบ
- รองรับการใช้งานบน Desktop / Tablet / Mobile

---

> หากมีคำถามเพิ่มเติม สามารถติดต่อทีม Utotech ได้โดยตรง
