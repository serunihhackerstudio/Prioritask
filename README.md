# 🚀 Prioritask - Sistem Manajemen Tugas Premium

Prioritask adalah aplikasi web manajemen tugas (To-Do List) satu halaman (*Single Page Application*) kelas atas yang dirancang untuk meningkatkan produktivitas harian Anda. Aplikasi ini menggabungkan antarmuka pengguna (UI) yang elegan, fitur keamanan bawaan, pengatur waktu fokus (*countdown timer*), dan sinkronisasi basis data nirserver (*serverless*) menggunakan Google Spreadsheet.

Dibangun murni menggunakan **HTML5, Tailwind CSS, dan Vanilla JavaScript**, aplikasi ini dapat berjalan langsung di peramban (browser) apa pun tanpa memerlukan instalasi *backend* yang rumit.

---

## ✨ Fitur Unggulan

### 1. 🛡️ Keamanan Privasi (PIN Lock & Auto-Lock)

Data tugas Anda adalah privasi. Prioritask dilengkapi dengan sistem keamanan **PIN 4-digit**.

* **Layar Kunci Virtual**: Menghalangi akses ke dashboard jika PIN belum dimasukkan.
* **Pengawas Inaktivitas (Watchdog)**: Aplikasi akan mengunci otomatis jika tidak ada aktivitas (gerakan mouse, ketikan, atau gulir layar) sesuai dengan durasi waktu tenggang yang Anda atur (1 hingga 60 menit).

### 2. ⚡ Mode Fokus & Real-Time Countdown

Bukan sekadar daftar tugas biasa, Prioritask membantu Anda memonitor waktu pengerjaan.

* Tentukan **Estimasi Durasi** (1-24 jam) saat membuat tugas.
* Tekan tombol **Mulai (Play)** untuk mengaktifkan status *In Progress*. Kartu tugas akan memancarkan animasi *Glow Border* premium dan waktu akan menghitung mundur secara real-time.
* **Jeda Pintar (Pause)**: Anda dapat menjeda pengerjaan kapan saja tanpa kehilangan sisa waktu yang sudah berjalan.

### 3. ☁️ Penyimpanan Hibrida (Lokal & Google Sheets)

Prioritask mendukung dua mode penyimpanan secara instan:

* **Mode Offline (Lokal)**: Menyimpan semua data di *Local Storage* peranti Anda.
* **Mode Cloud (Google Sheets)**: Hubungkan aplikasi ke Google Spreadsheet menggunakan URL Web App dari Google Apps Script. Data tugas dan parameter konfigurasi akan disimpan rapi dalam format JSON.
* **Optimistic UI Update**: Penghapusan dan pencentangan tugas terasa instan (0 milidetik latensi) di layar, sementara sinkronisasi data dilakukan di latar belakang (*background sync*).

### 4. 🎨 Kustomisasi Premium Tanpa Batas

Sesuaikan tampilan aplikasi agar sesuai dengan estetika produktivitas Anda. Semua konfigurasi disimpan persisten.

* **Mode Gelap/Terang**: Dukungan penuh *Dark Mode* yang mulus.
* **Warna Dasar Dinamis**: Pilih dari 6 preset warna premium (Indigo, Emerald, Blue, Amber, Rose, Violet) atau gunakan **Custom Color Picker**. Algoritma pencampuran warna (*color blending*) internal akan secara matematis meracik palet kustom Anda agar tetap indah.
* **Logo Aplikasi**: Ubah ikon sudut kiri atas menggunakan 18 preset FontAwesome atau masukkan *class* FontAwesome kustom Anda sendiri (misal: `fa-coffee`, `fa-brain`).
* **Banner Kustom**: Ubah kata sambutan dan subjudul motivasi di dashboard sesuka hati.

### 5. 🧹 Manajemen Cerdas (Bulk Delete)

* Pisahkan tugas berdasarkan kategori bawaan: **Kantor** dan **Rumah**.
* Filter instan berdasarkan prioritas (Tinggi, Sedang, Rendah) atau fungsi pencarian teks.
* **Pembersihan Massal**: Hapus semua tugas yang sudah selesai (*Completed*) dalam satu kategori hanya dengan satu klik praktis.

---

### 6. ✨ Desain Baru yang Lebih Segar & Mudah Digunakan

