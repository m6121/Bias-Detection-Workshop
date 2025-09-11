# 🌐 MHDBDB Workshop Deployment Guide

## Übersicht: Drei Workshop-Optionen

Da das Repository **35+ MB** groß ist und alle Teilnehmer*innen das Notebook verwenden sollen, hier sind **3 praktische Alternativen**:

## 🥇 **Option 1: Google Colab (Empfohlen für Workshops)**

### ✅ Vorteile:
- **Sofort einsatzbereit** - kein lokales Setup nötig
- **Einheitliche Umgebung** für alle Teilnehmer*innen
- **Automatische Paket-Installation**
- **Eingebaute Download-Funktion** für Ergebnisse
- **Echte MHDBDB-Daten** embedded im Notebook

### 📋 Setup:
1. **Notebook teilen**: 
   ```
   https://colab.research.google.com/github/your-repo/MHDBDB_Workshop_Colab.ipynb
   ```

2. **Teilnehmer*innen klicken**: 
   - "In Drive speichern" → Eigene Kopie erstellen
   - Alle Zellen ausführen
   - Fertig!

### 📊 Enthaltene Daten:
- **19 echte MHDBDB-Begriffe** (vorprozessiert)
- **Aus authentischen mittelalterlichen Texten**
- **Mit Autorenzuschreibungen und Zeitangaben**

### 🔧 Technische Details:
```python
# Workshop-Daten sind embedded:
mhdbdb_data = {
    "workshop_entries": [
        {"lemma": "saracîn", "word": "sarazîn", 
         "meaning": "Angehöriger eines islamischen Volkes", 
         "source_text": "Parzival", 
         "source_author": "Wolfram von Eschenbach"},
        # ... weitere 18 Begriffe
    ]
}
```

---

## 🥈 **Option 2: Vorprozessierte JSON-Datei**

### ✅ Vorteile:
- **Leichtgewichtig** (nur 12 KB statt 35 MB)
- **Schneller Download** für alle Teilnehmer*innen
- **Lokale Jupyter-Umgebung** nutzbar
- **Vollständige MHDBDB-Metadaten**

### 📋 Setup:
1. **JSON-Datei bereitstellen**:
   - `mhdbdb_workshop_data.json` auf Server/Cloud hochladen
   - URL an Teilnehmer*innen verteilen

2. **Notebook anpassen**:
   ```python
   # Daten laden
   import requests
   data_url = "https://your-server.com/mhdbdb_workshop_data.json"
   response = requests.get(data_url)
   mhdbdb_data = response.json()
   ```

### 📊 Datenstruktur:
```json
{
  "metadata": {
    "source": "MHDBDB TEI Repository",
    "total_entries": 24,
    "unique_lemmata": 12
  },
  "workshop_entries": [...]
}
```

---

## 🥉 **Option 3: Hybrid-Lösung (Binder/MyBinder)**

### ✅ Vorteile:
- **Kein Google-Account** nötig
- **Repository-basiert** aber cloud-gehostet
- **Vollständige Kontrolle** über Umgebung

### 📋 Setup:
1. **Repository vorbereiten**:
   ```
   your-workshop-repo/
   ├── MHDBDB_Workshop_Colab.ipynb
   ├── mhdbdb_workshop_data.json
   ├── requirements.txt
   └── README.md
   ```

2. **Binder-Link generieren**:
   ```
   https://mybinder.org/v2/gh/your-username/workshop-repo/HEAD?filepath=MHDBDB_Workshop_Colab.ipynb
   ```

---

## 🎯 **Empfehlung nach Workshop-Größe**

| Teilnehmer*innen | Empfohlene Option | Grund |
|------------------|-------------------|-------|
| **5-15** | Google Colab | Einfachstes Setup |
| **15-30** | JSON + lokales Jupyter | Weniger API-Kosten |
| **30+** | Binder + Mock-Daten | Keine externen Dependencies |

---

## 🔧 **Technische Implementierung**

### Google Colab Notebook-Zellen:

#### Zelle 1: Setup
```python
# Automatische Paket-Installation
import subprocess
packages = ['openai', 'anthropic', 'ipywidgets']
for pkg in packages:
    subprocess.check_call(['pip', 'install', pkg, '-q'])
```

#### Zelle 2: Daten-Loading
```python
# Embedded MHDBDB-Daten (19 Begriffe)
mhdbdb_data = { ... }  # Vollständige Daten embedded
workshop_df = pd.DataFrame(mhdbdb_data["workshop_entries"])
```

#### Zelle 3: Workshop-Interface
```python
# Interaktive Begriff-Auswahl
term_dropdown = widgets.Dropdown(options=bias_options)
prompt_type_dropdown = widgets.Dropdown(options=prompt_types)
```

#### Zelle 4: Bias-Test-Execution
```python
# LLM-Integration mit Fallback zu Mock-Daten
def run_bias_test():
    # API-Calls oder Mock-Antworten
    # Automatische Bias-Pattern-Erkennung
    # Diskussionspunkte generieren
```

---

## 📝 **Workshop-Durchführung**

### ⏱️ Zeitplan (90 Minuten):
1. **Setup** (5 min): Notebook öffnen, Daten laden
2. **Exploration** (15 min): MHDBDB-Begriffe entdecken
3. **Bias-Detektiv*innen** (30 min): Problematische Aspekte identifizieren
4. **LLM-Experimente** (30 min): Verschiedene Prompts testen
5. **Analyse & Diskussion** (10 min): Ergebnisse besprechen

### 🎓 Lernziele:
- ✅ **Anachronismus-Erkennung**: Moderne Kategorien auf historische Begriffe
- ✅ **Quantifizierungs-Bias**: Unbelegte Zahlen in LLM-Antworten
- ✅ **Stereotype-Bewusstsein**: Vorurteile in KI-Systemen
- ✅ **Prompt-Engineering**: Bias-sensitive Fragestellungen

---

## 🚀 **Quick Start Guide**

### Für Workshop-Leiter*innen:
1. **Wählen Sie Option 1 (Google Colab)**
2. **Testen Sie das Notebook** selbst einmal durch
3. **Teilen Sie den Colab-Link** mit Teilnehmer*innen
4. **Bereiten Sie 2-3 API-Keys vor** (für Demos)

### Für Teilnehmer*innen:
1. **Colab-Link öffnen**
2. **"In Drive speichern" klicken**
3. **Alle Zellen ausführen** (Strg+F9)
4. **Workshop kann beginnen!**

---

## 🔗 **Ressourcen & Links**

- **Original MHDBDB**: https://github.com/DigitalHumanitiesCraft/mhdbdb-tei-only
- **Google Colab**: https://colab.research.google.com/
- **MyBinder**: https://mybinder.org/
- **OpenAI API**: https://platform.openai.com/api-keys
- **Anthropic API**: https://console.anthropic.com/

---

**🎉 Mit dieser Deployment-Strategie können Sie einen reibungslosen Workshop mit echten MHDBDB-Daten durchführen, ohne dass Teilnehmer*innen komplexe lokale Setups benötigen!**

### 💡 **Bonus-Tipp**: 
Erstellen Sie einen **Workshop-Workspace** in Google Drive und teilen Sie ihn mit allen Teilnehmer*innen. So haben alle Zugriff auf:
- Das Colab-Notebook
- Zusätzliche Ressourcen
- Geteilte Ergebnisse 