---
description: Code sample of Mail XSL style sheet.
seo-description: Code sample of Mail XSL style sheet.
seo-title: Sample Mail XSL Style Sheet
solution: Analytics
title: Sample Mail XSL Style Sheet
topic: Data workbench
uuid: 32773443-f033-43b4-8945-a15ccd11af71
index: y
internal: n
snippet: y
---

# Sample Mail XSL Style Sheet{#sample-mail-xsl-style-sheet}

Code sample of Mail XSL style sheet.

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
<xsl:template match="/">
<html>
<body>
<h2>Reports</h2>
<xsl:for-each select="REPORTS/REPORT[@format!='xls']">
<img><xsl:attribute name="src">cid:<xsl:value-of select="PATH"/></xsl:attribute></img><p/>
</xsl:for-each>
</body>
</html>
</xsl:template>
</xsl:stylesheet>

```

