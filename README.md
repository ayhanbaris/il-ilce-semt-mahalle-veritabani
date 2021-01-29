# il, ilçe, semt, mahalle veritabanı
Türkiye İl, İlçe, Semt, Mahalle Veritabanı MySQL formatında. Tablolar ve ve veri tek dosyadadır.

```
create table iller
(
    id     int unsigned auto_increment
        primary key,
    il_adi varchar(20) not null
)


create table ilceler
(
    id       int unsigned auto_increment
        primary key,
    il_id    int         not null,
    ilce_adi varchar(20) not null
)


create table semtler
(
    id       int unsigned auto_increment
        primary key,
    il_id    int         null,
    ilce_id  int         not null,
    semt_adi varchar(30) not null
)


create table mahalleler
(
    id          int unsigned auto_increment
        primary key,
    il_id       int         null,
    ilce_id     int         null,
    semt_id     int         not null,
    mahalle_adi varchar(90) not null,
    posta_kodu  varchar(5)  not null
)
```

Dikkat: iller plaka numarasına göre değil kendi id'sine göre girilmiştir. plaka numasasını aynıca kolon olarak ekleyebilirisiniz.

# Örnek Sorgular
Kocaeli'nin İlçeleri
```
SELECT * FROM il_ilce_mahalle.ilceler WHERE il_id=52
```

Darıca ilçesinin semtleri
```
SELECT * FROM il_ilce_mahalle.semtler WHERE ilce_id = 614
```

Darıca'nın tüm mahalleleri
```
SELECT * FROM il_ilce_mahalle.mahalleler WHERE ilce_id= 614
```

![alt text](https://github.com/ayhanbaris/il-ilce-semt-mahalle-veritabani/blob/main/daricanin-mahalleleri-ss.png?raw=true)



Kocaeli'nin tüm mahalleleri
```
SELECT * FROM il_ilce_mahalle.mahalleler WHERE il_id=52
```

Kocaeli'nin tüm semtleri
```
SELECT * FROM il_ilce_mahalle.semtler WHERE il_id=52
```


