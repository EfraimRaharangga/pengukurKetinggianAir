# Proyek Pengukur Kedalaman Air

Proyek ini menggunakan Arduino Nano untuk mengukur kedalaman air dengan sensor ultrasonik (HC-SR04), dilengkapi dengan umpan balik visual dan audio melalui LED, buzzer, dan layar LCD. Sistem ini memberikan cara mudah untuk memantau kedalaman air untuk berbagai aplikasi yang disimulasikan.

---

## **Fitur**
- Mengukur kedalaman air menggunakan sensor ultrasonik.
- Menampilkan kedalaman air secara real-time dalam sentimeter di LCD (HD44780).
- Memberikan indikasi status kedalaman air dengan tiga LED (hijau, kuning, merah):
  - **Hijau**: Kedalaman air di bawah 1 meter.
  - **Kuning**: Kedalaman air antara 1 dan 2 meter.
  - **Merah**: Kedalaman air di atas 2 meter.
- Memberikan umpan balik audio melalui buzzer:
  - Bunyi pendek untuk kedalaman di bawah 1 meter.
  - Bunyi sedang untuk kedalaman antara 1 dan 2 meter.
  - Bunyi panjang untuk kedalaman di atas 2 meter.

---

## **Komponen yang Dibutuhkan**

### **Daftar Komponen**
1. **Arduino Nano**
2. **Sensor Ultrasonik (HC-SR04)**
3. **LCD HD44780** (16x2) dengan pin data penuh (D0-D7)
4. **Potensiometer** (10kΩ untuk mengatur kontras LCD)
5. **LED** (Hijau, Kuning, Merah)
6. **Resistor**:
   - 330Ω untuk masing-masing LED.
   - 220Ω untuk lampu latar LCD.
   - 10kΩ pull-up untuk simulasi pin Echo (jika diperlukan).
7. **Buzzer**

### **Koneksi Pin**
#### **Sensor Ultrasonik HC-SR04**
| Pin     | Arduino Nano |
|---------|--------------|
| VCC     | 5V           |
| GND     | GND          |
| Trig    | A4           |
| Echo    | A5           |

#### **LCD HD44780 (16x2)**
| Pin   | Arduino Nano |
|-------|--------------|
| VSS   | GND          |
| VDD   | 5V           |
| V0    | Potensiometer|
| RS    | D6           |
| RW    | GND          |
| E     | D7           |
| D0    | D8           |
| D1    | D9           |
| D2    | D10          |
| D3    | D11          |
| D4    | D12          |
| D5    | D13          |
| D6    | A0           |
| D7    | A1           |
| A (Anoda LED) | 5V (via resistor 220Ω) |
| K (Katoda LED)| GND          |

#### **LED**
| Warna LED | Arduino Nano | Resistor |
|-----------|--------------|----------|
| Hijau     | D2           | 330Ω    |
| Kuning    | D3           | 330Ω    |
| Merah     | A2           | 330Ω    |

#### **Buzzer**
| Pin        | Arduino Nano |
|------------|--------------|
| Positif    | A3           |
| Negatif    | GND          |

---

## **Perangkat Lunak yang Dibutuhkan**
- Arduino IDE (versi terbaru)
- Pustaka LiquidCrystal (sudah tersedia di Arduino IDE)
- Simulide

---

## **Cara Pengaturan dan Penggunaan**

1. **Rakit Rangkaian:**
   - Hubungkan semua komponen sesuai dengan koneksi pin di atas.
   - Pastikan pasokan daya ke Arduino Nano dan komponen sudah benar.

2. **Unggah Kode ke Arduino:**
   - Buka sketsa Arduino yang disediakan di Arduino IDE.
   - Pilih papan (**Arduino Nano**) dan port yang benar dari menu Tools.
   - Unggah kode ke papan.

3. **Jalankan Sistem:**
   - Tempatkan sensor ultrasonik di atas permukaan air.
   - Pantau kedalaman air di LCD.
   - Amati indikasi LED dan dengarkan buzzer untuk peringatan kedalaman.

---

## **Cara Kerja**
1. **Sensor Ultrasonik:**
   - Mengukur waktu yang dibutuhkan gelombang suara untuk mencapai permukaan air dan kembali.
   - Mengubah waktu tersebut menjadi jarak (dalam sentimeter).

2. **Umpan Balik Visual:**
   - LED Hijau: Kedalaman < 1 meter.
   - LED Kuning: Kedalaman antara 1 dan 2 meter.
   - LED Merah: Kedalaman > 2 meter.

3. **Umpan Balik Audio:**
   - Bunyi pendek: Kedalaman < 1 meter.
   - Bunyi sedang: Kedalaman antara 1 dan 2 meter.
   - Bunyi panjang: Kedalaman > 2 meter.

4. **LCD:**
   - Menampilkan kedalaman air secara real-time dalam sentimeter.

---

## **Pengembangan di Masa Depan**
- Mengganti LED dengan satu LED RGB untuk desain yang lebih ringkas.
- Menambahkan modul nirkabel (misalnya, ESP8266) untuk memantau kedalaman secara jarak jauh.
- Menggunakan sensor ultrasonik tahan air untuk aplikasi di luar ruangan.

---

## **Pemecahan Masalah**
- **LCD Tidak Menyala:**
  - Periksa potensiometer untuk penyesuaian kontras yang benar.
  - Pastikan koneksi pin data sudah benar.

- **Pembacaan Kedalaman Tidak Akurat:**
  - Pastikan sensor diposisikan tegak lurus dengan permukaan air.
  - Periksa adanya penghalang yang menghalangi gelombang ultrasonik.

- **LED/Buzzer Tidak Berfungsi:**
  - Periksa koneksi dan nilai resistor.
  - Pastikan konfigurasi pin di kode sudah benar.

---

## **Penulis**
Proyek ini dibuat sebagai bagian dari sistem pengukur kedalaman air berbasis Arduino Nano. Anda bebas memodifikasi dan mengembangkannya sesuai kebutuhan.
