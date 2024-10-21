Changes in PDFio
================


v1.3.2 - 2024-08-15
-------------------

- Added some more sanity checks to the TrueType font reader.
- Updated documentation (Issue #77)
- Fixed an issue when opening certain encrypted PDF files (Issue #62)


v1.3.1 - 2024-08-05
-------------------

- CVE 2024-42358: Updated TrueType font reader to avoid large memory
  allocations.
- Fixed some documentation errors and added examples (Issue #68, Issue #69)


v1.3.0 - 2024-06-28
-------------------

- Added `pdfioFileGetCatalog` API for accessing the root/catalog object of a
  PDF file (Issue #67)
- Updated number support to avoid locale issues (Issue #61)
- Updated the PDFio private header to allow compilation with MingW; note that
  MingW is NOT a supported toolchain for PDFio (Issue #66)
- Optimized string pool code.


v1.2.0 - 2024-01-24
-------------------

- Now use autoconf to configure the PDFio sources (Issue #54)
- Added `pdfioFileCreateNumberObj` and `pdfioFileCreateStringObj` functions
  (Issue #14)
- Added `pdfioContentTextMeasure` function (Issue #17)
- Added `pdfioContentTextNewLineShow` and `pdfioContentTextNewLineShowf`
  functions (Issue #24)
- Renamed `pdfioContentTextNextLine` to `pdfioContentTextNewLine`.
- Updated the maximum number of object streams in a single file from 4096 to
  8192 (Issue #58)
- Updated the token reading code to protect against some obvious abuses of the
  PDF format.
- Updated the xref reading code to protect against loops.
- Updated the object handling code to use a binary insertion algorithm -
  provides a significant (~800x) improvement in open times.
- Fixed handling of encrypted PDFs with per-object file IDs (Issue #42)
- Fixed handling of of trailer dictionaries that started immediately after the
  "trailer" keyword (Issue #58)
- Fixed handling of invalid, but common, PDF files with a generation number of
  65536 in the xref table (Issue #59)


v1.1.4 - 2023-12-03
-------------------

- Fixed detection of encrypted strings that are too short (Issue #52)
- Fixed a TrueType CMAP decoding bug.
- Fixed a text rendering issue for Asian text.
- Added a ToUnicode map for Unicode text to support text copying.


v1.1.3 - 2023-11-15
-------------------

- Fixed Unicode font support (Issue #16)
- Fixed missing initializer for 40-bit RC4 encryption (Issue #51)


v1.1.2 - 2023-10-10
-------------------

- Updated `pdfioContentSetDashPattern` to support setting a solid (0 length)
  dash pattern (Issue #41)
- Fixed an issue with broken PDF files containing extra CR and/or LF separators
  after the object stream token (Issue #40)
- Fixed an issue with PDF files produced by Crystal Reports (Issue #45)
- Fixed an issue with PDF files produced by Microsoft Reporting Services
  (Issue #46)
- Fixed support for compound filters where the filter array consists of a
  single named filter (Issue #47)
- Fixed builds on Windows - needed windows.h header for temporary files
  (Issue #48)


v1.1.1 - 2023-03-20
-------------------

- CVE-2023-28428: Fixed a potential denial-of-service with corrupt PDF files.
- Fixed a few build issues.


v1.1.0 - 2023-02-06
-------------------

- CVE-2023-24808: Fixed a potential denial-of-service with corrupt PDF files.
- Added `pdfioFileCreateTemporary` function (Issue #29)
- Added `pdfioDictIterateKeys` function (Issue #31)
- Added `pdfioContentPathEnd` function.
- Added protection against opening multiple streams in the same file at the
  same time.
- Documentation updates (Issue #37)
- Fixed "install-shared" target (Issue #32)
- Fixed `pdfioFileGet...` metadata APIs (Issue #33)
- Fixed `pdfioContentMatrixRotate` function.


v1.0.1 - 2022-03-02
-------------------

- Added missing `pdfioPageGetNumStreams` and `pdfioPageOpenStream` functions.
- Added demo pdfiototext utility.
- Fixed bug in `pdfioStreamGetToken`.


v1.0.0 - 2021-12-14
-------------------

- First stable release.


v1.0rc1 - 2021-11-30
--------------------

- Fixed a few stack/buffer overflow bugs discovered via fuzzing.


v1.0b2 - 2021-11-07
-------------------

- Added `pdfioFileCreateOutput` API to support streaming output of PDF
  (Issue #21)
- Fixed `all-shared` target (Issue #22)
- Fixed memory leaks (Issue #23)
- Updated `pdfioContentSetDashPattern` to accept `double` values (Issue #25)
- Added support for reading and writing encrypted PDFs (Issue #26)
- Fixed some issues identified by a Coverity scan.


v1.0b1 - 2021-08-30
-------------------

- Initial release
