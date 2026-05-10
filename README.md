# 📐 DVSwitch Dashboard Responsive Layout Overlay

<p align="center">
  <img src="https://img.shields.io/badge/DVSwitch-Responsive%20Layout-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Version-v0.5--test-brightgreen?style=for-the-badge">
  <img src="https://img.shields.io/badge/Debian%2013-Trixie-red?style=for-the-badge&logo=debian">
  <img src="https://img.shields.io/badge/ASL3-Compatible-success?style=for-the-badge">
</p>

---

## 📌 Overview

The **DVSwitch Dashboard Responsive Layout Overlay** modernizes the stock DVSwitch Dashboard layout for modern browsers and larger displays while preserving original dashboard functionality and upstream behavior.

This project focuses on:

```text
Safe responsive layout improvements
Minimal dashboard modification
Production-safe rollback support
Preserving original DVSwitch behavior
```

The goal is to improve dashboard usability and readability without rewriting the original DVSwitch dashboard.

---

## 📥 Installation

```bash
git clone https://github.com/ke2hni/DVSwitch-Responsive-Layout.git
cd DVSwitch-Responsive-Layout
chmod +x dvswitch-responsive-layout.sh
sudo ./dvswitch-responsive-layout.sh
```

---

## 🎨 Responsive Layout Features

### 📏 Modern Container Scaling

The stock dashboard uses fixed-width layout sizing.

This overlay safely modernizes layout scaling for:

* widescreen displays
* modern browsers
* larger monitors
* tablets
* responsive resizing

without changing core dashboard logic.

---

### 🧩 Responsive Dashboard Sections

Improves scaling behavior for:

* Main dashboard container
* Gateway Activity
* Local Activity
* Hardware Info section

while preserving original dashboard appearance.

---

### 📝 Improved Table Wrapping

Safely changes:

```text
white-space: nowrap;
```

to:

```text
white-space: normal;
```

This improves:

* long network label handling
* responsive text wrapping
* dashboard readability
* mobile/browser resizing behavior

---

### 🛡️ Safe Backup / Restore System

The script automatically creates:

#### Protected Original Backup

```text
/usr/share/dvswitch/.dvs-dashboard-responsive-original
```

Created once and never overwritten.

---

#### Per-Run Backups

```text
/usr/share/dvswitch/.dvs-dashboard-responsive-backup-YYYYMMDD-HHMMSS
```

Created during every apply operation for safe rollback/testing.

---

## 📋 Menu

```text
DVSwitch Dashboard Responsive Layout v0.5-test

1 = Apply responsive layout tweaks
2 = Restore latest per-run backup
3 = Restore protected original files
4 = Show responsive-layout status markers
0 = Exit
```

---

## 🧩 What The Script Modifies

### Dashboard Files

```text
/usr/share/dvswitch/index.php
/usr/share/dvswitch/css/css.php
/usr/share/dvswitch/include/lh.php
/usr/share/dvswitch/include/localtx.php
/usr/share/dvswitch/include/system.php
```

---

## 🧠 Proven Responsive Layout Changes

### ✅ Main Container Width Scaling

Changes:

```text
width: 900px;
```

to:

```text
width: min(96vw, 1200px);
```

Result:

* modern responsive scaling
* improved large-screen usability
* preserved centered layout appearance

---

### ✅ Gateway Activity Responsive Scaling

Safely converts fixed-width fieldsets into responsive scaling fieldsets.

Result:

* improved browser resizing
* better widescreen support
* cleaner responsive behavior

---

### ✅ Local Activity Responsive Scaling

Applies the same responsive improvements to Local Activity.

---

### ✅ Hardware Info Responsive Scaling

Improves scaling and centering behavior for:

* Hardware Info
* system status sections
* dashboard information tables

---

### ✅ Hardware Info Centering

Safely centers Hardware Info containers using:

```text
margin-left:auto;
margin-right:auto;
```

instead of fixed positioning.

---

## ⚠️ Important Design Decisions

### Preserved Stock Navigation Width

The original navigation width:

```text
width : 185px;
```

was intentionally preserved.

A tested responsive conversion:

```text
width : 20%;
```

was rejected because it caused:

* left-column compression
* label wrapping issues
* poor real-world node usability

especially on systems with long network names.

---

## 🧠 Design Philosophy

This project intentionally avoids:

* large dashboard rewrites
* replacing dashboard logic
* unsafe global CSS changes
* destructive layout redesigns

Instead it uses:

* surgical responsive tweaks
* lightweight layout improvements
* reversible patch logic
* upstream-safe modifications

---

## 🔁 Restore Options

### Restore Latest Backup

Restores the most recent backup created by the script.

---

### Restore Factory Dashboard

Restores the original untouched dashboard files from the protected original backup.

Allows returning to stock DVSwitch dashboard files without reinstalling DVSwitch.

---

## 🧪 Tested Systems

* Debian 13 / Trixie
* ASL3
* Raspberry Pi 4
* Raspberry Pi 5

Tested against:

* production nodes
* lab nodes
* responsive layout test systems

---

## 🎯 Long-Term Project Goals

Future goals include:

* improved responsive behavior
* compact layout modes
* cleaner widescreen support
* mobile-friendly improvements
* update-safe overlays
* GitHub release packaging
* install/uninstall helper scripts

while remaining:

```text
lightweight
reversible
upstream-friendly
safe for real radio systems
```

---

## 📌 Current Stable Baseline

```text
dvswitch-responsive-layout.sh
Responsive Layout Baseline: v0.5-test
```

Includes:

* responsive container scaling
* responsive Gateway Activity scaling
* responsive Local Activity scaling
* responsive Hardware Info scaling
* Hardware Info centering
* protected original backups
* restore support
* preserved stock navigation width

---

## 📜 License

Use at your own risk.

Always test on a non-production node first.

---

<p align="center">
  📐 Built to modernize DVSwitch Dashboard layout safely without breaking upstream behavior
</p>
