# Klar V6.7 Late Attendance Fix

Perbaikan utama:

- Check-in lewat `Batas telat` otomatis diberi status `telat`.
- Backend memakai waktu server Apps Script, bukan jam HP, untuk menentukan telat.
- Record absensi menyimpan `isLate`, `lateMinutes`, `lateAfter`, dan `needsLateApproval`.
- Monitor Admin menampilkan badge Telat dan menit keterlambatan.
- Dashboard menampilkan kartu Telat Hari Ini dan ringkasan telat.
- Payroll menghitung telat sebagai telat, bukan hadir biasa, tetapi tetap dihitung sebagai kehadiran untuk tunjangan kehadiran jika aturan memperbolehkan.

Catatan:

- `Batas telat` diatur di menu Aturan Absensi.
- Contoh: batas telat 07:15, karyawan check-in 07:28, status menjadi `telat` dan `lateMinutes` = 13.
- Jika perlu approval untuk telat ekstrem, pakai `Batas butuh approval`; versi ini menyimpan penanda `needsLateApproval`, tetapi approval workflow penuh bisa dibuat di versi berikutnya.
