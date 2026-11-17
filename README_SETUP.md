# 🛠️ คู่มือเตรียมสภาพแวดล้อม VS Code (สำหรับมือใหม่)

หน่วยการเรียนรู้นี้ต้อง **รันโค้ด Python จริงใน VS Code** ผ่านไฟล์ notebook (.ipynb)
ทำครบ **ครั้งเดียว** แล้วใช้ได้ทั้งหน่วย ประมาณ 15–20 นาที

---

## สิ่งที่ต้องมี (3 อย่าง)

| ลำดับ | โปรแกรม | ดาวน์โหลดจาก | หมายเหตุ |
|---|---|---|---|
| 1 | **Python 3.11 ขึ้นไป** | https://www.python.org/downloads/ | ตอนติดตั้งต้อง **ติ๊ก "Add python.exe to PATH"** |
| 2 | **Visual Studio Code** | https://code.visualstudio.com/ | เลือกรุ่นตามระบบปฏิบัติการของเรา |
| 3 | ส่วนขยาย 2 ตัวใน VS Code | ภายใน VS Code | ดูขั้นตอนที่ 3 |

---

## ขั้นตอนที่ 1 · ติดตั้ง Python

1. เปิด https://www.python.org/downloads/ → กดปุ่มเหลือง **Download Python 3.1x**
2. เปิดไฟล์ที่ดาวน์โหลด → หน้าต่างตัวติดตั้ง ให้ **ติ๊กเลือก "Add python.exe to PATH" ไว้ด้วย** (สำคัญที่สุด!)
3. กด **Install Now** แล้วรอจนเสร็จ
4. ตรวจสอบ: เปิด **Command Prompt (Windows)** หรือ **Terminal (macOS)** พิมพ์
   ```
   python --version
   ```
   ถ้าขึ้น `Python 3.11.x` ขึ้นมา = ผ่าน ✅

## ขั้นตอนที่ 2 · ติดตั้ง VS Code

ดาวน์โหลดและติดตั้งจาก https://code.visualstudio.com/ แบบ Next → Next → Install ปกติ

## ขั้นตอนที่ 3 · ติดตั้งส่วนขยาย (Extension)

1. เปิดโปรแกรม VS Code
2. กดไอคอน **Extensions** แถบซ้าย (หรือกด `Ctrl+Shift+X`)
3. ค้นหาและกด **Install** สองตัวนี้:
   - **Python** (โดย Microsoft)
   - **Jupyter** (โดย Microsoft)

## ขั้นตอนที่ 4 · เปิดโฟลเดอร์นี้ใน VS Code

1. แตกไฟล์ student_files.zip ให้เป็นโฟลเดอร์ `student_files` (อย่าแยกไฟล์ออกจากโฟลเดอร์!)
2. ใน VS Code: **File > Open Folder** → เลือกโฟลเดอร์ `student_files` ทั้งโฟลเดอร์

## ขั้นตอนที่ 5 · สร้างสภาพแวดล้อมเสมือน (venv) — ทำครั้งเดียว

1. ใน VS Code กด **Terminal > New Terminal** (เมนูด้านบน)
2. พิมพ์คำสั่งตามนี้:

   **Windows:**
   ```
   python -m venv .venv
   .venv\Scripts\activate
   pip install -r requirements.txt
   ```
   **macOS / Linux:**
   ```
   python3 -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   ```

3. รอดาวน์โหลด pandas, numpy, matplotlib สักครู่ (ครั้งแรกประมาณ 1–3 นาที)
   เมื่อเสร็จจะขึ้นข้อความ `Successfully installed ...` ✅

> 💡 **venv คืออะไร?** คือ "กล่องไลบรารีส่วนตัว" ของหน่วยนี้ ติดตั้งอะไรก็ไม่กระทบเครื่องหรือวิชาอื่น — เป็นแนวปฏิบัติมาตรฐานของโปรแกรมเมอร์มืออาชีพ

## ขั้นตอนที่ 6 · เปิด notebook และเลือก Kernel

