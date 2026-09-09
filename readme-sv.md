# Maintain 0.9.12

Göra och underhålla tillägg. Utvecklad av Anna Svensson.

<p align="center"><img src="screenshot.png" alt="Skärmdump" /></p>

## Hur man installerar ett tillägg

[Ladda ner ZIP-filen](https://github.com/annaesvensson/yellow-maintain/archive/refs/heads/main.zip) och kopiera den till din `system/extensions` mapp. [Läs mer om tillägg](https://github.com/annaesvensson/yellow-update/tree/main/readme-sv.md).

## Hur man gör ett tillägg

[Börja med en exempel-funktion](https://github.com/annaesvensson/yellow-example) eller [ett exempel-tema](https://github.com/annaesvensson/yellow-stockholm) för Datenstrom Yellow. Det är bäst att titta på koden för några tillägg i `system/workers` mappen och bekanta dig med den. Sen kan du dyka in i vilket tillägg som helst och hitta en välbekant struktur som du snabbt kan hitta runt i. För sofistikerade tillägg finns det ett [API för utvecklare](https://datenstrom.se/sv/yellow/help/api-for-developers). De flesta tillägg består av kod, dokumentation och andra filer. [Tilläggsinställningar](#inställningar-extension) lagras i filen `extension.ini`. Dessa tilläggsinställningar innehåller information om alla filer som ska installeras. Gjorde du ett nytt tillägg? Skapa ett nytt repository på [Codeberg](https://codeberg.org/explore/repos?q=datenstrom-yellow&topic=true&sort=moststars), [GitHub](https://github.com/topics/datenstrom-yellow) eller någon av de många Git-hostingplattformarna. Ladda upp dina filer till ditt repository och lägg till temat `datenstrom-yellow` i ditt repository.

## Hur man förbättrar ett tillägg

Du kan förbättra tillägg och visa dem för andra människor. Det här är ett bra sätt att få feedback och att experimentera med funktioner. De flesta tillägg börjar som experimentella med `Status: experimental`. Med tiden får man en bättre förståelse för vad människor behöver och kan förbättra tillägg. Föreställ dig vad användaren vill göra och vad som skulle göra deras liv enklare. Fråga dig själv, behöver jag det här, vill jag det här, kan jag göra det här bättre? Kom ihåg att fokusera på människor. Inte på tekniska detaljer och massor av funktioner. För erfarna utvecklare finns det en [stilguide](https://github.com/annaesvensson/yellow-help/blob/main/yellow-style-guide.md). Förbättrade du ett tillägg från en annan utvecklare? Gör en fork av relevanta repository och skicka en pull-request till utvecklaren.

## Hur man underhåller ett tillägg

Detta steg är endast nödvändigt för [tillägg på officiella webbplatsen](https://datenstrom.se/sv/yellow/extensions/) med `Status: maintained`. Underhållning informerar [uppdateringsmekanismen](https://github.com/annaesvensson/yellow-update/tree/main/readme-sv.md) om att en ny version av ett tillägg är tillgänglig. Underhållning uppdaterar dessutom readme-filen med det nya versionsnumret. Tänk på att endast tillägg som är tillgängliga på den officiella webbplatsen kommer att ingå i uppdateringsmekanismen.

Du kan underhålla tillägg på [kommandoraden](https://github.com/annaesvensson/yellow-core/tree/main/readme-sv.md). Se till att du har fyllt i [kontrollistan](https://github.com/annaesvensson/yellow-help/blob/main/yellow-review-checklist.md) innan du börjar. Är du redo att underhålla tillägg? Öppna ett terminalfönster. Gå till installationsmappen där filen `yellow.php` finns. Skriv `php yellow.php maintain all`. Du kan valfritt lägga till namnet på en mapp. Detta uppdaterar nödvändiga filerna i relevanta mapparna. Ladda upp dina ändringar och skicka en pull-request till repository `datenstrom/yellow`.

## Exempel

Tilläggsinställningar för en funktion:

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

Tilläggsinställningar för ett språk:

~~~
# Datenstrom Yellow extension settings

Extension: Swedish
Version: 0.9.6
Description: Swedish language.
Translator: Anna Svensson
Tag: language
DownloadUrl: https://github.com/annaesvensson/yellow-language/raw/main/downloads/swedish.zip
DocumentationUrl: https://github.com/annaesvensson/yellow-language/tree/main/translations/swedish
Published: 2026-09-08 21:54:03
Status: maintained
system/workers/swedish.php: swedish.php, create, update
~~~

Tilläggsinställningar för ett tema:

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

Visar mappar på kommandoraden:

`php yellow.php maintain`  

Underhålla alla mappar på kommandoraden:

`php yellow.php maintain all`  

Underhålla tillägg på kommandoraden:

`php yellow.php maintain yellow-example`  
`php yellow.php maintain yellow-language`  
`php yellow.php maintain yellow-stockholm`  

## Inställningar

Följande inställningar kan konfigureras i filen `system/extensions/yellow-system.ini`:

`MaintainCodeDirectory` = mapp med kod för tillägg  
`MaintainWebsiteDirectory` = mapp med filer för den officiella webbplatsen  

<a id="inställningar-extension"></a>Följande inställningar kan konfigureras i filen `extension.ini`:

`Extension` = tilläggets namn  
`Version` = tilläggets versionsnummer  
`Description` = tilläggets beskrivning, en kort mening  
`Developer` = ansvarig utvecklare av en funktion, kommaseparerade  
`Designer` = ansvarig formgivare av ett tema, kommaseparerade  
`Translator` = ansvarig översättare av ett språk, kommaseparerade  
`Tag` = taggar för kategorisering av tillägget, kommaseparerade  
`DownloadUrl` = tilläggets nedladdningsadress  
`DocumentationUrl` = tilläggets dokumentation  
`DocumentationLanguage` = tilläggets dokumentationsspråk, kommaseparerade  
`Published` = tilläggets publiceringsdatum, ÅÅÅÅ-MM-DD format  
`Status` = tilläggets status, [stödda statusvärden](#inställningar-status)  

<a id="inställningar-status"></a>Följande statusvärden stöds:

`experimental` = tillägget är experimentellt, användning på egen risk  
`maintained` = tillägget underhålls och [visas på officiella webbplatsen](https://datenstrom.se/sv/yellow/extensions/)  
`unmaintained` = tillägget underhålls inte längre  
`unassembled` = tillägget sätts ihop av verktygskedjan  

<a id="inställningar-actions"></a> Följande filåtgärder stöds:

`create` = skapa fil om den inte finns  
`update` = skriv över fil om den inte finns  
`delete` = ta bort fil om den inte finns  
`optional` = endast för första installationen  
`additional` = endast efter första installationen  
`careful` = endast om den inte ändras  
`compress` = skapa ZIP-fil från angivna mappen  
`multi-language` = använda innehållsfil från motsvarande mappen  

Har du några frågor? [Få hjälp](https://datenstrom.se/sv/yellow/help/).
