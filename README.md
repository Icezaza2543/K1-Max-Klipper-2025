# K1-Max-Klipper-2025 🚀

ยินดีต้อนรับสู่โปรเจค **Creality K1 Max Klipper 2025** ซึ่งเป็นการรวบรวมไฟล์ Configuration สำหรับเครื่องปริ้นท์ 3D Creality K1 Max เพื่อการใช้งานที่เสถียรและมีประสิทธิภาพสูงสุด

โปรเจคนี้ถูกจัดระเบียบใหม่ (Refactored) เพื่อให้ง่ายต่อการอ่าน, การแก้ไข, และการนำไปใช้งาน

## 📂 โครงสร้างของโปรเจค (Directory Structure)

ไฟล์ Configuration ทั้งหมดถูกจัดเก็บในโฟลเดอร์ย่อยตามประเภทการทำงาน ดังนี้:

- `printer.cfg`: ไฟล์หลักสำหรับโหลด Config ทั้งหมด (ห้ามย้ายหรือเปลี่ยนชื่อ)
- `moonraker.conf`: ไฟล์ตั้งค่าสำหรับ Moonraker Server
- `core/`: ไฟล์ Config พื้นฐานของระบบ
  - `sensorless.cfg`: การตั้งค่า Sensorless Homing
  - `client.cfg`: ตั้งค่า Fluidd / Mainsail Client
  - `fan_control.cfg`: ควบคุมพัดลม
  - `guppyscreen.cfg`: หน้าจอ Guppyscreen
  - `webcam.conf`: การตั้งค่ากล้อง
- `macros/`: มาโคร G-code ต่างๆ 
  - `start_end.cfg`: มาโครสำหรับก่อนและหลังปริ้นท์ (START_PRINT / END_PRINT)
  - `useful_macros.cfg`: มาโครอรรถประโยชน์ต่างๆ (การเปลี่ยนเส้น, โหลดเส้น, WARMUP)
  - `quickstart.cfg`: มาโครสำหรับการเริ่มทำงานอย่างรวดเร็ว
  - `timelapse.cfg` / `.conf`: ระบบถ่าย Timelapse
- `cartographer/`: การตั้งค่า Cartographer 3D / CartoTouch
- `configs/`: ไฟล์ตั้งค่าเสริม (KAMP_Settings, notifier)

## 🛠️ สิ่งที่ได้รับการปรับปรุง (Improvements & Refactoring)

1. **Clean Architecture**: จัดกลุ่มไฟล์ `.cfg` ทั้งหมดลงในโฟลเดอร์ย่อย ทำให้ `printer.cfg` ดูสะอาดตาและจัดการได้ง่ายขึ้น
2. **Logic Enhancement**: 
   - ปรับปรุงและตรวจสอบ G-code macros เพื่อให้ทำงานได้อย่างไหลลื่น ไม่ซ้ำซ้อน
   - ลบโค้ดส่วนที่ไม่ได้ใช้งาน (Dead code) และทำความสะอาด syntax
3. **Better Sensorless Homing**: ใช้ Homing logic ที่เสถียรและปลอดภัยขึ้น (ตรวจเช็คและใช้เซฟโซนก่อนโฮม)

## 🚀 การติดตั้ง (Installation)

1. ทำการ Backup ไฟล์ `printer.cfg` ของเดิมไว้เสมอ
2. นำไฟล์ใน Repository นี้ทั้งหมดไปวางทับในโฟลเดอร์ `printer_data/config` ใน Klipper
3. รีสตาร์ท Firmware (Klipper Restart)
4. ตรวจสอบว่า `[include ...]` ใน `printer.cfg` โหลดไฟล์ต่างๆ ถูกต้อง

## ⚠️ ข้อควรระวัง
- โปรดตรวจสอบและ Calibrate `PID`, `Input Shaper`, และ `Z-Offset` ใหม่ทุกครั้งเมื่อนำ Config นี้ไปใช้งานกับเครื่องของคุณ
- ไฟล์ Config นี้ใช้งานสำหรับ **Creality K1 Max** เป็นหลัก การนำไปใช้กับรุ่นอื่นอาจทำให้เกิดความเสียหายได้

---
*จัดทำและพัฒนาสำหรับ K1 Max 2025 Edition*
