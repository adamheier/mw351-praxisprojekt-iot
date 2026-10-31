# TODO – Praxisprojekt IoT (mw351)
> Kickoff: 26. Oktober 2026 | Gebäudeleittechnik / RCU-Anbindung

---

## Kritische Deadlines

- [ ] **Prüfungsanmeldung** bis Mitte November 2026 beim Prüfungsamt (Frau Thüret) — Nachmeldung nicht möglich!
- [ ] Projektabschluss idealerweise bis **Anfang März 2027**

---

## Student (Olison)

### Einarbeitung
- [ ] InfluxDB-Dokumentation lesen
- [ ] Flux Query-Sprache lernen (bevorzugte Query-Sprache im Projekt)
- [ ] Bestehende Systemarchitektur verstehen (InfluxDB → Kestra → PostgreSQL/TimescaleDB)
- [ ] Bestehende Kestra-Flows und Datenbankschemas analysieren

### Konzept / Planung
- [ ] Konzept erarbeiten: Wie kommen MQTT-Daten in InfluxDB?
  - Option A: Python-Script (MQTT-Client)
  - Option B: Node-RED
  - Option C: Kestra-Flow (hat MQTT-Adapter)
- [ ] Pro/Contra-Analyse der Optionen (Kestra-Stabilität beachten!)

### Hauptaufgaben (nach RCU-Installation)
- [ ] **Schritt 1:** Rohdaten der Gebäudeleittechnik via MQTT in neues InfluxDB-Bucket schreiben
- [ ] **Schritt 2:** Aggregierte Daten in neue PostgreSQL-Tabelle übertragen
  - Datenbankschema entwickeln (orientieren an bestehenden Tabellen)
  - Aggregation direkt via Flux-Query in InfluxDB (nicht in Pandas/Python)
- [ ] **Optional / Schritt 3:** Test-UI in Grafana zur Datenanzeige

### Prüfungsformalitäten
- [ ] Prüfungsanmeldung klären (Frau Thüret / Prüfungsamt)
- [ ] Entscheiden: dieses Semester oder nächstes?

---

## Betreuer

- [ ] Beim Facility-Management-Kollegen nachhaken wegen RCU-Installation (wurde für "morgen" zugesagt)
- [ ] Studenten per E-Mail informieren, sobald Installationstermin bekannt

---

## Facility Management

- [ ] RCU (BACnet + M-Bus) in Gebäude C (Keller) installieren
- [ ] Konfigurationstabelle / Datenpunkt-Codes für proprietäre Semantik bereitstellen

---

## Gemeinsam (nach RCU-Installation)

- [ ] Brainstorming-Sitzung zur Systemarchitektur-Integration (online oder vor Ort, ggf. mit Facility Management)
- [ ] Priorisierung der Datenpunkte festlegen:
  - [ ] Energieverbrauch Lüftungsanlage
  - [ ] CO₂-Wert (Luftstrom)
  - [ ] Temperatur (Raum & Luftstrom)
- [ ] Kestra-Monitoring verbessern (E-Mail-Alerts bei Flow-Abbruch)

---

## Offene Risiken

| Risiko | Status |
|---|---|
| RCU-Installationszeitpunkt unklar (FM-Kollege abwesend) | offen |
| Datenpunkt-Codes proprietär – Zugang unsicher | offen |
| Welche Messwerte tatsächlich über BACnet/M-Bus verfügbar? | unklar |
| Kestra-Stabilität / Entscheidung Python vs. Kestra | offen |
| PostgreSQL-Schema erst designbar wenn Datenstruktur bekannt | blockiert |
| Grafana-Visualisierung zeitlich möglicherweise nicht realisierbar | optional |
