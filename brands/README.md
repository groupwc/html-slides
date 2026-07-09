# brands/

CSS theme files — กำหนด CSS custom properties (variables) สำหรับแต่ละ brand/สไตล์  
นำไปใช้โดย import ใน global CSS หรือ link ใน `<head>`

---

## ไฟล์ทั้งหมด

| ไฟล์ | สไตล์ | โทนสี | Font |
|------|-------|-------|------|
| `catppuccin.css` | Pastel developer | ม่วง-ฟ้า บน cream | Montserrat + Fira Code |
| `elegant-luxury.css` | Luxury minimal | ทอง-ดำ คอนทราสต์สูง | Serif หรูหรา |
| `modern-minimal.css` | Clean SaaS | ขาว-เทา neutral | Sans-serif สะอาด |
| `sage-garden.css` | Nature organic | เขียว sage-เบจ | Serif อบอุ่น |
| `vercel.css` | Dark tech | ขาวบนดำ | Geist / mono |
| `vintage-paper.css` | Warm handcrafted | น้ำตาล-ครีม | Libre Baskerville + IBM Plex Mono |

---

## Variables ที่แต่ละไฟล์กำหนด

```
--background / --foreground   สีพื้นหลังและข้อความหลัก
--primary / --secondary       สีหลักและรอง
--accent                      สี accent
--muted                       สีหน่วงสำหรับ placeholder/disabled
--border / --input / --ring   สี UI elements
--card / --popover            สีพื้นหลัง card และ dropdown
--destructive                 สีแจ้งเตือนผิดพลาด
--radius                      ความโค้งมุม border-radius
--font-sans / --font-serif / --font-mono   font families
--sidebar-*                   สีสำหรับ sidebar
--chart-1..5                  สีสำหรับ data visualization
--shadow-*                    shadow color, blur, opacity
```

---

## วิธีใช้

```css
/* ใน global.css */
@import "@/brands/vintage-paper.css";
```

หรือเลือกตาม theme โดยใช้ class:
```css
.theme-vintage { @import "./vintage-paper.css"; }
```
