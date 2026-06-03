---
name: project-icon-system
description: Aturan visual language icon system Pinang — apa yang fixed, apa yang boleh diubah per icon
metadata:
  type: project
---

# Pinang Icon System — Rules

## Canvas

- Ukuran selalu: `width="150" height="130" viewBox="0 0 150 130"`
- Tidak boleh diubah — semua icon seragam

## Layer Structure (urutan dari bawah ke atas)

1. **Blur blobs** (background depth)
2. **Document base** (fixed — tidak boleh diubah)
3. **Overlay icon** (berubah per icon)
4. **Badge** (berubah per icon)

---

## Layer 1: Blur Blobs

**Selalu ada 2 blob:**

| Blob | Posisi | Warna | Aturan |
|------|--------|-------|--------|
| Kiri (primary) | bottom-left | accent color | Berubah per icon — harus match warna badge |
| Kanan (secondary) | top-right | `#8695A1` | SELALU sama, tidak boleh diubah |

**Parameter yang tidak boleh diubah:**
- Path shape blob kiri: `M85.0005 104.499 ... L85.0005 104.499Z`
- Path shape blob kanan: `M69 27.5002 ... L69 27.5002Z`
- `opacity="0.7"` pada wrapper group
- `feGaussianBlur stdDeviation="13.5"`
- Filter bounds (x, y, width, height)

---

## Layer 2: Document Base (FIXED — jangan diubah)

Komponen yang SELALU identik di semua icon:

- Rect dokumen: `x="45" y="28" width="61" height="73" rx="2"` — white fill, `#133F5D` stroke
- Avatar ellipse: `cx="58.1703" cy="42.7402" rx="6.23864" ry="6.31731"` — fill `#C9E4AA`
- Header lines (3 baris): y = 37.83, 42.04, 46.25 — stroke `#D1E5F4`
- Content block: `x="51.9316" y="67.3076" width="45.75" height="11.2308"` — fill `#D1E5F4`, stroke `#A4CCE9`
- Scatter lines: y=85.56, 57.48, 61.69, 74.33 — stroke `#D1E5F4`

---

## Layer 3: Overlay Icon

**Area penempatan:** x: 78–120, y: 55–108 (boleh sedikit keluar batas dokumen ke kanan/bawah)

**Style rules:**
- Stroke primary: `#133F5D`, stroke-width `1.5`
- Fill primary: `#D1E5F4` (light blue)
- Stroke secondary: `#A4CCE9`, stroke-width `1.2`
- `stroke-linecap="round"` dan `stroke-linejoin="round"` untuk semua path
- Tidak boleh pakai warna solid gelap sebagai fill utama (kecuali small accent)

---

## Layer 4: Badge

**Position: selalu sama** — `x="64" y="89" width="22" height="22" rx="11"`

**Aturan:**
- Bentuk selalu circle (rx = setengah width = 11)
- Fill = accent color (harus sama dengan blob kiri)
- Stroke selalu `#133F5D` + `stroke-miterlimit="10"`
- Simbol di dalam: stroke putih (`white`), stroke-width `2`, linecap+linejoin `round`

---

## Accent Colors per Kategori

| Kategori | Blob kiri | Badge fill | Contoh icon |
|----------|-----------|------------|-------------|
| Danger / Delete | `#E35273` | `#E35273` | delete-document |
| Success / Upload | `#5B8EE6` | `#4CAF82` | upload-document |
| Warning / Lock | `#F4A261` | `#F4A261` | lock-document |
| Info / Share | `#8B5CF6` | `#3B82F6` | share-document |

**Catatan:** Blob dan badge tidak harus warna identik — boleh tone sejenis (lihat upload: blob biru, badge hijau).

---

## Icon Catalog

| File | Overlay | Blob kiri | Badge |
|------|---------|-----------|-------|
| `icons/delete-document.svg` | Trash can | `#E35273` | `#E35273` ✕ |
| `icons/upload-document.svg` | Cloud upload | `#5B8EE6` | `#4CAF82` ✓ |
| `icons/lock-document.svg` | Padlock | `#F4A261` | `#F4A261` 🔒 |
| `icons/share-document.svg` | Share nodes | `#8B5CF6` | `#3B82F6` → |
