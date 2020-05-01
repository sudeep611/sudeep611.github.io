---
layout: post
title:  "Convert the list of images to PDF file and add watermark using python"
categories: Programming
tags: Python
---
<strong>Converting list of images to PDF in Ubuntu</strong><br />
Let's use ImageMagick tool. Normally it is installed in Ubuntu. If you need to install it then run:

```
$ sudo apt-get install imagemagick
```

Then you can convert it by using:
```
$ convert image_1.jpg image_2.jpg output.pdf
```

You can specify any numbers of images but the last argument must be a name of your PDF file along with extension (.pdf).

<strong>Adding the watermark in the PDF file</strong><br/>
We use Python script for adding watermark to each page in the PDF file. We will be using "PyPDF2" python library.

```
$ pip install PyPDF2
```

Make your watermark ready, convert it to PDF file. Make sure that watermark file is of same page size as of your PDF file.

Then run this code by modifying the file names:

```python
import PyPDF2

originalFile = open('inputfile_pdf', 'rb')
pdfReader = PyPDF2.PdfFileReader(originalFile)
pdfWriter = PyPDF2.PdfFileWriter()

for i in range(0, pdfReader.numPages):
    originalfile_page = pdfReader.getPage(i)
    pdfWatermarkReader = PyPDF2.PdfFileReader(open('watermark.pdf', 'rb'))
    originalfile_page.mergePage(pdfWatermarkReader.getPage(0))
    pdfWriter.addPage(originalfile_page)

resultPdfFile = open('watermarked_outputfile.pdf', 'wb')
pdfWriter.write(resultPdfFile)
originalFile.close()
resultPdfFile.close()
```
