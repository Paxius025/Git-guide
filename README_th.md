# **🚀 คู่มือการใช้ Git สำหรับนักพัฒนา (Developer Guide)**

Git เป็นเครื่องมือสำคัญในการพัฒนา Software ไม่ว่าจะเป็นโปรเจคขนาดเล็กหรือขนาดใหญ่ 🛠️ การใช้งาน Git อย่างถูกต้องช่วยให้การทำงานเป็นทีมมีประสิทธิภาพ ลดปัญหาความขัดแย้งของโค้ด และสามารถย้อนกลับไปยังสถานะก่อนหน้าได้ง่าย 🏗️

[🇺🇸 English](README.md) | [🇹🇭 ภาษาไทย](README_th.md)

---

## **📌 พื้นฐานที่นักพัฒนาควรรู้**

### **1️⃣ ตั้งค่า Git เบื้องต้น**
ก่อนใช้งาน Git ควรตั้งค่าข้อมูลพื้นฐานของผู้ใช้งาน:

```sh
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

ตรวจสอบค่าที่ตั้งไว้:
```sh
git config --list
```

---

## **📑 ตัวอย่าง Commit ที่ดี**

### **✅ แนวทางเขียนข้อความ Commit ที่ดี**
- ใช้ **คำอธิบายที่ชัดเจน** และตรงประเด็น
- เริ่มต้นด้วยคำกริยาที่บอกถึงการกระทำ เช่น `Add`, `Fix`, `Update`
- ระบุปัญหาหรือฟีเจอร์ที่เกี่ยวข้อง เช่น `Fixes #42`

#### **💡 ตัวอย่างข้อความ Commit ที่ดี**
```sh
git commit -m "Fix: Fix login page loading issue (Fixes #42)"  # แก้ไขปัญหาการโหลดหน้าเข้าสู่ระบบ (แก้ไข #42)
git commit -m "Feat: Add Dark Mode to UI"  # เพิ่มโหมดมืดให้กับ UI
git commit -m "Docs: Update README with API usage instructions"  # อัปเดต README พร้อมวิธีใช้งาน API
git commit -m "Perf: Improve Dashboard loading performance"  # ปรับปรุงประสิทธิภาพการโหลดของแดชบอร์ด
git commit -m "Refactor: Restructure authentication system code"  # ปรับโครงสร้างโค้ดของระบบตรวจสอบสิทธิ์
```

---

## **🛠️ การแก้ปัญหาเบื้องต้นในการใช้ Git**

### **🗂️ 1. กู้คืนไฟล์ที่เผลอลบไป**
หากลบไฟล์โดยไม่ได้ตั้งใจและยังไม่ได้ Commit สามารถใช้คำสั่งนี้เพื่อกู้คืน:
```sh
git checkout -- filename
```

หากลบไปแล้วและ Commit ไปแล้ว ให้ใช้:
```sh
git revert HEAD -- filename
```

---

### **✏️ 2. แก้ไข Commit ล่าสุด**
หาก Commit ไปแล้วแต่ต้องการแก้ไขข้อความหรือเพิ่มไฟล์:
```sh
git commit --amend -m "Fix: Improve validateUser function code"  # ปรับปรุงโค้ดฟังก์ชัน validateUser
```

---

### **❌ 3. ยกเลิกการเปลี่ยนแปลงที่ยังไม่ได้ Commit**
หากต้องการย้อนกลับไปยังสถานะก่อนหน้า:
```sh
git reset --hard HEAD
```

หากต้องการเก็บการเปลี่ยนแปลงไว้ แต่ไม่ต้องการ Commit:
```sh
git reset --soft HEAD~1
```

---

### **⚠️ 4. แก้ปัญหา Merge Conflict**
หากเกิด Conflict ขณะ Merge ให้ทำตามขั้นตอนนี้:
1. เปิดไฟล์ที่มี Conflict และแก้ไขโค้ดให้ถูกต้อง
2. ใช้คำสั่งเพิ่มไฟล์ที่แก้ไขแล้ว
```sh
git add resolved-file.js
```
3. Commit การแก้ไข
```sh
git commit -m "Fix merge conflict in resolved-file.js"  # แก้ไขปัญหา Merge Conflict ใน resolved-file.js
```

---

### **⏪ 5. ย้อนกลับไปยังเวอร์ชันก่อนหน้า**
หากต้องการย้อนกลับไปยังเวอร์ชันก่อนหน้าแต่ยังเก็บการเปลี่ยนแปลงไว้:
```sh
git checkout commit-hash
```

หากต้องการย้อนกลับไปโดยลบการเปลี่ยนแปลง:
```sh
git reset --hard commit-hash
```

---

## **🔍 ทริคการใช้งาน Git ให้มีประสิทธิภาพ**

- **🛑 ใช้ .gitignore** เพื่อหลีกเลี่ยงการเพิ่มไฟล์ที่ไม่จำเป็น
- **⚡ ใช้ Git Alias** เพื่อย่อคำสั่ง Git เช่น:
  ```sh
  git config --global alias.co checkout
  git config --global alias.cm "commit -m"
  ```
- **📊 ใช้ Git Log แบบสั้น**
  ```sh
  git log --oneline --graph --decorate --all
  ```
- **🔄 ใช้ Hooks อัตโนมัติ** เช่น `pre-commit` เพื่อตรวจสอบโค้ดก่อน Commit

---

## **🎯 สรุป**
✅ **ตั้งค่า Git ให้พร้อมใช้งาน**
✅ **สร้างและจัดการ Branch อย่างถูกต้อง**
✅ **Commit และ Push โค้ดอย่างเป็นระบบ**
✅ **อัปเดตโค้ดจากต้นทางเพื่อหลีกเลี่ยง Conflict**
✅ **ใช้ Git Stash และ Rebase เพื่อให้ Workflow สะอาดขึ้น**
✅ **ตั้งค่า Alias และใช้ Git Hooks เพื่อลดข้อผิดพลาด**
✅ **แก้ปัญหาเบื้องต้น เช่น กู้คืนไฟล์ แก้ Conflict และ Reset โค้ดได้**

การใช้งาน Git อย่างถูกต้องช่วยให้โปรเจคพัฒนาได้อย่างราบรื่น และทำงานร่วมกับทีมได้มีประสิทธิภาพมากขึ้น! 🚀
