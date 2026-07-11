# Delete Empty Folders (ลบโฟลเดอร์ว่างเปล่า)

คำสั่ง PowerShell สำหรับการสแกนหาโฟลเดอร์ย่อยที่ว่างเปล่า (ไม่มีไฟล์หรือโฟลเดอร์อื่นอยู่ข้างในเลย) และทำการลบทิ้งโดยอัตโนมัติ เพื่อช่วยทำความสะอาดและจัดระเบียบไดรฟ์ของคุณ

## คำสั่ง PowerShell
เปลี่ยนที่อยู่โฟลเดอร์เป้าหมายในคำสั่งด้านล่าง จากนั้นนำไปวางใน PowerShell แล้วกด **Enter**:

```powershell
Get-ChildItem -Path "ใส่ที่อยู่โฟลเดอร์ที่นี่" -Recurse -Directory | Where-Object { (Get-ChildItem -Path $_.FullName -Force).Count -eq 0 } | Remove-Item -Force
```

---

## 🛠️ ตัวอย่างการใช้งาน

สมมติว่าต้องการลบโฟลเดอร์ว่างทั้งหมดในไดรฟ์ `D:\MyData` ให้เปลี่ยนเป็น:

```powershell
Get-ChildItem -Path "D:\MyData" -Recurse -Directory | Where-Object { (Get-ChildItem -Path $_.FullName -Force).Count -eq 0 } | Remove-Item -Force
```

> ⚠️ **คำแนะนำ:** ควรตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางโฟลเดอร์ (Path) ถูกต้องก่อนรันคำสั่ง เพื่อป้องกันการลบโฟลเดอร์ในตำแหน่งที่ไม่ต้องการ
