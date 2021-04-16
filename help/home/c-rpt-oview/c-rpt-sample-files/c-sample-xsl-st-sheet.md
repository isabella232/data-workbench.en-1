---
description: Code sample of XSL style sheet.
title: Sample XSL Style Sheet
uuid: cac5c5ad-b0ec-45d8-901d-e39ce1f6d61a
exl-id: 688b0ce5-999b-4cfc-9228-146450132aee
---
# Sample XSL Style Sheet{#sample-xsl-style-sheet}

Code sample of XSL style sheet.

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
<xsl:template match="/">
  <html>
  <body>
    <h2>Reports</h2>
    <xsl:for-each select="REPORTS/REPORT">
    <a>
    <xsl:attribute name="href">
    <xsl:value-of select="PATH"/>
    </xsl:attribute>
    <xsl:value-of select="NAME"/>
    </a><p/>
    </xsl:for-each>
  </body>
  </html>
</xsl:template>
</xsl:stylesheet>
```
