# Github-Shared-CNC-Tool-Library

 
### Hvordan importere til Fusion360

#### For Mac/OSX

1. Trykk på **Code** og åpne repoet i **GitHub Desktop** (Eventuelt klon repoet til pc'en din vha https, ssh eller cli)

2. Lagre repoet i **DittBrukernavn/Library/Application Support/Autodesk/CAM360/libraries/Local**.
![Add Repo GitHub Desktop](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/GitHubDesktopAddRepo.png?raw=true)
 ###### :bulb: Dersom Library mappen ikke vises i Finder, trykk **cmd + J** i Finder og huk av **Show Library Folder**

3. For å sjekke at biblioteket er importert, åpne Fusion360, gå til CAM/Manufacture-arbeidsområdet og trykk på dette 
![Tool Library Button](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ToolLibrarySymbol.png?raw=true)
 symbolet. 
 ![Tool Library Location](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ToolLibraryInFusion.png?raw=true)
 Verktøybiblioteket til CNCen på verkstedet vil ligge under **Local -> Github-Shared-CNC-Tool-Library -> IPD Datron**

3. Oppdater repoet med jevne mellomrom gjennom git for å holde verktøybiblioteket og *feeds & speeds* oppdatert.


### Alternativ måte

###### :warning: *Med denne måten så vil man ikke kunne oppdatere verktøybiblioteket igjennom git*

1. Last ned repoen som en .zip og ekspander .zip-folderen.
2. Åpne Fusion 360, gå til **CAM/Manufature-arbeidsområdet** og trykk på ![Tool Library Button](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ToolLibrarySymbol.png?raw=true) for å komme til *Tool Library*. 
3. Importer verkstedet sitt verktøysbibliotek for CNCmaskinen ved å trykke på importer ![Import Button](https://github.com/tckaland/Github-Shared-CNC-Tool-Library/blob/master/ImportLibrarySymbol.png?raw=true) og velg **IPD Datron.json** som befinner seg i *.zip* filen du lastet ned fra GitHub.


