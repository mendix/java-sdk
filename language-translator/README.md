# Language Translator

## Installation

##### Maven
```xml
<dependency>
  <groupId>com.ibm.watson.developer_cloud</groupId>
  <artifactId>language-translator</artifactId>
  <version>6.11.0</version>
</dependency>
```

##### Gradle
```gradle
'com.ibm.watson.developer_cloud:language-translator:6.11.0'
```

## Usage
Select a domain, then identify or select the language of text, and then translate the text from one supported language to another.  
Example: Translate 'hello' from English to Spanish using the [Language Translator][language_translator] service.

```java
LanguageTranslator service = new LanguageTranslator();
IamOptions iamOptions = new IamOptions.Builder()
  .apiKey("<iam_api_key>")
  .build();
service.setIamCredentials(iamOptions);

TranslateOptions translateOptions = new TranslateOptions.Builder()
  .addText("hello")
  .source(Language.ENGLISH)
  .target(Language.SPANISH)
  .build();
TranslationResult translationResult = service.translate(translateOptions).execute();

System.out.println(translationResult);
```

[language_translator]: https://console.bluemix.net/docs/services/language-translator/index.html
