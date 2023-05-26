# qurban

## Sequence: pendaftaran

```mermaid
sequenceDiagram
    participant sq as Jamaah /<br>Shohibul Qurban
    participant pa as Panitia
    participant vq as Vendor Hewan
    participant tj as Tim Jagal
    participant ex as External
    participant vt as Vendor Tenda
    participant im as Imam/Ustadz
    
    %%
    note over sq, pa: PENDAFTARAN
    sq->>pa: Mendaftar via WAG paguyuban
    sq->>pa: Transfer biaya qurban
    pa->>sq: Konfirmasi pembayaran via update status di WAG
    loop setiap pekan
      note left of pa: membuat flyer & count down
      pa->>sq: Reminder pendaftaran shohibul qurban
    end
    note left of pa: Bikin Google Form
    pa->>sq: Reminder isi detil nama SQ via Google Form
    sq->>pa: Isi form detil nama SQ

    %%
    note over vq, pa: PENGADAAN HEWAN QURBAN
    pa->>vq: Survey hewan dan booking hewan
    pa->>vq: (Perlu) Bayar DP ?
    pa->>vq: Titip hewan sampai hari H-1
    vq->>pa: Delivery hewan qurban di H-1

    %%
    note over pa, vt: SEWA TENDA
    pa->>vt: booking sewa tenda
    vt->>pa: Delivery tenda di H-1

    %%
    note over pa, im: KAJIAN TEMATIK IDUL ADHA
    note right of pa: alokasi budget
    note right of pa: Propose jadwal dan judul kajian tematik menyambut hr raya idul adha
    pa->>im: Book jadwal untuk kajian ahad
    loop setiap 2 pekan
      pa->>im: Konfirmasi jadwal kajian ahad
      note left of pa: bikin flyer kajian
      pa->>sq: Pengumuman kajian
      note right of pa: logistik, rekaman audio / video
      im->>pa: Membawakan kajian ahad
    end

    %%
    note over pa, im: SHOLAT IED
    pa->>im: Book jadwal sholat ied
    im->>pa: Menjadi imam sholat ied di hari H
    pa->>sq: Pengumuman penyelenggaraan sholat ied

    %%
    note over pa, tj: JAGAL & EKSEKUSI
    pa->>tj: Booking jadwal
    note right of pa: rapat internal untuk sepakat ttg syar'i compliance 
    pa->>tj: Briefing syar'i compliance

    note over pa, tj: EKSEKUSI QURBAN
    loop Untuk seluruh hewan qurban:
      pa->>tj: dispatch urutan eksekusi hewan qurban ke kamar sembelih
      note right of pa: dokumentasi eksekusi terlihat nama SQ dan hewan qurban"
      note right of pa: membacakan "qurban atas nama..."
      note left of tj: hewan qurban disembelih sampai mati
      note left of tj: dipindah ke kamar sebelah untuk dikuliti
    end
    
    %%
    note over pa, ex: Distribusi external
    pa->>ex: Survey mustahik
    pa->>ex: Survey partner masjid/musholla untuk distribusi

    note over sq, pa: Distribusi
    pa->>pa: Beli terpal, plastik daging, timbangan, tatakan
    pa->>sq: menimbang daging, packing, distribusi ke SQ
    pa->>sq: menimbang daging sesuai porsi SQL, packing, labeling nama SQ, penyerahan

    note over sq, pa: Laporan Amanah
    pa->>pa: membuat laporan
    pa->>sq: pelaporan via WAG
```

## Timeline

```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section PENDAFTARAN
    Mendaftar via WAG paguyuban: active,2023-05-21, 4w
    Reminder pendaftaran 1: 2023-05-28,1d 
    Reminder pendaftaran 2: 2023-06-04,1d
    Reminder pendaftaran 3: 2023-06-11,1d

    section PENGADAAN HEWAN QURBAN
    Survey hewan dan booking hewan: 2023-05-28, 1d
    Pembayaran DP: 2023-06-11, 1d
    Delivery hewan qurban di H-1: 2023-06-28, 1d

    section SEWA TENDA
    Delivery tenda di H-1: 2023-06-28, 1d

    section KAJIAN TEMATIK
    Book jadwal ustadz: b1, 2023-05-28, 3d
    Pengumuman kajian 1: pk1, after b1, 3d
    Persiapan logistik kajian 1: lk1, after pk1, 1d
    Deliver kajian 1: after lk1, 1d

    Book jadwal ustadz: b2, 2023-06-011, 3d
    Pengumuman kajian 2: pk2, after b2, 4d
    Persiapan logistik kajian 2: lk2, after pk2, 1d
    Deliver kajian 2: after lk2, 1d

    section SHOLAT IED
    Book jadwal imam: done, 2023-05-25, 1d

    section SEMBELIH QURBAN
    Book jadwal tim jagal qurban: done, 2023-05-21, 1d
    Persiapan tempat hewan qurban dan jagal: 2023-06-22, 7d
    Persiapan pembagian daging qurban: 2023-06-22, 7d
    
    section HARI-H
    Sholat Idul Adha: 2023-06-29,1d
```

## SUmmary Activity
```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section PENDAFTARAN
    Mendaftar via WAG paguyuban: active,2023-05-21, 4w
    Reminder pendaftaran 1: 2023-05-28,1d 
    Reminder pendaftaran 2: 2023-06-04,1d
    Reminder pendaftaran 3: 2023-06-11,1d

    section PENGADAAN HEWAN QURBAN
    Survey hewan dan booking hewan: 2023-05-28, 1d
    Pembayaran DP: 2023-06-11, 1d
    Delivery hewan qurban di H-1: 2023-06-28, 1d

    section KAJIAN TEMATIK
    Book jadwal ustadz: b1, 2023-05-28, 3d
    Pengumuman kajian 1: pk1, after b1, 3d
    Persiapan logistik kajian 1: lk1, after pk1, 1d
    Deliver kajian 1: after lk1, 1d

    Book jadwal ustadz: b2, 2023-06-011, 3d
    Pengumuman kajian 2: pk2, after b2, 4d
    Persiapan logistik kajian 2: lk2, after pk2, 1d
    Deliver kajian 2: after lk2, 1d

    section SHOLAT IED
    Book jadwal imam [Om Mirza]: done, 2023-05-25, 1d
    Sewa tenda: 2023-06-01,1d

    section SEMBELIH QURBAN
    Beli terpal dan timbangan: 2023-06-01,1d
    Book jadwal tim jagal qurban [Om Sobirin]: done, 2023-05-21, 1d
    Persiapan tempat hewan qurban dan jagal: 2023-06-22, 7d
    Persiapan pembagian daging qurban: 2023-06-22, 7d
    
    section HARI-H
    Sholat Idul Adha: 2023-06-29,1d
```
