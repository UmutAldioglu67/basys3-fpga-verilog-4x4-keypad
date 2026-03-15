# Basys3 FPGA Tabanlı 4x4 Matris Keypad Sürücüsü ve Özel PCB Tasarımı
### 🇬🇧 FPGA Based 4x4 Matrix Keypad Driver & Custom PCB Design

![University](https://img.shields.io/badge/Kocaeli%20University-EHM-green)
![Hardware](https://img.shields.io/badge/Hardware-Basys3%20FPGA-orange)
![Software](https://img.shields.io/badge/Software-Vivado%20%7C%20Verilog-blue)

---

## 🇹🇷 Proje Hakkında (Turkish)

[cite_start]Bu proje, Kocaeli Üniversitesi Elektronik ve Haberleşme Mühendisliği bölümü kapsamında geliştirilmiştir[cite: 1, 3]. [cite_start]Xilinx Artix-7 tabanlı Digilent Basys 3 FPGA kartı için PMOD standardına tam uyumlu bir 4x4 matris tuş takımı donanımını ve Verilog sürücü tasarımını içermektedir[cite: 18, 19, 40].

[cite_start]Projede, Vivado ortamında modüler tasarım prensibi kullanılarak yazılım mimarisi oluşturulmuştur[cite: 32]. Tasarımda harici bir asenkron `rst` (reset) sinyaline ihtiyaç duyulmadan, tamamen senkron ve stabil bir çalışma hedeflenmiştir.

### 🚀 Öne Çıkan Özellikler
* [cite_start]**Freeze & Latch (Dondur ve Kilitle) Algoritması:** Tarama sırasında herhangi bir tuşa basıldığı anda (sütun verisi > 0), tarama sayacı o anki satırda dondurulur[cite: 117]. [cite_start]Bu yöntem, harici bir ark sönümleyiciye (debouncer) olan ihtiyacı azaltarak kararlı bir okuma sağlar[cite: 118].
* [cite_start]**Güvenli Donanım Mimarisi:** FPGA giriş/çıkış pinlerini olası kısa devrelerden korumak için 330Ω seri SMD koruma dirençleri kullanılmıştır[cite: 55, 66].
* [cite_start]**Sinyal Kararlılığı:** Butonlara basılmadığında giriş sinyallerinin "havada" (floating) kalmasını ve gürültüden etkilenmesini önlemek amacıyla 10kΩ SMD pull-down dirençleri entegre edilmiştir[cite: 57, 67].
* [cite_start]**Özgün PCB Üretimi:** Devre şeması sıfırdan tasarlanmış olup, fiziksel üretim sürecinde "Ütü ile Toner Transferi" ve "Asit İndirme" yöntemleri kullanılmıştır[cite: 88].
  
### 📂 Klasör Yapısı
* `src/` -> Verilog kaynak kodları (`Top_Module.v`, `Keypad_Scanner.v`, `Clock_Divider.v`, `Seven_Seg_Driver.v`).
* `hardware/` -> PCB şematik çizimleri ve üretim dosyaları.
* `docs/` -> Proje raporu, devre şeması (PDF) ve montajı tamamlanmış donanım görselleri.

---

## 🇬🇧 Project Description (English)

[cite_start]This repository contains the full **Verilog source code** and **custom PCB design** files for a PMOD-compatible 4x4 Matrix Keypad project implemented on the Digilent Basys 3 FPGA board[cite: 18, 40].

[cite_start]The project features a custom-developed **"Freeze & Latch" scanning algorithm** [cite: 117] [cite_start]that eliminates the need for traditional debouncer modules by locking the state upon signal detection[cite: 118]. The design is optimized to run smoothly without requiring an external asynchronous `rst` (reset) signal.

### 🚀 Key Features
* [cite_start]**Freeze Logic:** Unlike standard scanning, the counter instantly stops (freezes) when a column signal is detected[cite: 117, 139]. [cite_start]This ensures a stable output and prevents false readings[cite: 140].
* [cite_start]**Hardware Protection:** Equipped with 330Ω SMD series resistors to limit current and protect the fragile FPGA I/O pins[cite: 55].
* [cite_start]**Signal Stability:** Utilizes 10kΩ SMD pull-down resistors to keep the input lines grounded when buttons are unpressed, preventing floating states and electrical noise interference[cite: 57, 58].
* [cite_start]**Custom PCB Manufacturing:** The hardware is designed from scratch and manufactured using the DIY Toner Transfer and Acid Etching methods[cite: 88].

### ⚙️ Pinout (PMOD Interface)
| FPGA / PMOD Pin | Keypad Pin | Direction |
|-----------------|------------|-----------|
| Pin 1           | COL 1      | Input     |
| Pin 2           | COL 2      | Input     |
| Pin 3           | COL 3      | Input     |
| Pin 4           | COL 4      | Input     |
| Pin 7           | ROW 1      | Output    |
| Pin 8           | ROW 2      | Output    |
| Pin 9           | ROW 3      | Output    |
| Pin 10          | ROW 4      | Output    |

---

## 👥 Authors & Acknowledgments / Yazar ve Teşekkür

**Project Developer / Proje Geliştiricisi:**
* **Umut Aldıoğlu** - *Hardware Design, PCB Manufacturing & FPGA Logic Design*
  * 📧 umut671167@gmail.com
  * 💻 https://github.com/UmutAldioglu67

## 📄 License
This project is open-source and available for educational purposes.
