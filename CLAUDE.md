# Pinang Icons — Claude Context

Repo ini berisi SVG icon system untuk project Pinang.
Semua icon mengikuti visual language yang ketat — baca rules sebelum membuat atau memodifikasi icon.

@memory/MEMORY.md
@memory/project_icon_system.md
@memory/project_color_palette.md
@memory/feedback_tone.md

---

# Struktur Repo

```
pinang-icons/
├── icons/          — icon siap pakai (SVG final)
├── templates/      — base-template.svg (duplikat ini untuk icon baru)
├── docs/           — rules.md (referensi visual language)
└── memory/         — context untuk Claude
```

---

# Workflow: Buat Icon Baru

1. Duplikat `templates/base-template.svg`
2. Ganti `<!-- BLOB_LEFT_COLOR -->` dengan accent color yang sesuai
3. Tambah overlay icon di area kanan dokumen (x: 78–118, y: 55–105)
4. Ganti badge fill + simbol di badge
5. Simpan ke `icons/nama-icon.svg`
6. Update `docs/rules.md` → tambah entry ke icon catalog

---

# Commit Rules

| Siapa | Prefix |
|-------|--------|
| Claude Code CLI (Sepuh) | `sepuh:` |
| Manual | `feat:` / `fix:` / `chore:` |

---

# GitHub Account

Gunakan akun `damnn88` untuk project ini.
Switch: `gh auth switch --user damnn88`
