# Translatable

Abstract class that makes retrieving translations in your controllers easier. 🏳️‍🌈  
Extend pages / components with this one. Automatically adds a _translations_ property, where all the requested translations are stored.

# Installation

Add to your project via npm.
```
$ npm i @webfactor/ionic-translatable
```

## Methods / Properties
```typescript
getTranslations(keys: string | string[]): Promise<any>
```
Gets the requested translations and stores them in the _translations_ property.

```typescript
protected translations
```
Holds the translations, once retrieved by the `getTranslations()` Method.

## Example
```typescript
export class HomePageComponent extends Translatable {
    constructor(protected translate: TranslateService) {
       super(translate);
       this.getTranslations('home').then(translations => {
           // do something maybe
       }, err => console.log(err));
    }

    logTranslation(): void {
        console.log(this.translations.someTranslation);
    }
}
```
