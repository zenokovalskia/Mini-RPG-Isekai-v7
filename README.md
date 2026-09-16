# ⚔️ Mini RPG — Isekai v8.2

> **RPG petualangan berbasis browser** (HTML5 Canvas + Vanilla JavaScript) dengan sistem Isekai lengkap: 1000 monster, 5000 item, 60 class, dungeon, tower, crafting, gathering, bank, dan 7-tier currency.

![Version](https://img.shields.io/badge/version-8.2.0-blue?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)
![Platform](https://img.shields.io/badge/platform-Web%20%7C%20Mobile-orange?style=for-the-badge)
![Engine](https://img.shields.io/badge/engine-Vanilla%20JS%20%2B%20Canvas-yellow?style=for-the-badge)
![Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen?style=for-the-badge)
![Size](https://img.shields.io/badge/size-~250KB-blueviolet?style=for-the-badge)

---

## 📖 Daftar Isi

- [Deskripsi](#-deskripsi)
- [Fitur Utama](#-fitur-utama)
- [Cara Menjalankan](#-cara-menjalankan)
- [Cara Update ke GitHub](#-cara-update-ke-github)
- [Cara Buat APK](#-cara-buat-apk)
- [Kontrol](#-kontrol)
- [Panduan Bermain](#-panduan-bermain)
- [Sistem Game](#-sistem-game)
- [Database Game](#-database-game)
- [Struktur File](#-struktur-file)
- [Kustomisasi](#-kustomisasi)
- [Troubleshooting](#-troubleshooting)
- [FAQ](#-faq)
- [Lisensi](#-lisensi)

---

## 📖 Deskripsi

**Mini RPG — Isekai** adalah game RPG turn-based yang dapat dimainkan **langsung di browser** tanpa instalasi, tanpa server, dan tanpa dependency eksternal. Seluruh game terdiri dari **satu file HTML** (`index.html`) yang self-contained.

Pemain memulai sebagai petualang yang terlempar ke dunia Isekai, memilih **race** dan **class** secara permanen, lalu menjelajahi **37 lokasi** di **8 benua** untuk:

- ⚔️ Bertarung melawan **1000 monster** unik
- 🎒 Mengumpulkan **5000 item** berbeda
- 🔨 Menempa equipment, membuat potion, memasak makanan
- 🏰 Menantang **Dungeon** (finite) dan **Tower** (infinite)
- 🌳 Mengembangkan karakter melalui **60 class** dan **jalur evolusi**

**Genre:** Action RPG / JRPG-inspired / Isekai  
**Target Platform:** Desktop & Mobile Browser  
**Bahasa:** Indonesia  
**Storage:** localStorage (offline-ready)

---

## ✨ Fitur Utama

### 🌍 Dunia & Eksplorasi
- **37 lokasi** tersebar di **8 benua** besar (Asteria, Valthera, Kaiserheim, Dravern, Noctis, Elysion, Ancient, Worldroot)
- **15 biome** berbeda: forest, mountain, volcano, ice, desert, swamp, ruins, sky, aether, void
- **Peta dunia interaktif** dengan navigasi antar benua
- **Sistem siang-malam** — 1 siklus penuh = 2 jam real-time
- **Efek visual dinamis** — night overlay, sunset, sunrise tinting, ambient particles

### ⚔️ Sistem Combat
- **Turn-based battle** dengan UI bersih dan responsif
- **4 aksi utama**: Attack, Skill, Item, Flee
- **Sistem elemental** — fire, ice, holy, dark, poison, wind, earth, arcane, physical, void
- **Weakness & Resistance** — damage ×1.4 (weak) atau ×0.7 (resist)
- **Status effect** — poison (DoT), stun, freeze, buff ATK, buff dodge
- **Critical hit** — chance berdasarkan SPD, damage ×1.6
- **Dodge & accuracy** system
- **Enrage** mechanic untuk boss (ATK ×1.4 saat HP < 30%)
- **Regen** mechanic untuk boss tertentu

### 🎭 Karakter & Progression
- **7 Race** dengan bonus unik
- **20 Base Class** + **40 Evolusi Class** = **60 class total**
- **Jalur evolusi bercabang** — setiap base class bisa evo ke 2-3 class berbeda
- **7 Second Class** permanen
- **Stat allocation**: STR, VIT, AGI, INT, WIS (+3 poin per level)
- **Skill upgrade** tanpa batas level
- **Guild Rank** — E, D, C, B, A, S, SS, SSS, SSS+
- **Power Rank** — F, E, D, C, B, A, S, SS, SSS

### 💰 Sistem Ekonomi
- **7 Tier mata uang** — Bronze → Silver → Gold → Platinum → Mithril → Adamantite → Divine
- **Bank** — simpan uang aman dari death penalty
- **Merchant** — beli & jual item di setiap kota
- **8 preset jumlah** transfer bank
- **Auto-format currency** (tampil 3 tier tertinggi)

### 🔨 Gathering & Crafting
- **Menambang** 🪨 — dapat ore (Copper → Starmetal)
- **Menebang** 🌲 — dapat kayu (Oak → Worldtree)
- **Memetik** 🌸 — dapat herba
- **Respawn 30 detik** untuk semua tile
- **3 kategori crafting**:
  - **FORGE** — 800 resep weapon & armor
  - **ALCHEMY** — 400 resep potion
  - **COOK** — 200 resep makanan
- **NPC specialist**: Blacksmith 🔨, Alchemist ⚗️, Cook 🍳

### 🏰 Raid: Dungeon & Tower
- **Dungeon** — 5-15 lantai (skala level), boss di akhir, reward besar
- **Tower** — Infinite floors, tantangan tak terbatas
- **Monster TANPA scaling** — level asli dari database
- **Elite monster** setiap 5 lantai (⭐)
- **Boss dungeon** — HP ×3, ATK ×1.2, DEF ×1.3, EXP ×2.5
- **Record system** — hanya mencatat lantai TERTINGGI
- **Heal antar lantai** — 35% HP & MP

### 📊 Records & Stats
- **Total kills** — jumlah monster dibunuh
- **Dungeon Best** — floor tertinggi Dungeon
- **Tower Best** — floor tertinggi Tower
- **Deaths** — total kematian
- **Achievements** — reward untuk milestone tertentu
- **Guild Rank** — berdasarkan power

### 💾 Save System
- **localStorage** — save otomatis setiap event penting
- **Multi-akun** — setiap username punya save terpisah
- **Login / Register** — terpisah dengan validasi
- **Delete save** — untuk reset karakter

### 📱 Mobile-Friendly
- **On-screen D-Pad** — navigasi 4 arah
- **Action buttons** — A, B, Menu, Map, Status
- **Responsive layout** — adaptif untuk layar kecil
- **Touch-optimized** — no zoom, no tap highlight, no scroll
- **Safe-area support** — iPhone notch & Android cutout

---

## 🚀 Cara Menjalankan

### Metode 1: Langsung Buka (Paling Cepat)

1. Simpan file `index.html` di komputer
2. **Double-click** file tersebut
3. Game akan terbuka di browser default

> ⚠️ Beberapa browser memblokir `localStorage` pada `file://` protocol. Jika save tidak bekerja, gunakan Metode 2.

### Metode 2: Local Server (Direkomendasikan)

**Python 3:**
```bash
cd folder/berisi/index.html
python -m http.server 8000
# Buka http://localhost:8000
