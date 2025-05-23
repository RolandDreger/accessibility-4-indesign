# Accessibility-4-InDesign

The *Accessibility-4-InDesign* plug-in is designed to help you identify and resolve problems at an early stage when creating accessible documents with *Adobe InDesign*.

## Report

The report lists potential problems during the creation of an InDesign document. As a checklist, it can help to keep an eye on the most important accessibility requirements even before the PDF or ePub export.

The individual sections of the report can be created independently of each other using the corresponding buttons or together using the `All` button. You can use the filters in the report areas to show or hide the entries according to your requirements.

### Metadata

The metadata report provides an overview of the most important metadata for PDF and ePub documents. You can change the entries directly using the input fields and checkboxes.

[Preview of the metadata report on vimeo](https://vimeo.com/1036508410)

### Images

The image report lists all images and graphics with their entries for *alternate and actual text*. Groups are also shown in the list if they have been assigned an alternate text. By clicking on the images in the panel, you can jump directly to the corresponding elements in the InDesign document.

[Preview of the image report on vimeo](https://vimeo.com/1031495125)

The first time the image report is created, the images are cached in the plugin memory. Depending on the number of images available, this takes a little longer than the subsequent runs. The plug-in memory can be cleared using the `Clear` button at the bottom of the panel, for example if you have changed the cropping of an image.

**Tip:** If the ALT text panel is open in addition to the report panel, missing alternate texts can be entered directly via this panel.

**Note**: If you are working with XML, tags may be assigned incorrectly in the exported PDF. Unfortunately, these problems cannot be detected automatically.[^1]

[^1]: Bug report: [Before tag and after untag frame with different behavior](https://indesign.uservoice.com/forums/601180-adobe-indesign-bugs/suggestions/49266116)

#### Which objects are listed in the image report?

The image report lists those objects that result in an entry for alternative or actual text in the exported PDF or ePub. 

PDF 
- Attribute *ALT* in the “Tag” element (Adobe Acrobat: *Alternate text for images*) 
- Attribute *ActualText* in the “Tag” element (Adobe Acrobat: *Actual text*)

ePub
- Attribute *alt* in the “img” element

#### Why is there a filter for PDF and ePub?

Because in some cases the PDF and ePub export behave differently. Example of grouped elements: If you enter an alternate text for a group in the InDesign document, this is added to the “tag” element in the exported PDF. However, the alternate texts of the individual group elements get lost. The opposite is true for ePub exports. Here, the alternate text of the group is ignored and those of the group elements are transferred to the ALT attributes. 

To make it easier to keep an overview, only those objects are listed in the image report that also result in an entry for alternative or actual text. You can additionally use the filter function to select which ones are relevant for you - depending on whether you are exporting a PDF or ePub.

Translated with DeepL.com (free version)

### Export Tags

The tag report lists all *tags* (PDF tag structure, ePub HTML element names) for character, paragraph and object styles contained in the InDesign document. The assigned language is also displayed in the table for the text styles.

[Preview of the export tag report on vimeo](https://vimeo.com/1036510247)

In accessible documents, tags are used to create a logical structure for the content. These tags determine the role of an object, such as a heading, a paragraph or an illustration. This enables screen readers and other assistive technologies to interpret and output the content correctly. The tag structure is an additional layer of the document structure that goes beyond the visual representation. 

In InDesign, you can define the tags for ePub/HTML and PDF in the styles (character styles, paragraph styles, object styles) under `Tag export`. If no selection is made here, the assignment is made automatically. These tag names **automatically assigned by InDesign** are shown in the report **in square brackets.** If more than one tag name is shown in the table here, the assigned tag also depends on the settings made during export.

#### Highlight Styles

The small highlight icon in the last table column can be used to highlight the individual character and paragraph styles in the document, or more precisely: text passages to which this style is applied are “ highlighted” with a color. 

The highlighting is done via conditional text: Window → Font and Tables → Conditional Text. (To make the highlighting with conditional text visible, the plugin switches the display mode of InDesign to 'Normal').

You can remove the highlighting by clicking on the highlight icon in the table row again. If you want to remove **all highlights for a format type**, you can click on the first **highlight icon in the table header**.

**Note:** If you are working with **"Conditional Text ”** in the InDesign document, it is possible that this condition is removed from the highlighted text passages by clicking on the icon. If the use of text conditions is important for your document, please do not use this feature.

### Articles

The article report provides a list of all articles added in the InDesign article panel. In addition, possible related errors are displayed.

[Preview of the article report on vimeo](https://vimeo.com/1044736860)

The article function in InDesign is used to define the order of the tag structure of content in a document. In the InDesign article panel, you can define which content is tagged in the document and in which order. This ensures that the content is read aloud by screen readers in the correct order.

#### Headlines

The heading levels are checked across all articles - in the order in which the articles and their contained objects are added in the article control panel.

##### Errors and warnings for PDFs: 

- No headings available.
- First heading not on the first level.
- Heading level skipped.
- Illogical order of headings.

##### Errors and warnings for ePubs:

- No headings available.
- Illogical order of headings.

#### Show/hide article

You can use the eye icon next to the article name to hide and show all objects of an article. This helps you to check whether all the required objects are assigned to one of the articles.

### Hyperlinks

Listing of the hyperlinks contained in the InDesign document. The first field shows the text of the hyperlink displayed in the document, the second field shows the target (URL, anchor, page, ...). By clicking on the first field, you can jump directly to the text passages with the hyperlink.

**Note:** For technical reasons, the alternate text for hyperlinks cannot be accessed in InDesign at present. (User interface: Edit hyperlink → Accessibility) However, experts advise against using this anyway. If possible, “speaking names” should be used for hyperlinks instead. This benefits all target groups equally. (For print, these can then be converted into URLs using scripts or CSS).

### Text

The text report points out possible problems in relation to text. The following also applies here: It is not always possible to clearly identify all problem areas using an automated search, or issues may be found that are not issues at all. Check the issues individually by using the `Search` button to jump to the relevant text passages in the document.

### Export as PDF

The result of the report can be exported as a PDF file. Only those sections and entries that are visible in the panel are exported. This allows you to control exactly which information is to be included in the exported PDF by showing/hiding the sections and applying filters.

The generated PDF for the report is saved in the plugin's temporary folder by default and then automatically opened in your standard PDF application. Alternatively, you can select the `Open save dialog` option in the plugin settings. This allows you to select an individual storage location for the PDF file.

[Vorschau des PDF-Exports auf vimeo](https://vimeo.com/1053449077)

To create the report PDF, the [Adobe PDF Services API is used](https://developer.adobe.com/document-services/).

#### The PDF is not shown after the export?

The generated PDF for the report is saved in the plugin folder by default and then automatically opened in your standard PDF application. Alternatively, you can select the InDesign document folder as the storage location or the ‘Open save dialog’ option in the plugin settings. This allows you to select an individual storage location for the report.

## Ask

In the `Questions` tab, you will find a assistant that will answer your questions about accessibility. You can also ask about the use of InDesign and Acrobat. The assistant is based on a Large Language Model (LLM) from OpenAI. Language models can make mistakes. Therefore, check important information and do not enter any sensitive data, such as personal data.

The sources that were used as the basis for the answer are listed below each of the assistant's answers. Use the links to find further information on the topic. If no URL is displayed, the information is based on the plugin's own data (or the assistant has messed up).

## Settings
### License Key

In the `Settings` tab, you can enter the license key that you got when you purchased the plug-in.

### Report
#### Export

A document title and the name of the creator can be entered for the exported report.

Option `Open save dialog`: Here you can specify whether a selection dialog for the storage location of the PDF file of the exported report should be displayed. By default, the temporary folder of the plugin is preselected as the storage location.

Option `Show PDF after export`: With this option you determine whether the PDF is opened in your default application after exporting the report. (The default application is the application in which a PDF file is opened by double-clicking in the file browser).


## Limitations of plug-in and InDesignn

Currently, not all requirements for an accessible document can be met with InDesign's on-board tools, such as the implementation of accessible tables in the exported PDF or the setting of the PDF/UA marker. This must either be carried out using specialized extensions - e.g. MadeToTag - or after the export in corresponding applications - e.g. for PDFs in Adobe Acrobat or in the case of an ePub in an ePub editor.

The exported PDF and ePub documents can be tested after export with specialized applications:

- [PAC](https://pac.pdf-accessibility.org/de)
- [veraPDF](https://verapdf.org/)

- [EPUP-Checker (Pagina)](https://pagina.gmbh/startseite/leistungen/publishing-softwareloesungen/epub-checker/)
- [EPUBCheck (W3C)](https://www.w3.org/publishing/epubcheck/)

## Limitations of automated checks

Automated checks can only cover some of the accessibility of digital content. For example, it is not possible to identify so-called “layout tables”, i.e. tables that are used solely for the purpose of layout - without any meaning in terms of content. Or when information is communicated only by color. To name just a few examples.

Therefore, even if no errors or warnings are displayed in the plugin report in InDesign or the checking tools, this does not mean that an exported PDF or ePub meets all accessibility requirements. (Keywords: practical accessibility, WCAG compliance)

A manual check tailored to the target group is recommended in any case.

## Known issues

- Links in the notes of the assistant (`Ask` tab) do not open in an external browser[^2].

[^2]: [Open external url](https://forums.creativeclouddeveloper.com/t/shell-openexternal-url-with-error-messages/9185/4)