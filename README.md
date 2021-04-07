Using Custom Web Fonts
The custom web fonts you add to your tenant can be used in story pages and the Digital Boardroom.

Administrators can add custom web fonts by going to the following location: Start of the navigation pathSystem Next navigation step Administration Next navigation step Default Appearance Next navigation step Story FontsEnd of the navigation path

Note
Custom fonts are not yet supported on mobile or as text for PDF export.

You can use Google or Adobe fonts, or custom web fonts that have been set up according to the guidelines in the section Setting Up Custom Web Fonts.

Tip
When selecting a Google, Adobe, or other web font, you need to select all the styles that you want to use, including Bold and Italic (making it a font family). If you don't include specific styles, the default styles will be used instead.

Remember
You can include multiple styles for the font, but you must have only one font (or font family) listed for a specific URL.

After you get the URL for the desired font or font family, add it to the web page:
In the Story Fonts section, select (add a web font).
Type the URL in the dialog box, and then click OK.
Example
You want to add the Google font named Crimson Text. After customizing the text (in this case selecting Regular, Bold, Italic, and Bold-Italic fonts), you would see the following link on the embed tab:

<link href="https://fonts.googleapis.com/css?family=Crimson+Text:400,400i,700,700i&display=swap" rel="stylesheet">
Select the URL from the link ( https://fonts.googleapis.com/css?family=Crimson+Text:400,400i,700,700i&display=swap ) and paste that into the field on the web font dialog.

Setting Up Custom Web Fonts
To use your own proprietary fonts from your own web server, make sure you have only one font listed for a specific URL, and use the following parameters.

The HTTP header for the URL needs to include content-type: text/css.

The response body should contain the following:

/* latin */
@font-face {
 font-family: 'MyWebfont';
 font-style: normal;
 font-weight: 400;
 font-display: swap;
src: url (<URL for font>) format('<font-type>');
 
@font-face {
 font-family: 'MyWebfont';
 font-style: normal;
 font-weight: 700;
 font-display: swap;
src: url (<URL for font>) format('<font-type>');
 
font-family: the name of the font.
font-style: either normal or italic
font-weight: 400 (regular) or 700 (bold)
font-type: valid formats are truetype, eot, woff, and woff2
Both the HTTP response and the actual font file need the access-control-allow-origin (CORS) access flag to access your font page. The header must be set to either * or your SAP Analytics Cloud tenant URL.

Example
The following is an example of a response header with the CORS access flag.

Accept-Ranges: bytes
Access-Control-Allow-Origin: *
Access-Control-Expose-Headers: Access-Control-Allow-Origin,Access-Control-Allow-Methods
Content-Length: 172
Content-Type: text/css
The following are valid options for the HTTP response header of the actual font file in <URL for font>:
font/ttf
application/x-font-truetype
font/otf
application/x-font-opentype
font/woff
application/font-woff
font/woff2
application/font-woff2
application/vnd.ms-fontobject
  
