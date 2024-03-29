# Github-Shared-CNC-Tool-Library

### Hva er dette?

Hvis du vil kutte ut noe på CNC-maskinen på verkstedet, eller bare er *keen* på å lære deg å programmere CNC-maskinen igjennom Fusion360, så er dette plassen for deg! 

I GitHub-repoet finner du et stadig voksende bibliotek over verktøy som finnes til CNC-maskinen vår, med tilhørende forhåndsinnstillinger for hastighet og kuttedybde. I tillegg finner du en egen *postprosessor* til vår CNC (Datron M8 fra 2006) som gjør det enklere å bruke verktøy med manuellt skifte.

I readme-filen (filen du leser nå :astonished:) finner du også info om temaene under:

- [Hvordan importere verktøysbibliotek til Fusion360](#Hvordan-importere-verktøysbibliotek-til-fusion360)
- [Hvordan importere postprosessor til Fusion360](#Hvordan-importere-postprosessor-til-Fusion360)
- [Programmering av CNC-maskinen i Fusion360](#Programmering-av-CNC-maskinen-i-Fusion360)
- [Oppstart av CNC-maskinen](#Oppstart-av-CNC-maskinen)
- [Manuell styring](#Manuell-styring)
- [Feste *stock* i CNCen](#Feste-stock-i-CNCen)
- [Sette nullpunkt](#Sette-nullpunkt)
- [Laste inn og starte kutteprogram](#Laste-inn-og-starte-kutteprogram)
- [Justere hastighet og kjøling under programkjøring](#Justere-hastighet-og-kjøling-under-programkjøring)
- [Skru av maskinen](#Skru-av-maskinen)
- [Manuelt verktøyskifte under programkjøring](#Manuelt-verktøyskifte-under-programkjøring)
- [Utføre enkle kutt direkte på CNCen](#Utføre-enkle-kutt-direkte-på-CNCen)
- [Andre festemetoder](#Andre-festemetoder)
- [Lagre og laste inn nullpunkt](#Lagre-og-laste-inn-nullpunkt)
- [Vri koordinatsystem til CNCen](#Vri-koordinatsystem-til-CNCen)
- [Starte et program fra en spesifikk plass](#Starte-et-program-fra-en-spesifikk-plass)
- [Bytte ut et internt fresestål med et lenger fresestål](#Bytte-ut-et-internt-fresestål-med-et-lenger-fresestål)
- [Rotasjonsakse](#Rotasjonsakse)



<br>

---

<br>

## Hvordan importere verktøysbibliotek til Fusion360

Verktøysbiblioteket er en liste over alle fresestålene (aka verktøyene) som vi har tilgjengelige for bruk i CNCen. Verktøysbiblioteket blir brukt når du skal sette opp operasjoner/programmere CNCen, hvor en da velger hvilke verktøy CNCen skal bruke til en bestemt operasjon. Verktøysbiblioteket inneholder info som diameter, antall kuttekanter, max kutt-dybde, hastighet, rotasjonshastighet og forhåndsinnstillinger for operasjoner som gjør det enklere å sette opp kutteoperasjoner og gjør du du kan simulere og sjekke om maskinen kommer til å kræsje eller ikke (veldig nyttig!). 

<br>

#### For Mac/OSX
###### Fremgangsmåte for windows kommer snart... :grimacing: 

<br>

1. Trykk på **Code** i GitHub på web og åpne repoet i **GitHub Desktop** (Eventuelt klon repoet til pcen din vha. https, ssh eller cli)
   <br><img src=.Images/GitHubClone.gif>
   <br><h6>:bulb: GitHub Desktop kan lastes ned **[her](https://desktop.github.com/)**</h6>

2. **For Mac/OSX** <br>Lagre repoet i **DittBrukernavn/Library/Application Support/Autodesk/CAM360/libraries/Local/Github-Shared-Tool-Library**.<br>
   ###### :bulb: Dersom Library mappen ikke vises i Finder, trykk **cmd + J** i Finder og huk av **Show Library Folder** <br><br>
   **For Windows** <br>Lagre repoet i **DittBrukernavn\AppData\Roaming\Autodesk\CAM360\libraries\Local\Github-Shared-Tool-Library**
   ![Add repo in GitHub Desktop](.Images/GitHubDesktopAddRepo.png)


3. For å sjekke at biblioteket er importert, åpne Fusion360 og gå til CAM/Manufacture-arbeidsområdet.<br>
   <br><img src=".Images/ChangeToManufacture.gif" width="250">
   <br>Deretter trykk på dette ![Tool Library Symbol](.Images/ToolLibrarySymbol.png) symbolet. Du burde nå ha fått opp et lignende vindu som vist under. :point_down:
   <br><img src=".Images/ToolLibraryInFusion.png">
   Verktøybiblioteket til CNCen på verkstedet vil ligge under **Local -> Github-Shared-CNC-Tool-Library -> IPD Datron**

4. Oppdater repoet med jevne mellomrom gjennom git for å holde verktøybiblioteket og *feeds & speeds* oppdatert. 
   <br>Dersom du bruker GitHub Desktop, så gjøres dette enkelt ved å trykke på knappen "fetch origin".


### Alternativ måte
###### :warning: *Med denne måten så vil man ikke kunne oppdatere verktøybiblioteket igjennom git fortløpende*

1. Last ned repoen som en .zip og ekspander .zip-folderen.
2. Åpne Fusion 360, gå til **CAM/Manufature-arbeidsområdet** og trykk på ![Tool Library Button](.Images/ToolLibrarySymbol.png) for å komme til *Tool Library*. 
3. Importer verkstedet sitt verktøysbibliotek for CNCmaskinen ved å trykke på importer ![Import Button](.Images/ImportLibrarySymbol.png) og velg **IPD Datron.json** som befinner seg i *.zip* filen du lastet ned fra GitHub.

<br>

### Alternativ måte
###### :warning: *Med denne måten så vil man ikke kunne oppdatere verktøybiblioteket igjennom git fortløpende*

1. Last ned repoen som en .zip og ekspander .zip-folderen.
2. Åpne Fusion 360, gå til **CAM/Manufature-arbeidsområdet** og trykk på ![Tool Library Button](.Images/ToolLibrarySymbol.png) for å komme til *Tool Library*. 
3. Importer verkstedet sitt verktøysbibliotek for CNCmaskinen ved å trykke på importer ![Import Button](.Images/ImportLibrarySymbol.png) og velg **IPD Datron.json** som befinner seg i *.zip* filen du lastet ned fra GitHub.

<br>

---

<br>


## Hvordan importere postprosessor til Fusion360

Postprosessoren er en liten kodesnutt som oversetter kutteopreasjonene dine i Fusion360 til en Datron-spesifikk G-kode som vår CNCmaskin forstår. Uten postprosessoren vil ikke vår CNCmaskin forstå hva du har programmert i Fusion360. Postprosessoren gjør det også mulig å bruke flere verktøy enn det som står i det interne vektøymagasinet i CNCen.

#### For Mac/OSX
###### Fremgangsmåte for windows kommer snart... :grimacing: 

<br>

1. Du må først laste ned GitHub-repoet som vist i steg 1 og 2 i [Hvordan importere verktøysbibliotek til Fusion360](#Hvordan-importere-verktøysbibliotek-til-Fusion360).

2. Når repoet er lastet ned, åpne Fusion360, gå til *manufacture-arbeidsområdet* og trykk på *post library* ![Post Library Button](.Images/PostLibraryButton.png) som ligger i *manage* fanen.

3. Gå til My posts -> Local i menyen til venstre.

4. Trykk på Import-knappen ![Import button](.Images/Import.png) i fanen som kommer opp, og velg filen IPDDatronM8mcr.cps som ligger i repoen/folderen som du lastet ned fra GitHub.
<br><img src=".Images/AddPostProcessor.png" width="49%"> <img src=".Images/AddPostProcessorSelected.png" width="49%">
<br><h6>:bulb: Dersom du har følgt fremgangsmåten som vist [her](#Hvordan-importere-verktøysbibliotek-til-Fusion360), så skal folderen ligge i **DittBrukernavn/Library/Application Support/Autodesk/CAM360/libraries/Local/Github_Shared-Tool-Library** dersom du har Mac, eller i **C:\Users\DittBrukermavn\AppData\Roaming\Autodesk\CCAM360\libraries\Local\Github_Shared-Tool-Library**</h6>

4. Ferdig! Postprosessoren for CNCen skal nå være tilgjengelig både i *Post Library* vinduet :point_down: og som en valgbar postprosessor når du trykker på *Post Process* ![Post Process button](.Images/PostProcess.png) når du skal eksportere et CNCprogram.
<br><img src=".Images/DatronM8Added.png">

<br>

---

<br>

## Programmering av CNC-maskinen i Fusion360

Okay, du har lastet ned og importert verktøysbiblioteket og postprosessoren til Fusion360, men hva nå? Hvordan går man fra en Fusion360fil til en fysisk modell? For å gå fra digital til fysisk modell så må du programmere inn hvordan modellen din ligger i CNCen, definere et nullpunkt, generere baner som sier hvordan CNCen skal kutte vekk materiale og eksportere oppsettet og banene til noe CNCen forstår (aka G-kode). Den generelle arbeidsflyten er:

1. [Lage *setup*](#Lage-setups)
2. [Legge til og generere kutteoperasjoner](#Legge-til-operasjoner)
3. [Simulere kutting](#Simulere-kutting)
4. [Eksportere koden til mcr-fil](#Eksportere-til-G-kode)


#### Lage *setups*

<img src=".Images/MakeSetup.gif">

<br>En *setup* forteller maskinen hvordan modellen din er plassert i CNCmaskinen. Dette innebærer bla. hva som er nullpunktet, hvor stor klump med materiale som du begynner med (aka *stock*) og hva som er X-, Y- og Z-aksen. Du kan lage flere setups for én modell, f.eks to setups med Z-akse vridd 180° for en tosidig maskinering.

Slik går du frem for å lage en *setup*:
1. I *manufacturearbeidsområdet, trykk på setupknappen ![Setup Button](.Images/SetupButton.png) som ligger under setupfanen i menyen. Du burde nå få opp noe som ligner på dette :point_down:
<br><img src=".Images/SetupAdded.png">
<br>Her ser du hva som er *stock* (i gult) og hva som er nullpunkt og X-, Y-, og Z-akse i setupen (Blå, grøn og rød pil).

2. Dersom du har flere modeller i filen, gå på *model* og velg den modellen du vil bruke som utgangspunkt for generering av kutteoperasjoner.

3. Velg hva som skal være nullpunkt og X-, Y-, og Z-akse i setupen. På vår CNC peker Z-aksen oppover, X-aksen går fra venstre mot høyre og Y-aksen går fra helt fremme i maskinen og innover bak i maskinen. Du må altså velge X-, Y-, og Z-akse på modellen din slik at Z peker opp og X og Y peker til siden og bak.
    - For å overstyre orienteringen på modellen som automatisk blir satt, trykk på *orientation* under *Work Coordinate System (WCS)* og velg *select z axis/plane & x axis*. Velg deretter hva som skal være referansene for Z-aksen og X-aksen. Dersom aksene peker feil vei, huk av *flip axis* på den aksen som det gjelder.
    - For å velge hva som skal være nullpunkt i modellen din, trykk på *origin* og velg hva slags type nullpunkt du vil ha. Her kan du velge mellom *model origin*, *selected point*, *model box point* og *stock box point*. Som oftest så er det enklest og best å bruke *stock box point*. Deretter velger du hvor på *stocken* nullpunktet ditt skal være. Her er det som oftest enklest og best å velge det nederste venstre hjørnet som ligger på toppen av *stocken* din. Se bilde under :point_down:
    -  Trykk på *stock-fanen*![Stock Tab](.Images/StockTab.png) for å definere hvor stor *stock* du skal ha. Her er det igjen ganske mange forskjellige alternativer, men det funker ofte greit å bare velge *relative size box* og sette på et par millimeter *offset* på toppen og sidene av *stocken*.
    <br>En setup vil som oftest se sånn ut :point_down:
    <br><br>![Setup Finished](.Images/SetupCorrect.png)<br>
4. Trykk på ok.

<br>

#### Legge til operasjoner

<img src=".Images/AddCuttingOperation.gif">

<br>Nå som en setup er laget så kan du begynne å lage og generere kutteoperasjoner! En kutteoperasjon er en generert "sti" som CNCmaskinen følger med en fres for å kutte vekk materiale som ikke er modellen din, slik at du ender opp med at kun modellen din står igjen. Den finnes mange forskjellige strategier for hvordan en kutteoperasjon skal oppføre seg, og det er normalt at man må lage flere kutteoperasjoner med forskjellige fresestørrelser og strategier for å lage et program som funker bra. 

Det å generere kutteoperasjoner er et veldig stort felt innen CNCmaskinering, og det er umilig å samle og forklare alt her. Det beste er å kikke på YouTube og å prøve seg frem for å lære seg og bli bedre på å lage kutteoperasjoner. Med det sagt, her er en generell fremgangsmåte:

1. Velg den *setupen* som skal få en ny kutteoperasjon.

2. Legg til en kurtteoperasjon ved å velge en strategi fra menybaren.
<br><img src=".Images/CuttingStrategies.png" width="300">
<br>Her kan du velge mellom mange forskjellige strategier, men de vanligste er *2D contour*, *Adaptive Clearing*, *Pocket Clearing*, *Horizontal* og *Face*. 
<br><h6>:bulb: Hovre over de forksjellige strategiene i Fusion360 for å få en liten forklaring på hva de gjør.</h6>

3. Når du har valgt en type strategi å bruke så får du opp et vindu med masse variabler :point_down:
<br><br><img src=".Images/ToolpathWindow.png" width="200">
<br><br>Det første du må gjøre i dette vinduet er å velge et verktøy fra verktøysbiblioteket. Dette gjøres ved å trykke på *Select* under *tool* og velge det verktøyet du vil bruke i verktøysbibliotekvinduet som popper opp. Deretter kan du velge en *preset* under *feed & speed* eller skrive inn egne variabler. Det beste er å ta utgangspunkt i en *preset*, for så å forandre på de variablene som det trengs å forandre på. Her må du bare prøve deg frem!
<br><h6>:bulb: Verktøyene med nr **1-13** er **interne** verktøy og CNCmaskinen bytter automatisk mellom disse verktøyene når den kjører de forskjellige kutteoperasjonene. Verktøyene med nr **20 og oppover** er **eksterne** verktøy og må byttes manuelt underveis. Når det er tid for et eksternt verktøysbytte vil CNCmaskinen legge fra seg det nåværende verktøyet, for så å instruere deg om å sette inn det nye eksterne verktøyet. Se [manuelt verktøyskifte under programkjøring](#Manuelt-verktøyskifte-under-programkjøring)</h6>

4. Gå igjennom de forksjellige fanene og se og prøv deg frem med alle variablene som finnes der. To variabler å legge seg merke til er *stepdown* og *stepover*. *Stepdown* er hvor mye fresen skal dykke ned i materialet når den kutter, mens *stepover* er hvor mye fresen skal kutte på siden for hver gang den går over et område.  

5. Trykk på OK og vent til kutteoperasjoonen er generert ferdig. Dette kan ta litt tid hvis det er en stor eller avansert operasjon.<br>
   ###### :bulb: For å generere en kutteoperasjon på  nytt, trykk på **cmd** + **G**.

6. Legg til flere kutteoperasjoner ved å repetere steg 1 - 5. CNCmaskinen kommer til å utføre kutteoperasjonene sekvensiellt fra top til bunn og du kan forandre rekkefølgen på kutteoperasjonene ved å klikke og dra operasjonene opp og ned under setup-treet.

<br>

##### :fire: Noen tips :fire:

* Lag egne *sketcher* i designarbeidsområdet og bruk de som *machining boundary* dersom du vil at en kutteoperasjon kun skal kutte i et spesifikt område.

* Dersom du bruker *2D contour* på en del som har mye sidestock, skru av *lead out* i *linking* fanen i variabelmenyen til operasjonen (dobbelklikk på kutteoperasjonen). Da slipper man at fresen krasjer i *stocken* når maskinen er ferdig med kutteoperasjonen.

* For metall og andre harde materialer er det bedre å ta grunne/lette og raske kutt istedenfor dype og trege kutt.

* *Ballnose*freser er kun til lette *finishing*kutt. Gå derfor først over med en vanlig butt fres for å ta vekk mesteparten av materialet, men skru på *stock to leave* og sett den til 0.5mm så grovkuttet ikke går helt ned til modellen.

* Vår CNC kan i utgangspunktet kun kutte plast, tre, skum, aluminium, messing og kobber.

<br>

#### Simulere kutting

<img src=".Images/Simulate.gif">

<br>Det er lurt å simulere alle kutteoperasjonene før en eksporterer koden for å sjekke at operasjonene kutter som de skal og ikke krasjer i noe. Simuleringen i Fusion360 tar hensyn til diameteren, kuttedybde og lengde på fresestålet for alle operasjonene for å sjekke om maskinen kommer til å krasje eller ikke. I simuleringen kan en også vise hvor nærme den ferdige delen kommer til å være CAD-modellen din.

For å kjøre en simulering, velg de *setupene* du vil simulere (eventuelt spesifikke kutteoperasjoner) og trykk på simuleringsknappen ![Simulate Button](.Images/SimulateButton.png). Du kan nå spille av en animasjon av hvordan CNCen kommer til å kutte. Dersom det blir noen krasj i CNCprogrammet ditt så vil dette vises som en rød strek/felt i den grønne tidslinjebaren helt nederst på skjermen.

:bulb: Du kan velge flere *setups* samtidig og simulere de sammen. Det er nyttig dersom du har en flersidig CNC-fresing og vil simulere hvordan alle *setupene* kommer til å interagere med hverandre. 

:bulb: Dersom du kutter i gråskum så gjør det ikke så mye om du får en kollisjon med *stock*

:bulb: Dersom du krasjer (i simuleringen) pga. et for kort fresestål, så kan du bytte ut fresestålet med et lengre et. Dette gjøres manuelt nede på verkstedet. Dersom du gjør dette så må du huske på å holde diameteren på verktøyet det samme! Altså verktøy nr 9 (6mm) skal **kun** byttes ut med et annet 6mm fresestål.

<br>

#### Eksportere til G-kode

<img src=".Images/Export.gif">

<br>For å eksportere kutteprogrammet ditt, velg den *setupen* du vil eksportere og trykk på eksporteringsknappen ![Export button](.Images/ExportButton.png). Her må du velge *personal posts* som *source* og deretter velge "IPD DATRON M8" som *post processor*. Deretter kan du gi kuttefilen din et navn under *program number* og trykke på ok(Mac)/post(windows) for å eksportere programmet til G-kode.

:bulb: Hvis du skifter navn på filen når du velger hvor du skal lagre filen, husk å end navnet med *.mcr*. Hvis .mcr-endingen ikke er med så vil ikke CNCen kunne åpne filen.

<br>

---

<br>

## Oppstart av CNC-maskinen

For å bruke CNCen må den slås på, kontrollpcen inni CNCen må koble seg til CNCen sitt kontrollsystem og CNCen må utføre en oppstartskalibrering. Alt dette gjøres ved å utføre stegene under :point_down:

1. Skru på strømmen til CNCmaskinen ved å vri den store strømbryteren bak på CNCmaskinen (Stor blå vribryter). Når bryteren vris på så skal det være ganske åpenbart at CNCen skrur seg på, dvs. lyser slår seg på, rare lyder starter, pc-skjermen viser at pcen starter osv.

2. Trykk på den grønne knappen på fremsiden av CNCen. Denne knappen skrur på *emergency relay*, som må være på for at CNCen skal kunne bevege på seg.

3. Når PCen har startet opp (dette tar litt tid), start programmet *Datron* som ligger på skrivebordet på PCen.

4. Trykk OK på advarselen *Machine will move after confirmation*. Nå starter CNCen *homing*prosessen sin. Dersom maskinen ikke beveger på seg, skru opp hastigheten på CNCen (Se [manuell styring](#Manuell_styring)).

5. Etter *homing*sekvensen åpner verktøymagasinet seg og det kommer en *touch-tool-sensor*instruksjon. Åpne da CNCen og trykk **lett** ned på verktøysensoren som ligger inni verktøymagasinet.

6. Se etter hvilket verktøy som ligger i spindelen (kuttehodet til CNCen) og sjekk at det er det samme som står på PC-skjermen. Hvis det er det samme, trykk OK. Det verktøynummeret ikke stemmer overens, bruk piltastene til å velge det verktøyet som står i spindelen og trykk på OK.
<br><h6>:bulb:Du finner verktøysnummeret på verktøyet i spindelen ved å se hvilken plass i verktøysmagasinet som er tomt. Dersom ingen er tomme så er verktøyet i spindelen nr 0 (dvs eksternt verktøy).</h6><br>

7. CNCen er nå skrudd å og du burde se et slikt :point down: vindu på pcskjermen.

<br>

---

<br>

## Manuell styring

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Feste *stock* i CNCen

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Sette nullpunkt

Her kommer det info snart. Jeg lover!

<br>

---

<br>


## Laste inn og starte kutteprogram

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Justere hastighet og kjøling under programkjøring

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Skru av maskinen

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## manuelt verktøyskifte under programkjøring

<br>

---

<br>


## Utføre enkle kutt direkte på CNCen

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Andre festemetoder

Her kommer det info snart. Jeg lover!

### Pneumatiske tvinger

### Flyttbare festebord i aluminium

### Direkte feste til CNCbordet

<br>

---

<br>


## Lagre og laste inn nullpunkt

Her kommer det info snart. Jeg lover!

<br>

---

<br>


## Vri koordinatsystem til CNCen

Her kommer det info snart. Jeg lover!

<br>

---

<br>


## Starte et program fra en spesifikk plass

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Bytte ut et internt fresestål med et lenger fresestål

Her kommer det info snart. Jeg lover!

<br>

---

<br>

## Rotasjonsakse

Vi har en rotasjonsakse, men vi får den ikke koblet til :disappointed:. Maskinen detekterer aksen når det blir koblet til (du må restarte Datron programmet for at den skal bli detektert), men får feilmelding 1246 overload når den *homer*. Motorfeilmeldingen er mer spesifikt *overload drag error*. Kan se ut som det er H-broen til DC-motoren inni servoen som er problemet, men det er ennå usikkert. Har sjekket DC-motoren, rotasjonsenkoderen og endestoppet, og de funker fint. Ser også ut som logikken til servoen fungerer ettersom maskinen får koblet seg til og får feilmeldingsdata fra servoen. 

Har tatt kontakt med Datron, men har ikke kommet frem til noen tekniker enda (Datron sin kundeservice suuuger). Tipper det beste er å spørre om de har og kan sende et nytt kretskort til servoen.

**Update 23.06.2021** Har bestilt nytt driverkort til rotasjonsaksen fra Datron/ABC-maskin. Kostet 14500kr :dizzy_face:

<br>

---

<br>