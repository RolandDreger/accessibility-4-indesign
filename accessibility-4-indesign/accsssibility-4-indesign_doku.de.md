
# Accessibility-4-InDesign – Dokumentation

Das Plug-in *Accessibility-4-InDesign* soll dir dabei helfen, barrierefreie Dokumente mit *Adobe InDesign* zu erstellen, und dabei Probleme frühzeitig zu erkennen.

## Report

Der Report listet mögliche Probleme schon während der Erstellung eines InDesign-Dokumentes auf. Als Checkliste kann er helfen, die wichtigsten Anforderungen an die Barrierefreiheit noch vor dem PDF- oder ePub-Export im Blick zu behalten.

Die einzelnen Abschnitte des Reports können über die zugehörigen Buttons unabhängig voneinander oder über den Button `Alle` gemeinsam erstellt werden. Über Anwendung der Filter in den Report-Bereichen kannst du die Einträge nach deinen Anforderungen ein- oder ausblenden.

### Metadaten

Der Metadaten-Report bietet eine Übersicht über die wichtigsten Metadaten für PDF- und ePub-Dokumente. Über die Eingabefelder und Checkboxen kannst du die Einträge direkt ändern.

[Vorschau des Metadaten-Reports auf vimeo](https://vimeo.com/1036508410)

### Bilder

Der Bild-Report listet alle Bilder und Grafiken mit ihren Einträgen für *alternativen- und tatsächlichen Text* auf. Auch Gruppen werden in der Liste angeführt, sofern diesen ein alternativer Text zugewiesen ist. Durch Klick auf die Bilder im Panel kann direkt zu den zugehörigen Elementen im InDesign-Dokument gesprungen werden.

[Vorschau des Bild-Reports auf vimeo](https://vimeo.com/1031495125)

Beim ersten Erstellen des Bild-Reports werden die Bilder in den Plugin-Speicher geladen. Dies nimmt (abhängig von der Anzahl der vorhandenen Bilder) etwas mehr Zeit in Anspruch als die weiteren Durchläufe. Der Plug-Speicher kann über den Button `Leeren` im Fuß des Panels geleert werden, etwa wenn du den Ausschnitt eines Bildes geändert hast.

**Tipp:** Ist neben dem Report-Panel auch das ALT-Text-Panel geöffnet, können fehlende Alternativtexte gleich über dieses eingegeben werden.

**Hinweis**: Wenn du mit XML arbeitest, kann es zu einer fehlerhaften Zuordnung von Tags im exportieren PDF kommen. Diese Problemstellen sind automatisiert leider nicht zu ermitteln.[^1]

[^1]: Bug report: [Before tag and after untag frame with different behavior](https://indesign.uservoice.com/forums/601180-adobe-indesign-bugs/suggestions/49266116)

#### Welche Objekte werden im Bild-Report gelistet?

Im Bild-Report werden jene Objekte gelistet, die zu einem Eintrag für alternativen oder tatsächlichen Text im exportieren PDF bzw. ePub führen. 

PDF 
- Attribut *ALT* im <Tag>-Element (Adobe Acrobat: *Alternativtext für Bilder*) 
- Attribut *ActualText* im <Tag>-Element (Adobe Acrobat: *Originaltext*)

ePub
- Attribut *alt* im <img>-Element

#### Warum gibt es hier einen Filter für PDF und ePub?

Da sich hier in einigen Fällen der PDF- und ePub-Export unterschiedlich verhält. Beispiel gruppierte Elemente: Trägst du für eine Gruppe im InDesign-Dokument einen alternativen Text ein, wird dieser dem <Tag>-Element im exportierten PDF zugewiesen. Die alternativen Texte der einzelnen Gruppen-Elemente gehen hingegen verloren. Umgekehrt verhält es sich beim ePub-Export. Hier wird der Alternativtext der Gruppe ignoriert und jene der Gruppen-Elemente werden in die ALT-Attribute übernommen. 

Um leichter den Überblick zu bewahren, werden nur jene Objekte im Bild-Report gelistet, die auch zu einem Eintrag für alternativen oder tatsächlichen Text führen. Zudem kannst du über die Filterfunktion auswählen, welche für dich relevant sind – je nachdem, ob du ein PDF oder ePub exportierst. 

### Export-Tags

Der Tag-Report listet alle *Tags* (PDF-Tagstruktur, ePub-HTML-Elementnamen) für im InDesign-Dokument vorhandenen Zeichen-, Absatz- und Objektformate auf. Zudem wird in der Tabelle für die Textformate die zugewiesene Sprache angezeigt.

[Vorschau des Export-Tag-Report auf vimeo](https://vimeo.com/1036510247)

In barrierefreien Dokumenten werden Tags verwendet, um eine logische Struktur der Inhalte zu schaffen. Diese Tags bestimmen die Rolle eines Objekts, wie z.B. eine Überschrift, einen Absatz oder eine Abbildung. Dies ermöglicht Screenreader und anderen assistiven Technologien, die Inhalte korrekt zu interpretieren und wiederzugeben. Die Tag-Struktur ist eine zusätzliche Ebene der Dokumentenstruktur, die über die visuelle Darstellung hinausgeht. 

In InDesign kannst du die Tags für ePub/HTML und PDF in den Formatvorlagen (Zeichenformate, Absatzformate, Objektformate) unter dem Punkt `Tagexport` festlegen. Wird hier keine Auswahl getroffen, erfolgt die Zuordnung automatisch. Diese von InDesign **automatisch vergebenen Tag-Namen** stehen im Report **in eckigen Klammern.** Wenn in der Tabelle hier mehr als ein Tag-Name angezeigt wird, hängt der zugewiesen Tag zudem von den getroffenen Einstellungen beim Export ab.

#### Formate hervorheben

Mit dem kleine Highlight-Icon in der letzten Tabellenspalte können die einzelnen Zeichen- und Absatzformate im Dokument hervorgehoben werden, genauer: Textstellen, denen dieses Format zugewiesen ist, werden mit einer Farbe »markiert«. 

Die Hervorhebung erfolgt dabei über bedingten Text: Fenster → Schrift und Tabellen → Bedingter Text. (Um die Hinterlegung mit bedingtem Text sichtbar zu machen, schaltet das Plugin den Anzeige-Modus von InDesign auf `Normal` um.)

Durch erneutes Klicken auf das Highlight-Icon in der Tabellen-Zeile kannst du die Hervorhebung wieder entfernen. Willst du **alle Hinterlegungen für einen Formattype entfernen,** kannst du das erste **Highlight-Icon im Tabellenkopf** anklicken.

**Hinweis:** Wird im InDesign-Dokument mit **»Bedingtem Text«** gearbeitet, können durch Klicken auf das Highlight-Icon diese Bedingung von den hervorgehobenen Textstellen entfernt werden. Wenn die Anwendung von Textbedingung also für dein Dokument wichtig ist, diese Funktion bitte **nicht verwenden**.

### Artikel

Der Artikel-Report bietet eine Auflistung aller im Artikelbedienfeld von InDesign angelegten Artikel. Zudem werden mögliche, damit im Zusammenhang stehende Fehler angezeigt.

[Vorschau des Artikel-Reports auf vimeo](https://vimeo.com/1044736860)

Die Artikelfunktion in InDesign dient dazu, die Reihenfolge der Tag-Struktur von Inhalten in einem Dokument festzulegen. Im Artikelbedienfeld von InDesign kannst du definieren, welche Inhalte im Dokument getaggt werden und in welcher Reihenfolge. Damit stellst du sicher, dass die Inhalte in der richtigen Reihenfolge von Screenreader vorgelesen werden.

#### Überschriften

Die Überschriftenebenen werden über alle Artikel hinweg kontrolliert – in der Reihenfolge, in der die Artikel und ihre enthaltenen Objekte im Artikelbedienfeld eingefügt sind.

##### Fehler und Warnungen für PDFs: 

- Keine Überschriften vorhanden.
- Erste Überschrift nicht auf der ersten Ebene.
- Übersprungene Überschriftenebene.
- Unlogische Reihenfolge der Überschriften.

##### Fehler und Warungen für ePubs:

- Keine Überschriften vorhanden.
- Unlogische Reihenfolge der Überschriften.

#### Artikel ein-/ausblenden

Über das Augen-Icon neben dem Artikelnamen kannst du alle Objkte eines Artikels aus- und wieder einblenden. Das hilft dir festzustellen, ob auch alle gewünschten Objekte einem der Artikel zugeordnet sind. 

### Hyperlinks

Auflistung der im InDesign-Dokument enthaltenen Hyperlinks. Im ersten Feld wird der im Dokument angezeigte Text des Hyperlinks angezeigt, im zweiten Feld das hinterleget Ziel (URL, Anker, Seite, ...). Über einen Klick aufs erste Feld kannst du die Textstellen mit dem Hyperlink direkt anspringen.

**Hinweis:**: Aus technischen Gründen kann der Alternativtext für Hyperlinks in InDesign derzeit nicht ausgelesen werden. (Benutzeroberfläche: Hyperlink bearbeiten → Barrierefreiheit) Expert:innen raten aber ohnehin von der Verwendung eher ab. Wenn möglich, sollten stattessen »sprechende Namen« für Hyperlinks verwendet werden. Davon profitieren alle Zielgruppen gleichermaßen. (Für Print können diese dann per Skript oder CSS in URL umwandelt werden.)

### Text

Im Text-Report wird auf mögliche Probleme im Zusammenhang mit Text hingewiesen. Auch hier gilt: Durch eine automatisierte Suche ist es nicht immer möglich, alle Problemstellen eindeutig zu ermitteln, bzw. werden auch Probleme gefunden, die möglicherweise gar keine sind. Überprüfe die Probleme einzeln, indem du über den Button `Suchen` an die betroffenen Textstellen im Dokument springst.

### Export als PDF

Das Ergebnis des Reports kann als PDF-Datei exportiert werden. Dabei werden nur jene Abschnitte und Einträge exportiert, die auch im Panel sichtbar sind. Somit kannst du über das Ein-/Ausblenden der Abschnitte und über die Filter genau steuern, welche Information in das exportierte PDF übernommen werden sollen.

Das generierte PDF für den Report wird standardmäßig im temporären Ordner des Plugins gespeichert und danach in deiner Standard-Anwendung für PDFs automatisch geöffnet. Alternativ kann in den Einstellungen des Plugins die Option `Speichern-Dialog öffnen` gewählt werden. Damit kannst du einen individuellen Speicherort für die PDF-Datei auswählen.

[Vorschau des PDF-Exports auf vimeo](https://vimeo.com/1053449077)

Für die Erstellung des Report-PDFs wird die [Adobe PDF Services API verwendet](https://developer.adobe.com/document-services/).

#### Das PDF wird nach dem Export nicht angezeigt?

Der PDF-Report wird in der Standard-Anwendung geöffnet, in der diese auch via Doppelklick über den Dateibrowser geöffnet worden wäre. Sollte die PDF-Datei unter Windows nicht angezeigt werden, kann stattdessen in den Einstellungen des Plugins, die Option `Speichern-Dialog öffnen` gewählt werden. Damit kannst du einen individuellen Speicherort für den Report auswählen. 

## Fragen

Im Reiter `Fragen` findest du einen Assistenten, der dir auf Fragen zum Thema Barrierefreiheit antwortet. Du kannst aber auch Fragen zur Bedienung von InDesign und Acrobat stellen. Der Assistent basiert auf einem Large Language Model (LLM) von OpenAI. Sprachmodelle können Fehler machen. Überprüfe deshalb wichtige Informationen und gib keine sensiblen Daten ein, beispielsweise keine personenbezogenen oder vertraulichen Daten.

Unter den Antworten des Assistenten werden jeweils die Quellen genannt, die als Grundlage für die Beantwortung herangezogen wurden. Über die Links findest du weitere Informationen zum Thema. Wird kein URL angezeigt, beruht die Information auf den eigenen Daten des Plugins (oder der Assistent hat Mist gebaut).

## Einstellungen
### Lizenzschlüssel

Im Reiter `Einstellungen` kann der Lizenzschlüssel eingegeben werden, den du beim Kauf des Plug-ins erhalten hast.

### Report
#### Export

Für den exportieren Report kann ein Dokument-Titel und der Name der Erstellerin, des Erstellers eingetragen werden.

Option `Speichern-Dialog öffnen`: Hier kannst du festlegen, ob ein Auswahldialog für den Speicherort der PDF-Datei des exportierten Reports angezeigt werden soll. Standardmäßig ist als Speicherort der temporären Ordner des Plugins vorausgewählt.

Option `PDF nach Export anzeigen`: Mit dieser Option legst du fest, ob das PDF nach dem Export des Reports in deiner Standard-Anwendung geöffnet wird. (Die Standard-Anwendung ist jene Anwendung, in der eine PDF-Datei via Doppelklick über den Dateibrowser geöffnet wird.)


## Grenzen von Plug-in und InDesign

Derzeit können nicht immer alle Anforderungen an ein barrierefreies Dokument mit Bordmitteln von InDesign erfüllt werden, wie beispielsweise die Umsetzung von barrierefreien Tabellen im exportierten PDF oder das Setzen des PDF/UA-Markers. Dies muss entweder mittels dafür spezialisierter Erweiterungen – z.B. MadeToTag – oder nach dem Export in entsprechenden Anwendungen durchgeführt werden – z.B für PDFs in Adobe Acrobat oder im Falle eines ePubs in einem ePub-Editor.

Die exportierten PDF- und ePub-Dokumente können nach dem Export mit darauf spezialisierten Anwendungen getestet werden:

- [PAC](https://pac.pdf-accessibility.org/de)
- [veraPDF](https://verapdf.org/)

- [EPUP-Checker (Pagina)](https://pagina.gmbh/startseite/leistungen/publishing-softwareloesungen/epub-checker/)
- [EPUBCheck (W3C)](https://www.w3.org/publishing/epubcheck/)

Darüber hinaus ist eine manuelle, auf die Zielpersonen abgestimmte Prüfung jedenfalls angeraten.

## Grenzen automatisierter Prüfung

Automatisierte Prüfungen können nur einen Teil der Barrierefreiheit digitaler Inhalte abdecken. So können etwa keine sogenannten »Layout-Tabellen« erkannt werden, also Tabellen, die ausschließlich zum Zwecke des Layouts eingesetzt werden – ohne inhaltliche Bedeutung. Oder wenn Informationen ausschließlich durch Farbe kommuniziert werden. Um nur einige Beispiele zu nennen.

Deshalb gilt: Auch wenn im Report des Plugins in InDesign oder den Prüfungstools keine Fehler oder Warnungen angezeigt werden, bedeutet dies nicht, dass ein exportiertes PDF oder ePub alle Anforderungen für Barrierefreiheit erfüllt. (Stichworte: praktische Barrierefreiheit, WCAG-Compliance) 

## Bekannte Fehler

- InDesign 2024: Eingabe in Textfelder aktualisieren die Werte der Dokument- oder Objekteigenschaften nicht. (z.B. Metadaten des Dokuments) 
- Links in den Anmerkungen des Assistenten (Tab `Fragen`) öffnen nicht in einem externen Browser.[^2]
- Alternativtexte für Hyperlinks werden nicht im Report angezeigt.[^3]

[^2]: [Open external url](https://forums.creativeclouddeveloper.com/t/shell-openexternal-url-with-error-messages/9185/4)
[^3]: [Add alternate text for hyperlinks ](https://indesign.uservoice.com/forums/601021-adobe-indesign-feature-requests/suggestions/44895820-add-alternate-text-for-hyperlinks)


https://forums.creativeclouddeveloper.com/t/with-indesign-sp-textfield-does-not-trigger-change-event/6769