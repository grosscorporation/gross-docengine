![DocEngine](https://raw.githubusercontent.com/GoGross/gross-docengine/master/docengine.png)

---
## DocEngine Premium

Serveless, Scalable HTML to PDF API for Developers. Create high quality, customizable PDF documents from data sources & HTML templates.

## :cloud: Installation

```sh
# Using npm
npm install --save gross-docengine

```

## Getting started

[![DocEngine](https://raw.githubusercontent.com/GoGross/fincharts/master/free-key.jpg)](https://cloud.gogross.com)

Signup for a free account at docengine.gogross.com to obtain a free API Key.

Document engine is fully built on HTTPS REST interface and integrates with several programming languages

## API

DocEngine exposes its data via an Application Programming Interface (API), so developers can interact in a programmatic way with the DocEngine Service. This document is the official reference for that functionality.

## Authentication

#### Auth: API Key
All DocEngine API endpoints require an access token generated from your dashboard as an API key.

## Cross-Origin Resource Sharing (CORS) 

DocEngine is CORS enabled and allows Access-Control Headers. This will enable you to use our API via Cross-Origin HTTP Requests in application/json, application/x-www-form-urlencoded, multipart/form-data, text/plain. You don't need to specify any headers to make a CORS request as they are enabled by default.

## :clipboard: Example

### REST

```
curl -X GET \
  -H "Content-Type: application/json" \
  -d '{"HTML":"<div>body</div>","pdfName":"try.pdf"}' \
  https://api.gogross.com/docengine?key=get_free_api_key
```

### NodeJS

```js

const DocEngine     = require ( 'gross-docengine' );
const DOCENGINE_KEY   = process.env.DOCENGINE_KEY;  // API Key

const DOC = {
	HTML: "<div>body</div>",
	pdfName : "try",
	options: {
		headerHTML : "<div>header</div>",
		footerHTML : "<div>footer</div>",
		pageSize : "A4",
		pageOrientation : "portrait",
		marginWidthTop : "10mm",
		marginWidthLeft : "10mm",
		marginWidthRight : "10mm",
		marginWidthBottom : "10mm",
		headerHeight : "10mm",
		footerHeight : "10mm"
	}
};

const docEngine     = new DocEngine ( DOC, DOCENGINE_KEY  );
docEngine.print ( )
	.then ( ( documentUrl ) => {
		
		console.log ( documentUrl );
		
	} )
	.catch ( ( error ) => {
		
		console.trace ( error );
		
	} );




```

Except as otherwise noted, the content of this page is licensed under the Creative Commons Attribution 3.0 License, and code samples are licensed under the Apache 2.0 License. For details, see our Site Policies. Java is a registered trademark of Oracle and/or its affiliates.





