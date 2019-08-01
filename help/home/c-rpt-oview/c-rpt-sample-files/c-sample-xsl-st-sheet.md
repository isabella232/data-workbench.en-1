---
description: Code sample of XSL style sheet.
seo-description: Code sample of XSL style sheet.
seo-title: Sample XSL Style Sheet
solution: Analytics
title: Sample XSL Style Sheet
topic: Data workbench
uuid: afe121d7-c253-4038-92c1-c7575c54cf60
index: y
internal: n
snippet: y
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

