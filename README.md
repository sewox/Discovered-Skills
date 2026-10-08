# Discovered Skills

A curated repository of high-impact AI skills extracted from proven methodologies, productivity workflows, and system debugging practices.

[🇹🇷 Türkçe Açıklama](#türkçe-açıklama) | [🇬🇧 English Description](#english-description)

---

## English Description

This repository contains modular AI skill definitions compatible with modern LLM agent ecosystems (Claude Projects/Artifacts, Gemini Spark Skills, Cursor, Codex, and OpenAI Custom GPTs).

### Repository Structure

```
Discovered-Skills/
├── en/                           # English Skills
│   ├── ste-tech-writer/          # Simplified Technical English (ASD-STE100)
│   ├── flow-diagrammer/          # Diagrams & Schemas over Prose (Mermaid/ASCII)
│   ├── disposable-web-artifact/  # Standalone Interactive HTML/JS Visualizers
│   └── triad-diff-debugger/      # Root-Cause Debugging (What changed, works, broke)
├── tr/                           # Türkçe Beceriler (TDK & STE-TR Uyumlu)
│   ├── ste-tech-writer/          # Sade Teknik Yazım (ASD-STE100 & TDK)
│   ├── flow-diagrammer/          # Metin Yerine Şema ve Diyagram Akışı
│   ├── disposable-web-artifact/  # Tek Kullanımlık İnteraktif Web Simülasyonu
│   └── triad-diff-debugger/      # Üçlü Kırılım Hata Ayıklayıcı
└── README.md
```

### Skills Overview

| Skill | Purpose | Key Trigger |
| :--- | :--- | :--- |
| **`ste-tech-writer`** | Enforces ASD-STE100 and Turkish Language Association (TDK) standards: active voice, kurallı cümle, max 20 words, unambiguous terminology. | "Explain simply", "ASD-STE100 kurallarına göre yaz" |
| **`flow-diagrammer`** | Replaces dense text with step-by-step Mermaid sequence diagrams, flowcharts, and terminal-friendly ASCII charts. | "Bunu yazıyla anlatma, şemasını çiz", "Draw sequence diagram" |
| **`disposable-web-artifact`** | Generates standalone single-file interactive HTML/CSS/JS visualizers with steppers, state inspectors, and channel separation. | "HTML olarak hazırla", "Adım adım simülasyon yap" |
| **`triad-diff-debugger`** | Enforces rigorous 3-pillar root-cause triage: *1. What changed? 2. What is still working? 3. What is broken?* | "Ne bozuldu?", "Triage production incident" |

---

## Türkçe Açıklama

Bu depo; karmaşık teknik konuları anlama, sistem tasarımı ve hata ayıklama süreçlerinde yapay zekâ modellerinden en yüksek verimi almak için geliştirilmiş modüler becerileri (skill) içerir.

### Becerilerin Özeti

1. **`ste-tech-writer` (Sade Teknik Yazım):**
   - Havacılık standardı olan ASD-STE100 ile Türk Dil Kurumu (TDK) yazım ve bilişim kurallarını harmanlar.
   - Yüklemi sonda kurallı cümleler, eylemin failini belirten etken çatı ve cümle başına tek yargı zorunluluğu getirir.
2. **`flow-diagrammer` (Metin Yerine Şema):**
   - Paragraflar dolusu metin yerine protokolleri (OAuth2, OIDC, TLS vb.) ve sistem akışlarını Mermaid sıra diyagramları ve ASCII tablolarıyla görselleştirir.
3. **`disposable-web-artifact` (Tek Kullanımlık Web Simülasyonu):**
   - Dış bağımlılığı olmayan (harici CDN/kütüphane içermeyen), tarayıcıda doğrudan çalışan, adım adım butonlu ve canlı parametre panelli interaktif HTML araçları üretir.
4. **`triad-diff-debugger` (Üçlü Kırılım Hata Ayıklayıcı):**
   - Ezbere tahminde bulunmayı engelleyerek 3 net soru üzerinden kök neden analizi yapar: *1. Ne değişti?, 2. Ne çalışıyor?, 3. Ne bozuldu?*.

### Nasıl Kullanılır?

İstediğiniz becerinin klasöründeki `SKILL.md` dosyasını Gemini Spark, Claude Project, Cursor veya kullandığınız etmen ortamının yetenekler/talimatlar bölümüne eklemeniz yeterlidir.

---

### Lisans & Katkı
Açık kaynak topluluğu ve bağımsız geliştiriciler için hazırlanmıştır. Katkılarınızı PR olarak gönderebilirsiniz.
