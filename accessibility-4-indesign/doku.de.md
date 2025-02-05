
# Accessibility-4-InDesign

Das Plug-in *Accessibility-4-InDesign* soll eine einfache Hilfestellung bieten, um Probleme zu ermitteln, die bei der Erstellung von barrierefreien Dokumenten *Adobe InDesign* auftreten können.

## Grenzen von Plug-in und von InDesign

Derzeit können nicht immer alle Anforderungen an ein barrierefreies Dokument mit Bordmitteln von InDesign erfüllt werden – wie etwa das Taggen von komplexen Tabellen. Dies muss entweder mittels dafür spezialisierter Erweiterungen oder nach dem Export (in Adobe Acrobat oder einem ePub-Editor) durchgeführt werden.

## Grenzen automatisierter Prüfungen

Automatisierte Prüfungen können nur einen kleinen Teil der Barrierefreiheit digitaler Inhalte abdecken. Auch wenn im Report des Plugins in InDesign keine Fehler oder Warnungen angezeigt werden, bedeutet dies nicht, dass ein exportiertes PDF oder ePub alle Anforderungen für Barrierefreiheit erfüllt. (Stichwort: praktische Barrierefreiheit, WCAG-Compliance) Die exportierten PDF- und ePub-Dokumente können nach dem Export mit darauf spezialisierten Anwendungen getestet werden. ([PAC](https://pac.pdf-accessibility.org/de), [veraPDF](https://verapdf.org/) [EPUP-Checker (Pagina)](https://pagina.gmbh/startseite/leistungen/publishing-softwareloesungen/epub-checker/), [EPUBCheck (W3C)](https://www.w3.org/publishing/epubcheck/)) Darüber hinaus ist eine manuelle, auf die Zielpersonen abgestimmte Prüfung jedenfalls angeraten.

# Dokumentation

## Report

Der Report listet mögliche Probleme oder fehlende Einträge während der Erstellung eines InDesign-Dokumentes auf. Als eine Art Checkliste kann der Report helfen, die wichtigsten Anforderungen an die Barrierefreiheit noch vor dem PDF- oder ePub-Export im Blick zu behalten.

Die einzelnen Abschnitte des Reports können über die zugehörigen Buttons unabhängig voneinander oder über den Button `Alle` gemeinsam erstellt werden. Mit Filtern in den Report-Bereichen kannst du die angezeigten Einträge nach deinen Wünschen eingeschränkt.

### Metadaten
Der Metadaten-Report bietet eine Übersicht über die wichtigsten Metadaten für PDF und ePub. Über die Eingabefelder können die Einträge geändert werden.

[Vorschau des Metadaten-Reports auf vimeo](https://vimeo.com/1036508410)

### Bilder
Der Bild-Report listet alle Bilder und Grafiken mit den Einträgen für *alternativen- und tatsächlichen Text* auf. Auch Gruppen werden in der Liste angeführt, sofern diesen ein alternativer Text zugewiesen ist. Durch Klick auf die Bilder im Panel kann direkt zu den zugehörigen Elementen im InDesign-Dokument gesprungen werden.

[Vorschau des Bild-Reports auf vimeo](https://vimeo.com/1031495125)

Beim ersten Erstellen des Bild-Reports werden die Bilder in den Plugin-Speicher geladen und nimmt damit etwas mehr Zeit in Anspruch. Der Speicher kann über den Button `Leeren` im Fuß des Panels geleert werden, etwa wenn sich der Ausschnitt eines Bildes geändert hat.

**Tipp:** Ist neben dem Report-Panel auch das ALT-Text-Panel geöffnet, können fehlende Alternativtexte gleich über dieses eingegeben werden.

**Hinweis**: Wenn du mit XML arbeitest, kann es zu einer fehlerhaften Zuordnung von Tags im exportieren PDF kommen. Diese Problemstellen sind automatisiert leider nicht zu ermitteln.[1]

[1] Bug report: [Before tag and after untag frame with different behavior](https://indesign.uservoice.com/forums/601180-adobe-indesign-bugs/suggestions/49266116)

### Export-Tags
Der Tag-Report listet alle *Tags* (PDF-Tagstruktur, ePub-HTML-Elementnamen) für im InDesign-Dokument vorhandenen Zeichen-, Absatz- und Objektformate auf. Zudem wird in der Tabelle die zugewiesene Sprache angezeigt.

In barrierefreien Dokumenten werden Tags verwendet, um eine logische Struktur der Inhalte zu schaffen. Diese Tags bestimmen die Rolle eines Objekts, wie z.B. eine Überschrift, einen Absatz oder eine Abbildung. Es ermöglicht Screenreader und anderen assistiven Technologien, die Inhalte korrekt zu interpretieren und wiederzugeben. Die Tag-Struktur ist eine zusätzliche Ebene der Dokumentenstruktur, die über die visuelle Darstellung hinausgeht. 

In InDesign kannst du die Tags für ePub/HTML und PDF in den Formatvorlagen (Zeichenformate, Absatzformate, Objektformate) unter dem Punkt `Tagexport` festlegen. Wird hier keine Auswahl getroffen, erfolgt die Zuordnung automatisch. Diese von InDesign **automatisch vergebenen Tag-Namen** stehen im Report **in eckigen Klammern.** Wenn in der Tabelle hier mehr als ein Tag-Name angezeigt wird, hängt der zugewiesen Tag von den getroffenen Einstellungen beim Export ab.

[Vorschau des Export-Tag-Report auf vimeo](https://vimeo.com/1036510247)

### Artikel
Der Artikel-Report bietet eine Auflistung aller im InDesign-eigenen Artikelbedienfeld angelegten Artikel. Zudem werden mögliche, damit im Zusammenhang stehende Fehler angezeigt.

[Vorschau des Artikel-Reports auf vimeo](https://vimeo.com/1044736860)

Die Artikelfunktion in InDesign dient dazu, die Reihenfolge der Tag-Struktur von Inhalten in einem Dokument festzulegen. Im Artikelbedienfeld von InDesign kannst du definieren, welche Inhalte im Dokument getaggt werden und in welcher Reihenfolge. Damit stellst du sicher, dass die Inhalte in der richtigen Reihenfolge von Screenreader vorgelesen werden.

Mit dem kleine Lampen-Icon in der letzten Tabellenspalte können die einzelnen Zeichen- und Absatzformate im Dokument hervorgehoben werden, genauer: die Textstellen mit diesen Formaten werden mit einer Farbfläche hinterlegt. Die Hervorhebung erfolgt dabei über bedingten Text: Fenster → Schrift und Tabellen → Bedingter Text. Durch erneutes Klicken auf das Lampen-Icon in der Tabellen-Zeile kannst du die Hervorhebung wieder entfernen. Willst du **alle Hinterlegungen für einen Formattype entfernen,** kannst du das erste **Lampen-Icon im Tabellenkopf** anklicken.

### Hyperlinks

Auflistung der im InDesign enthaltenen Hyperlinks. Im ersten Feld wird der im Dokument angezeigte Text des Hyperlinks angezeigt, im zweiten Feld die hinterleget URL. Über einen Klick kannst du der Hyperlink direkt im Text anspringen.

### Text

Im Text-Report wird auf mögliche Probleme im Zusammenhang mit Text hingewiesen. Auch hier gilt: Durch eine automatisierte Suche ist es nicht immer möglich, alle Problemstellen eindeutig zu ermitteln, bzw. werden auch Probleme gefunden, die möglicherweise gar keine sind. Überprüfe die Probleme einzeln, indem du über den Button `Suchen` an die betroffenen Textstellen im Dokument springst.

### Export als PDF

Das Ergebnis des Reports kann als PDF-Datei exportiert werden. Dabei werden nur jene Abschnitte und Einträge exportiert, die im Panel sichtbar sind. Werden Einträge etwa durch Filter ausgeblendet, werden diese nicht mit ins exportierte PDF übernommen.

[Vorschau des PDF-Exports auf vimeo](https://vimeo.com/1053449077)

## Fragen

Im Reiter `Fragen` findest du einen Assistenten, der Fragen zu Barrierefreiheit beantwortet. Du kannst aber auch Fragen zur Bedienung von InDesign und Acrobat stellen. Dieser Assistent basiert auf einem Large Language Model (LLM) von OpenAI. Sprachmodelle können Fehler machen. Überprüfe deshalb wichtige Informationen und gib keine sensiblen Daten ein, etwas personenbezogene Daten.

Unter den Antworten wird die Quelle genannt, mit deren Hilfe deine Frage beantwortet wurde. Unter den Links finden sich weiter Informationen zum entsprechenden Thema. Ist keine URL angegeben, beruht die Information auf den eigenen Daten des Plugins.

## Einstellungen

Im Reiter `Einstellungen` kann der Lizenzschlüssel eingegeben werden, den du beim Kauf des Plug-ins erhalten hast.

# Bekannte Fehler

- Links in den Anmerkungen des Assistenten (Tab  `Fragen`) öffnen nicht in einem externen Browser.
- Alternativtexte für Hyperlinks werden nicht im Report angezeigt.