# Klar V6.6 — Template Rules + Overtime

Perubahan utama:

- Menambahkan `template-import-klar.xlsx`.
- Template berisi sheet Karyawan, Jabatan, Golongan, Komponen, Jadwal, Kalender Libur, Lembur, dan Payroll Awal.
- Payroll Awal sudah punya formula agar gaji mengikuti aturan Excel.
- Tunjangan lembur dihitung dari sheet Lembur dengan status Disetujui.
- Import Klar tetap membaca Payroll Awal sebagai snapshot sehingga nominal final mengikuti Excel.
- Teks import di admin diperjelas.
- Cache PWA dibump ke `klar-v6-6-template-rules`.

Catatan:
- Ini belum modul lembur otomatis penuh di aplikasi. Ini adalah tahap aman: lembur dihitung di template Excel dan diimport sebagai payroll snapshot.
- Modul penuh nantinya perlu Jadwal Kerja, Kalender Libur, Penugasan Lembur, Approval Lembur, dan Audit Log dalam aplikasi.
