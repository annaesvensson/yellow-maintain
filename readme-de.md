# Maintain 0.9.12

Erweiterungen erstellen und pflegen. Entwickelt von Anna Svensson.

<p align="center"><img src="screenshot.png" alt="Bildschirmfoto" /></p>

## Wie man eine Erweiterung installiert

[ZIP-Datei herunterladen](https://github.com/annaesvensson/yellow-maintain/archive/refs/heads/main.zip) und in dein `system/extensions`-Verzeichnis kopieren. [Weitere Informationen zu Erweiterungen](https://github.com/annaesvensson/yellow-update/tree/main/readme-de.md).

## Wie man eine Erweiterung erstellt

[Beginne mit einer Beispiel-Funktion](https://github.com/annaesvensson/yellow-example) oder [einem Beispiel-Theme](https://github.com/annaesvensson/yellow-stockholm) für Datenstrom Yellow. Am besten schaust du dir den Code von einigen Erweiterungen im `system/workers`-Verzeichnis an und machst dich damit vertraut. Dann kannst du in jede Erweiterung eintauchen und findest eine vertraute Struktur vor, in der du dich schnell zurecht findet. Für anspruchsvolle Erweiterungen gibt es eine [API für Entwickler](https://datenstrom.se/de/yellow/help/api-for-developers). Die meisten Erweiterungen bestehen aus Code, Dokumentation und weiteren Dateien. Die [Erweiterungseinstellungen](#einstellungen-extension) sind in der Datei `extension.ini` gespeichert. Diese Erweiterungseinstellungen enthalten Informationen über alle Dateien die installiert werden sollen. Hast du eine neue Erweiterung erstellt? Erstelle ein neues Repository auf [Codeberg](https://codeberg.org/explore/repos?q=datenstrom-yellow&topic=true&sort=moststars), [GitHub](https://github.com/topics/datenstrom-yellow) oder einer der vielen Git-Hosting-Platformen. Lade deine Dateien in dein Repository hoch und füge das Thema `datenstrom-yellow` zu deinem Repository hinzu.

## Wie man eine Erweiterung verbessert

Du kannst Erweiterungen verbessern und anderen Menschen zeigen. Das ist eine großartige Möglichkeit um Feedback zu erhalten und mit Funktionen zu experimentieren. Die meisten Erweiterungen beginnen experimentell mit `Status: experimental`. Im Laufe der Zeit bekommt man ein besseres Verständnis dafür was Menschen brauchen und kann experimentelle Erweiterungen verbessern. Stell dir vor was der Benutzer machen möchte und was dessen Leben einfacher machen würde. Frage dich selbst, brauche ich das, will ich das, kann ich das besser machen? Denk daran dich auf Menschen zu konzentrieren. Nicht auf technische Details und viele Funktionen. Für erfahrene Entwickler gibt es einen [Styleguide](https://github.com/annaesvensson/yellow-help/blob/main/yellow-style-guide.md). Hast du die Erweiterung eines anderen Entwicklers verbessert? Mache ein Fork vom entsprechenden Repository und sende einen Pull-Request an den Entwickler.

## Wie man eine Erweiterung pflegt

Dieser Schritt ist nur für [Erweiterungen auf der offiziellen Webseite](https://datenstrom.se/de/yellow/extensions/) mit `Status: maintained` erforderlich. Durch das Pflegen wird der [Aktualisierungsmechanismus](https://github.com/annaesvensson/yellow-update/tree/main/readme-de.md) darüber informiert, dass eine neue Version einer Erweiterung verfügbar ist. Durch das Pflegen wird ausserdem die Readme-Datei mit der neuen Versionsnummer aktualisiert. Denke daran, dass nur Erweiterungen die auf der offiziellen Webseite verfügbar sind in den Aktualisierungsmechanismus einbezogen werden.

Du kannst Erweiterungen in der [Befehlszeile](https://github.com/annaesvensson/yellow-core/tree/main/readme-de.md) pflegen. Stelle sicher, dass du die [Überprüfungscheckliste](https://github.com/annaesvensson/yellow-help/blob/main/yellow-review-checklist.md) ausgefüllt hast, bevor du damit beginnst. Bist du bereit eine Erweiterung zu pflegen? Öffne ein Terminalfenster. Gehe ins Installations-Verzeichnis, dort wo sich die Datei `yellow.php` befindet. Gib ein `php yellow.php maintain all`. Du kannst wahlweise den Namen eines Verzeichnisses angeben. Das aktualisiert die notwendigen Dateien in den Repositories. Lade deine Änderungen hoch und sende einen Pull-Request an das Repository `datenstrom/yellow`.

## Beispiele

Erweiterungseinstellungen für eine Funktion:

~~~
# Datenstrom Yellow extension settings

Extension: Example
Version: 0.9.2
Description: Example feature for Datenstrom Yellow.
Developer: Anna Svensson
Tag: example, feature
DownloadUrl: https://github.com/datenstrom/yellow-example/archive/refs/heads/main.zip
DocumentationUrl: https://github.com/datenstrom/yellow-example
Published: 2026-01-30 19:00:30
Status: experimental
system/workers/example.php: example.php, create, update
~~~

Erweiterungseinstellungen für eine Sprache:

~~~
# Datenstrom Yellow extension settings

Extension: German
Version: 0.9.6
Description: German language.
Translator: David Fehrmann
Tag: language
DownloadUrl: https://github.com/annaesvensson/yellow-language/raw/main/downloads/german.zip
DocumentationUrl: https://github.com/annaesvensson/yellow-language/tree/main/translations/german
Published: 2026-09-08 21:54:03
Status: maintained
system/workers/german.php: german.php, create, update
~~~

Erweiterungseinstellungen für ein Theme:

~~~
# Datenstrom Yellow extension settings

Extension: Stockholm
Version: 0.9.6
Description: Stockholm is a clean theme.
Designer: Anna Svensson
Tag: example, theme
DownloadUrl: https://github.com/annaesvensson/yellow-stockholm/archive/refs/heads/main.zip
DocumentationUrl: https://github.com/annaesvensson/yellow-stockholm
DocumentationLanguage: en, de, sv
Published: 2026-02-23 09:49:55
Status: maintained
system/workers/stockholm.php: stockholm.php, create, update
system/themes/stockholm.css: stockholm.css, create, update, careful
system/themes/stockholm.png: stockholm.png, create
system/themes/stockholm-opensans-bold.woff: stockholm-opensans-bold.woff, create, update, careful
system/themes/stockholm-opensans-light.woff: stockholm-opensans-light.woff, create, update, careful
system/themes/stockholm-opensans-regular.woff: stockholm-opensans-regular.woff, create, update, careful
~~~

Vorhandene Verzeichnisse in der Befehlszeile anzeigen:

`php yellow.php maintain`  

Alle Verzeichnisse in der Befehlszeile pflegen:

`php yellow.php maintain all`  

Erweiterungen in der Befehlszeile pflegen:

`php yellow.php maintain yellow-example`  
`php yellow.php maintain yellow-language`  
`php yellow.php maintain yellow-stockholm`  

## Einstellungen

Die folgenden Einstellungen können in der Datei `system/extensions/yellow-system.ini` vorgenommen werden:

`MaintainCodeDirectory` = Verzeichnis mit dem Code der Erweiterungen  
`MaintainWebsiteDirectory` = Verzeichnis mit den Dateien der offiziellen Webseite  

<a id="einstellungen-extension"></a>Die folgenden Einstellungen können in der Datei `extension.ini` vorgenommen werden:

`Extension` = Name der Erweiterung  
`Version` = Versionsnummer der Erweiterung  
`Description` = Beschreibung der Erweiterung, ein kurzer Satz  
`Developer` = verantwortlicher Entwickler einer Funktion, durch Komma getrennt  
`Designer` = verantwortlicher Designer eines Themes, durch Komma getrennt  
`Translator` = verantwortlicher Übersetzer einer Sprache, durch Komma getrennt  
`Tag` = Tags zur Kategorisierung der Erweiterung, durch Komma getrennt  
`DownloadUrl` = Adresse zum Herunterladen der Erweiterung  
`DocumentationUrl` = Dokumentation der Erweiterung  
`DocumentationLanguage` = Dokumentationssprachen der Erweiterung, durch Komma getrennt  
`Published` = Veröffentlichungsdatum der Erweiterung, JJJJ-MM-TT Format  
`Status` = Status der Erweiterung, [unterstützte Statuswerte](#einstellungen-status)  

<a id="einstellungen-status"></a>Die folgenden Erweiterungs-Statuswerte werden unterstützt:

`experimental` = Erweiterung ist experimentell, Nutzung auf eigene Gefahr  
`maintained` = Erweiterung wird gepflegt und [auf der offiziellen Webseite angezeigt](https://datenstrom.se/de/yellow/extensions/)  
`unmaintained` = Erweiterung wird nicht mehr gepflegt  
`unassembled` = Erweiterung wird durch Werkzeugkette zusammengebaut  

<a id="einstellungen-actions"></a>Die folgenden Dateiaktionen werden unterstützt:

`create` = Datei erstellen falls nicht vorhanden  
`update` = Datei überschreiben falls vorhanden  
`delete` = Datei löschen falls vorhanden  
`optional` = nur bei Neuinstallation  
`additional` = nur nach Neuinstallation  
`careful` = nur falls nicht verändert  
`compress` = ZIP-Datei aus dem angegebenen Verzeichnis erstellen  
`multi-language` = Inhaltsdatei aus dem entsprechenden Verzeichnis verwenden  

Hast du Fragen? [Hilfe finden](https://datenstrom.se/de/yellow/help/).
