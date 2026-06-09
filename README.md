# Readme: heeft tijdsdruk een effect op de ervaren stress?
geschreven door Jasmijn Peterse, Tristan Kruithof en Alexander Fluttert.
contactgegevens: jrj.peterse@st.hanze.nl, tjd.kruithof@st.hanze.nl en ajlt.fluttert@st.hanze.nl
het project heeft van 4/5/2026 tot 9/6/2026 gelopen.


de hoofdvraag van dit onderzoek is: 
Beïnvloedt een tijdsdruk de bloeddruk,hartslag en de prestatie?

onze H0 is dat studenten onder tijdsdruk niet significant meer stress ervaren. 
onze H1 is dat studenten onder tijdsdruk wel significant meer stress ervaren. 

Daarnaast zijn er twee nevenvragen: 

Heeft sexe invloed op ervaren stress onder tijdsdruk?

H0: De sexe heeft geen invloed op de ervaren stress onder tijdsdruk.
H1: De sexe heeft invloed op de ervaren stress onder tijdsdruk. 

Heeft de dagelijks ervaren stress invloed op de stress onder tijdsdruk?

H0: De dagelijks ervaren stress heeft invloed op de stress onder tijdsdruk.
H1: De dagelijks ervaren stress heeft geen invloed op de stress onder tijdsdruk.



## Dataverzameling

In dit onderzoek is gebruik gemaakt van vragenlijsten en korte rekentoetsen in google forms.
Deze rekentoetsen en vragenlijsten zijn gemaakt op een laptop.
De hartslagdata is verzameld door middel van de polar verity sense met bijbehorende software.
Deze is aan het begin van elke meting (met meerdere testen) gestart.
De data van de bloeddruk is verzameld door een omron bloeddrukmeter. 
De metingen zijn gedaan in lokaal D1.07 en D1.08 van het van Doorenveste in Groningen.
Voor verdere details op hoe deze data is verzameld, staat het protocol op /protocols/protocol.Rmd.


Om onze scripts te runnen moet de verzamelde data in de volgende structuur:

De hartslagmetingen moeten van een polar verity sense komen en gedownload worden als csv.
Verder moeten deze metingen vernoemd worden als yyyy_mm_dd_heartrate_x.Csv.

Daarnaast moeten de testtijden bijgehouden worden in seconden, dus niet minuut:seconden.

De bloeddrukdata moet gestructureerd zijn zoals deze gedownload wordt van de omron-app.



## Waar kan ik wat vinden?

### protocols
In deze map staan de protocols die gebruikt zijn voor het experiment.

### raw_data
In deze map staat de rauwe data die uit onze apparaten/vragenlijst is gekomen

### analysis

In de /data map staat de afgeleide data die is afgeleid van onze rauwe data. 
In de /scripts map staan de scripts waarmee deze data is afgeleid en/of verwerkt. 

### docs
In deze map staan eventuele aanvullende documenten die gebruikt zijn voor het onderzoek.

### publication
In deze map staat onze eigen publicatie 2 keer, een keer als een .RMD bestand en een keer
als een .pdf bestand. 


## Analyse

Voor de analyse van de data is R versie 4.5.3 (2026-03-11 ucrt) gebruikt.
Verder zijn de gebruikte packages voor de analyse readr, ggplot, ARTool en tidyr.
De scripts moeten van boven naar beneden uitgevoerd worden, maar kunnen los van elkaar gerund worden.