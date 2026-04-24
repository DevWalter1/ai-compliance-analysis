# 07 — Produktvision: AI Process Intelligence Platform

> **Korrigierte Vision (April 2025):** Nicht Shadow-Überwachung, sondern vollständige Transparenz über AI-Nutzung in Geschäftsprozessen.

---

## Das echte Problem

Unternehmen wissen nicht:
- **Wo** überall AI in ihren Prozessen steckt
- **Wie viel** AI in jedem Prozessanteil enthalten ist
- **Welche** AI-Tools in welchen Systemen laufen
- **Ob** sie compliant sind (EU AI Act)

> "Wir haben 47 Systeme, die irgendwie AI nutzen. Keiner weiß genau wo und wie viel."
> — CTO, Mittelständler

---

## Die Lösung: AI Process Intelligence

```
┌─────────────────────────────────────────────────────────────────┐
│              AI PROCESS INTELLIGENCE PLATFORM                    │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   EINGABE                    VERARBEITUNG              AUSGABE   │
│                                                                  │
│  ┌─────────────┐           ┌─────────────┐          ┌─────────┐ │
│  │ Approved AI │──────────►│  Process    │─────────►│ Unified │ │
│  │ (API Keys,  │           │  Mapping &  │          │Dashboard│ │
│  │  SSO, SDK)  │           │  AI % Calc  │          │         │ │
│  └─────────────┘           └─────────────┘          └────┬────┘ │
│         ▲                       ▲                        │      │
│         │                       │                        ▼      │
│  ┌──────┴──────┐          ┌─────┴──────┐          ┌──────────┐ │
│  │ Shadow AI   │          │ Business   │          │Compliance│ │
│  │ (optional,  │          │ Process    │          │  Reports │ │
│  │  Add-on)    │          │ Context    │          │          │ │
│  └─────────────┘          └────────────┘          └──────────┘ │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Kernkomponenten

### 1. Approved AI Governance (Core)

**Integration mit bekannten, genehmigten AI-Tools:**

| Kategorie | Beispiele | Erfassung |
|-----------|-----------|-----------|
| **Cloud LLMs** | OpenAI, Anthropic, Azure OpenAI | API-Key Monitoring, Usage Tracking |
| **Copilots** | GitHub Copilot, MS Copilot, Google Duet | SSO + API Integration |
| **AI SaaS** | Notion AI, Slack AI, Salesforce Einstein | OAuth, SCIM |
| **Custom Models** | Interne LLMs, Hugging Face | SDK/Agent |
| **RAG Systems** | Pinecone, Weaviate, Vector DBs | API Monitoring |

**Gemessene Metriken:**
- API-Call-Volumen pro System/Prozess
- Genutzte Modelle (GPT-4, Claude, etc.)
- Datenmengen (Input/Output Tokens)
- Kosten pro Prozess/Schritt
- Response-Zeiten, Fehlerraten

---

### 2. Process-Aware AI Tracking (Core)

**Das Unterscheidungsmerkmal:** Nicht nur "wer nutzt AI", sondern **"in welchem Prozess steckt wie viel AI?"**

```
Beispiel: Kreditvergabe-Prozess

