### MASTER TEMPLATE

1. The entire email content must be placed inside the main `<table>` within the `<body>`. The insertion point is marked by `{# Insert html blocks HERE #}`.

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xmlns:v="urn:schemas-microsoft-com:vml" xmlns:o="urn:schemas-microsoft-com:office:office"><head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<meta name="x-apple-disable-message-reformatting">
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title> MandM</title>
{# MASTER HEAD HTML with styles #}{{ block("62ebb86504d58573e18baaad") }}
</head>

<body style="background: #ffffff;">
	<table cellpadding="0" cellspacing="0" style="margin:0 auto;background:#fff;max-width:610px;width:100%;" width="100%" align="center" border="0" background="#fff"><tr align="center"><td style="font-size:0px;padding:0px;" align="center">  

		{# HEADER - web version #}{{ block('632887a1bfd26a5ccea3f7c3', {}) }}
		
		{# NAV BAR - All-in-one #}{{ block('645b7f44d604ca21b2e24335', {"CATALOG":"uk_nav_bar"}) }}
		
		{# SPACER #}{{ block("632867c50ffb643df2e9daa9", {"BACKGROUND":"#ffffff","HEIGHT":"5"}) }}
		
		{# GBP - Unlimited banner #}{{ block('65fa9c606b14c38526cc9d74', {'SPACE_AFTER': 0}) }}
		
		{# SPACER #}{{ block("632867c50ffb643df2e9daa9", {"BACKGROUND":"#ffffff","HEIGHT":"5"}) }}
		
		<!--  ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ -->
		<!-- XXX STATIC HEADER - DO NOT CHANGE XXXXXXXXXXXXXXX -->
		
		<!-- XXX INSERT HTML BLOCKS BELOW XXXXXXXXXXXXXXX -->
		<!--  ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ -->

            {# Insert html blocks HERE #}

		<!--  ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ ⬆ -->
		<!-- XXX INSERT HTML BLOCKS ABOVE XXXXXXXXXXXXXXX -->
		
		
		<!-- XXX STATIC FOOTER XXXXXXXXXXXXXXX -->
		<!--  ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ ⬇ -->    
		
		{# SOCIALS #}{{ block('632883d486509559d63ee39a', {}) }}
		
		{# TRUSTPILOT #}{{ block('6328852786509559d63ee3a1', {}) }}
		
		{# FOOTER #}{{ block('63288681bfd26a5ccea3f7bc', {}) }}
    
	</td></tr></table>
</body></html>
```