* **Tambah Cepat**: Ketik judul lalu tekan Enter, tugas langsung masuk ke kategori aktif. Butuh pengaturan detail? Klik **Detail** untuk membuka panel samping (di HP tampil sebagai *bottom sheet*).
* **Panel Fokus**: Tugas yang sedang dikerjakan tampil di sidebar dengan timer besar serta tombol Jeda/Selesai.
* **Catatan Tugas**: Setiap tugas bisa diberi catatan tambahan (detail, link, langkah-langkah). Catatan ikut dicari, tautan otomatis bisa diklik, dan disimpan di kolom `Notes` pada Spreadsheet.
* **Urungkan Hapus**: Tugas yang terhapus bisa dipulihkan dari notifikasi selama beberapa detik.
* **Penanda Terlambat**: Tugas yang melewati target tanggal ditandai merah secara otomatis.
* **Pintasan Keyboard**: `N` tugas baru, `/` cari, `Esc` tutup panel.
* **Ramah HP**: Tombol tambah melayang (FAB), kontrol berukuran sentuh, dan tata letak satu kolom.

---

## 🛠️ Teknologi yang Digunakan

* **Markup & Layout**: HTML5 Semantik.
* **Styling**: [Tailwind CSS v3](https://tailwindcss.com/) (dimuat via CDN dengan injeksi konfigurasi kustom JIT).
* **Tipografi**: [Plus Jakarta Sans](https://fonts.google.com/specimen/Plus+Jakarta+Sans) dari Google Fonts.
* **Logika & Fungsionalitas**: Vanilla JavaScript (ES6+).
* **Ikonografi**: [FontAwesome v6](https://fontawesome.com/).
* **Animasi Tambahan**: [Canvas Confetti](https://www.kirilv.com/canvas-confetti/) (untuk efek perayaan saat tugas selesai).
* **Backend / Database**: Google Apps Script (GAS) & Google Spreadsheet.

---

## 🚀 Panduan Memulai Cepat (Quick Start)

Karena aplikasi ini bersifat *client-side* seutuhnya, Anda tidak perlu menginstal Node.js, NPM, atau mengatur server database SQL.

1. **Unduh / Kloning** berkas `index.html`.
2. Klik ganda (buka) berkas `index.html` tersebut menggunakan peramban modern (Google Chrome, Firefox, Safari, atau Edge).
3. **Selesai!** Aplikasi sudah siap digunakan dalam Mode Penyimpanan Lokal.
* *Catatan:* PIN default saat pertama kali dijalankan adalah **`2911`**.



---

## 🔗 Panduan Integrasi Database (Google Spreadsheet)

Agar data tugas dan pengaturan Anda bisa diakses dari perangkat mana saja (HP, Laptop lain), Anda dapat menghubungkan Prioritask ke Google Sheets secara gratis.

1. Buka browser dan buat Google Spreadsheet baru di [sheets.new](https://sheets.new).
2. Pada menu atas Spreadsheet, klik **Ekstensi > Apps Script**.
3. Hapus kode bawaan, lalu salin dan tempel (Paste) skrip backend berikut:

```javascript
function doGet(e) {
  var db = SpreadsheetApp.getActiveSpreadsheet();
  var taskSheet = db.getSheetByName("TASKS") || db.insertSheet("TASKS");
  var paramSheet = db.getSheetByName("PARAMETER") || db.insertSheet("PARAMETER");

  var tasks = [];
  var rows = taskSheet.getDataRange().getValues();
  if(rows.length > 1) {
    for (var i = 1; i < rows.length; i++) {
      tasks.push({
        id: rows[i][0], title: rows[i][1], priority: rows[i][2],
        duration: rows[i][3], category: rows[i][4], targetDate: rows[i][5],
        completed: rows[i][6] === true || rows[i][6] === "true",
        notes: rows[i][7] || ""
      });
    }
  }

  var parameters = {};
  var paramData = paramSheet.getRange(1, 1).getValue();
  if (paramData) {
    try { parameters = JSON.parse(paramData); } catch(e) {}
  }

  return ContentService.createTextOutput(JSON.stringify({tasks: tasks, parameters: parameters})).setMimeType(ContentService.MimeType.JSON);
}

function doPost(e) {
  var db = SpreadsheetApp.getActiveSpreadsheet();
  var taskSheet = db.getSheetByName("TASKS") || db.insertSheet("TASKS");
  var paramSheet = db.getSheetByName("PARAMETER") || db.insertSheet("PARAMETER");

  var data = JSON.parse(e.postData.contents);
  var action = data.action;

  if (action === "update_config") {
    paramSheet.getRange(1, 1).setValue(JSON.stringify(data.parameters));
    return ContentService.createTextOutput(JSON.stringify({success: true})).setMimeType(ContentService.MimeType.JSON);
  }

  if (taskSheet.getLastRow() == 0) {
    taskSheet.appendRow(["ID", "Title", "Priority", "Duration", "Category", "TargetDate", "Completed", "Notes"]);
  } else if (taskSheet.getRange(1, 8).getValue() === "") {
    taskSheet.getRange(1, 8).setValue("Notes");
  }
  var rows = taskSheet.getDataRange().getValues();

  if (action === "create") {
    taskSheet.appendRow([data.id, asText(data.title), data.priority, data.duration, data.category, data.targetDate, data.completed, asText(data.notes)]);
  } else if (action === "update") {
    for (var i = 1; i < rows.length; i++) {
      if (rows[i][0] == data.id) {
        taskSheet.getRange(i + 1, 2).setValue(asText(data.title));
        taskSheet.getRange(i + 1, 3).setValue(data.priority);
        taskSheet.getRange(i + 1, 4).setValue(data.duration);
        taskSheet.getRange(i + 1, 5).setValue(data.category);
        taskSheet.getRange(i + 1, 6).setValue(data.targetDate);
        taskSheet.getRange(i + 1, 7).setValue(data.completed);
        taskSheet.getRange(i + 1, 8).setValue(asText(data.notes));
        break;
      }
    }
  } else if (action === "delete") {
    for (var i = 1; i < rows.length; i++) {
      if (rows[i][0] == data.id) {
        taskSheet.deleteRow(i + 1);
        break;
      }
    }
  }
  return ContentService.createTextOutput(JSON.stringify({success: true})).setMimeType(ContentService.MimeType.JSON);
}

// Simpan teks apa adanya (cegah teks seperti "=..." dibaca sebagai rumus)
function asText(value) {
  var text = value == null ? "" : String(value);
  return /^[=+\-@]/.test(text) ? "'" + text : text;
}
```

4. Klik tombol **Terapkan (Deploy)** > **Penerapan Baru (New Deployment)**.
5. Pilih jenis (Select type): **Aplikasi Web (Web App)**.
6. Akses: Ubah menjadi **Siapa saja (Anyone)**.
7. Klik Deploy, lalu salin **URL Web App** yang diberikan.
8. Buka kembali aplikasi Prioritask Anda, klik tombol indikator **"Penyimpanan lokal"** di menu atas.
9. Paste URL Web App tersebut ke dalam kolom yang tersedia dan simpan.

> **Sudah memakai versi lama skripnya?** Tempel ulang skrip di atas, lalu buka **Terapkan > Kelola penerapan > Edit (ikon pensil) > Versi: Versi baru > Terapkan** agar URL lama tetap dipakai. Tanpa langkah ini, catatan tugas hanya tersimpan di browser.

Kini data Anda akan tersinkronisasi otomatis dengan Google Spreadsheet pada dua tab berbeda: `TASKS` (untuk daftar tugas) dan `PARAMETER` (untuk JSON konfigurasi kustom).

---

## 🎨 Modifikasi Lanjutan

Bagi pengembang yang ingin memodifikasi kode UI:

* **Warna Bawaan CSS**: Anda bisa mengatur warna bawaan dasar sebelum Javascript berjalan pada blok `<style>` di tag `:root`.
* **Komponen UI**: Kelas komponen (`.card`, `.btn`, `.chip`, `.input`, `.task-card`, dll.) didefinisikan di blok `<style type="text/tailwindcss">` sehingga mudah diubah dari satu tempat.
* **Struktur Modal**: Semua modal & panel memakai kelas `.modal` (dibuka dengan `openModal(id)`), bisa ditutup dengan `Esc` atau klik area luar. Layar kunci PIN berada di lapisan paling atas (`z-[60]`).
