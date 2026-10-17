# เฉลาย/แนวคำตอบ Exercise 4 และคำถามท้ายแลป (เขียนใหม่ด้วยภาษาของตนเองก่อนส่ง)

## Exercise 4
Workflow เริ่มทำงานเมื่อมีการ push ไปยัง branch main (หรือกดรันเองผ่าน workflow_dispatch)
Job deploy จะ checkout โค้ด ตรวจว่ามี index.html ตั้งค่า Pages อัปโหลดไฟล์เว็บเป็น Artifact แล้ว deploy ขึ้น GitHub Pages

## คำถามท้ายแลป
1. GitHub Actions คือระบบรันงานอัตโนมัติจากเหตุการณ์ เช่น push ส่วน GitHub Pages คือบริการโฮสต์เว็บ Static ให้เข้าถึงผ่าน URL สาธารณะ Actions เป็นตัวนำเว็บไปวางบน Pages
2. เพราะ main คือโค้ดเวอร์ชันหลักที่พร้อมเผยแพร่ เมื่อ push เข้ามาจึง deploy อัตโนมัติ ทำให้เว็บตรงกับโค้ดล่าสุดเสมอ และไม่ deploy จาก branch ทดลอง
3. ไม่เปลี่ยน เพราะ Workflow ทำงานจากโค้ดบน GitHub เท่านั้น การแก้ในเครื่องที่ยังไม่ commit และ push GitHub จึงไม่รู้ว่ามีการเปลี่ยนแปลง
4. เพราะ GitHub Pages ให้บริการเฉพาะไฟล์ Static ไม่มี Server ที่รันโค้ด PHP หรือฐานข้อมูล MySQL ต้องแยกส่วนหน้าเว็บ หรือใช้ Hosting ที่รองรับ PHP
5. เปิดแท็บ Actions → เลือก run ที่ Failed → เปิด Job และ Step ที่เป็นสีแดง → อ่าน Log หาข้อความ error → ตรวจสาเหตุ เช่น YAML เยื้องผิด, permissions, ตั้งค่า Pages ไม่ใช่ GitHub Actions, ไม่มี index.html → แก้ไข แล้ว commit/push ใหม่
