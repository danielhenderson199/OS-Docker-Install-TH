# ยินดีต้อนรับสู่ขั้นตอนการติดตั้ง Windows ผ่าน Docker
Docker เป็นแพลตฟอร์มที่ใช้สำหรับการพัฒนาและรันแอปพลิเคชันโดยใช้คอนเทนเนอร์ (Container) ซึ่งช่วยให้แอปพลิเคชันทำงานได้อย่างเสถียรในทุกสภาพแวดล้อม ไม่ว่าจะเป็นเครื่องของนักพัฒนา, เซิร์ฟเวอร์หรือบนคลาวด์ รวมถึงการใช้สภาพแวดล้อมในการทำงานเพื่อเรียกใช้ระบบปฏิบัติการ Windows ซึ่งในวิธีการใช้คำสั่งจะต้องเพิ่ม [Github Codespaces](https://github.com/codespaces) สามารถมีอย่างน้อยในหนึ่ง Repository ที่ต้องสร้าง แนะนำตั้งค่าประมาณ 4 Core RAM 16 GB - 32 GB

ขั้นตอนติดตั้งผ่านคำสั่ง
```js
sudo su
sudo apt update
sudo apt install -y docker.io docker-compose
mkdir cloudpc && cd cloudpc
wget -O windows.yml https://raw.githubusercontent.com/MCFirsting/Windows-Docker-Install-TH/main/windows.yml
sudo docker-compose -f windows.yml up
```
เมื่อทำงานจะเชื่อมต่อเซิร์ฟเวอร์ลิ้งค์ที่แสดงพอร์ตให้เราเข้าไป
ถ้าสังเกตว่ามีอยู่สองพอร์ตแนะนำไปที่ [พอร์ต 8006](http://localhost:8006) เพื่อดูระหว่างการติดตั้ง Windows

หากเข้าการใช้งานได้แต่ประสิทธิภาพไม่ลื่นบนมือถือ
แนะนำติดตั้งโปรแกรม Anydesk ได้ทั้งมือถือและคอม

สามารถเลือกเวอร์ชั่น [Windows](https://github.com/dockur/windows/?tab=readme-ov-file#how-do-i-select-the-windows-version) ตามต้องการระหว่างติดตั้งครั้งแรก

# ข้อเตือนสำคัญ
อย่าลืมหยุดงาน GitHub Codespaces ตลอดเพื่อไม่เกินจำนวนโควต้า
สามารถตรวจสอบ[โควต้า](https://github.com/settings/billing/summary)ได้ที่นี่

# การกลับมาใช้งานใหม่ในคำสั่ง
```js
cd cloudpc && sudo docker-compose -f windows.yml start
```
