# 03 — Regulatorische Analyse: EU AI Act & Globale Regulierung

## Executive Summary

Die regulatorische Landschaft für KI ist **der stärkste Treiber** für AI Compliance Lösungen. Der EU AI Act ist das weltweit erste umfassende KI-Gesetz und setzt den Gold-Standard. Unternehmen, die nicht compliant sind, riskieren **Strafen bis zu €35 Millionen oder 7% des weltweiten Jahresumsatzes**.

---

## EU AI Act — Das Wichtigste im Überblick

### Timeline & Deadlines

| Datum | Meilenstein |
|-------|-------------|
| **August 2024** | AI Act tritt in Kraft (veröffentlicht im EU Amtsblatt) |
| **Februar 2025** | Verbotene AI-Praktiken müssen eingestellt werden |
| **August 2025** | Governance-Infrastruktur operational, GPAI-Model-Verpflichtungen beginnen |
| **August 2026** | Vollständige Anwendung auf High-Risk AI-Systeme |
| **August 2027** | Bestehende GPAI-Modelle müssen compliant sein |

### Risk-Based Approach

Der EU AI Act klassifiziert AI-Systeme nach Risiko:

```
┌─────────────────────────────────────────────────────────────┐
│  UNACCEPTABLE RISK    → Verboten                            │
│  • Sozial Scoring durch Staaten                             │
│  • Echtzeit-Fernerkennung in öffentlichen Räumen            │
│  • Emotionserkennung am Arbeitsplatz (außer Sicherheit)     │
│  • Manipulationstechniken                                   │
├─────────────────────────────────────────────────────────────┤
│  HIGH RISK            → Strikte Anforderungen               │
│  • Kritische Infrastruktur                                  │
│  • Bildung, Beschäftigung                                   │
│  • Finanzdienstleistungen (Kreditscoring)                   │
│  • Rechtssystem, Migration                                  │
├─────────────────────────────────────────────────────────────┤
│  LIMITED RISK         → Transparenzpflichten                │
│  • Chatbots                                                 │
│  • Deepfakes                                                │
│  • AI-generierte Inhalte                                    │
├─────────────────────────────────────────────────────────────┤
│  MINIMAL RISK         → Freiwillige Codes                   │
│  • AI-enabled Videospiele                                   │
│  • Spam-Filter                                              │
└─────────────────────────────────────────────────────────────┘
```

### High-Risk AI System Requirements (Art. 8-15)

Für High-Risk AI-Systeme gelten folgende Pflichten:

| Anforderung | Beschreibung | Relevanz für deine Plattform |
|-------------|--------------|------------------------------|
| **Risk Management** (Art. 9) | Kontinuierliches Risikomanagement während des gesamten Lebenszyklus | ✅ Core Feature |
| **Data Governance** (Art. 10) | Trainingsdaten müssen bestimmte Qualitätskriterien erfüllen | ✅ Monitoring |
| **Technical Documentation** (Art. 11) | Umfassende Dokumentation für Behörden | ✅ Auto-Generierung |
| **Record-Keeping** (Art. 12) | Automatische Protokollierung (Logs) | ✅ Audit Trails |
| **Transparency** (Art. 13) | Nutzer müssen über AI-Interaktion informiert werden | ✅ Nachweisbarkeit |
| **Human Oversight** (Art. 14) | Menschliche Aufsicht muss gewährleistet sein | ✅ Monitoring |
| **Accuracy & Robustness** (Art. 15) | Angemessene Genauigkeit, Robustheit, Cybersicherheit | ✅ Performance Monitoring |

### Strafen (Art. 99)

| Verstoß | Strafe |
|---------|--------|
| Verbotene AI-Praktiken | Bis zu €35 Mio. oder 7% des weltweiten Jahresumsatzes |
| Nichteinhaltung High-Risk Anforderungen | Bis zu €15 Mio. oder 3% des weltweiten Jahresumsatzes |
| Falsche/Misleading Informationen | Bis zu €7,5 Mio. oder 1% des weltweiten Jahresumsatzes |

### General Purpose AI Models (GPAI)

Ab August 2025 gelten zusätzliche Anforderungen für GPAI-Modelle (z.B. GPT-4, Claude):

- **Transparenz:** Technische Dokumentation, Trainingsdaten-Summary
- **Copyright:** Respektierung von Urheberrechten
- **Safety:** Systemische Risiken müssen gemeldet werden

---

## Andere Jurisdiktionen

### USA

| Initiative | Status | Details |
|------------|--------|---------|
| **Executive Order 14110** | Aktiv | Biden Administration: Safety-Standards, Red-Team-Testing für große Modelle |
| **NIST AI Risk Management Framework** | Aktiv | Freiwilliger Rahmen, aber weit verbreitet |
| **State-Level** | Fragmentiert | Colorado AI Act (SB 205), California Draft Regulations |
| **Congress** | In Diskussion | Keine umfassende Bundesgesetzgebung bislang |

**Trend:** Fragmentierte Landschaft, aber wachsender Druck. Unternehmen mit EU-Präsenz müssen ohnehin EU AI Act einhalten.

### UK

| Initiative | Status | Details |
|------------|--------|---------|
| **Pro-Innovation Approach** | Aktiv | Keine neue Regulierung, stattdessen existierende Regulierer |
| **AI White Paper** | Veröffentlicht | Prinzipien-basierter Ansatz |
| **Regulatorische Sandbox** | In Planung | Testumgebung für innovative AI |

**Trend:** Pragmatisch, innovation-freundlich. Weniger strikt als EU.

### China

- **Algorithm Registry:** Pflicht zur Registrierung bestimmter Algorithmen
- **Deep Synthesis Provisions:** Regulierung von Deepfakes
- **Generative AI Measures:** Anforderungen an Trainingsdaten, Content-Labeling

