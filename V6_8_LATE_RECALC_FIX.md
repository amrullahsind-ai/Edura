# Klar V6.8 Late Recalculation Fix

Perbaikan ini membuat status telat tidak hanya bergantung pada field `status` dari server.
Jika record lama masih tersimpan sebagai `hadir`, Klar akan menghitung ulang dari `checkInTime` dan `attendanceRules.lateAfter`.

Dampak:
- Monitor admin menampilkan Telat jika check-in melewati batas telat.
- Dashboard menghitung Telat Hari Ini dengan benar.
- Payroll menghitung rekap telat dari data hasil rekalkulasi.
- Data lama otomatis dikoreksi lalu disimpan/sync.
- Employee page juga punya fallback tampilan telat.

Wajib redeploy frontend dan Apps Script.
