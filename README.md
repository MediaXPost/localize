# localize

[![NPM](https://nodei.co/npm/@mediaxpost/localize.png?downloads=true)](https://nodei.co/npm/@mediaxpost/localize/)

[![Actual version published on npm](http://img.shields.io/npm/v/@mediaxpost/localize.svg)](https://www.npmjs.org/package/@mediaxpost/localize)
[![Travis build status](https://travis-ci.org/MediaXPost/localize.svg?branch=master)](https://www.npmjs.org/package/@mediaxpost/localize)
[![Total npm module downloads](http://img.shields.io/npm/dt/@mediaxpost/localize.svg)](https://www.npmjs.org/package/@mediaxpost/localize)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/5df4541beccd4014bc2c80e275b0bf21)](https://www.codacy.com/app/chronosis/localize?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=MediaXPost/localize&amp;utm_campaign=Badge_Grade)
[![Codacy Badge](https://api.codacy.com/project/badge/Coverage/5df4541beccd4014bc2c80e275b0bf21)](https://www.codacy.com/app/chronosis/localize?utm_source=github.com&utm_medium=referral&utm_content=MediaXPost/localize&utm_campaign=Badge_Coverage)
[![Dependencies badge](https://david-dm.org/MediaXPost/localize/status.svg)](https://david-dm.org/MediaXPost/localize?view=list)

`localize` is a basic i18n module for Node.JS.

# [Installation](#installation)
<a name="installation"></a>

```shell
npm install @mediaxpost/localize
```

# [Usage](#usage)
<a name="usage"></a>

```js
const Localize = require('@mediaxpost/localize');
const i18n = new Localize({
  'en': {
    'TestKey': 'Test'
  },
  'es': {
    'TestKey': 'Prueba'
  }
});

console.log(i18n.tr('TestKey'));
```

# [API Reference](#api)
<a name="api"></a>

## Localize constructor(dictionaries, defaultLang) &#x27fe; instanceof Localize
Create an instance of Localize with the dictionaries provided and using the default language. If no default language is provided then `'en'` will be used.

## Localize isLanguageAvailable(lang) &#x27fe; boolean
Returns a boolean regarding the availability of a dictionary for the provided `lang`.

## Localize sanitizeLanguageCode(lang) &#x27fe; string
Sanitizes a the `lang` provided to only the first two characters of a string. If a non-string value for `lang` is provided then `'en'` is returned.

## Localize setDefaultLanguage(lang) &#x27fe; string
Sets the default language to the `lang` provided after sanitization. If no dictionary for the `lang` is available, then an error is thrown.

## Localize listLanguages &#x27fe; Array<string>
Returns an Array of the available dictionary languages.

## Localize loadDictionary(lang, dictionary)
Loads and overwrites dictionary entries for the given `lang`. Existing key values are overwritten by values loaded.

## Localize tr(key, lang) &#x27fe; string
Returns the translations provided for a given key of the `lang` provided. If no `lang` is provided or is not available, then the default language is used. If the key does not exist in the dictionary, then an empty string is returned.

# [License](#license)
<a name="license"></a>

Licensed under the MIT license.
Copyright (c) 2019 Out of Sync Studios LLC
