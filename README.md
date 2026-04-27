# Frontend-unit-testing01
Vitest + React

# React Unit Testing Workshop
โปรเจกต์นี้จัดทำขึ้นเพื่อสาธิตการเขียน Unit Testing บน React โดยใช้ Vitest และ React Testing Library เพื่อทดสอบการทำงานของ Component ต่างๆ ทั้งในส่วนของ Logic, การเรียก API และการตรวจสอบความถูกต้องของฟอร์ม

# โครงสร้างโปรเจกต์
text
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


# รายละเอียดการทดสอบ
1. Counter Component
ทดสอบการแสดงผลค่าเริ่มต้นของตัวนับ
ทดสอบการทำงานของปุ่มเพิ่มค่า (Increment) เมื่อมีการคลิก
ทดสอบการทำงานของปุ่มลดค่า (Decrement) เมื่อมีการคลิก

2. UserList Component
ทดสอบการดึงข้อมูลจาก API ผ่าน Axios เมื่อ Component ถูก Render
ทดสอบการนำข้อมูลที่ได้รับมาแสดงผลบนตารางอย่างถูกต้อง
ทดสอบระบบค้นหา (Search) โดยกรองข้อมูลตามชื่อหรืออีเมลจากข้อความที่พิมพ์ใน 

3. RegisterForm Component
ทดสอบความถูกต้องของข้อมูล (Validation):
ชื่อ: ต้องไม่เป็นค่าว่าง
อีเมล: ต้องถูกต้องตามรูปแบบ Email Format
เบอร์โทรศัพท์: ต้องเป็นตัวเลขครบ 10 หลัก
ทดสอบการส่งข้อมูล (Submit): ข้อมูลต้องถูกส่งไปยัง API เฉพาะเมื่อผ่านการตรวจสอบทั้งหมดแล้ว

# การติดตั้ง
สร้างโปรเจกต์และติดตั้ง Library พื้นฐาน:
bash
npm create vite@latest react-test-app -- --template react
cd react-test-app
npm install

# ติดตั้งเครื่องมือสำหรับการทดสอบ:
npm install --save-dev vitest @testing-library/react 
npx vitest --ui
npx vitest --coverage
@testing-library/jest-dom

# วิธีการใช้งาน
รันแอปพลิเคชัน
bash
npm run dev


# รันการทดสอบ (Unit Test)
bash
npx vitest
npx vitest --coverage
npx vitest --ui