┌─────────────────────────────────────────────────────────────┐
│ Schritt 1: Antragseingang                                   │
│ ├─ Menschlich: 100%                                         │
│ └─ AI-Anteil: 0%                                            │
├─────────────────────────────────────────────────────────────┤
│ Schritt 2: Dokumentenprüfung                                │
│ ├─ OCR (Azure AI): 25%                                      │
│ ├─ Fraud Detection (internes ML): 20%                       │
│ └─ Menschlich: 55%                                          │
├─────────────────────────────────────────────────────────────┤
│ Schritt 3: Risikobewertung                                  │
│ ├─ Credit Scoring Model (AI): 70%                           │
│ └─ Menschliche Überprüfung: 30%                             │
├─────────────────────────────────────────────────────────────┤
│ Schritt 4: Entscheidung                                     │
│ ├─ Empfehlungssystem (AI): 40%                              │
│ └─ Menschliche Entscheidung: 60%                            │
├─────────────────────────────────────────────────────────────┤
│ GESAMT: 40% AI-Anteil im Kreditvergabe-Prozess              │
│ Risk Level: HIGH (laut EU AI Act)                           │
│ Audit Trail: Vollständig dokumentiert ✓                     │
└─────────────────────────────────────────────────────────────┘
```

**Use Cases:**
- Kunden verlangen: "Dieses Projekt darf maximal 10% AI enthalten"
- Compliance: "High-Risk AI-Systeme müssen dokumentiert werden"
- Interne Transparenz: "Wo haben wir AI-Abhängigkeiten?"

---

### 3. Shadow AI Discovery (Add-on, optional)

**Nicht das Hauptprodukt, sondern Ergänzung:**

| Methode | Zweck | Priorität |
|---------|-------|-----------|
| **Browser Extension** | Erkennt nicht-genehmigte Web-Tools | Phase 2 |
| **Network Monitoring** | Erkennt API-Calls zu unbekannten Diensten | Phase 3 |
| **Endpoint Agents** | Erkennt lokale AI-Tools (Copilot, etc.) | Phase 3 |

**Wichtig:** Shadow AI ist **nur ein Input** für die Gesamtübersicht, nicht das Hauptziel.

---

## Technische Architektur

### Empfohlener Ansatz: Hybrid

```
┌─────────────────────────────────────────────────────────────────┐
│                     AI PROCESS INTELLIGENCE                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  LAYER 1: COLLECTION                                             │
│  ├─ SDK (für Custom Integration)                                │
│  ├─ API Gateway (für zentrale Kontrolle)                        │
│  ├─ Log Aggregation (für bestehende Systeme)                    │
│  └─ Browser Extension (für Shadow AI, optional)                 │
│                                                                  │
│  LAYER 2: PROCESSING                                             │
│  ├─ Event Stream (Kafka)                                        │
│  ├─ AI Call Classification                                      │
│  ├─ Process Context Mapping                                     │
│  └─ Cost & Risk Calculation                                     │
│                                                                  │
│  LAYER 3: STORAGE                                                │
│  ├─ Time-Series DB (Usage Metrics)                              │
│  ├─ Graph DB (Process Relationships)                            │
│  └─ Document Store (Audit Trails)                               │
│                                                                  │
│  LAYER 4: PRESENTATION                                           │
│  ├─ Process AI-Dashboard                                        │
│  ├─ Compliance Reports                                          │
│  ├─ Cost Attribution                                            │
│  └─ Audit Trail Viewer                                          │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Integrations-Optionen

### Option A: SDK (Empfohlen für Start)

```python
from aicompliance import ProcessAI

# Prozess-Kontext definieren
ai = ProcessAI(
    process_id="kreditvergabe",
    step_id="dokumentenpruefung",
    system_id="dms-prod-01"
)

# AI-Call wird automatisch geloggt mit Kontext
response = ai.openai.chat.completions.create(
    model="gpt-4",
    messages=[...]
)

# Ergebnis: "Kreditvergabe → Dokumentenprüfung → 1 API-Call → $0.023"
```

**Vorteile:**
- Granularer Kontext (Prozess, Schritt, System)
- Keine Architektur-Änderungen nötig
- Einfache Adoption

**Nachteile:**
- Code-Änderungen erforderlich
- Muss pro System integriert werden

---

### Option B: API Gateway

```
┌─────────┐     ┌─────────────┐     ┌─────────┐
│ System A│────►│ AI Gateway  │────►│ OpenAI  │
│ System B│────►│  (Proxy)    │────►│ Claude  │
│ System C│────►│             │────►│ Azure   │
└─────────┘     └─────────────┘     └─────────┘
                       │
                       ▼
              ┌─────────────────┐
              │ AI Compliance   │
              │ - Logging       │
              │ - Routing       │
              │ - Cost Tracking │
              └─────────────────┘
```

**Vorteile:**
- Zentrale Kontrolle
- Keine Code-Änderungen in Systemen
- Policy Enforcement möglich

**Nachteile:**
- Single Point of Failure
- Latenz
- Komplexere Integration

---

### Option C: Log Aggregation (Passive)

- Nutzt bestehende Logs (Application, CloudTrail, etc.)
- Pattern Matching für AI-Calls
- Keine Code-Änderungen

**Nachteile:**
- Reaktiv, nicht proaktiv
- Weniger Kontext
- Unvollständig

---

## Produkt-Roadmap (korrigiert)

### Phase 1: Process-Aware SDK (Monate 1-3)

**Ziel:** Erste Kunden mit SDK-Integration

**Features:**
- [ ] SDK für Python/Node.js
- [ ] Integration mit OpenAI, Anthropic
- [ ] Manuelle Process Mapping (Config-basiert)
- [ ] Dashboard: AI-Anteil pro Prozess
- [ ] Basic Compliance Reports

**Success Metrics:**
- 3 Pilotkunden
- 10+ Prozesse gemapped
- Klare AI-Prozentsätze sichtbar

---

### Phase 2: Gateway & Automation (Monate 4-6)

**Ziel:** Zentrale Kontrolle, automatisches Mapping

