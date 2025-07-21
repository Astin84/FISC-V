<div style="font-family: 'Shabnam', sans-serif; direction: rtl; line-height: 1.6;">

<!-- ========================= BADGES ========================= -->
<p align="center">
  <a href="https://github.com/yourusername/fisc-v">
    <img src="https://img.shields.io/badge/پروژه-FISC--V-blue?style=for-the-badge" alt="Project FISC-V" />
  </a>
  <img src="https://img.shields.io/badge/زبان-Verilog-orange?style=for-the-badge" alt="Language: Verilog" />
  <img src="https://img.shields.io/badge/مجوز-MIT-blue?style=for-the-badge" alt="License: MIT" />
</p>

# 💡 FISC-V  
**یک CPU آموزشی و ساده RISC-V با معماری Single-Cycle**

<p align="center">
  <img src="docs/assets/datapath.png" alt="Data Path Diagram" width="600"/>
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
FISC-V یک هسته‌ی آموزشی RISC-V ساده و **Single-Cycle** است که با هدف:
- یادگیری اصول پایه طراحی پردازنده  
- پروتوتایپ سریع روی FPGA  
- شبیه‌سازی دیداری در **Logisim**  
پیاده‌سازی شده است.

---

## ویژگی‌ها
- 🌟 **Single-Cycle Architecture**  
  هر دستورالعمل در یک چرخه‌ی کلاک کامل می‌شود.
- 📚 **مجموعه دستورات RV32I** شامل:  
  - حسابی/بیتی: `add`, `sub`, `sll`, `srl`, `sra`, `slt`, `sltu` و نسخه‌های فوری: `addi`, `slli`, …  
  - منطقی: `and`, `or`, `xor` و فوری‌ها: `andi`, `ori`, …  
  - بارگذاری/ذخیره: `lb`, `lh`, `lw`, `lbu`, `lhu`, `sw`  
  - پرش شرطی: `beq`, `bne`  
- 🖥️ **شبیه‌سازی در Logisim**  
  مشاهده‌ی مسیر داده و واحد کنترل به صورت گرافیکی  
- 🔧 **پیاده‌سازی سریع**  
  - آماده برای FPGAهای **Xilinx** و **Intel/Altera**  
  - قابل استفاده با **Verilator** و ابزارهای استاندارد RISC-V  

---

## معماری کلی

```text
┌─────────┐   ┌──────────┐   ┌────────┐   ┌───────────┐   ┌─────────┐
│  IF     │ → │  ID      │ → │  EX    │ → │   MEM     │ → │   WB    │
│ (Fetch) │   │ (Decode) │   │ (ALU)  │   │ (Load/Store)│ │ (Write) │
└─────────┘   └──────────┘   └────────┘   └───────────┘   └─────────┘

IF: واکشی دستور از حافظه

ID: رمزگشایی و خوانش ثبات‌ها

EX: عملیات ALU و محاسبه آدرس

MEM: دسترسی خواندن/نوشتن به حافظه داده

WB: نوشتن نتایج در فایل ثبات

## کلون مخزن
git clone https://github.com/yourusername/fisc-v.git
cd fisc-v

## شبیه‌سازی با Verilator
mkdir build && cd build
verilator --cc ../src/top.sv --exe ../tests/testbench.cpp
make -C obj_dir -j -f Vtop.mk Vtop
./obj_dir/Vtop

نکته: برای شبیه‌سازی بصری، فایل Logisim در docs/logisim/ قرار دارد. آن را باز کنید و مسیر داده را بررسی کنید 🚀


استفاده روی FPGA
ایجاد فایل رویت
yosys -p "synth_ice40 -top top -json top.json" src/top.sv

بیت‌استریم
nextpnr-ice40 --hx8k --package ct256 --json top.json --asc top.asc
icepack top.asc top.bin
فلش به برد


iceprog top.bin

ساختار پروژه

fisc-v/
├── src/               # کد Verilog
│   ├── if_unit.sv
│   ├── id_unit.sv
│   ├── ex_unit.sv
│   ├── mem_unit.sv
│   └── wb_unit.sv
├── tests/             # بنچ‌تست‌ها (C++)
├── docs/              # دیاگرام‌ها و فایل‌های Logisim
├── build/             # دایرکتوری شبیه‌سازی
└── README.md

مشارکت
۱. مخزن را فورک کنید
۲. شاخه‌ی جدید بسازید
git checkout -b feature/YourFeature

۳. تغییرات را کمیت کنید


git commit -m "Add awesome feature"

۴. پوش کنید و Pull Request بزنید 🚀




