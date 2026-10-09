# Discovered Skills 🧠⚡

> A growing, curated repository of modular, battle-tested AI skills and operational workflows designed for autonomous agents, developers, and LLM-assisted engineering.

[🇹🇷 Türkçe](#türkçe-açıklama) | [🇬🇧 English](#english-overview)

---

## English Overview

**Discovered Skills** is an open, scalable knowledge hub of structured AI capabilities (skills). Rather than generic prompts, each skill in this repository encapsulates a domain-specific methodology, strict constraints, and repeatable execution steps that modern AI agents (such as Gemini Spark, Claude Projects, Cursor, and custom LLM workflows) can autonomously invoke.

### 🗂️ Skill Catalog

| Category | Skill | Description | Primary Triggers |
| :--- | :--- | :--- | :--- |
| **📝 Documentation & Standards** | [`ste-tech-writer`](./ste-tech-writer/) | Enforces ASD-STE100 aerospace precision and TDK language rules. Active voice, max 20 words, unambiguous technical terms. | `"Explain simply"`, `"Sade dille yaz"`, `"ASD-STE100"` |
| **🏗️ Architecture & Flows** | [`flow-diagrammer`](./flow-diagrammer/) | Replaces dense technical narratives with Mermaid sequence diagrams, flowcharts, and terminal-friendly ASCII charts. | `"Şemasını çiz"`, `"Draw sequence diagram"`, `"Akışı görselleştir"` |
| **⚡ Interactive Tooling** | [`disposable-web-artifact`](./disposable-web-artifact/) | Generates zero-dependency, self-contained single-file HTML/CSS/JS visualizers with step controls and parameter inspectors. | `"HTML olarak hazırla"`, `"Interactive simulation"`, `"Kullan ve sil araç"` |
| **🔍 Debugging & Incident Triage** | [`triad-diff-debugger`](./triad-diff-debugger/) | Eliminates guesswork in production failures via a strict 3-pillar triage: *1. What changed? 2. What works? 3. What broke?* | `"Ne bozuldu?"`, `"Triage incident"`, `"Kök neden analizi"` |
| **💡 Ideation & Creative Strategy** | [`anti-cliche-ideator`](./anti-cliche-ideator/) | Generates breakthrough ideas by first mapping predictable AI clichés, treating them as negative boundaries to avoid. | `"Anti-cliche"`, `"Ezber fikir üretme"`, `"Farklı açı bul"` |

*(More categories and skills are continuously added: DevOps & Cloud, Database Tuning, Agent Workflows, and Domain Calculators).*

---

### 📦 Anatomy of a Skill

Each skill resides in its own isolated directory and follows the standardized Agent Skill format:

```text
skill-name/
├── SKILL.md            # Required: YAML frontmatter + detailed markdown instructions
├── SKILL.en.md         # Optional: English localization if default is Turkish
└── assets/             # Optional: Templates, reference scripts, or examples
```

#### Standard Frontmatter Specification

```yaml
---
name: skill-name
description: Clear, action-oriented trigger explanation defining WHAT the skill does and WHEN to invoke it.
---
```

---

### 🚀 How to Use

#### 1. In Gemini Spark / Agent Workspaces
Import or paste the `SKILL.md` content into your agent's skills manager or workspace instruction set.

#### 2. In Claude Projects / Custom GPTs
Upload the target `SKILL.md` directly into your Project Knowledge or Custom GPT Instructions.

#### 3. In Cursor / IDE Rules
Reference the skill file or copy its rules directly into your project's `.cursorrules` or `.windsurfrules`.

---

### 🤝 Contributing

We welcome contributions! To submit a newly discovered skill:

1. **Fork** the repository and create a new branch (`feat/add-my-skill`).
2. Create a new directory under root with a descriptive kebab-case name (`my-new-skill/`).
3. Add a complete `SKILL.md` adhering to the standard frontmatter and structural rules (imperative mood, verifiable instructions, zero filler text).
4. Update the **Skill Catalog** table in `README.md`.
5. Submit a **Pull Request**.

---

## Türkçe Açıklama

**Discovered Skills**, geliştiriciler, yazılım mimarları ve yapay zekâ etmenleri için sahada test edilmiş, sürekli genişleyen açık kaynaklı bir **AI beceri deposudur**. Sıradan sistem prompt'ları yerine; her beceri belirli bir mühendislik disiplinini, katı kısıtları ve adım adım işletim protokollerini içeren modüler bir yetenek paketidir.

### 🗂️ Beceri Kataloğu

* **📝 Dokümantasyon ve Standartlar (`ste-tech-writer`):** ASD-STE100 havacılık standartları ve TDK ilkeleriyle kurallı, etken çatılı ve yoruma kapalı teknik metinler üretir.
* **🏗️ Mimari ve Akış Şemaları (`flow-diagrammer`):** Karmaşık protokol ve servis iletişimlerini metin yerine Mermaid (`sequenceDiagram`, `flowchart`) ve ASCII şemalarına dönüştürür.
* **⚡ Etkileşimli Araçlar & Simülasyon (`disposable-web-artifact`):** Dış kütüphane bağımlılığı olmayan, tarayıcıda doğrudan çalışan tek dosyalık interaktif HTML/CSS/JS görsel simülatörleri oluşturur.
* **🔍 Hata Ayıklama & Olay Teşhisi (`triad-diff-debugger`):** Üretim ortamı kesintilerini ve regresyonları *"1. Ne değişti?, 2. Ne çalışıyor?, 3. Ne bozuldu?"* disipliniyle kök nedene indirger.
* **💡 İnovasyon & Tersine Fikir Geliştirme (`anti-cliche-ideator`):** İlk akla gelen yüzeysel yapay zekâ klişelerini negatif kısıt ilan edip, sınırın tamamen dışındaki özgün fikirleri üretir.

### 📌 Depo Vizyonu & Gelecek Planı

Bu depo sadece mevcut becerilerle sınırlı değildir. Düzenli olarak aşağıdaki alanlarda yeni beceriler eklenmeye devam edecektir:
- **Bulut & DevOps:** Kubernetes otomasyonları, CI/CD boru hatları ve konteyner optimizasyonları.
- **Veritabanı & Performans:** PostgreSQL sorgu optimizasyonu, indeksleme stratejileri ve kuyruk mimarileri.
- **Yapay Zekâ İş Akışları:** Çok etmenli (multi-agent) orkestrasyon, RAG boru hatları ve prompt kalıpları.

Katkıda bulunmak için depoyu fork'layabilir ve yeni beceri önerilerinizi Pull Request (PR) olarak iletebilirsiniz.

---

### 📄 Lisans
Bu depo açık kaynak topluluğu için [MIT Lisansı](./LICENSE) ile sunulmaktadır.
