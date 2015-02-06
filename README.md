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

It is also possible to have the redirect happen only on the homepage by checking **Only detect language on homepage** in module settings.

## Support
Please use the [bug tracker](https://github.com/plauclair/AutodetectLanguage/issues) to submit bugs and feature requests.

## Licence
Licensed under the [MIT License (MIT)](http://opensource.org/licenses/MIT). Copyright © 2014 Pierre-Luc Auclair
