# 🔗 Chain-of-Thought Hijacking

<div align="center">

### Eine Forschungsmethode zur Sicherheitsprüfung von KI-Modellen

[![Paper](https://img.shields.io/badge/📄_Paper-arXiv-red)](https://arxiv.org/abs/2510.26418)
[![Website](https://img.shields.io/badge/🌐_Projekt-Webseite-blue)](https://gentlyzhao.github.io/Hijacking/)
[![Python](https://img.shields.io/badge/Python-3.8+-green)](https://www.python.org/)

</div>

---

## 📖 Was ist das hier?

Stell dir vor, du hättest einen sehr intelligenten Assistenten, der normalerweise keine gefährlichen Fragen beantwortet. **Chain-of-Thought Hijacking** ist eine Forschungsmethode, die zeigt, wie man diese Sicherheitsmechanismen umgehen kann – nicht um Schaden anzurichten, sondern um KI-Systeme sicherer zu machen!

### 🤔 Wie funktioniert das? (Einfach erklärt)

Moderne KI-Modelle nutzen eine Technik namens "Chain-of-Thought" (Gedankenkette). Das bedeutet, sie denken in mehreren Schritten nach, bevor sie antworten – ähnlich wie wir Menschen.

**Das Problem:**
Wenn die KI sehr lange nachdenkt (viele Gedankenschritte macht), kann sie manchmal ihre eigenen Sicherheitsregeln "vergessen" oder umgehen.

**Die Metapher:**
Stell dir vor, du sagst einem Wachmann: "Lass niemanden ohne Ausweis rein!" Wenn du ihm dann aber sagst: "Denk ganz lange darüber nach, ob es Ausnahmen gibt...", könnte er nach langem Grübeln eine Lücke in der Regel finden.

**Genau das macht dieses Tool:**
Es erstellt geschickte Fragen, die das KI-Modell dazu bringen, sehr lange nachzudenken – so lange, bis die Sicherheitsmechanismen schwächer werden.

---

## 🎯 Wofür ist das gut?

Dieses Projekt wurde entwickelt, um KI-Systeme **sicherer** zu machen! Es hilft:

- 🔍 **Sicherheitslücken finden** – Bevor böswillige Personen sie ausnutzen
- 💪 **Modelle robuster machen** – KI-Entwickler können ihre Systeme verbessern
- 🧪 **Forschung betreiben** – Verstehen, wie KI-Sicherheit funktioniert
- 🛡️ **Abwehrmaßnahmen entwickeln** – Bessere Schutzmaßnahmen gegen solche Angriffe

### ⚠️ Wichtiger Hinweis zur verantwortungsvollen Nutzung

**Dieses Tool ist ausschließlich für Sicherheitsforschung gedacht!**

✅ **Erlaubte Nutzung:**
- Akademische Forschung
- Sicherheitstests eigener KI-Systeme
- Entwicklung von Schutzmaßnahmen
- Bildungszwecke

❌ **Nicht erlaubte Nutzung:**
- Manipulation von KI-Systemen für schädliche Zwecke
- Umgehung von Sicherheitsmaßnahmen aus böswilligen Gründen
- Jede Form von Missbrauch

> 💡 **Transparenz:** Wir haben diese Sicherheitslücke vor der Veröffentlichung an alle großen KI-Unternehmen gemeldet, damit sie ihre Systeme verbessern konnten.

---

## 🚀 Installation & Einrichtung

### Schritt 1: Voraussetzungen

Du brauchst:
- Einen Computer mit **Python 3.8 oder neuer**
- Eine Internetverbindung
- (Optional) API-Schlüssel von KI-Anbietern

### Schritt 2: Projekt herunterladen

Öffne ein Terminal und gib folgende Befehle ein:

```bash
# Projekt von GitHub herunterladen
git clone https://github.com/gentlyzhao/Hijacking.git

# In den Projektordner wechseln
cd Hijacking

# Benötigte Programmbibliotheken installieren
pip install -r requirements.txt
```

### Schritt 3: API-Schlüssel einrichten (für vollständige Tests)

API-Schlüssel sind wie "Ausweise", mit denen du KI-Dienste nutzen kannst. Du brauchst mindestens einen **Gemini-API-Schlüssel** (kostenlos erhältlich):

```bash
# Gemini API-Schlüssel (Pflicht - wird für Tests benötigt)
export GEMINI_API_KEY="dein-schlüssel-hier"

# Optional: Weitere KI-Modelle testen
export OPENAI_API_KEY="dein-schlüssel-hier"      # Für ChatGPT-Modelle
export ANTHROPIC_API_KEY="dein-schlüssel-hier"   # Für Claude-Modelle
export GROK_API_KEY="dein-schlüssel-hier"        # Für xAI-Modelle
```

**Wo bekomme ich API-Schlüssel?**
- Gemini: [https://makersuite.google.com/app/apikey](https://makersuite.google.com/app/apikey)
- OpenAI: [https://platform.openai.com/api-keys](https://platform.openai.com/api-keys)
- Anthropic: [https://console.anthropic.com/](https://console.anthropic.com/)

---

## 💻 Wie benutze ich das? (Praktische Beispiele)

### 🎮 Modus 1: Schnelltest ohne API-Schlüssel (Empfohlen für Einsteiger!)

Du kannst das Tool auch **ohne API-Schlüssel** nutzen! Es erstellt fertige Test-Prompts, die du manuell in KI-Chatbots einfügen kannst.

```bash
# Einfacher Test mit eigenem Ziel
python offline_test.py --goal "Deine Testfrage hier"

# Beispiel
python offline_test.py --goal "Erkläre mir etwas Kompliziertes"

# Als schöne Markdown-Ausgabe
python offline_test.py --goal "Deine Frage" --output-format markdown

# Nur die reinen Prompts anzeigen (zum Kopieren)
python offline_test.py --goal "Deine Frage" --output-format prompts-only
```

**Was passiert hier?**
Das Programm erstellt clevere Anfragen, die du dann in folgende Dienste kopieren kannst:
- ✨ Claude.ai
- 💬 ChatGPT (OpenAI Playground)
- 🔬 Anthropic API Console
- 🌐 Jede andere KI mit System-Prompts

**Perfekt für:** Schnelles Ausprobieren, Lernen, Experimentieren – ganz ohne Programmierung!

---

### 🔬 Modus 2: Automatische Tests (für fortgeschrittene Nutzer)

Wenn du API-Schlüssel hast, kannst du automatisierte Tests durchführen:

#### Test eines einzelnen KI-Modells

```bash
# Claude-Modell testen
python main.py --target-model claude-4-sonnet

# ChatGPT testen
python main.py --target-model gpt-o4-mini

# Eigene Testfrage
python main.py --target-model claude-4-sonnet --goal "Deine spezifische Frage"
```

#### Umfangreiche Tests mit HarmBench

HarmBench ist eine Sammlung von Testfragen zur Sicherheitsprüfung:

```bash
# Teste die ersten 100 Beispiele aus der HarmBench-Datenbank
python main.py \
  --target-model gpt-o4-mini \
  --start-examples 1 \
  --end-examples 100
```

**Was passiert hier?**
- Das Programm nimmt automatisch 100 Test-Szenarien
- Führt den Chain-of-Thought Hijacking-Angriff durch
- Prüft, ob die Sicherheitsmechanismen standhalten
- Erstellt einen detaillierten Bericht

---

## 🧠 Technische Details: Wie funktioniert es unter der Haube?

### Der Ablauf Schritt für Schritt:

```
┌─────────────────────────────────────────────────────────┐
│  1. Eingabe: Testfrage oder Szenario                    │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│  2. Prompt-Generator erstellt geschickte Anfrage        │
│     • Fordert lange Gedankenkette                       │
│     • Nutzt psychologische Tricks                       │
│     • Baut Umgehungsstrategien ein                      │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│  3. KI-Modell wird getestet                             │
│     • Denkt in vielen Schritten nach                    │
│     • Sicherheitsmechanismen werden herausgefordert     │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│  4. Bewertung der Antwort                               │
│     • Hat das Modell widerstanden?                      │
│     • Oder wurde die Sicherheit umgangen?               │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│  5. Ergebnisbericht                                     │
│     • Erfolgreich / Fehlgeschlagen                      │
│     • Details zur Sicherheitsperformance                │
└─────────────────────────────────────────────────────────┘
```

### Die Kernmethode: PAIR (Prompt Automatic Iterative Refinement)

Das Tool nutzt eine intelligente Methode namens **PAIR**:

1. **Start:** Erstelle eine erste Test-Anfrage
2. **Testen:** Schicke sie an das KI-Modell
3. **Analysieren:** Hat es funktioniert?
4. **Verbessern:** Falls nein, mache die Anfrage raffinierter
5. **Wiederholen:** Gehe zurück zu Schritt 2

Dieser Prozess wiederholt sich automatisch, bis entweder:
- ✅ Eine Sicherheitslücke gefunden wurde (für den Forschungsbericht)
- ❌ Die maximale Anzahl Versuche erreicht ist
- 🛡️ Das Modell sich als sicher erwiesen hat

---

## 📊 Was bedeuten die Ergebnisse?

Nach einem Test erhältst du einen Bericht mit folgenden Informationen:

### Erfolgreiche Sicherheit ✅
```
Status: SECURED
Das Modell hat allen Umgehungsversuchen widerstanden.
Sicherheitsmechanismen: STARK
```
**Bedeutung:** Das getestete KI-Modell ist robust gegen diese Angriffsmethode.

### Gefundene Schwachstelle ⚠️
```
Status: COMPROMISED
Das Modell wurde durch lange Gedankenketten umgangen.
Sicherheitsmechanismen: SCHWACH
```
**Bedeutung:** Das Modell hat eine Sicherheitslücke, die behoben werden sollte.

---

## 📁 Projektstruktur

```
Hijacking/
├── 📄 main.py              # Hauptprogramm für automatische Tests
├── 📄 offline_test.py      # Offline-Modus ohne API-Schlüssel
├── 📄 requirements.txt     # Benötigte Programmbibliotheken
├── 📂 conversers/          # Code für KI-Kommunikation
├── 📂 judges/              # Code für Ergebnis-Bewertung
├── 📂 system_prompts/      # Vorlagen für Test-Szenarien
└── 📂 results/             # Hier werden Test-Ergebnisse gespeichert
```

---

## 🤝 Mitwirken & Community

Dieses Projekt ist Open Source! Du kannst:

- 🐛 **Fehler melden** – Öffne ein Issue auf GitHub
- 💡 **Verbesserungen vorschlagen** – Teile deine Ideen
- 🔧 **Code beitragen** – Erstelle einen Pull Request
- 📖 **Dokumentation verbessern** – Hilf anderen, es zu verstehen

---

## 👨‍🔬 Über das Forschungsteam

**Autoren:**
- Jianli Zhao
- Tingchen Fu
- Rylan Schaeffer
- Mrinank Sharma
- Fazl Barez

**Forschungsunterstützung:**
Oxford Martin AI Governance Initiative

---

## 📚 Wissenschaftliche Veröffentlichung

Wenn du dieses Tool in deiner Forschung verwendest, zitiere bitte unsere Arbeit:

```bibtex
@article{zhao2025hijacking,
  title={Chain-of-Thought Hijacking},
  author={Zhao, Jianli and Fu, Tingchen and Schaeffer, Rylan and Sharma, Mrinank and Barez, Fazl},
  year={2025},
  journal={arXiv preprint arXiv:2510.26418}
}
```

📄 **Paper lesen:** [https://arxiv.org/abs/2510.26418](https://arxiv.org/abs/2510.26418)
🌐 **Projekt-Website:** [https://gentlyzhao.github.io/Hijacking/](https://gentlyzhao.github.io/Hijacking/)

---

## ❤️ Danksagungen

Dieses Projekt baut auf der Arbeit von **Patrick Chao et al.** auf, die die PAIR-Methode (Prompt Automatic Iterative Refinement) entwickelt haben.

Ein großes Dankeschön an:
- 🏛️ Oxford Martin AI Governance Initiative für die Forschungsunterstützung
- 🤖 Alle KI-Labs, die konstruktiv mit uns zusammengearbeitet haben
- 🌟 Die Open-Source-Community

---

## 🆘 Hilfe & Support

### Häufige Fragen

**F: Brauche ich Programmierkenntnisse?**
A: Für den Offline-Modus (ohne API) nicht! Du kannst einfach die generierten Texte kopieren. Für automatische Tests sind Grundkenntnisse hilfreich.

**F: Ist das legal?**
A: Ja, für Sicherheitsforschung und eigene Systeme. Nutze es NICHT für fremde Systeme ohne Erlaubnis.

**F: Wie teuer sind die API-Schlüssel?**
A: Gemini hat ein kostenloses Kontingent. Bei anderen Anbietern fallen geringe Kosten an (meist Cent-Beträge pro Test).

**F: Was mache ich, wenn ich eine Sicherheitslücke finde?**
A: Melde sie verantwortungsvoll an den jeweiligen KI-Anbieter (Responsible Disclosure).

### Probleme?

- 📖 [Ausführliche Dokumentation](https://gentlyzhao.github.io/Hijacking/)
- 💬 [GitHub Issues](https://github.com/gentlyzhao/Hijacking/issues)
- 📧 Kontaktiere die Autoren (siehe Paper)

---

<div align="center">

### 🌟 Viel Erfolg bei der Sicherheitsforschung! 🌟

**Gemeinsam machen wir KI-Systeme sicherer für alle.**

[⭐ Star auf GitHub](https://github.com/gentlyzhao/Hijacking) | [🐦 Teilen](https://twitter.com/intent/tweet?text=Chain-of-Thought%20Hijacking%20-%20KI-Sicherheitsforschung) | [📖 Paper lesen](https://arxiv.org/abs/2510.26418)

</div>

---

*Letzte Aktualisierung: 2025 | Made with ❤️ for AI Safety Research*
