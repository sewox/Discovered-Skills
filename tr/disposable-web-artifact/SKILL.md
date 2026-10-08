---
name: disposable-web-artifact
description: Çok adımlı süreçleri, protokolleri ve algoritmaları etkileşimli denetimlerle (butonlar, durum göstergeleri, günlükler) görselleştiren bağımsız, tek dosyalık HTML/CSS/JS simülasyonları üretir. İnteraktif web sayfası, adım adım simülatör veya tek kullanımlık araç istendiğinde kullanın.
---
# Tek Kullanımlık İnteraktif Web Simülasyonu

Soyut ve çok adımlı teknik süreçleri; tıklanabilir, adım adım ilerleyen, harici bağımlılığı olmayan tek dosyalık ("kullan & sil") interaktif HTML/CSS/JS görsel simülatörlerine dönüştürür.

## Ne Zaman Kullanılır?

- Kullanıcı bir konuyu anlamak veya incelemek için interaktif bir web sayfası/simülasyon istediğinde
- Çok aşamalı protokoller (OAuth2 el sıkışması, TLS anlaşması, iki fazlı taahhüt / 2PC) açıklanırken
- Statik metin veya şemaların yetersiz kaldığı, kullanıcının butonlarla adım adım ilerleyip parametreleri görmek istediği durumlarda
- Anında tarayıcıda çalıştırılabilecek hafif ve bağımsız bir görselleştirme gerektiğinde

## Simülasyonun Yapısı

### 1. Tek Dosyada Bağımsız Tasarım
- Tüm kodlar (HTML5, modern CSS ve saf Vanilla JavaScript) tek bir `.html` dosyasında yer alır.
- Sıfır dış bağımlılık: Harici CDN, kütüphane veya internet bağlantısı gerektiren fontlar kullanılmaz. Sistem fontları ve satır içi SVG ikonlar tercih edilir.

### 2. Etkileşimli Bileşenler
- **Adım Yöneticisi:** "Önceki", "Sonraki" ve "Sıfırla" butonları ile adım göstergesi (Örn: "Adım 3 / 12").
- **Görsel Sahne:** Aktörleri, aktif iletişim kanallarını ve hareket eden veri paketlerini gösteren dinamik alan.
- **Parametre & Günlük Paneli:** O anki adımda gönderilen HTTP başlıklarını, JSON gövdelerini, jetonları ve durum değişkenlerini gösteren inceleme penceresi.
- **Kanal Ayrımı:** Ön Kanal (tarayıcıdan geçen) ve Arka Kanal (sunucular arası doğrudan) iletişimlerini farklı renk ve çizgilerle vurgular.

## Uygulama Adımları

1. Süreci mantıksal, numaralandırılmış aşamalara böl (genellikle 6-12 adım).
2. Her adım için ilgili aktörleri, veri yüklerini ve durum değişikliklerini tanımla.
3. Koyu ve açık tema uyumlu, temiz ve erişilebilir anlamsal HTML/CSS yaz.
4. Adım butonlarıyla tetiklenen saf JavaScript durum yönetimini bağla.
5. Kullanıcının doğrudan tarayıcıda açıp kullanabileceği eksiksiz kodu sun.

## Dikkat Edilecek Noktalar (Gotchas)

- Çevrimdışı ortamlarda çalışmayı bozacak harici kütüphaneler (Bootstrap, jQuery, Google Fonts) ekleme.
- Adımlarda geriye gidildiğinde durumun tutarsız kalmaması için durum sıfırlama mantığını kusursuz kur.
