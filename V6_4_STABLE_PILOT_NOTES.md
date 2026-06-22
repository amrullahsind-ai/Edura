# Klar V6.4 Stable Pilot Notes

Versi ini fokus ke stabilitas pilot, bukan penambahan fitur besar.

## Perubahan utama
- Branding tampilan menjadi **Klar** saja, tanpa label V6 pada landing page.
- Palet warna baru: Deep Green `#085842` + Fresh Teal `#39AE89`.
- Hapus karyawan diubah menjadi **Arsipkan**, agar absensi/payroll lama tidak putus.
- Modal daftar besar tetap terbuka setelah arsip karyawan.
- Payroll punya validasi sebelum finalisasi: gaji Rp0/negatif, duplikat identitas, jabatan/golongan kosong, dan potongan melebihi pendapatan.
- Backup otomatis dibuat sebelum import Excel dan sebelum finalisasi payroll.
- Audit log dasar ditambahkan di tab Sync.
- Import Excel menyimpan riwayat import dan tetap menjaga gaji bersih Excel sebagai snapshot.

## Catatan batasan
Klar V6.4 masih cocok untuk pilot sekolah kecil-menengah dengan database Spreadsheet masing-masing sekolah. Untuk massal besar, tetap disarankan migrasi bertahap ke database proper seperti Supabase/PostgreSQL.
