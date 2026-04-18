# SVRMed ERP

ระบบ ERP สำหรับภายในบริษัท SVRMed — บริษัทจำหน่ายอุปกรณ์การแพทย์

## โครงสร้างโปรเจค

```
SVRMed-ERP/
├── index.html          หน้า Dashboard หลัก
├── vendors.html        จัดการผู้จำหน่าย (Vendor)
├── products.html       จัดการสินค้า (Product)       [กำลังพัฒนา]
├── customers.html      จัดการลูกค้า (Customer)      [กำลังพัฒนา]
├── quotations.html     ใบเสนอราคา (Quotation)       [กำลังพัฒนา]
├── orders.html         ออเดอร์ (Order)               [กำลังพัฒนา]
├── stock.html          สต็อกสินค้า (Stock)           [กำลังพัฒนา]
├── invoices.html       ใบแจ้งหนี้ (Invoice)          [กำลังพัฒนา]
└── README.md
```

## ฐานข้อมูล

ใช้ **Google Sheets** เป็นฐานข้อมูลหลัก ชื่อไฟล์: `SVRMed ERP`

| Sheet | ข้อมูล |
|-------|--------|
| Venders | ข้อมูลผู้จำหน่าย |
| Products | ข้อมูลสินค้า |
| Customers | ข้อมูลลูกค้า |
| Config | ค่า Dropdown ทั้งหมด |
| Database | ข้อมูลอ้างอิง |

## Apps Script

URL: เก็บไว้ใน Google Apps Script ของไฟล์ SVRMed ERP

Actions ที่รองรับ:
- `?action=get&sheet=Venders` — ดึงข้อมูล
- `?action=add&sheet=Venders&data={}` — เพิ่มข้อมูล
- `?action=update&sheet=Venders&keyCol=...&keyVal=...&data={}` — แก้ไข
- `?action=delete&sheet=Venders&keyCol=...&keyVal=...` — ลบ
- `?action=getConfig` — ดึงค่า Dropdown จาก Config Sheet
- `?action=initDropdowns&sheet=Venders` — อัปเดต Dropdown ใน Sheet

## การเพิ่มค่า Dropdown

1. เปิด Google Sheet `SVRMed ERP` → Sheet `Config`
2. พิมพ์เพิ่มต่อท้ายกลุ่มที่ต้องการ (คอลัมน์ A = กลุ่ม, B = ค่า)
3. รัน URL: `...exec?action=initDropdowns&sheet=Venders`

## สถานะการพัฒนา

| Module | สถานะ |
|--------|-------|
| Vendor Management | ✅ เสร็จแล้ว |
| Product Management | 🔄 กำลังพัฒนา |
| Customer Management | 🔄 กำลังพัฒนา |
| ใบเสนอราคา | ⏳ รอพัฒนา |
| ออเดอร์ | ⏳ รอพัฒนา |
| สต็อก | ⏳ รอพัฒนา |
| ใบแจ้งหนี้ | ⏳ รอพัฒนา |

## เทคโนโลยีที่ใช้

- **Frontend**: HTML, CSS, JavaScript (Vanilla)
- **Database**: Google Sheets
- **Backend**: Google Apps Script
- **Hosting**: GitHub Pages
