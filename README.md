# README — Map of Content
# html-slides

> คลังทรัพยากรสำหรับสร้าง HTML Presentation (สไลด์ที่รันในเบราว์เซอร์ ไม่มี dependency)
> ใช้ plugin/skill **frontend-slides** เป็นตัวสร้างไฟล์จริง โดยรับ Blueprint จากโปรเจกต์ [slide-architect](../slide-architect/)

## Flow ภาพรวม (ทำงานคู่กับ slide-architect)

```
../slide-architect/  ──▶  storyboarder ร่าง Blueprint (.md)
                                │
                                ▼
                    sources/<ชื่อ>-blueprint-<วันที่>.md
                                │
                                ▼
                    /frontend-slides อ่าน Blueprint
                    เลือก Brand/Component/Background ตามที่ระบุ
                                │
                                ▼
                    output/ → ไฟล์ HTML Presentation พร้อมเปิดดูจริง
```

> โปรเจกต์นี้**ไม่มี agent ของตัวเอง** — ใช้ `frontend-slides` skill/plugin (ติดตั้งเป็น marketplace plugin ของ Claude Code) อ่านทรัพยากรในโฟลเดอร์นี้โดยตรง

## ทรัพยากรที่มีให้ใช้

| โฟลเดอร์ | มีอะไร | อ่านรายละเอียดที่ |
|---|---|---|
| `brands/` | Brand CSS Theme 6 แบบ (สี, ฟอนต์, CSS Variables) | `brands/README.md` |
| `components/` | React component พร้อมใช้ 10 ไฟล์ (section, UI, motion) | `components/README.md` |
| `backgrounds/` | Three.js/WebGL shader background 1 แบบ (`paper-shaders.tsx`) | `backgrounds/README.md` |
| `frontend-slides/` | ตัว plugin/skill หลัก — มี Style Preset 12 แบบ (`STYLE_PRESETS.md`), Bold Template 34 แบบ (`bold-template-pack/`), กฎ animation (`animation-patterns.md`) | `frontend-slides/README.md`, `frontend-slides/SKILL.md` |
| `sources/` | ไฟล์ Blueprint (.md) ที่รอแปลงเป็นสไลด์ — รับมาจาก `slide-architect` | — |
| `output/` | ไฟล์ HTML Presentation ที่สร้างเสร็จแล้ว | — |

## หลักการออกแบบของ frontend-slides (สรุปจาก `frontend-slides/SKILL.md`)

- **Zero Dependencies** — ไฟล์ HTML เดี่ยว inline CSS/JS ทั้งหมด ไม่ต้องใช้ npm หรือ build tool
- **Fixed Stage 16:9** — ทุกสไลด์ขนาด 1920×1080 คงที่ ไม่ reflow ตามหน้าจอ ไม่มี scroll
- **ห้าม "AI Slop"** — ห้ามใช้ฟอนต์ทั่วไป (Inter, Roboto, Arial), ห้ามใช้สี generic (เช่น purple gradient on white)
- **Progressive Disclosure** — เลือก Brand ก่อนเสมอ แล้วเสริมด้วย Style Preset หรือ Bold Template เมื่อจำเป็น

## ไฟล์ที่เกี่ยวข้อง

| ไฟล์/Folder | ความหมาย |
|---|---|
| `../slide-architect/` | โปรเจกต์ต้นทางที่สร้าง Blueprint ส่งมาให้ที่นี่ |
| `../.claude/agents/storyboarder.md` | agent ที่สร้าง Blueprint (อยู่ที่ root ของ agentic-ai) |
| `frontend-slides/plugins/` | ตัว plugin ที่ลงทะเบียนกับ Claude Code marketplace |
| `.git` | repo แยกของตัวเอง — `github.com/groupwc/html-slides` (ไม่ใช่ submodule ของ `agentic-ai`) |

## หมายเหตุ

- Repo นี้ใช้ร่วมกันทั้งเครื่อง Mac และ Windows (sync ผ่าน OneDrive บนฝั่ง Windows) — push/pull แยกจาก repo หลัก `agentic-ai`
- ถ้าจะเรียกสร้างสไลด์ ให้เปิดใช้ skill `/frontend-slides` แล้วชี้ไปที่ไฟล์ Blueprint ใน `sources/`
