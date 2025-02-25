# Alt-text-4-InDesign – Documentation

The *Alt-text-4-InDesign* plug-in is designed to help you create alternative texts for images and graphics in *Adobe InDesign*.

## Alternate Text

Alternative text, also known as ALT text, is an essential component of accessible documents. It is used to describe non-textual content such as images or graphics and can be read and reproduced by assistive technologies such as screen readers.

If an image is selected in the open InDesign document, the plugin reads the alternate text from the object export options. (Object → Object export options ... → Alternate text) If a text is available, it is displayed in the `Images` tab of the plugin panel in the top input field. You can also change the alternative text directly via the input field for the selected object.

If no alternative text is stored, you can insert one using the input field in the panel. To do so, activate the checkbox `Custom Alt-text` and enter the desired text in the field. This is then applied as the alternative text for the selected object.

[Preview Alt-text generation on vimeo](https://vimeo.com/1026952093)

A suggestion for an alternate text can be created using the `Generate` button. The generation is based on a Large Language Model (LLM) from OpenAI. Please note that language models can make mistakes. Therefore, check the suggested texts and do not enter any sensitive data in the prompt input field, for example no personal or confidential data.

An existing text in the ALT text field (top input field in the plugin panel) provides the context for the generation of the (new) ALT text. This is helpful, for example, if a specific region for a landscape photo or the name of a celebrity in a photo is to be included in the description of the content.

### Prompt

An instruction (prompt) for the LLM is predefined for the automated generation of the alternative text. You can adapt this prompt suggestion or enter it from scratch. To do this, activate the checkbox `Alt-text instructions` in the footer of the panel. This will display an additional input field.

**Note:** The input also affects the automatic generation of alternative texts for all linked images.

### Language

It may happen that the language of your InDesign user interface does not match the document language, i.e. the language in which the alternate texts are to be generated. In this case, you can specify a specific language. To do this, select the desired target language from the drop-down menu on the right above the prompt input field. The following are available: Afrikaans, Catalan, Danish, German, English, Spanish, French, Hindi, Italian, Korean and Swedish.

If the prompt input field with the dropdown for the language selection is not visible, activate the checkbox `Alt-text instructions` in the footer of the panel.

**Note:** The setting also affects the automatic generation of alternate texts for all linked images.

### Source for Alternate Text

The source for the alternate text can be specified above the input field for the alternate text, for example if the alternative text is to be inserted from the object's metadata (XMP). To do this, use the `Source` drop-down menu on the right above the input field.

## PDF with Tags

You can also use the panel to change the options for exporting PDFs with a tag structure, including an input option for actual text or marking an object as an artefact.

### Actual Text

Actual text is used to describe text that is visually perceived as text but is not encoded as such. A typical example is an image that represents a single word or a vector object that represents a single character. 

The actual text makes it possible to link the text perceived by sighted users to the corresponding objects. This additional text-based representation of the content can be used by screen readers or other assistive technologies. 

If the input field for the actual text is not visible, activate the checkbox `PDF with tags` in the footer area of the panel.

### Source for Actual Text

The source for the actual text can be specified above the input field. To do this, use the drop-down menu `Source` on the right above the input field.

### Artefacts

The option `Decorative element (no PDF tag)` is always visible. If this checkbox is activated, the selected object is marked as a decorative element (non-text element) in the InDesign document. This object therefore does not appear in the tag structure in the exported PDF file.

The object marked in this way is also marked as a decorative element for ePub or HTML. In the exported ePub or HTML document, this element is assigned an empty alt attribute (i.e. alt=“”) and is therefore ignored by assistive technologies (e.g. screen readers).

## Automated Actions
### All linked Images

The `All linked images` action automatically assigns an alternative text to all objects with links. The active InDesign document is processed. Links whose InDesign object is marked as a decorative image or non-text element are skipped. 

A Large Language Model (LLM) from OpenAI is used to create the alternative texts. The images are processed via the OpenAI API interface. The specifications for the generation instruction (prompt) and the target language are taken from the settings in the panel. If the prompt input field and the drop-down menu for the language selection are not visible, activate the checkbox `Instruction for ALT text` in the footer of the panel.

In the `Settings` tab, you can make **additional settings for automated Alt-text generation** in the `Automated actions` section. Here you can specify, for example, whether existing alternative text should be overwritten or whether existing text should be used as a context during generation. 