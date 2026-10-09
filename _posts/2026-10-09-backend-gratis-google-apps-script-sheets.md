---
layout: post
title: "Backend Gratis dengan Google Apps Script dan Sheets"
description: "Cara membuat aplikasi web tanpa server sendiri: Google Sheets sebagai database, Apps Script sebagai API, dan GitHub Pages sebagai tampilan."
date: 2026-10-09 08:00:00 +0700
tags: [tutorial, google-apps-script, web]
published: false   # hapus baris ini setelah tulisan selesai
# image: /assets/images/backend-gratis-apps-script.png
# image_alt: Diagram alur data dari GitHub Pages ke Apps Script dan Google Sheets
---
<!-- TARGET: 1.200-1.800 kata. Tulis dengan pengalaman Anda sendiri; ganti semua panduan di komentar. -->
<!-- PEMBUKA (2-3 paragraf): masalah nyata yang Anda hadapi (mis. butuh aplikasi kecil tanpa biaya server), apa yang akan dibangun, dan hasil akhirnya. Ini jadi ringkasan di beranda. -->

Tulis paragraf pembuka di sini.

<!--more-->

## Gambaran arsitektur

<!-- Jelaskan alur: tampilan (HTML di GitHub Pages) -> permintaan fetch -> Apps Script (doGet/doPost) -> Google Sheets. Sertakan 1 diagram buatan sendiri (alt text wajib). -->

## Kapan cara ini cocok, dan kapan tidak

<!-- Cocok: aplikasi internal, prototipe, data ribuan baris, pengguna puluhan. Tidak cocok: trafik tinggi, data sangat sensitif, butuh transaksi kompleks. Jujur soal batas ini; pembaca dan Google menghargainya. -->

## Langkah 1: menyiapkan Google Sheets

<!-- Contoh struktur sheet dari pengalaman Anda: sheet Data, Users, AuditLog. Jelaskan fungsi tiap sheet dan nama kolomnya. Sertakan tangkapan layar asli. -->

## Langkah 2: menulis API dengan Apps Script

<!-- Jelaskan doGet dan doPost. Contoh minimal di bawah, sesuaikan dan jelaskan baris per baris. -->

```js
function doPost(e) {
  const data = JSON.parse(e.postData.contents);
  const sheet = SpreadsheetApp.getActive().getSheetByName('Data');
  sheet.appendRow([new Date(), data.nama, data.catatan]);
  return ContentService
    .createTextOutput(JSON.stringify({ ok: true }))
    .setMimeType(ContentService.MimeType.JSON);
}
```

## Langkah 3: deploy sebagai web app

<!-- Menu Deploy > New deployment > Web app. Jelaskan pilihan "Execute as" dan "Who has access", serta kenapa URL deployment berubah jika salah memilih versi. -->

## Langkah 4: menghubungkan ke tampilan di GitHub Pages

<!-- Contoh fetch dari frontend. Bahas masalah CORS yang Anda temui dan solusinya (mis. kirim sebagai text/plain agar tidak memicu preflight). -->

## Keamanan yang sering terlewat

<!-- Validasi input di sisi server, jangan simpan kunci API di frontend, batasi akses, gunakan LockService agar penulisan bersamaan tidak bentrok, catat aktivitas di AuditLog. -->

## Batas kuota dan cara mengatasinya

<!-- Waktu eksekusi, jumlah panggilan harian, kecepatan membaca sheet besar. Sebutkan angka dari dokumentasi resmi terbaru dan cantumkan tautannya, karena batas bisa berubah. -->

## Kesimpulan

<!-- 1 paragraf: ringkasan, apa yang Anda pelajari, dan tautan ke tulisan lain di blog ini. -->
