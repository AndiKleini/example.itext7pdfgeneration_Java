# example.itext7pdfgeneration

The example creates a pdf file under usage of iText7 library.

Created artifacts are:

  1. Paragraph
  2. List
  3. Table
  2. Image
 
 ## Paragraph
Add a paragraph with proper header and text (font size: 14, font HELVETICA).

``` Java
Paragraph loremIpsumHeader = new Paragraph("Lorem Ipsum header...")
          .setFont(PdfFontFactory.createFont(StandardFonts.HELVETICA))
          .setFontSize(14)
          .setBold()
          .setFontColor(ColorConstants.RED);
document.add(loremIpsumHeader);
document.add(new Paragraph(LOREM_IPSUM_TEXT));
```
## List
Create a list of items with a blue header (font site: 14, font: TIMES_BOLD).

``` Java
Paragraph listHeader = new Paragraph("Lorem Ipsum ...")
                .setFont(PdfFontFactory.createFont(StandardFonts.TIMES_BOLD))
                .setFontSize(14)
                .setBold()
                .setFontColor(ColorConstants.BLUE);
List list = new List()
       .setSymbolIndent(12)
       .setListSymbol("\u2022")
       .setFont(PdfFontFactory.createFont(StandardFonts.TIMES_BOLD));
list.add(new ListItem("lorem ipsum 1"))
       .add(new ListItem("lorem ipsum 2"))
       .add(new ListItem("lorem ipsum 3"))
       .add(new ListItem("lorem ipsum 4"))
       .add(new ListItem("lorem ipsum 5"))
       .add(new ListItem("lorem ipsum 6"));
document.add(listHeader);
document.add(list);
```

## Table
Draw a table by specifying header and ordinary cells.

``` Java
 Paragraph tableHeader = new Paragraph("Lorem Ipsum Table ...")
                .setFont(PdfFontFactory.createFont(StandardFonts.TIMES_ROMAN))
                .setFontSize(18)
                .setBold()
                .setFontColor(ColorConstants.GREEN);
document.add(tableHeader);
Table table = new Table(UnitValue.createPercentArray(4)).useAllAvailableWidth();
table.addHeaderCell(getHeaderCell("Ipsum 1"));
table.addHeaderCell(getHeaderCell("Ipsum 2"));
table.addHeaderCell(getHeaderCell("Ipsum 3"));
table.addHeaderCell(getHeaderCell("Ipsum 4"));
table.setFontSize(14).setBackgroundColor(ColorConstants.WHITE);
table.addCell("lorem 1");
table.addCell("lorem 2");
table.addCell("lorem 3");
table.addCell("lorem 4");
document.add(table);
```
## Image
Add an image to the document.

``` Java
Paragraph imageHeader = new Paragraph("Lorem Ipsum Image ...")
         .setFont(PdfFontFactory.createFont(StandardFonts.TIMES_ROMAN))
         .setFontSize(18)
         .setBold()
         .setFontColor(ColorConstants.GREEN);
document.add(imageHeader);
ImageData imageData = ImageDataFactory.create(GOOGLE_MAPS_PNG);
document.add(new Image(imageData));
```

## Common
The generated pdf file (target.pdf) is placed on top level.
All the source code is placed in main class com.pdfexample.App.
