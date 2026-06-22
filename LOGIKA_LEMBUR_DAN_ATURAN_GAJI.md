# Klar — Logika Lembur dan Aturan Gaji dari Excel

## Konsep utama
Klar tidak memaksa semua sekolah memakai satu rumus gaji. Untuk sekolah yang sudah punya aturan sendiri, rumus bisa disiapkan di Excel lalu Klar mengimport hasilnya sebagai **Payroll Awal / snapshot**.

Artinya:

1. Sheet **Karyawan** berisi identitas karyawan.
2. Sheet **Jabatan** berisi kode jabatan dan tunjangan jabatan.
3. Sheet **Golongan** berisi gaji pokok dan tunjangan hadir.
4. Sheet **Komponen** berisi aturan tambahan: masa kerja, makan, alpha, telat, pinjaman, insentif, dll.
5. Sheet **Jadwal** dan **Kalender Libur** menjadi rujukan untuk logika kerja normal dan hari libur.
6. Sheet **Lembur** berisi lembur yang sudah disetujui.
7. Sheet **Payroll Awal** menghitung gaji bersih memakai rumus Excel.
8. Klar mengimport **Payroll Awal** sebagai nominal final/snapshot.

## Logika lembur yang disarankan
Lembur jangan otomatis masuk hanya karena karyawan check-in di luar jam. Yang aman:

- sistem mendeteksi potensi lembur,
- admin/atasan menyetujui,
- hanya status **Disetujui** yang masuk payroll.

Di template:

```text
Lembur.Bulan + Lembur.Kode/Nama + Lembur.Status = Disetujui
→ masuk ke Payroll Awal.Tunj. Lembur
```

Rumus di Payroll Awal memakai key:

```text
Bulan|Kode/Nama
```

supaya nominal lembur masuk ke karyawan dan periode yang tepat.

## Kenapa pakai snapshot?
Payroll menyangkut uang. Jika aturan gaji berubah bulan depan, slip bulan lama tidak boleh ikut berubah. Karena itu hasil import dari Excel disimpan sebagai snapshot.

## Cara pakai template
1. Isi **Karyawan**.
2. Isi/ubah **Jabatan**.
3. Isi/ubah **Golongan**.
4. Isi/ubah **Komponen**.
5. Isi **Lembur** jika ada.
6. Cek sheet **Payroll Awal**.
7. Pastikan kolom **Gaji Bersih** sudah benar.
8. Upload ke Klar → Baca & Analisis → preview → Terapkan Import.

## Catatan penting
- Jangan hapus header utama di Payroll Awal.
- Jika sekolah punya komponen baru, tambahkan kolom baru di Payroll Awal dengan nama yang jelas, misalnya `Tunj. Transport`, `Tunj. Piket`, atau `Potongan Koperasi`.
- Klar akan membaca nominal akhir dari kolom gaji yang cocok, terutama **Gaji Bersih**.
