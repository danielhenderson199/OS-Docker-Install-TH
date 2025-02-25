# ยินดีต้อนรับสู่ขั้นตอนการติดตั้ง Windows ผ่าน Docker
Docker เป็นแพลตฟอร์มที่ใช้สำหรับการพัฒนาและรันแอปพลิเคชันโดยใช้คอนเทนเนอร์ (Container) ซึ่งช่วยให้แอปพลิเคชันทำงานได้อย่างเสถียรในทุกสภาพแวดล้อม ไม่ว่าจะเป็นเครื่องของนักพัฒนา, เซิร์ฟเวอร์หรือบนคลาวด์ รวมถึงการใช้สภาพแวดล้อมในการทำงานเพื่อเรียกใช้ระบบปฏิบัติการ Windows ซึ่งในวิธีการใช้คำสั่งจะต้องเพิ่ม [Github Codespaces](https://github.com/codespaces) สามารถมีอย่างน้อยในหนึ่ง Repository ที่ต้องสร้าง แนะนำตั้งค่าประมาณ 4 Core RAM 16 GB - 32 GB

ขั้นตอนติดตั้งผ่านคำสั่ง
```js
sudo apt update sudo apt install docker.io docker-compose mkdir cloudpc && cd cloudpc wget -O windows.yml https://raw.githubusercontent.com/MCFirsting/Windows-Docker-Install-TH/main/windows.yml sudo docker-compose -f windows.yml up
```
เมื่อทำงานจะเชื่อมต่อเซิร์ฟเวอร์ลิ้งค์
ที่แสดงพอร์ตให้เราเข้าไป เมื่อเข้าใช้งานได้
ห้ามย้อนกลับจนกว่าเซิร์ฟเวอร์จะหยุด
การเชื่อมต่ออาจเป็นผลเฉพาะบางเครื่อง
หากถูกตัดการเชื่อมต่อระหว่าง Setup
ให้กลับมาตรวจสอบใน Terminal

ใช้คำสั่งเพื่อเริ่มทำงานอีกครั้ง
```js
sudo docker-compose -f windows.yml start
```
หากเข้าการใช้งานได้แต่ประสิทธิภาพไม่ลื่น
แนะนำติดตั้งโปรแกรม Anydesk ทางมือถือและคอม
สามารถเลือกเวอร์ชั่น [Windows](https://github.com/dockur/windows/?tab=readme-ov-file#how-do-i-select-the-windows-version) ตามต้องการ

# ข้อเตือนสำคัญ
หากทำการปิดการเชื่อมต่อจาก Codespaces โดยไม่ได้ปิด Windows หรือการ Shut Down โดยตรง ส่งผลให้คอนเทนเนอร์เสียหาย จำเป็นต้อง Rebuild ใหม่ (ข้อมูลหาย) ถ้าปิดภายใน Windows ถูกวิธีเพื่อให้คอนเทนเนอร์ทำงานเสร็จสิ้น ที่สำคัญอย่าลืมหยุดงาน GitHub Codespaces ตลอด เพื่อไม่เกินจำนวนโควต้า สามารถตรวจสอบ[โควต้า](https://github.com/settings/billing/summary)ได้ที่นี่

การกลับมาใช้งานใหม่ให้พิมพ์คำสั่ง
```js
cd cloudpc sudo docker-compose -f windows.yml start
```
