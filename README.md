# OpenPDF is an open source Java library for PDF files #

OpenPDF is a Java library for creating and editing PDF files with a LGPL and MPL open source
license. OpenPDF is the LGPL/MPL open source successor of iText, and is based on some forks of iText
4 svn tag. We welcome contributions from other developers. Please feel free to submit pull-requests
and bugreports to this GitHub repository.

![CI](https://github.com/LibrePDF/OpenPDF/actions/workflows/maven.yml/badge.svg)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.librepdf/openpdf/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.github.librepdf/openpdf)
[![License (LGPL version 3.0)](https://img.shields.io/badge/license-GNU%20LGPL%20version%202.1-blue.svg?style=flat-square)](http://opensource.org/licenses/LGPL-2.1)
[![License (MPL)](https://img.shields.io/badge/license-Mozilla%20Public%20License-yellow.svg?style=flat-square)](http://opensource.org/licenses/MPL-2.0)

[![Join the chat at https://gitter.im/LibrePDF/OpenPDF](https://badges.gitter.im/LibrePDF/OpenPDF.svg)](https://gitter.im/LibrePDF/OpenPDF)

## OpenPDF version 1.3.38 released 2024-01-17 ##

Get version 1.3.38 here - https://github.com/LibrePDF/OpenPDF/releases/tag/1.3.38

- [Previous releases](https://github.com/LibrePDF/OpenPDF/releases)

## Features ##
Some of the features of OpenPDF include:

* Creating PDFs: You can use OpenPDF to create new PDF documents from scratch.

* Manipulating Existing PDFs: OpenPDF allows you to modify existing PDF documents by adding or removing pages, modifying text, and more.

* Text and Font Support: You can add text to PDF documents using various fonts and styles, and extract text from PDF files.

* Graphics and Images: OpenPDF supports the addition of images and graphics to PDF files.

* Table Support: The library facilitates the creation of tables in PDF documents.

* Encryption: You can encrypt PDF documents for security purposes.

* Page Layout: OpenPDF allows you to set the page size, orientation, and other layout properties.
    

## Use OpenPDF as Maven dependency

Add this to your pom.xml file to use the latest version of OpenPDF:

```xml

<dependency>
  <groupId>com.github.librepdf</groupId>
  <artifactId>openpdf</artifactId>
  <version>1.3.38</version>
</dependency>
```

## License ##

[GNU Lesser General Public License (LGPL), Version 2.1](https://www.gnu.org/licenses/old-licenses/lgpl-2.1)

For a short explanation see https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License

[Mozilla Public License Version 2.0](http://www.mozilla.org/MPL/2.0/)

For a short explanation see https://en.wikipedia.org/wiki/Mozilla_Public_License

You can find also a nice explanation of these licenses under https://itsfoss.com/open-source-licenses-explained/

We want OpenPDF to consist of source code which is consistently licensed with the LGPL and MPL
licences only. This also means that any new contributions to the project must have a dual LGPL and
MPL license only.

## Documentation ##

- [Examples](pdf-toolbox/src/test/java/com/lowagie/examples)
- [JavaDoc](https://librepdf.github.io/OpenPDF/docs-1-3-17/)
- [Tutorial](https://github.com/LibrePDF/OpenPDF/wiki/Tutorial) (wiki, work in progress)
- [Migration from iText, TIFF support](https://github.com/LibrePDF/OpenPDF/wiki/Migrating-from-iText-2-and-4)

## Hello world example ##

```java
public class HelloWorld {
    /**
     * Generates a PDF file with the text 'Hello World'
     */
    public static void main(String[] args) {

        // step 1: creation of a document-object
        Document document = new Document();
        try {
            // step 2:
            // we create a writer that listens to the document
            // and directs a PDF-stream to a file
            PdfWriter.getInstance(document, new FileOutputStream("HelloWorld.pdf"));

            // step 3: we open the document
            document.open();
            // step 4: we add a paragraph to the document
            document.add(new Paragraph("Hello World"));
        } catch (DocumentException de) {
            System.err.println(de.getMessage());
        } catch (IOException ioe) {
            System.err.println(ioe.getMessage());
        }

        // step 5: we close the document
        document.close();
    }
}
```

## Background ##

OpenPDF is open source software with a LGPL and MPL license. It is a fork of iText version 4, more
specifically iText svn tag 4.2.0, which was hosted publicly on sourceforge with LGPL and MPL license
headers in the source code, and LGPL and MPL license documents in the svn repository. Beginning with
version 5.0 of iText, the developers have moved to the AGPL to improve their ability to sell
commercial licenses.

OpenPDF ancestors in GitHub (in fork order):

1. [@rtfarte](https://github.com/rtfarte) / [OpenPDF](https://github.com/rtfarte/OpenPDF) - parent
   of LibrePDF/OpenPDF
2. [@kulatamicuda](https://github.com/kulatamicuda)
   / [iText-4.2.0](https://github.com/kulatamicuda/iText-4.2.0)
3. [@daviddurand](https://github.com/daviddurand)
   / [iText-4.2.0](https://github.com/daviddurand/iText-4.2.0)
4. [@ymasory](https://github.com/ymasory) / [iText-4.2.0](https://github.com/ymasory/iText-4.2.0) -
   original parent on GitHub

## Projects using OpenPDF ##

- Spring Framework https://github.com/spring-projects/spring-framework
- flyingsaucer https://github.com/flyingsaucerproject/flyingsaucer
- Confluence PDF Export
- Digital Signature Service - https://github.com/esig/dss
- OpenCMS, Nuxeo Web Framework, QR Invoice Library and many closed source commercial applications as
  well.
- Full list here: https://mvnrepository.com/artifact/com.github.librepdf/openpdf/usages

## Android ##

OpenPDF can be used with Android, more info
here: [Android-support](https://github.com/LibrePDF/OpenPDF/wiki/Android-support)

## Contributing ##

Release the hounds!  Please send all pull requests. Make sure that your contributions can be
released with a dual LGPL and MPL license. In particular, pull requests to the OpenPDF project must
only contain code that you have written yourself. GPL or AGPL licensed code will not be acceptable.

### Coding Style ###

- Code indentation style is 4 spaces.
- Generally try to preserve the coding style in the file you are modifying.

## Dependencies ##

### Required Dependencies: ###

- Java 11 or later is required to use OpenPDF versions 1.3.37 and later. All versions Java 11 to Java OpenJDK 21 have been tested to work. We are working on modernizing the OpenPDF library for Java 11+.  
  

### UTF-8 Fonts: ###

As of 1.3.21 the UTF-8 Liberation fonts moved to its own module, to reduce the size of the OpenPDF
jar. If you want to use the bundled UTF-8 fonts, please add the following dependency to your project
and use the class `org.librepdf.openpdf.fonts.Liberation`.

```xml
<dependency>
  <groupId>com.github.librepdf</groupId>
  <artifactId>openpdf-fonts-extra</artifactId>
  <version>${openpdf.version}</version>
</dependency>
```

### Supporting complex glyph substitution/ Ligature substitution: ###

OpenPDF supports glyph substitution which is required for correct rendering of fonts ligature substitution requirements.
FOP dependency is required to enable this feature. Refer following wiki for
details: [wiki](https://github.com/LibrePDF/OpenPDF/wiki/Multi-byte-character-language-support-with-TTF-fonts)

### Supporting OpenType layout, glyph positioning, reordering and substitution: ###

OpenPDF supports OpenType layout, glyph positioning, reordering and substitution which is e.g. required for correct
positioning of accents, the rendering of non-Latin and right-to-left scripts. OpenPDF supports DIN 91379.
See: [wiki](https://github.com/LibrePDF/OpenPDF/wiki/Accents,-DIN-91379,-non-Latin-scripts)

### Optional: ###

- [BouncyCastle](https://www.bouncycastle.org/) (BouncyCastle is used to sign PDF files, so it's a recommended
  dependency)
    - Provider (`org.bouncycastle:bcprov-jdk18on` or `org.bouncycastle:bcprov-ext-jdk18on` depending
      on which algorithm you are using)
    - PKIX/CMS (`org.bouncycastle:bcpkix-jdk18on`)
- Apache FOP (`org.apache.xmlgraphics:fop`)
- Please refer to our [pom.xml](pom.xml) to see what version is needed.

## Credits ##
Please see [Contributors.md](Contributors.md).
