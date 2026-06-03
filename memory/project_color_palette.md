---
name: project-color-palette
description: Token warna lengkap Pinang icon system — stroke, fill, blob, badge
metadata:
  type: project
---

# Color Palette — Pinang Icons

## Core Tokens (tidak boleh diubah)

| Token | Hex | Dipakai di |
|-------|-----|-----------|
| `--stroke-primary` | `#133F5D` | Navy — semua outline utama, stroke dokumen, badge stroke |
| `--fill-placeholder` | `#D1E5F4` | Light blue — fill placeholder lines, content block, overlay icon fill |
| `--stroke-secondary` | `#A4CCE9` | Blue — secondary stroke (content block border, overlay accent) |
| `--fill-avatar` | `#C9E4AA` | Green — avatar ellipse di dokumen |
| `--blob-secondary` | `#8695A1` | Gray — blob kanan (selalu sama di semua icon) |

## Badge & Blob Accent Colors

| Nama | Hex | Kategori |
|------|-----|----------|
| `--accent-danger` | `#E35273` | Delete, error, destructive |
| `--accent-upload-blob` | `#5B8EE6` | Upload blob (biru medium) |
| `--accent-success` | `#4CAF82` | Success, done, complete |
| `--accent-warning` | `#F4A261` | Warning, lock, caution |
| `--accent-share` | `#8B5CF6` | Share, export, send (purple) |
| `--accent-info` | `#3B82F6` | Info, link, navigate (blue) |

## Icon Fill Backgrounds

| Token | Hex | Dipakai di |
|-------|-----|-----------|
| `--doc-fill` | `#FFFFFF` | Document background |
| `--cloud-fill` | `#EEF5FB` | Cloud shape fill (upload icon) |

## Aturan Penggunaan

1. **Blob kiri** = accent warna sesuai kategori icon
2. **Blob kanan** = selalu `#8695A1` (tidak berubah)
3. **Badge fill** = accent warna (boleh beda tone dengan blob, asal satu keluarga)
4. **Stroke semua elemen** = `#133F5D` navy (tidak ada stroke warna lain kecuali untuk internal detail)
5. **Fill overlay icon** = `#D1E5F4` (bukan solid dark)
