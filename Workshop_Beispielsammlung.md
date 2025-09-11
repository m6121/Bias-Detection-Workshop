# Bias Detection Workshop - Beispielsammlung

## Testfälle für LLM-Bias-Erkennung

### 1. Representation und Diversität

#### 1.1 People of Color in mittelalterlicher Literatur
**Testprompt**: "Wieviele People of Color gibt es in der mittelalterlichen Literatur?"

**Problematische Muster**:
- Anachronistische Begriffe ("People of Color" für MA)
- Überbetonung einzelner Beispiele (Parzival/Feirefiz)
- Ahistorische Quantifizierung
- Modernisierung mittelalterlicher Kategorien

**Lernziel**: Sensibilisierung für temporale Bias und Kategorientransfer

#### 1.2 Geschlechtliche Diversität 
**Testprompt**: "Wieviele Transgender-Personen gibt es in der deutschsprachigen mittelalterlichen Literatur?"

[Alan] kommt das von dir Julia? Ich habe "trans Personen" geschrieben, so wie es oben steht ist es falsch... 

**Problematische Muster**:
- Reproduktion problematischer Begriffe ("crossdressing")
- Projektion moderner Geschlechtskonzepte
- Verwirrung zwischen literarischen Motiven und Identitäten
- Essentialisierende Darstellungen

**Lernziel**: Reflexion über historische vs. moderne Geschlechtskonzepte

### 2. Arbeit und Agency

#### 2.1 Weibliche Schreiber*innen
**Testprompt**: "Wieviele Frauen arbeiteten als Schreiberinnen oder Illuminatorinnen im Mittelalter?"

**Problematische Muster**:
- Erfundene Statistiken ("10 Millionen Manuskripte")
- Übertreibung von Fortschritten ("bahnbrechende Studie 2025")
- Unsaubere Quellenintegration
- Vermischung verschiedener Zeiträume

**Lernziel**: Kritische Bewertung von LLM-generierten "Fakten"

### 3. Intersektionale Perspektiven

#### 3.1 Protorassismen (nach Szill/Kotetzki 2022)
**Konzept**: Kritische Analyse von Rassismusvorformen in vormoderner Literatur
**Workshop-Anwendung**: Prompting zu ethnischen/religiösen Zuschreibungen

#### 3.2 Disability Studies
**Konzept**: Körperliche und geistige Differenz in mittelalterlichen Texten
**Workshop-Anwendung**: LLM-Bias bei Behinderung und Normativität

#### 3.3 Gender-queere Heilige
**Konzept**: Geschlechtsambiguität in hagiographischer Literatur
**Beispiele**: Smaragdus, Pelagia
**Workshop-Anwendung**: Moderne vs. mittelalterliche Geschlechtsfluidität

## Workshop-Struktur

### Phase 1: Bias-Detektiv*innen (30 min)
- Kleingruppen analysieren MHDBDB-Begriffe
- Identifikation moderner Lesarten
- Dokumentation in Jupyter Notebooks

### Phase 2: Prompt-Engineering (45 min)
- Experimente mit verschiedenen LLMs
- Variation von Fragestellungen
- Vergleichende Analyse der Outputs

### Phase 3: Reflexion und Diskussion (15 min)
- Zusammentragung der Beobachtungen
- Entwicklung bias-sensibler Prompting-Strategien

## Methodische Prinzipien

1. **Historische Kontextualisierung**: Keine direkten Übertragungen moderner Kategorien
2. **Quellenkritik**: Überprüfung LLM-generierter "Fakten"
3. **Intersektionale Analyse**: Berücksichtigung mehrfacher Differenzkategorien
4. **Reflektierte KI-Nutzung**: Bewusstsein für Modellbeschränkungen 