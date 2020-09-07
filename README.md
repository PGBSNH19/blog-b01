# Blogg

Detta är bloggen för buddypar 1, Andreas Brochs, Hampus Kjellstrand och Kristoffer Ternstedt

Dag 1 31/8 2020: 
(Hampus, Andreas)

Priser: 
Azure runt 500:-/mån
Vi förstod även på andra grupper att det finns alla möjliga lösningar från typ 300:- till tusentals kronor.

Webbserver: 
Såg det mer som ett sätt att fräscha upp sina programmeringschops tillbaka efter sommaren.
Kändes som att man behövde påminna sig själv om en del saker igen, inte som man glömt direkt men som bara inte ligger på fingertopparna längre som det gjorde i våras.



Dag 2 2/9 2020:
(Hampus, Andreas)

Vi har idag prövat på att starta upp virtuella maskiner både lokalt och via Azure med varierande framgång.
Lokalt fungerade det för Andreas utan problem och via Azure så fungerade det för Hampus utan problem, vice versa stöttes några problem på.
Hampus kunde inte starta en VM lokalt då den inte bootade som den skulle. Andreas hade lite problem med att få ned sin SSH-nyckel från Azure när han skapat en VM.

Vi har även prövat att starta en VM med en server via ett exempel på GitHub och med hjälp av Pulumi och Powershell.
Detta fungerade bra för oss båda och vi kunde sedan se i Azure att den nya VM var uppe och snurrade.

Vi har inte hunnit göra någon SWOT-analys ännu utan får göra det en annan dag i veckan.

Dag 3 4/9 2020:
(Hampus, Andreas)

Vi har idag gjort SWOT-analysen. Laddar upp separat bild på den. 



Dag 4 7/9 2020:
(Hampus, Andreas)

Vi har installerat Docker (+Docker Desktop) på våra datorer. Det krävde lite uppdateringar och Linux-tillägg (WSL2 Backend) för att få att fungera.
Det krävdes även att Windows hade sin senaste uppdatering.

Status ca kl1400: Andreas hade lättare att installera Docker + alla uppdateringar och fick SimpleWebHalloWorld att fungera i en container strax efter lunch. Hampus blev färdig strax efter när hans uppdateringar kört färdigt. Windowsuppdateringen var en stor en och behövde en lite mer än halva förmiddagen på sig för att bli klar.

Vi följde en guide för att skapa en Dockerfile men den var inte helt enkel att följa. Bara för att få det att fungera (och höja moralen) skapade vi en Dockerfile i VisualStudio genom att högerklicka på Solution och add-Dockerfile. Det fungerade väl och gav oss också chansen att se hur en sådan fil ska se ut.

En Dockerfile fungerar i stort såhär.
(skulle lägga bild här, men funkade inte)

FROM = En "adress" där man hämtar en Image där appen ska köras. Vilket ramverk vi ska röra oss inom.

WORKDIR = Var i mappstrukturen ska imagen läggas.

COPY = Vilka filer som ska kopieras in i den slutliga imagen.

ENTRYPOINT = När det är dags att köra kommer dessa kommandon köras. I detta fall Kör SimpleWebHalloWorld.dll. Det blir själva starten eller "ingångspunkten" varifrån applikationen kommer börja köras.

För att köra applicationen i en container behöver man först bygga själva kontainern genom att köra kommandot: "docker build -t [namnet på bilden]".
Själva docker-imagen kommer då att byggas utifrån vad som är specificerat i "Docker"-filen i projektet. När filen är färdigbyggd så behöver man köra den. Detta gör man genom att skriva: "docker run -d -p 8080:80 --name [namnet på containern] [namnet på bilden].
Kommandot "docker run" både skapar och kör kontainern. Om man bara vill köra en kontainer kan man starta upp den på nytt i Docker Desktop eller skriva: "docker container start [OPTIONS (valfritt)] CONTAINER [CONTAINER...]" i exempelvis powershell.

Nu är din container igång och om du öppnar valfri webläsare och skriver in den port du kör på så kan du se applikationen köras.

Vår [blogg](index.md)