1. ใน VS Code คลิกเปิดไฟล์ **SETUP.ipynb**
2. ถ้าขึ้นแถบเหลืองถาม **"Select Kernel"** ให้คลิกเลือก → เลือก `.venv (Python 3.1x)`
   (ไม่เห็นชื่อ .venv ให้กด **Python Environments** แล้วเลือกตัวที่มีคำว่า `.venv`)
3. กดปุ่ม **▶ Run Cell** ที่เซลล์แรก
4. ถ้าแสดงเลขเวอร์ชัน pandas / numpy / matplotlib ครบ = **พร้อมเรียนทั้งหน่วยแล้ว** 🎉
   แล้วกลับไปทำ **ภารกิจที่ 0 ใน Moodle**

---

## 🚑 ปัญหาที่พบบ่อย (Troubleshooting)

| อาการ | สาเหตุ | วิธีแก้ |
|---|---|---|
| `python` ไม่ใช่คำสั่งภายใน/ภายนอกโปรแกรม | ตอนติดตั้ง Python ไม่ได้ติ๊ก Add to PATH | ติดตั้ง Python ใหม่แล้วติ๊กช่องนี้ หรือลองใช้คำสั่ง `py` แทน |
| `No module named 'pandas'` | ยังไม่ได้ `pip install` หรือเลือก kernel ผิดตัว | ทำขั้นตอนที่ 5 ใหม่ แล้วกด **Select Kernel** เลือก `.venv` |
| Kernel หาไม่เดือดหรือไม่ขึ้น Run Cell | ยังไม่ได้ติดตั้ง extension Jupyter | กลับไปขั้นตอนที่ 3 ติดตั้ง **Jupyter** ให้ครบ |
| `FileNotFoundError: 'data/...'` | เปิดไฟล์ notebook โดยไม่ได้เปิดโฟลเดอร์ student_files ทั้งโฟลเดอร์ | **File > Open Folder** เลือกโฟลเดอร์ `student_files` แล้วเปิดไฟล์ใหม่ |
| เซลล์รันแล้วเหมือนไม่มีอะไรเกิดขึ้น | กดรันไม่ใช่เซลล์บนสุดก่อน | รันจากบนลงล่างตามลำดับเสมอ |

---

## 📁 โครงสร้างไฟล์ในโฟลเดอร์นี้

```
student_files/
├── README_SETUP.md              ← คู่มือนี้
├── requirements.txt             ← รายชื่อไลบรารีที่ต้องติดตั้ง
├── SETUP.ipynb                  ← ตรวจสภาพแวดล้อม (ภารกิจที่ 0)
├── ch01_pandas_intro.ipynb      ← บทที่ 1 · รู้จักกับ pandas
├── ch02_select_data.ipynb       ← บทที่ 2 · เข้าถึงและคัดเลือกข้อมูล
├── ch03_clean_summarize.ipynb   ← บทที่ 3 · ทำความสะอาดและสรุปข้อมูล
├── ch04_line_plots.ipynb        ← บทที่ 4 · วาดกราฟเส้นด้วย pyplot
├── ch05_bar_scatter_hist_pie.ipynb ← บทที่ 5 · แท่ง จุด ฮิสโตแกรม วงกลม
├── ch06_project_coffee.ipynb    ← บทที่ 6 · โปรเจกต์ร้านกาแฟ 3 สาขา
├── ch07_playground.ipynb         ← บทที่ 7 · สนามซ้อมโค้ด
└── data/
    ├── thai_monthly_climate_1991_2020.csv   ← อากาศจริง TMD ค่าปกติ 30 ปี
    ├── titanic.csv                          ← บันทึกผู้โดยสาร Titanic ค.ศ. 1912
    └── coffee_sales_nyc_2023.csv.gz         ← ธุรกรรมร้านกาแฟ NYC 149,116 รายการ (บีบอัด)
```

> 🗂️ รายละเอียด "ที่มาของข้อมูลแต่ละชุด" อ่านได้ใน **การ์ดข้อมูล** ประกอบแต่ละบทใน Moodle
