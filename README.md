# README — Heeft tijdsdruk een effect op ervaren stress?

**Auteurs:**  
Jasmijn Peterse, Tristan Kruithof, Alexander Fluttert  

**Contact:**  
- jrj.peterse@st.hanze.nl  
- tjd.kruithof@st.hanze.nl  
- ajlt.fluttert@st.hanze.nl  

**Projectperiode:** 4 mei 2026 – 9 juni 2026

---

## Doel van het project
Dit project onderzoekt of **tijdsdruk invloed heeft op fysiologische stressreacties** (hartslag, bloeddruk) en op **prestatie** tijdens korte rekentoetsen.  
Daarnaast wordt onderzocht:

- of **geslacht** invloed heeft op deze stressreactie  
- of **dagelijks ervaren stress** (PSS‑10 score) samenhangt met de gemeten fysiologische stress

---

## Onderzoeksvragen & Hypothesen

### Hoofdvraag  
**Beïnvloedt tijdsdruk de bloeddruk, hartslag en prestatie?**

- **H0:** Tijdsdruk heeft geen effect op fysiologische stress of prestatie.  
- **H1:** Tijdsdruk verhoogt fysiologische stress en verlaagt prestatie.

### Deelvraag 1 — Geslacht  
- **H0:** Geslacht heeft geen invloed op stressreacties onder tijdsdruk.  
- **H1:** Geslacht heeft wél invloed op stressreacties onder tijdsdruk.

### Deelvraag 2 — Dagelijkse stress (PSS‑10)  
- **H1:** Dagelijkse stress heeft geen invloed op de stressreactie onder tijdsdruk.
- **H0:** Dagelijkse stress heeft invloed op de stressreactie onder tijdsdruk.  

---

## Dataverzameling

De data is verzameld via:

- **Google Forms** (rekentoetsen, PSS‑10, geslacht)
- **Polar Verity Sense** (continue hartslagregistratie)
- **Omron bloeddrukmeter** (bloeddruk na rust periode en na elke toets)

De metingen zijn uitgevoerd in **lokaal D1.07 en D1.08** van het Van Doorenveste (Groningen).

Het volledige protocol staat in:  
`/protocols/protocol.Rmd`

---

## Datastructuur (FAIR)

Alle ruwe data staat in `/raw_data`.  
De bestanden moeten de volgende structuur hebben:

### Hartslagbestanden
- Afkomstig van Polar Verity Sense  
- Formaat: **CSV**  
- Bestandsnaam:  yyyy_mm_dd_heartrate_x.csv
- Kolommen: tijdstempel, hartslag (bpm)

### Testtijden
- Bestand: `testtijden.csv`  
- Bevat start- en eindtijden (in seconden) van:
- geen tijdsdruk  
- lichte tijdsdruk  
- hoge tijdsdruk

### Bloeddruk
- Map: `/raw_data/blood pressure/`  
- Bestand: `bloodpressure.xlsx`  
- Kolommen: systolisch, diastolisch, tijdstip, conditie

### PSS + geslacht + prestaties
- Bestand: `pss_gender_scores.csv`  
- Kolommen:
- Gender  
- PSS‑10 score  
- Totaal rekenscore  
- Fouten per ronde (F1, F2, F3)

---

## Mappenstructuur

### `/protocols`
Bevat het volledige experimentele protocol (Rmd).

### `/raw_data`
Ruwe, onbewerkte data:
- hartslagbestanden  
- bloeddrukbestanden  
- testtijden  
- PSS‑scores  

### `/analysis`
- `/data` → afgeleide datasets  
- `/scripts` → alle R‑scripts:
- `wetenschappelijke_cyclus.Rmd` (hartslaganalyse)
- `bloodpressure.Rmd` (bloeddrukanalyse)
- `Analyse_doc.Rmd`
- logboeken van alle groepsleden

### `/docs`
Aanvullende documenten, o.a.:
- FAIR‑checklist

### `/publication`
Bevat de eindpublicatie:
- `publicatie.Rmd`
- `publicatie.pdf`
- `/figures` → alle gebruikte afbeeldingen

---

## Analyse uitvoeren

### Software
- **R versie 4.5.3 (2026‑03‑11 ucrt)**  
- Gebruikte packages:
- readr  
- ggplot2  
- tidyr  
- ez  
- pwr  
- ARTool  
- readxl  

### Stappenplan

1. **Download de repository**
2. Plaats alle ruwe data in `/raw_data`
3. Controleer dat hartslagbestanden correct zijn genoemd:
4. Open het script:  
`/analysis/scripts/wetenschappelijke_cyclus.Rmd`
5. Installeer de benodigde packages (eenmalig):
```r
install.packages(c("readr", "ggplot2", "tidyr", "ez", "pwr", "ARTool", "readxl"))
```
6. Run het script van boven naar beneden
7. Voor bloeddrukanalyse: run bloodpressure.Rmd
