# AutodetectLanguage
This ProcessWire 2.x module tries finds a best match between HTTP_ACCEPT_LANGUAGE and currently installed languages. 

If a match is found, the user will be redirected from the requested page to the same page in his preferred language. This match occurs only on the first page load, and will work with default caching on.

For example:
- User requests http://example.com/fr/a-propos
- Module detects a preference for English. At first, the module tries to do a "full match" using the full language name (e.g. en-US -> en-US). If no match is found, it will fall back to a "partial match" using only the first part of the name (e.g. fr-CA -> fr-FR, matched with "fr" only).
- User is redirected to http://example.com/en/about

The module creates two ProcessWire session variables:
- **$session->languageAlreadyDetected** returns *true* if detection has run once
- **$session->languageDetectionFailed** returns *true* if fell back to default

## Configuration
Set the language code for the "default" language in Modules > Autodetect Language.

You must also use [BCP 47 formatted](http://www.rfc-editor.org/rfc/bcp/bcp47.txt) language codes as your language **names**. These are the typical **us** or **en-US** you commonly see. **If not set, will default back to "en"**.

It is possible to have the redirect happen only on the homepage by checking **Only detect language on homepage** in module settings.

Additionally, you can set a GET parameter to prevent language redirection on some requests with **Do not detect language if GET parameter is set**.

## Changes

### 1.0.3
- This version introduces a new option: "Do not detect language if GET parameter is set". Usage info can be found in the *Configuration* section of this document.

### 1.0.2 
- Add check if isset http\_accept\_language that could cause a warning if the website is requested through a REST call, for example.

### 1.0.1
- Removed debug stuff.
- Add option to detect the user language only on the homepage.
- Do not redirect if the requested page is already using the best language match.

### 1.0.0
- Initial commit.

You must also use [BCP 47 formatted](http://www.rfc-editor.org/rfc/bcp/bcp47.txt) language codes as your language *names*. These are the typical **us** or **en-US** you commonly see. **If not set, will default back to "en"**.

## Support
Please use the [bug tracker](https://github.com/plauclair/AutodetectLanguage/issues) to submit bugs and feature requests.

## Licence
Licensed under the [MIT License (MIT)](http://opensource.org/licenses/MIT). Copyright © 2014 Pierre-Luc Auclair
