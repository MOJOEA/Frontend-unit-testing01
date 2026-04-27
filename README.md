# Frontend Unit Testing 01
Vitest + React

## React Unit Testing Workshop
โปรเจกต์นี้จัดทำขึ้นเพื่อสาธิตการเขียน Unit Testing บน React โดยใช้ Vitest และ React Testing Library เพื่อทดสอบการทำงานของ Component ต่างๆ ทั้งในส่วนของ Logic, การเรียก API และการตรวจสอบความถูกต้องของฟอร์ม

---

## โครงสร้างโปรเจกต์

```text
.
├── src
│   ├── components
│   │   ├── Counter.jsx            # ระบบนับตัวเลข
│   │   ├── Counter.test.jsx       # ทดสอบการเพิ่ม/ลดค่า
│   │   ├── RegisterForm.jsx       # ฟอร์มลงทะเบียนพร้อม Validation
│   │   ├── RegisterForm.test.jsx  # ทดสอบความถูกต้องของข้อมูลฟอร์ม
│   │   ├── UserList.jsx           # การดึงข้อมูลผู้ใช้และระบบค้นหา
│   │   └── UserList.test.jsx      # ทดสอบการ Fetch API และ Filter ข้อมูล
│   ├── App.jsx
│   └── main.jsx
├── test-setup.js                  # การตั้งค่าเริ่มต้นสำหรับสภาพแวดล้อมการทดสอบ
└── vite.config.js                 # การตั้งค่า Vite และ Vitest
```

---

## รายละเอียดการทดสอบ

### 1. Counter Component
* ทดสอบการแสดงผลค่าเริ่มต้นของตัวนับ (ผูกกับ React Hook)
* ทดสอบการทำงานของปุ่มเพิ่มค่า (Increment) เมื่อมีการคลิก
* ทดสอบการทำงานของปุ่มลดค่า (Decrement) เมื่อมีการคลิก

### 2. UserList Component
* ทดสอบการดึงข้อมูลจาก API ผ่าน Axios เมื่อ Component เริ่ม Render
* ทดสอบการนำข้อมูลมาแสดงผลบนตารางในทุกแถวของผู้ใช้
* ทดสอบระบบค้นหา (Search) จาก Input โดยกรองตามชื่อหรืออีเมล

### 3. RegisterForm Component
* **Validation Testing:**
    * ชื่อ (Name): ต้องมีการกรอกข้อมูล
    * อีเมล (Email): ต้องถูกต้องตามรูปแบบ (Format)
    * เบอร์โทรศัพท์ (Phone): ต้องเป็นตัวเลขครบ 10 หลัก
* **Submission Testing:** ข้อมูลต้องถูกส่งไปยัง API เฉพาะเมื่อผ่านการตรวจสอบทั้งหมดแล้ว

---

## การติดตั้ง

1. **สร้างโปรเจกต์และติดตั้ง Library พื้นฐาน:**
```bash
npm create vite@latest react-test-app -- --template react
cd react-test-app
npm install
```

2. **ติดตั้งเครื่องมือสำหรับการทดสอบ:**
```bash
npm install --save-dev vitest @testing-library/react @testing-library/jest-dom @vitest/ui @vitest/coverage-v8
```

---

## วิธีการใช้งาน

### รันแอปพลิเคชัน (Development)
```bash
npm run dev
```

### รันการทดสอบ (Testing)
* **รัน Test ปกติ:**
  ```bash
  npx vitest
  ```
* **รัน Test แบบ UI Mode (เปิดบน Browser):**
  ```bash
  npx vitest --ui
  ```
* **รัน Test พร้อมดู Coverage Report:**
  ```bash
  npx vitest --coverage
  ```
