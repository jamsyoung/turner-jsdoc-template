# Turner - A JSDoc Template
This is a custom template for JSDoc.  It is a modified version of the default
template that comes with jsdoc-3.3.0-alpha13 to fit my needs.  This is free to
use and open for community input.  Feel free to create issues and pull requests.

## How to use as a node dependency
In your projects package.json file add a script and a dependency.
 
```json
"script": {
    "generate-docs": "node_modules/.bin/jsdoc --configure .jsdoc-conf.json --verbose"
},
"devDependencies": {
    "jsdoc": "3.3.0-alpha13"
}
```

In your .jsdoc-conf.json file, add a template option.

```json
"opts": {
    "template": "node_modules/turner-jsdoc-template/turner"
}
```

Here is my full .jsdoc-conf.json file for context.

```json
{
    "tags": {
        "allowUnknownTags": true,
        "dictionaries": ["jsdoc"]
    },
    "source": {
        "include": [".", "package.json", "README.md"],
        "includePattern": ".js$",
        "excludePattern": "(node_modules/|docs)"
    },
    "plugins": [
        "plugins/markdown"
    ],
    "templates": {
        "cleverLinks": false,
        "monospaceLinks": false
    },
    "opts": {
        "destination": "./docs/",
        "encoding": "utf8",
        "private": true,
        "recurse": true,
        "template": "node_modules/turner-jsdoc-template/turner"
    }
}
```
