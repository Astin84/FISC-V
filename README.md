<link href="https://cdn.jsdelivr.net/npm/vazir-font@latest/dist/font-face.css" rel="stylesheet">

<div style="font-family: 'Vazir', sans-serif; direction: rtl; text-align: right; line-height: 1.6;">

<!-- ========================= BADGES ========================= -->
<p align="center">
  <a href="https://github.com/yourusername/fisc-v">
    <img src="https://img.shields.io/badge/پروژه-FISC--V-blue?style=for-the-badge" alt="Project FISC-V" />
  </a>
  <img src="https://img.shields.io/badge/زبان-Verilog-orange?style=for-the-badge" alt="Language: Verilog" />
  <img src="https://img.shields.io/badge/مجوز-MIT-blue?style=for-the-badge" alt="License: MIT" />
</p>

# 💡 FISC‑V  
**یک CPU آموزشی و ساده RISC‑V با معماری Single‑Cycle**

<p align="center">
  <img src="https://github.com/Astin84/FISC-V/blob/main/PICs/DataPath.png?raw=true" alt="Data Path Diagram" width="600"/>
</p>

---

## 📋 فهرست مطالب
1. [معرفی](#معرفی)  
2. [ویژگی‌ها](#ویژگی‌ها)  
3. [معماری کلی](#معماری-کلی)  
4. [ساخت و شبیه‌سازی](#ساخت-و-شبیه‌سازی)  
5. [استفاده روی FPGA](#استفاده-روی-fpga)  
6. [ساختار پروژه](#ساختار-پروژه)  
7. [مشارکت](#مشارکت)  
8. [مجوز](#مجوز)  

---

## معرفی
FISC‑V یک هسته‌ی آموزشی RISC‑V ساده و **Single‑Cycle** است که با هدف:  
- یادگیری اصول پایه طراحی پردازنده  
- پروتوتایپ سریع روی FPGA  
- شبیه‌سازی دیداری در **Logisim**  
پیاده‌سازی شده است.

---

## ویژگی‌ها
- 🌟 **Single‑Cycle Architecture**  
  هر دستورالعمل در یک چرخه‌ی کلاک کامل می‌شود.
- 📚 **مجموعه دستورات RV32I** شامل:  
  - حسابی/بیتی: `add`, `sub`, `sll`, `srl`, `sra`, `slt`, `sltu`  
  - نسخه‌های فوری: `addi`, `slli`, `srli`, `srai`, `slti`, `sltiu`  
  - منطقی: `and`, `or`, `xor`  
  - فوری‌ها: `andi`, `ori`, `xori`  
  - بارگذاری/ذخیره: `lb`, `lh`, `lw`, `lbu`, `lhu`, `sw`  
  - پرش شرطی: `beq`, `bne`  
- 🖥️ **شبیه‌سازی در Logisim**  
  مشاهده‌ی مسیر داده و واحد کنترل به صورت گرافیکی  
- 🔧 **پیاده‌سازی سریع**  
  - آماده برای FPGAهای **Xilinx** و **Intel/Altera**  
  - سازگار با **Verilator** و ابزارهای استاندارد RISC‑V  

---

## معماری کلی

```text
┌─────────┐   ┌──────────┐   ┌────────┐   ┌───────────┐   ┌─────────┐
│  IF     │ → │  ID      │ → │  EX    │ → │   MEM     │ → │   WB    │
│ (Fetch) │   │ (Decode) │   │ (ALU)  │   │ (Load/Store)│ │ (Write) │
└─────────┘   └──────────┘   └────────┘   └───────────┘   └─────────┘
