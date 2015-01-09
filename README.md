# AutodetectLanguage
This ProcessWire 2.x module tries finds a best match between HTTP_ACCEPT_LANGUAGE and currently installed languages. 

If a match is found, the user will be redirected from the requested page to the same page in his preferred language. This match occurs only on the first page load, and will work with default caching on.

For example:
- User requests http://example.com/fr/a-propos
- Module detects a preference for English
- User is redirected to http://example.com/en/about

The module creates two ProcessWire session variables:
- **$session->languageAlreadyDetected** returns *true* if detection has run once
- **$session->languageDetectionFailed** returns *true* if fell back to default

## Configuration
Set the language code for "default" language in Modules > Autodetect Language
