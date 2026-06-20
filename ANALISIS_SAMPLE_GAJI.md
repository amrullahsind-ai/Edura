# Analisis `sample gaji.xlsx` untuk Edura V4.3

## Struktur Excel yang dibaca
File contoh berisi sheet:
- `ABSENSI PER TMT`: data SDM dan input absensi dasar.
- `Gapok`: master golongan/grade, gaji pokok, dan tunjangan hadir.
- `SLIP GAJI`: format slip gaji.
- `TJ. FUNGSIONAL`: master jabatan fungsional dan tunjangan.
- `POTONGAN BPJS JHT`: potongan BPJS per orang/bulan.
- `PINJAMAN`: potongan pinjaman per orang/bulan.
- `PER UNIT`: rekap final payroll per unit.

## Pola penting dari Excel
1. Payroll tidak hanya berdasarkan jabatan. Di contoh, golongan/grade mempengaruhi gaji pokok dan tunjangan kehadiran.
2. Sheet `Gapok` berisi grade seperti `IA1` sampai `IIIC10`.
3. Dalam sheet `PER UNIT`, gaji pokok memakai rumus VLOOKUP dari grade khusus ke `Gapok`.
4. Tunjangan kehadiran memakai grade:
   - kalau hadir/telat memenuhi hari kerja → pakai tunjangan hadir full/bulan.
   - kalau tidak penuh → pakai tunjangan hadir per hari x jumlah hadir/telat.
5. Tunjangan fungsional dan tunjangan rumah diambil dari kode jabatan fungsional.
6. Tunjangan masa kerja memakai pola `50.000 x masa kerja`.
7. Potongan absensi dari contoh dipetakan ke Edura:
   - Izin: 25.000
   - Sakit: 0
   - Alpha/Tanpa Keterangan: 60.000
   - Telat: 7.500

## Yang diterapkan ke Edura
- Master golongan Edura sekarang diisi dari `Gapok`.
- Golongan punya:
  - gaji pokok golongan
  - tunjangan hadir harian
  - tunjangan hadir full/bulan
  - tambahan golongan
  - minimal tahun
  - level pendidikan
- Master jabatan Edura sekarang mengambil contoh dari `TJ. FUNGSIONAL`.
- Payroll Edura sekarang menghitung:
  `gaji pokok golongan + tj hadir grade + tj fungsional jabatan + tj rumah + tj masa kerja + komponen custom - potongan`.
- Absensi yang terlalu jauh atau terlalu telat tidak langsung dihitung, tapi masuk pengajuan approval admin.
- Device lock ditambahkan agar 1 karyawan hanya bisa login dari 1 device aktif. Device baru harus ACC admin.

Total grade yang dimasukkan: 90
Total jabatan fungsional yang dimasukkan: 31
