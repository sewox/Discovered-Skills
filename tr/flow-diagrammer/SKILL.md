---
name: flow-diagrammer
description: Karmaşık teknik süreçleri, protokolleri ve algoritmaları uzun metinler yerine Mermaid şemaları, sıra diyagramları (sequence) ve ASCII akış tablolarına dönüştürür. 'Şemasını çiz', 'akışını görselleştir' veya metin yerine şema istendiğinde kullanın.
---
# Akış ve Şema Çizici (Metin Yerine Şema)

Uzun ve karmaşık metin anlatımlarını; anında kavranabilen, adım adım görselleştirilmiş Mermaid ve ASCII şemalarına dönüştürür.

## Ne Zaman Kullanılır?

- Kullanıcı bir süreci yazı yerine şema veya diyagram ile anlatmanı istediğinde ("Bunu yazıyla anlatma, şemasını çiz")
- Protokol el sıkışmaları (OAuth2, OIDC, TLS, WebSocket) açıklanırken
- Dağıtık mimari bileşenleri, veri boru hatları ve servis etkileşimleri modellenirken
- Karar ağaçları ve durum makineleri görselleştirilirken

## Şema Stratejisi

### 1. Sıra Diyagramları (Sequence Diagrams)
- Çok taraflı iletişimler için kullanılır (Tarayıcı <-> Uygulama Sunucusu <-> Yetki Sağlayıcı).
- Ön Kanal (tarayıcı üzerinden geçen) ve Arka Kanal (sunucular arası doğrudan) iletişimlerini net şekilde ayırır.
- Oklar üzerine kesin HTTP eylemlerini veya veri parametrelerini yazar (Örn: `POST /token {kod, doğrulayıcı}`).

### 2. Akış Şemaları ve Karar Ağaçları (Flowchart)
- Koşullu mantıklar, dallanmalar ve yeniden deneme (retry) döngüleri için kullanılır.
- Düğüm metinleri kısa ve öz tutulur (en fazla 4-5 kelime).

### 3. ASCII / Metin Şemaları
- Görsel render imkanı olmayan terminal ortamları için saf metin ASCII şemaları sunar.

## Uygulama Adımları

1. Süreçteki tüm aktörleri (İstemci, Önyüz, Ağ Geçidi, Mikroservis, Veritabanı) belirle.
2. Verinin ve kontrolün kronolojik akış sırasını çıkar.
3. Standart Mermaid kod blokları (`sequenceDiagram`, `flowchart TD/LR` veya `stateDiagram-v2`) üret.
4. Kritik denetim noktalarını (doğrulama, şifreleme, durum kontrolü) şema üzerinde işaretle.
5. Şemanın altına her kilit adım için tek cümlelik kısa bir özet ekle.

## Dikkat Edilecek Noktalar (Gotchas)

- Tek bir şemaya 6-7'den fazla aktör yığarak okunabilirliği bozma; gerekiyorsa alt şemalara böl.
- Yalnızca başarılı akışı (happy path) değil, hata ve zaman aşımı dallarını da şemaya dahil et.
