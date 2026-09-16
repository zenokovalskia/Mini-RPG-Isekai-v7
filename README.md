# ⚔️ Mini RPG — Isekai v7

> **RPG petualangan berbasis browser (HTML5 Canvas + JavaScript)** dengan sistem Isekai lengkap: crafting, gathering, dungeon, tower, auto-battle, bank, dan 7-tier currency.

![Version](https://img.shields.io/badge/version-7.0.0-blue?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)
![Platform](https://img.shields.io/badge/platform-Web%20%7C%20Mobile-orange?style=for-the-badge)
![Engine](https://img.shields.io/badge/engine-Vanilla%20JS%20%2B%20Canvas-yellow?style=for-the-badge)
![Size](https://img.shields.io/badge/size-%3C%20250KB-purple?style=for-the-badge)
![Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen?style=for-the-badge)

---

## 📑 Daftar Isi

- [Tentang Game](#-tentang-game)
- [Fitur Unggulan](#-fitur-unggulan)
- [Persyaratan Sistem](#-persyaratan-sistem)
- [Instalasi & Menjalankan](#-instalasi--menjalankan)
- [Kontrol](#-kontrol)
- [Panduan Bermain](#-panduan-bermain)
- [Sistem Game](#-sistem-game)
- [Database Game](#-database-game)
- [Progression Guide](#-progression-guide)
- [Build & Class Guide](#-build--class-guide)
- [Crafting Recipes](#-crafting-recipes)
- [Raid Strategy](#-raid-strategy)
- [Auto-Battle](#-auto-battle)
- [Save System](#-save-system)
- [Struktur File](#-struktur-file)
- [Arsitektur Kode](#-arsitektur-kode)
- [Kustomisasi & Modding](#-kustomisasi--modding)
- [Troubleshooting](#-troubleshooting)
- [FAQ](#-faq)
- [Kompatibilitas](#-kompatibilitas)
- [Changelog](#-changelog)
- [Roadmap](#-roadmap)
- [Kontribusi](#-kontribusi)
- [Lisensi](#-lisensi)
- [Kredit](#-kredit)

---

## 🎮 Tentang Game

**Mini RPG — Isekai** adalah game RPG turn-based yang dapat dimainkan **langsung di browser** tanpa instalasi. Pemain terlempar ke dunia Isekai dan memulai perjalanan sebagai petualang dengan **race** dan **class** yang dipilih secara permanen.

Dunia ini memiliki **8 benua**, **37 lokasi**, **1000 monster unik**, dan **5000 item** — semuanya di-generate secara prosedural untuk pengalaman yang kaya tanpa file aset eksternal.

### Filosofi Desain
- ✅ **Zero-dependency** — 1 file HTML, tanpa library
- ✅ **Mobile-first** — Kontrol touch-friendly dengan D-Pad virtual
- ✅ **Offline-ready** — Semua gameplay offline via localStorage
- ✅ **Procedural** — Monster & item digenerate, bukan hardcoded
- ✅ **Fair progression** — Record-based, no infinite scaling exploit

---

## ✨ Fitur Unggulan

### 🌍 Eksplorasi Dunia

| Fitur | Detail |
|-------|--------|
| **8 Benua** | Asteria, Valthera, Kaiserheim, Dravern, Noctis, Elysion, Ancient, Worldroot |
| **37 Lokasi** | City, Village, Wild, Boss area |
| **15 Biome** | Forest, Mountain, Volcano, Ice, Desert, Swamp, Coast, Ruins, Shadow, Sky, Aether, Void |
| **Day/Night Cycle** | 1 siklus penuh = 2 jam real-time |
| **World Map** | Peta interaktif dengan continent switch |
| **Weather Effects** | Night overlay, sunset/sunrise tinting |

### ⚔️ Combat System

| Fitur | Detail |
|-------|--------|
| **Turn-based Battle** | Attack / Skill / Item / Flee |
| **Auto-Battle** | Farming otomatis dengan AI heuristik |
| **Elemental System** | Fire, Ice, Holy, Dark, Poison, Wind, Earth, Arcane, Void |
| **Status Effects** | Poison, Stun, Freeze, Buff, Dodge |
| **Critical & Dodge** | Stat-based accuracy & evasion |
| **Enrage Mechanic** | Boss jadi lebih kuat saat HP < 30% |
| **Regeneration** | Beberapa monster regen HP per turn |

### 🎭 Karakter & Class

| Fitur | Jumlah |
|-------|--------|
| **Races** | 7 (Human, Nekomata, Elf, Dwarf, Draconid, Fairy, Beastkin) |
| **Base Classes** | 20 |
| **Evolution Classes** | 40 |
| **Second Classes** | 7 |
| **Skills** | 9 template, upgrade tanpa batas |
| **Stat Points** | STR, VIT, AGI, INT, WIS |

### 💰 Ekonomi
- **7 Tier Currency**: Bronze → Divine
- **Bank System**: Simpan uang aman dari death penalty
- **Merchant**: Beli & jual di setiap kota
- **Crafting**: Forge, Alchemy, Cook
- **Gathering**: Menambang, menebang, memetik

### 🏰 Endgame Content
- **Dungeon**: 5-15 lantai, boss di akhir
- **Tower**: Infinite floors
- **Record System**: Best floor tracking
- **Elite & Boss**: Variasi difficulty

---

## 💻 Persyaratan Sistem

### Minimum

| Komponen | Requirement |
|----------|-------------|
| **OS** | Windows 7+, macOS 10.12+, Linux, Android 5+, iOS 10+ |
| **Browser** | Chrome 61+, Firefox 60+, Safari 11+, Edge 79+ |
| **RAM** | 512 MB |
| **Storage** | 5 MB (termasuk cache browser) |
| **Display** | 480×360 minimum |
| **Input** | Keyboard/Mouse atau Touch screen |

### Recommended

| Komponen | Requirement |
|----------|-------------|
| **Browser** | Chrome 100+, Firefox 100+, Safari 15+ |
| **RAM** | 1 GB+ |
| **Display** | 720p+ |
| **Audio** | Speaker/Headphone |

### Tidak Didukung
- ❌ Internet Explorer (semua versi)
- ❌ Browser tanpa ES6 Modules support
- ❌ Browser tanpa Canvas 2D context

---

## 🚀 Instalasi & Menjalankan

### 📦 Metode 1: Buka Langsung (Paling Mudah)

1. **Download** file `index.html`
2. **Double-click** file tersebut
3. Game langsung terbuka di browser default

> ⚠️ **Catatan**: Beberapa browser memblokir `localStorage` pada `file://` protocol. Jika save tidak bekerja, gunakan Metode 2.

### 🌐 Metode 2: Local Server (Direkomendasikan)

**Python 3:**
```bash
cd /path/to/mini-rpg
python -m http.server 8000
# Buka: http://localhost:8000
