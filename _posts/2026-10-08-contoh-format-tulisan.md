---
layout: post
title: "Contoh format tulisan: gambar, kode, kutipan, tabel"
description: "Panduan singkat format Markdown yang bisa dipakai di Blog Andu: daftar, kutipan, blok kode, tabel, dan gambar."
date: 2026-10-08 09:30:00 +0700
tags: [tutorial, markdown]
---
Tulisan ini memperlihatkan format yang bisa dipakai di blog.

<!--more-->

## Teks dan tautan

Teks **tebal**, *miring*, dan [tautan ke GitHub Pages](https://pages.github.com).

## Daftar

- Poin pertama
- Poin kedua
  - Poin turunan

## Kutipan

> Menulis adalah cara paling sederhana untuk memahami apa yang kita pikirkan.

## Kode

```js
function sapa(nama) {
  return `Halo, ${nama}!`;
}
```

## Tabel

| Fitur | Keterangan |
|-------|------------|
| Cari  | Pencarian di halaman Cari |
| RSS   | Tersedia di /feed.xml |
| Tema  | Terang dan gelap |

## Gambar dan pratinjau media sosial

Untuk gambar sampul yang juga dipakai sebagai pratinjau di WhatsApp, Facebook, dan X, tambahkan di front matter:

```yaml
image: /assets/images/nama-gambar.jpg
image_alt: Deskripsi singkat gambar
```

Ukuran ideal 1200 x 630 piksel. Untuk gambar di dalam isi tulisan:

{% raw %}
```markdown
![Deskripsi gambar]({{ '/assets/images/foto.jpg' | relative_url }})
```
{% endraw %}
