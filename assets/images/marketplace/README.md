🖼️ Marketplace Images — Inventory & Maintenance Guide
 
Path:  assets/images/marketplace/  • Status: ✅ Complete Inventory
 
 
 
📂 สารบัญไฟล์ทั้งหมด (13 รายการ)
 
# ชื่อไฟล์ วัตถุประสงค์ สถานะ 
1  apps-with-unverified-publisher-badge-tooltip.png  ป้ายผู้เผยแพร่ ยังไม่ได้รับการยืนยัน + คำอธิบายเมื่อชี้เมาส์ ✅ มี 
2  apps-with-verified-publisher-badge-tooltip.png  ป้ายผู้เผยแพร่ ได้รับการยืนยัน + คำอธิบายเมื่อชี้เมาส์ ✅ มี 
3  edit-marketplace-listing-overview.png  หน้าจอแก้ไขรายละเอียดประกาศใน Marketplace ✅ มี 
4  marketplace-feature-card.png  การ์ดแสดงคุณสมบัติเด่นของแอป ✅ มี 
5  marketplace-insights.png  แดชบอร์ดสถิติ/ข้อมูลเชิงลึกสำหรับผู้เผยแพร่ ✅ มี 
6  marketplace-intro-description.png  ส่วนคำอธิบายเบื้องต้นในหน้าแรก ✅ มี 
7  marketplace-listing-overview.png  ภาพรวมหน้าประกาศแอป/โปรดักต์ ✅ มี 
8  marketplace-logo-and-badge.png  โลโก้ + ป้ายสถานะผู้เผยแพร่ ✅ มี 
9  marketplace-screenshots.png  พื้นที่แสดงภาพหน้าจอของแอป ✅ มี 
10  marketplace-short-description.png  ช่องคำอธิบายสั้นสำหรับรายการค้นหา ✅ มี 
11  marketplace-transactions.png  ประวัติการทำธุรกรรม/รายได้ ✅ มี 
12  marketplace-webhook-deliveries.png  สถานะการส่ง Webhook ไปยังแอป ✅ มี 
13  verified-creator-badge-for-actions.png  ป้ายผู้สร้างที่ได้รับการยืนยัน (เฉพาะ GitHub Actions) ✅ มี 
 
 
 
✅ การตรวจสอบคุณภาพ
 
📏 มาตรฐานปัจจุบัน
 
- ✅ บีบอัดด้วย Zopfli — ขนาดเล็ก เร็วโหลด
- ✅ ชื่อไฟล์อ่านง่าย — บอกชัดเจนว่าภาพอะไร
- ✅ ทุกไฟล์เป็น  .png  — รองรับทุกเบราว์เซอร์
- ✅ ไม่มีไฟล์ซ้ำ/เสียหาย
 
⚠️ ข้อสังเกต
 
- ไฟล์เก่าสุด ( marketplace-screenshots.png ) — อัปเดตล่าสุดปี 2020 อาจล้าสมัย
- ควรตรวจสอบว่าทุกภาพยังตรงกับหน้าจอปัจจุบันของ GitHub
 
 
 
📝 คู่มือการบำรุงรักษา
 
🔧 เมื่อต้องอัปเดตภาพ
 
bash  
# 1. บีบอัดก่อนนำเข้า (ใช้ Zopfli ตามมาตรฐานเดิม)
zopflipng -m input.png output.png

# 2. ตรวจสอบชื่อให้ตรงรูปแบบ:
# marketplace-[ส่วน]-[รายละเอียด].png
# ตัวอย่าง: marketplace-new-feature-card.png

# 3. อัปโหลดและบันทึก
git add assets/images/marketplace/
git commit -m "update: refresh marketplace screenshots — [ชื่อหน้าจอ]"
git push origin main
 
 
📐 หลักการตั้งชื่อไฟล์
 
รูปแบบ ตัวอย่าง 
 marketplace-[หน้า]-[ส่วน].png   marketplace-listing-pricing.png  
 *-badge-tooltip.png   actions-badge-tooltip.png  
 verified-*-badge.png   verified-partner-badge.png  
 
♿ การเข้าถึง (Accessibility)
 
- ทุกภาพต้องมี คำอธิบายภาพ (Alt Text) ในเอกสารที่อ้างอิง
- ขนาดภาพเหมาะสม — ไม่กว้างเกินหน้าจอ
- ความคมชัดพอเหมาะ — ไม่เบลอบนหน้าจอความละเอียดสูง
 
 
 
📄 สร้างดัชนีอัตโนมัติ (README.md)
 
บันทึกเป็น  assets/images/marketplace/README.md  เพื่อให้ทีมดูแลรักษาง่ายขึ้น:
 
markdown  
# 🖼️ Marketplace Images — สารบัญ

โฟลเดอร์นี้เก็บภาพประกอบสำหรับเอกสารเกี่ยวกับ GitHub Marketplace

## รายการภาพ
| ไฟล์ | คำอธิบาย |
|---|---|
| `apps-with-unverified-publisher-badge-tooltip.png` | ป้ายผู้เผยแพร่ยังไม่ได้รับการยืนยัน |
| `apps-with-verified-publisher-badge-tooltip.png` | ป้ายผู้เผยแพร่ที่ได้รับการยืนยัน |
| `edit-marketplace-listing-overview.png` | หน้าจอแก้ไขรายละเอียดประกาศ |
| `marketplace-feature-card.png` | การ์ดคุณสมบัติเด่นแอป |
| `marketplace-insights.png` | แดชบอร์ดข้อมูลเชิงลึก |
| `marketplace-intro-description.png` | ส่วนคำอธิบายเบื้องต้น |
| `marketplace-listing-overview.png` | ภาพรวมหน้าประกาศแอป |
| `marketplace-logo-and-badge.png` | โลโก้ + ป้ายสถานะ |
| `marketplace-screenshots.png` | พื้นที่แสดงภาพหน้าจอแอป |
| `marketplace-short-description.png` | ช่องคำอธิบายสั้น |
| `marketplace-transactions.png` | ประวัติธุรกรรมและรายได้ |
| `marketplace-webhook-deliveries.png` | สถานะการส่ง Webhook |
| `verified-creator-badge-for-actions.png` | ป้ายผู้สร้างที่ได้รับการยืนยัน (Actions) |

## มาตรฐาน
- รูปแบบ: **PNG**
- บีบอัดด้วย: **Zopfli**
- ชื่อไฟล์: อธิบายชัดเจน สื่อความหมาย
- ปรับปรุงเมื่อ: หน้าจอ GitHub มีการเปลี่ยนแปลง

---
*อัปเดตล่าสุด: 25 กันยายน 2026*
 
 
 
 
🚀 คำสั่งดำเนินการ
 
bash  
# สร้างสารบัญ
cat > assets/images/marketplace/README.md << 'EOF'
[เนื้อหาด้านบน]
EOF

git add assets/images/marketplace/README.md
git commit -m "docs: add inventory README for marketplace images folder"
git push origin main