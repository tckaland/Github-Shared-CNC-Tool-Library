# Github-Shared-CNC-Tool-Library

### Hva er dette?

Hvis du vil kutte ut noe på CNC-maskinen på verkstedet, eller bare er *keen* på å lære deg å programmere CNC-maskinen igjennom Fusion360, så er dette plassen for deg! 

Her finner du et stadig voksende bibliotek over verktøy som finnes til CNC-maskinen vår, med tilhørende forhåndsinnstillinger for hastighet og kuttedybde. I tillegg finner du en egen *postprosessor* til vår CNC (Datron M8 fra 2006) som gjør det enklere å bruke verktøy med manuellt skifte.

I readme-filen (filen du leser nå :astonished:), finner du også info om dette:

- [Hvordan importere verktøysbibliotek til Fusion360](#Hvordan-importere-verktøysbibliotek-til-fusion360)
- [Hvordan importere postprosessor til Fusion360](#Hvordan-importere-postprosessor-til-Fusion360)

<div style="page-break-after: always;"></div>

### Hvordan importere verktøysbibliotek til Fusion360

#### For Mac/OSX

1. Trykk på **Code** og åpne repoet i **GitHub Desktop** (Eventuelt klon repoet til pcen din vha. https, ssh eller cli)

2. Lagre repoet i **DittBrukernavn/Library/Application Support/Autodesk/CAM360/libraries/Local**.
######          :bulb: Dersom Library mappen ikke vises i Finder, trykk **cmd + J** i Finder og huk av **Show Library Folder**
![Add Repo GitHub Desktop](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/GitHubDesktopAddRepo.png?raw=true)


3. For å sjekke at biblioteket er importert, åpne Fusion360, gå til CAM/Manufacture-arbeidsområdet og trykk på dette 
![Tool Library Button](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ToolLibrarySymbol.png?raw=true)
 symbolet. 
 ![Tool Library Location](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ToolLibraryInFusion.png?raw=true)
 Verktøybiblioteket til CNCen på verkstedet vil ligge under **Local -> Github-Shared-CNC-Tool-Library -> IPD Datron**

3. Oppdater repoet med jevne mellomrom gjennom git for å holde verktøybiblioteket og *feeds & speeds* oppdatert. 
    <br>Dersom du bruker GitHub Desktop, så gjøres dette enkelt ved å trykke på knappen "fetch origin".


### Alternativ måte
###### :warning: *Med denne måten så vil man ikke kunne oppdatere verktøybiblioteket igjennom git fortløpende*

1. Last ned repoen som en .zip og ekspander .zip-folderen.
2. Åpne Fusion 360, gå til **CAM/Manufature-arbeidsområdet** og trykk på ![Tool Library Button](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ToolLibrarySymbol.png?raw=true) for å komme til *Tool Library*. 
3. Importer verkstedet sitt verktøysbibliotek for CNCmaskinen ved å trykke på importer ![Import Button](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ImportLibrarySymbol.png?raw=true) og velg **IPD Datron.json** som befinner seg i *.zip* filen du lastet ned fra GitHub.


### Hvordan importere postprosessor til Fusion360