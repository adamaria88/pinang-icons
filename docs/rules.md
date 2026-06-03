# Pinang Icon System — Visual Rules

## TL;DR

Setiap icon terdiri dari 4 layer. Yang boleh diubah hanya layer 3 (overlay icon) dan layer 4 (badge). Layer 1–2 selalu identik — kecuali warna blob kiri.

---

## Canvas

`150 × 130px`, viewBox `0 0 150 130`. Tidak berubah.

---

## Layer 1: Blur Blobs

Dua blob organik di background yang bikin efek depth neumorphic.

- **Blob kiri** (bottom-left): warna accent sesuai kategori icon
- **Blob kanan** (top-right): selalu `#8695A1` abu-abu

Shape blob tidak boleh diubah. Filter blur selalu `stdDeviation="13.5"`. Opacity group wrapper selalu `0.7`.

---

## Layer 2: Document Base

Identik di semua icon. Tidak boleh diubah sama sekali.

Terdiri dari: rect dokumen putih, avatar ellipse hijau, 3 header lines, scatter lines, content block.

---

## Layer 3: Overlay Icon

Icon yang mendeskripsikan aksi/fungsi.

**Area:** x 78–120, y 55–108 (boleh sedikit keluar batas dokumen ke kanan/bawah untuk kesan tumpang tindih)

**Style wajib:**
- Stroke utama: `#133F5D`, stroke-width `1.5`
- Fill: `#D1E5F4` (light blue) — bukan solid gelap
- `stroke-linecap="round"` dan `stroke-linejoin="round"`

---

## Layer 4: Badge

Circle kecil di pojok kiri bawah dokumen. Posisi tidak berubah: `x="64" y="89" width="22" height="22" rx="11"`.

- Fill: accent color (biasanya sama atau sejenis dengan blob kiri)
- Stroke: `#133F5D`
- Simbol: stroke putih, stroke-width `2`

---

## Color System

| Token | Hex | Dipakai di |
|-------|-----|-----------|
| Navy (primary stroke) | `#133F5D` | Semua outline |
| Light blue (fill) | `#D1E5F4` | Placeholder, overlay fill |
| Blue stroke | `#A4CCE9` | Secondary stroke |
| Green (avatar) | `#C9E4AA` | Avatar ellipse dokumen |
| Gray (blob kanan) | `#8695A1` | Blob sekunder — fixed |

### Accent per kategori

| Kategori | Hex |
|----------|-----|
| Danger / Delete | `#E35273` |
| Success / Done | `#4CAF82` |
| Warning / Caution | `#F4A261` |
| Info / Navigate | `#3B82F6` |
| Share / Export | `#8B5CF6` |
| Upload / Cloud | `#5B8EE6` |

---

## Icon Catalog

| Nama file | Overlay | Blob kiri | Badge |
|-----------|---------|-----------|-------|
| `delete-document.svg` | Trash can | `#E35273` | `#E35273` ✕ |
| `upload-document.svg` | Cloud + arrow up | `#5B8EE6` | `#4CAF82` ✓ |
| `lock-document.svg` | Padlock | `#F4A261` | `#F4A261` 🔒 |
| `share-document.svg` | Share nodes | `#8B5CF6` | `#3B82F6` → |

---

## Cara Buat Icon Baru

1. Duplikat `templates/base-template.svg`
2. Ganti `ICON_ID` dengan nama unik (semua instance)
3. Ganti `BLOB_ACCENT_COLOR` dengan accent color
4. Ganti `BADGE_FILL_COLOR` dengan badge color
5. Tambah overlay icon di antara comment `<!-- OVERLAY ICON -->`
6. Tambah simbol badge (path putih) di dalam badge rect
7. Simpan ke `icons/nama-icon.svg`
8. Update tabel catalog di file ini
