# ALT-Text-4-InDesign – Dokumentation

Das Plug-in *ALT-Text-4-InDesign* soll dir dabei helfen, alternative Texte für Bilder und Grafiken in *Adobe InDesign* zu erstellen.

## Alternativer Text

Alternativer Text, auch ALT-Text genannt, ist ein wesentlicher Bestandteil von barrierefreien Dokumenten. Er dient dazu, nicht-textuelle Inhalte wie Bilder oder Grafiken zu beschreiben und kann von assistiven Technologien, wie Screenreadern, ausgelesen und wiedergegeben werden.

Wird ein Bild im geöffneten InDesign-Dokument ausgewählt, liest das Plugin den alternativen Text aus den Objektexportoptionen aus. (Objekt → Objektexportoptionen ...  → Alternativer Text) Ist ein Text hinterlegt, wird dieser im Tab `Bilder` des Plugin-Panels im obersten Eingabefeld angezeigt. Du kannst den Alternativtext zudem direkt über das Eingabefeld für das ausgewählte Objekt geändert.

Ist kein alternativer Text hinterlegt, kann ein solcher über das Eingabefeld im Panel eingefügt werden. Dazu die Checkbox `Benutzerdefinierter ALT-Text` anhaken und im Feld den gewünschten Text eingeben. Dieser wird dann als alternativer Text für das ausgewählte Objekt übernommen.

[Vorschau der Erstellung von alternativem Text on vimeo](https://vimeo.com/1026952093)

Über den Button `Erstellen` kann ein Vorschlag für einen alternativen Text erstellt werden. Die Erstellung basiert dabei auf einem Large Language Model (LLM) von OpenAI. Bitte beachte, dass Sprachmodelle Fehler machen können. Überprüfe deshalb die vorgeschlagenen Texte und gib keine sensiblen Daten in das Prompt-Eingabefeld ein, beispielsweise keine personenbezogenen oder vertraulichen Daten.

Ein vorhandener Text im ALT-Text-Feld (oberstes Eingabefeld im Plugin-Panel) gibt den Kontext für die Erstellung des (neuen) ALT-Textes vor. Das ist beispielsweise dann hilfreich, wenn eine bestimmte Region für eine Landschaftsaufnahme oder der Namen einer bekannten Person auf einer Aufnahme für die Beschreibung des Inhaltes miteinbezogen werden soll.

### Prompt

Für die automatisierte Erstellung des alternativen Textes ist eine Anweisung (Prompt) für das LLM vorgeben. Diesen Prompt-Vorschlag kannst du anpassen oder ganz neu eingeben. Aktiviere dazu die Checkbox `Anweisung für ALT-Text` im Fußbereich des Panels. Damit wird ein zusätzliches Eingabefeld eingeblendet.

**Hinweis:** Die Eingabe wirkt sich auch auf die automatisierte Erstellung der alternativen Texte aus für alle verlinkten Bilder.

### Sprache

Es kann vorkommen, dass die Sprache deiner InDesign-Benutzeroberfläche, nicht mit der Dokument-Sprache übereinstimmt, also der Sprache, in der die Alternativtexte erstellt werden sollen. In diesem Fall kannst du eine bestimmte Sprache vorgeben. Wähle dazu mittels Dropdown-Menü rechts über dem Prompt-Eingabefeld die gewünschte Zielsprache aus. Zur Verfügung stehen: Afrikaans, Katalanisch, Dänisch, Deutsch, Englisch, Spanisch, Französisch, Hindi, Italienisch, Koreanisch und Schwedisch.

Ist das Prompt-Eingabefeld mit dem Dropdown für die Sprachauswahl nicht sichtbar, aktiviere die Checkbox `Anweisung für ALT-Text` im Fußbereich des Panels. 

**Hinweis:** Die Einstellung wirkt sich auch auf die automatisierte Erstellung der alternativen Texte aus.

### Quelle für alternativen Text

Über dem Eingabefeld für den alternativen Text kann die Quelle für diesen angegeben werden, beispielsweise wenn der alternative Text aus den Metadaten (XMP) des Objektes eingefügt werden soll. Verwende dazu das Dropdown-Menü `Quelle` rechts über dem Eingabefeld.

## PDF mit Tags

Über das Panel kannst du auch die Optionen für den Export von PDFs mit Tagstruktur ändern, darunter etwa eine Eingabemöglichkeit für tatsächlichen Text oder die Auszeichnung eines Objekts als Schmuckelement.

### Tatsächlicher Text

Tatsächlicher Text wird verwendet, um Text zu beschreiben, der visuell als Text wahrgenommen wird, aber nicht als solcher kodiert ist. Ein typisches Beispiel ist ein Bild, das ein einzelnes Wort darstellt, oder ein Vektorobjekt, das ein einzelnes Zeichen repräsentiert. 

Der tatsächliche Text ermöglicht es, den Text, der von sehenden Benutzerinnen und Benutzer wahrgenommen wird, mit den entsprechenden Objekten zu verknüpfen. Diese zusätzliche textbasierte Darstellung des Inhalts, kann von Screenreadern oder anderen assistiven Technologien genutzt werden. In der Anwendung *Adobe Acrobat* entspricht dieser dem sogenannten »Originaltext« oder »Actual Text«. 

Ist das Eingabefeld für den tatsächlichen Text nicht sichtbar, aktivieren die Checkbox `PDF mit Tags` im Fußbereich des Panels.

### Quelle für tatsächlicher Text

Über dem Eingabefeld für den tatsächlichen Text kann die Quelle für diesen angegeben werden. Verwende dazu das Dropdown-Menü `Quelle` rechts über dem Eingabefeld.

### Schmuckelement

Immer sichtbar ist die Option `Schmuckelement (kein PDF-Tag)`. Wird diese Checkbox angehakt, wird das ausgewählte Objekt im InDesign-Dokument als Schmuckelement (nicht-textliches Element) gekennzeichnet. In der exportierten PDF-Datei scheint dieses Objekt somit nicht in der Tag-Struktur auf.

Zudem wird das so markierte Objekt als dekoratives Element gekennzeichnet. Im exportierten ePub- oder HTML-Dokument wird diesem Element ein leeres alt-Attribut zugewiesen (also alt="") und dadurch von assistiven Technologien (z.B. Screenreadern) ignoriert.   

## Automatisierte Aktionen
### Alle verknüpften Bilder

Über die Aktion `Alle verknüpften Bilder` wird allen Verknüpfungen im InDesign-Dokument automatisiert ein alternativer Text zugewiesen. Für die Erstellung der alternativen Texte wird ein Large Language Model (LLM) von OpenAI verwendet. Die Bilder werden dazu über die API-Schnittstelle von OpenAI verarbeitet.

Die Vorgaben für die Erstellungsanweisung (Prompt) und die Zielsprache werden aus den Eingaben im Panel übernommen. Ist das Prompt-Eingabefeld und das Dropdown-Menü für die Sprachauswahl nicht sichtbar, aktiviere die Checkbox `Anweisung für ALT-Text` im Fußbereich des Panels.

Im Reiter `Settings` können im Abschnitt `Automatisierte Aktionen` **zusätzliche Einstellungen für die automatisierte ALT-Text-Erstellung** getroffen werden. Hier kannst du etwa festlegen, ob vorhandener alternativer Text überschrieben werden oder vorhandener Text bei der Erstellung als Kontext dienen soll. 