**Features:**
- [ ] API Gateway für zentrale AI-Routing
- [ ] Automatische Process Discovery
- [ ] Integration mit SSO (Okta, Azure AD)
- [ ] Cost Attribution pro Prozess
- [ ] EU AI Act Compliance Checks

**Success Metrics:**
- 10 zahlende Kunden
- 50+ Prozesse gemapped
- $10k MRR

---

### Phase 3: Shadow AI & Enterprise (Monate 7-12)

**Ziel:** Vollständige Sichtbarkeit, Enterprise-Features

**Features:**
- [ ] Browser Extension (Shadow AI)
- [ ] Network-Level Monitoring
- [ ] Process Mining Integration
- [ ] Enterprise SSO, RBAC
- [ ] Automated Remediation

**Success Metrics:**
- $100k ARR
- 3 Enterprise-Kunden
- 200+ Prozesse gemapped

---

## Positionierung vs. Wettbewerb

| Anbieter | Ihr Fokus | Unser Fokus |
|----------|-----------|-------------|
| **Credo AI** | Governance, Risk Scoring | ✅ Process-Aware Tracking |
| **Fiddler** | Model Performance | ✅ Business Process Context |
| **Arize** | ML Observability | ✅ AI-Anteil in Prozessen |
| **Datadog** | Infrastructure | ✅ AI-specific Process Intelligence |

**Unser USP:**
> "Die einzige Plattform, die zeigt, **wo und wie viel AI in deinen Geschäftsprozessen steckt** — nicht nur technisches Monitoring, sondern Business Context."

---

## Use Cases (korrigiert)

### Use Case 1: Kunden-Compliance-Nachweis

**Szenario:** Kunde in Verteidigungsindustrie verlangt: "Maximal 5% AI in diesem Projekt"

**Lösung:**
- Prozess wird in Plattform gemapped
- Jeder AI-Call wird erfasst und gewichtet
- Dashboard zeigt: "Projekt X: 3.2% AI-Anteil"
- Audit-Trail beweist Compliance

**Value:** Vertragsabschluss, Vertrauen

---

### Use Case 2: EU AI Act High-Risk Identification

**Szenario:** Unternehmen muss High-Risk AI-Systeme identifizieren

**Lösung:**
- Plattform klassifiziert Prozesse automatisch
- "Kreditscoring: 70% AI → HIGH RISK"
- Auto-generierte Dokumentation
- Compliance-Workflows

**Value:** Strafvermeidung, Audit-Readiness

---

### Use Case 3: AI Cost Attribution

**Szenario:** Welche Abteilung verursacht welche AI-Kosten?

**Lösung:**
- Jeder AI-Call wird einem Prozess/Team zugeordnet
- "Marketing: $5.200/Monat (Midjourney, GPT-4)"
- "Engineering: $12.800/Monat (Copilot, interne Modelle)"

**Value:** Budget-Transparenz, Optimierung

---

### Use Case 4: AI Dependency Mapping

**Szenario:** Was passiert, wenn OpenAI ausfällt?

**Lösung:**
- Plattform zeigt: "47 Prozesse abhängig von OpenAI"
- "12 Prozesse kritisch, 35 nice-to-have"
- Alternative Modelle vorschlagen

**Value:** Business Continuity, Risk Management

---

## Erweiterung: Cost Attribution (Nice-to-have)

> **Wichtig:** Reines Cost-Tracking ist kommoditisiert (Entropic, OpenAI, Azure bieten das bereits). Unser Mehrwert ist **Process-Aware Cost Attribution**.

### Was wir zusätzlich bieten

| Anbieter-Dashboard | Unsere Plattform |
|-------------------|------------------|
| "API Key 'eng-001': €5.000" | "Kreditvergabe → Dokumentenprüfung: €5.000 (OCR + Fraud Detection)" |
| "2,3M Tokens" | "2,3M Tokens in HIGH-RISK Prozess ohne Audit-Trail" |
| Isolierte Sicht | Cross-Tool Aggregation + Process Context + Compliance Status |

**Fazit:** Cost-Tracking ist **kein Hauptverkaufsargument**, sondern ein **zusätzlicher Nutzen** der Process Intelligence.

---

## Fazit

**Die korrigierte Vision:**
- ❌ Kein "Shadow AI Spyware"
- ✅ **AI Process Intelligence Platform**
- Fokus auf **genehmigte Tools** und **Prozess-Transparenz**
- Shadow AI als **optionale Ergänzung**, nicht Hauptprodukt

**Der Wert:**
- Unternehmen wissen endlich, **wo und wie viel AI** sie nutzen
- Compliance ist **nachweisbar**
- Kunden können **AI-Anteile garantieren**
- Interne **Kosten und Risiken** sind transparent

---

*Created by Walter 🎩 for Artur*