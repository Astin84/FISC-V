# 💡 FISC‑V: پردازنده‌ی آموزشی Single‑Cycle

![Language](https://img.shields.io/badge/زبان-Verilog-orange)  
![License](https://img.shields.io/badge/مجوز-MIT-blue)

یک هسته‌ی ساده و آموزشی RISC‑V با معماری **Single‑Cycle**، مناسب برای پروتوتایپ روی FPGA، یادگیری پایه‌های طراحی پردازنده و آزمایش در **Logisim** 🚀 :contentReference[oaicite:0]{index=0}

---

## 🚀 ویژگی‌ها

- 🌟 **معماری Single‑Cycle**  
  اجرای کامل هر دستورالعمل (واکسش، رمزگشایی، ALU، دسترسی به حافظه و نوشتن در رجیستر) در **یک چرخه‌ی کلاک** واحد :contentReference[oaicite:1]{index=1}  
- 📚 **مجموعه دستورات RV32I**  
  پشتیبانی از دستورات پایه:  
  - حسابی و بیتی: `add`, `sub`, `sll`, `srl`, `sra`, `slt`, `sltu` و نسخه‌ی فوری‌شده (`addi`, `slli`, …)  
  - منطقی: `and`, `or`, `xor` و نسخه‌ی فوری‌شده (`andi`, `ori`, …)  
  - بارگذاری/ذخیره: `lb`, `lh`, `lw`, `lbu`, `lhu`, `sw`  
  - پرش شرطی: `beq`, `bne` :contentReference[oaicite:2]{index=2}  
- 🖥️ **شبیه‌سازی در Logisim**  
  امکان مشاهده‌ی بصری مسیر داده (Data Path) و واحد کنترل برای درک بهتر اجرا :contentReference[oaicite:3]{index=3}  
- 🔧 **پیاده‌سازی سریع**  
  - مناسب برای FPGAهای Xilinx و Intel/Altera  
  - آماده‌ی استفاده با Verilator و ابزارهای استاندارد RISC‑V

---

## 📐 معماری کلی

```text
┌─────┐   ┌──────┐   ┌─────┐   ┌─────┐   ┌─────┐
│ IF  │ → │ ID   │ → │ EX  │ → │ MEM │ → │ WB  │
│(Fetch)│   │(Decode)│   │(ALU)│   │(Load/Store)│   │(Write)│
└─────┘   └──────┘   └─────┘   └─────┘   └─────┘


🤝 مشارکت
 (Fork) کنید

شاخه‌ی خود را ایجاد کنید (git checkout -b feature/YourFeature)

تغییرات را کمیت کنید (git commit -m "Add awesome feature")

پوش کنید و Pull Request بزنید 🚀


