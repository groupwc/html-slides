# components/

React components สำหรับใช้ใน slides และหน้าเว็บ  
Dependencies หลัก: `framer-motion`, `next/image`, `lucide-react`, `@/lib/utils`

---

## Sections — section เต็มหน้า

| ไฟล์ | Export | ใช้เมื่อ |
|------|--------|---------|
| `infinite-grid-hero.tsx` | `InfiniteGridHero` | Hero พื้นหลัง infinite grid เหมาะ tech/SaaS |
| `feature-section.tsx` | `FeatureSteps` | อธิบาย workflow แบบ step-by-step + auto-play รูป |
| `testimonials.tsx` | `Testimonials` | Social proof แบบ single column |
| `testimonials-columns.tsx` | `TestimonialsColumns` | Social proof แบบ multi-column หลายชิ้นพร้อมกัน |

---

## UI — ชิ้นส่วนนำไปวางซ้ำได้

| ไฟล์ | Export | ใช้เมื่อ |
|------|--------|---------|
| `spotlight-card.tsx` | `SpotlightCard` | Card มี spotlight ไล่ตาม cursor |
| `dock-two.tsx` | `DockTwo` | Navigation dock สไตล์ macOS |
| `image-comparison.tsx` | `ImageComparisonSlider` | Slider เปรียบเทียบ 2 รูป before/after |

---

## Motion — animation เป็นจุดเด่น

| ไฟล์ | Export | ใช้เมื่อ |
|------|--------|---------|
| `text-reveal.tsx` | `TextRevealByWord` | Scroll-driven fade in ทีละคำ (ต้องการ scroll room) |
| `hand-writing-text.tsx` | `HandWrittenTitle` | SVG วาดกรอบวงรีล้อมข้อความเหมือนขีดด้วยมือ |
| `hero-highlight.tsx` | `HeroHighlight`, `Highlight` | Dot pattern + gradient ไล่ตาม cursor, `Highlight` ใช้ครอบ text |

---

## Props สำคัญ

**FeatureSteps**
- `features` — `{ step, title?, content, image }[]`
- `autoPlayInterval?` — ms (default `3000`)

**ImageComparisonSlider**
- `leftImage`, `rightImage` — URL (required)
- `initialPosition?` — 0–100 (default `50`)

**HeroHighlight + Highlight**
```tsx
<HeroHighlight>
  <h1>สร้าง <Highlight>สิ่งดีๆ</Highlight> ด้วยกัน</h1>
</HeroHighlight>
```
