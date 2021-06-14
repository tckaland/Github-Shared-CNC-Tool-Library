# Github-Shared-CNC-Tool-Library

### Hva er dette?

Hvis du vil kutte ut noe på CNC-maskinen på verkstedet, eller bare er *keen* på å lære deg å programmere CNC-maskinen igjennom Fusion360, så er dette plassen for deg! 

I GitHub-repoet du et stadig voksende bibliotek over verktøy som finnes til CNC-maskinen vår, med tilhørende forhåndsinnstillinger for hastighet og kuttedybde. I tillegg finner du en egen *postprosessor* til vår CNC (Datron M8 fra 2006) som gjør det enklere å bruke verktøy med manuellt skifte.

I readme-filen (filen du leser nå :astonished:) finner du også info om dette:

- [Hvordan importere verktøysbibliotek til Fusion360](#Hvordan-importere-verktøysbibliotek-til-fusion360)
- [Hvordan importere postprosessor til Fusion360](#Hvordan-importere-postprosessor-til-Fusion360)
- [Programmering av CNC-maskinen i Fusion360](#Programmering-av-CNC-maskinen-i-Fusion360)
- [Interne og eksterne verktøy](#Eksterne-og-interne-verktøy)
- [Oppstart av CNC-maskinen](#Oppstart-av-CNC-maskinen)
- [Manuell styring](#Manuell-styring)
- [Sette nullpunkt](#Sette-nullpunkt)
- [Lagre og laste inn nullpunkt](#Lagre-og-laste-inn-nullpunkt)
- [Skru av maskinen](#Skru-av-maskinen)


<br>

---

<br>

## Hvordan importere verktøysbibliotek til Fusion360

Verktøysbiblioteket er en liste over alle fresestålene (aka verktøyene) som vi har tilgjengelige for bruk i CNCen. Verktøysbiblioteket blir brukt når du skal sette opp operasjoner/programmere CNCen, hvor en da velger hvilke verktøy CNCen skal bruke til en bestemt operasjon. Verktøysbiblioteket inneholder info som diameter, antall kuttekanter, max kutt-dybde, hastighet, rotasjonshastighet og forhåndsinnstillinger for operasjoner som gjør det enklere å sette opp kutteoperasjoner og gjør du du kan simulere og sjekke om maskinen kommer til å kræsje eller ikke (veldig nyttig!). 

<br>

#### For Mac/OSX
###### Fremgangsmåte for windows kommer snart... :grimacing: 

<br>

1. Trykk på **Code** og åpne repoet i **GitHub Desktop** (Eventuelt klon repoet til pcen din vha. https, ssh eller cli)

2. Lagre repoet i **DittBrukernavn/Library/Application Support/Autodesk/CAM360/libraries/Local**.
######          :bulb: Dersom Library mappen ikke vises i Finder, trykk **cmd + J** i Finder og huk av **Show Library Folder**
![Add Repo GitHub Desktop](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/GitHubDesktopAddRepo.png?raw=true)


3. For å sjekke at biblioteket er importert, åpne Fusion360 og gå til CAM/Manufacture-arbeidsområdet.<br>
![Change to Manufacture Workspace](changeToManufacture.gif)
 <br>Deretter trykk på dette 
![Tool Library Button](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ToolLibrarySymbol.png?raw=true)
 symbolet. Du burde nå ha fått opp et lignende vindu som vist under. :point_down:
 ![Tool Library Location](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ToolLibraryInFusion.png?raw=true)
 Verktøybiblioteket til CNCen på verkstedet vil ligge under **Local -> Github-Shared-CNC-Tool-Library -> IPD Datron**

4. Oppdater repoet med jevne mellomrom gjennom git for å holde verktøybiblioteket og *feeds & speeds* oppdatert. 
    <br>Dersom du bruker GitHub Desktop, så gjøres dette enkelt ved å trykke på knappen "fetch origin".


### Alternativ måte
###### :warning: *Med denne måten så vil man ikke kunne oppdatere verktøybiblioteket igjennom git fortløpende*

1. Last ned repoen som en .zip og ekspander .zip-folderen.
2. Åpne Fusion 360, gå til **CAM/Manufature-arbeidsområdet** og trykk på ![Tool Library Button](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ToolLibrarySymbol.png?raw=true) for å komme til *Tool Library*. 
3. Importer verkstedet sitt verktøysbibliotek for CNCmaskinen ved å trykke på importer ![Import Button](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ImportLibrarySymbol.png?raw=true) og velg **IPD Datron.json** som befinner seg i *.zip* filen du lastet ned fra GitHub.

<br>

---

<br>


## Hvordan importere postprosessor til Fusion360

Postprosessoren er en liten kodesnutt som oversetter kutteopreasjonene dine i Fusion360 til en Datron-spesifikk G-kode som vår CNCmaskin forstår. Uten postprosessoren vil ikke vår CNCmaskin forstå hva du har programmert i Fusion360. Postprosessoren gjør det også mulig å bruke flere verktøy enn det som står i det interne vektøymagasinet i CNCen.

#### For Mac/OSX
###### Fremgangsmåte for windows kommer snart... :grimacing: 

<br>

1. Du må først laste ned GitHub-repoet som vist i steg 1 og 2 i [Hvordan importere verktøysbibliotek til Fusion360](#Hvordan-importere-verktøysbibliotek-til-Fusion360).

2. Når repoet er lastet ned, åpne Fusion360 og trykk på 

<br>

---

<br>

## Programmering av CNC-maskinen i Fusion360

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Oppstart av CNC-maskinen

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Manuell styring

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Sette nullpunkt

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Lagre og laste inn nullpunkt

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Skru av maskinen