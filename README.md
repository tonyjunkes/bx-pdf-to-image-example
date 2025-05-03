# BoxLang PDF to Image Example


Example using [PDFBox 3.x](https://pdfbox.apache.org/) to convert PDF pages to images in BoxLang (concurrently). This project has also implemented a function for taking those resulting images and writing them back to a PDF.

## Usage

The example code provides a class with a function, `pdfToImage`, that allows for converting `all pages`, `n pages`, and `n pages starting at a specific page`. The code does not currently support reading pages in reverse, but it's something I may add.

### Examples:

#### Loading the class
```js
import bx:classes.PDFService;
PDFService = new PDFService();
pdfFile = fileReadBinary(expandPath("/resources/sample.pdf"));
```

#### All Pages
```js
pages = PDFService::pdfToImage(pdfFile = pdfFile, imageFormat = "jpg");
```

#### First 5 Pages
```js
pages = PDFService.pdfToImage(pdfFile = pdfFile, imageFormat = "jpg", pageLimit = 5);
```
#### Next 3 Pages Starting At Page 5
```js
pages = PDFService::pdfToImage(pdfFile = pdfFile, imageFormat = "jpg", pageStart = 5, pageLimit = 3);
```

#### PDF to Images to PDF (Because Why Not? :D)
```js
pages = PDFService::pdfToImage(pdfFile = pdfFile, imageFormat = "png");
PDFService::imagesToPDF(images = pages, outputFile = "/output/images.pdf");
```

## Installation

### CommandBox

[CommandBox](https://www.ortussolutions.com/products/commandbox) is the recommended way to run this project's examples.

Launch a terminal pointing at the project root and run `box` to get CommandBox going. Then run `install && start` to pull in the Java dependencies and start the server instance.
