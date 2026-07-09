# backgrounds/

Background และ environment components — ใช้ Three.js / WebGL  
ต้องการ `@react-three/fiber` และ `three` เป็น dependency

---

## paper-shaders.tsx
Three.js shader components สำหรับ animated background  
**Export:** `ShaderPlane`, `EnergyRing`

### ShaderPlane
Plane mesh ที่ใช้ custom GLSL shader สร้าง animated noise pattern + glow  
**Props:**
- `position` — `[x, y, z]` ใน 3D space (required)
- `color1?` — สีหลัก hex (default: `"#ff5722"`)
- `color2?` — สีรอง hex (default: `"#ffffff"`)

**หมายเหตุ:** ต้องวางภายใน `<Canvas>` ของ `@react-three/fiber`

### EnergyRing
วงแหวน Three.js หมุนต่อเนื่อง opacity เต้นตามเวลา  
**Props:**
- `radius?` — ขนาดวงแหวน (default: `1`)
- `position?` — `[x, y, z]` (default: `[0, 0, 0]`)

**ตัวอย่าง:**
```tsx
import { Canvas } from "@react-three/fiber"
import { ShaderPlane, EnergyRing } from "@/backgrounds/paper-shaders"

<Canvas>
  <ShaderPlane position={[0, 0, 0]} color1="#ff5722" color2="#ffffff" />
  <EnergyRing radius={1.5} position={[0, 0, -1]} />
</Canvas>
```