---

## Compliance-Anforderungen im Detail

### Audit Trail Requirements

Der EU AI Act verlangt in Art. 12 (Record-Keeping):

> "High-risk AI systems shall technically allow for the automatic recording of events (logs) over the duration of the lifetime of the system"

**Konkrete Anforderungen:**

| Aspekt | Anforderung |
|--------|-------------|
| **Retention Period** | Mindestens 6 Monate (länger bei sektoralen Anforderungen) |
| **Immutability** | Logs dürfen nicht manipulierbar sein |
| **Content** | Inputs, Outputs, Zeitstempel, Nutzer-IDs, Entscheidungslogik |
| **Accessibility** | Muss für Behörden verfügbar sein |
| **Reconstruction** | Muss Systemverhalten rekonstruierbar machen |

### Konformitätsbewertung

High-Risk AI-Systeme müssen eine **Conformity Assessment** durchlaufen:

1. **Internal Assessment** (meistens)
   - Selbstzertifizierung durch den Anbieter
   - Dokumentation, Testing, Quality Management

2. **Third-Party Assessment** (in bestimmten Fällen)
   - Durch "Notified Bodies"
   - Biometrische Identifikation, kritische Infrastruktur

### CE-Kennzeichnung

High-Risk AI-Systeme müssen mit **CE** gekennzeichnet werden, um in der EU in Verkehr gebracht zu werden.

---

## Geschäftliche Implikationen

### Wer muss complien?

| Rolle | Verantwortung |
|-------|---------------|
| **Provider** (Entwickler) | Vollständige AI Act Compliance |
| **Deployer** (Anwender) | Due Diligence, menschliche Aufsicht, Logging |
| **Distributor** | Sicherstellen, dass Produkte compliant sind |
| **Importer** | Sicherstellen, dass EU-Importe compliant sind |

### Marktchancen durch Regulierung

| Treiber | Opportunität |
|---------|--------------|
| **Strafandrohung** | Hoher Dringlichkeitsfaktor für Unternehmen |
| **Audit-Trail-Pflicht** | Technische Lösungen für Logging notwendig |
| **Conformity Assessment** | Automatisierung der Dokumentation |
| **Shadow AI** | Discovery-Lösungen für unautorisierte AI |
| **Cross-Border** | Unternehmen mit globaler Präsenz brauchen Multi-Jurisdiction-Lösungen |

### Herausforderungen

| Herausforderung | Beschreibung |
|-----------------|--------------|
| **Evolving Standards** | Harmonisierte Standards noch in Entwicklung |
| **Interpretation** | Viele Begriffe noch nicht klar definiert |
| **Enforcement** | Noch unklar, wie streng durchgegriffen wird |
| **Global Fragmentation** | Unterschiedliche Anforderungen weltweit |

---

## Wie deine Plattform helfen kann

### Mapping: Deine Features → AI Act Anforderungen

| Dein Feature | AI Act Requirement |
|--------------|-------------------|
| **AI Traffic Monitoring** | Art. 12 (Record-Keeping) |
| **Anomalie-Erkennung** | Art. 9 (Risk Management), Art. 15 (Robustness) |
| **Audit-Trails** | Art. 12 (Record-Keeping), Art. 19 (Post-Market Monitoring) |
| **KI-Nachweisbarkeit** | Art. 13 (Transparency), Art. 52 (Transparency Obligations) |
| **Fehleranalyse** | Art. 61 (Post-Market Monitoring) |
| **Compliance-Reporting** | Art. 11 (Technical Documentation) |

### Unique Selling Proposition (USP)

> "Die einzige Plattform, die **Echtzeit-Compliance** für AI-Systeme bietet — nicht nur Punkt-in-Zeit-Assessments, sondern kontinuierliche Überwachung und sofortige Anomalie-Erkennung."

---

## Fazit

Der **EU AI Act ist der Game-Changer** für den AI Governance Markt. Unternehmen haben keine Wahl: Sie müssen compliant werden oder riskieren existenzbedrohende Strafen.

**Deine Positionierung:**
- Fokus auf **Echtzeit-Compliance** (nicht nur Punkt-in-Zeit)
- **Automatisierte Audit-Trails** als Kernfeature
- **EU-First Strategie** (strikteste Anforderungen = höchster Bedarf)
- **Multi-Jurisdiction** als Wachstumspfad

**Timing ist gut:** Die ersten Deadlines sind bereits vergangen (Feb 2025), die nächsten kommen (Aug 2026). Unternehmen suchen jetzt nach Lösungen.

---

## Quellen

- [EU AI Act (Verordnung (EU) 2024/1689)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689)
- [artificialintelligenceact.eu — High-Level Summary](https://artificialintelligenceact.eu/high-level-summary/)
- [Legal Nodes: EU AI Act 2026 Updates](https://www.legalnodes.com/article/eu-ai-act-2026-updates-compliance-requirements-and-business-risks)
- [Kennedys Law: EU AI Act Implementation Timeline](https://www.kennedyslaw.com/en/thought-leadership/article/2026/the-eu-ai-act-implementation-timeline-understanding-the-next-deadline-for-compliance/)
- [Greenberg Traurig: Key Compliance Considerations](https://www.gtlaw.com/en/insights/2025/7/eu-ai-act-key-compliance-considerations-ahead-of-august-2025)
- [Stack Cybersecurity: EU AI Act Compliance Guide for US Businesses](https://stackcyber.com/posts/ai-eu-act)
- [Aqua Cloud: EU AI Act Compliance 2026](https://aqua-cloud.io/eu-ai-act-compliance/)

---

*Created by Walter 🎩 for Artur*