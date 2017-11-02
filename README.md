# Totem module: loadCSS
Twig partial for outputting your stylesheets in the loadCSS pattern to load your css asynchronous.

This module is created for [Totem](https://www.github.com/toolbarthomas/totem) projects but can also be used in any other Twig related project.

## Installation

Install totem.module.loadcss with [npm](https://www.npmjs.com/) (we assume you have pre-installed [node.js](https://nodejs.org/)).

```bash
$ npm install totem.module.loadcss --save
```

## How to include loadcss.twig
In the following example we will include loadcss.twig from our default page.
You can define multiple stylesheets at the include. You this by defining the **stylesheets** parameter.

```twig
<head>
    ...
    <link rel="stylesheet" href="main.css">
    {% include 'node_modules/totem.module.loadcss/partials/loadcss.twig' with {
        stylesheets: [
            'foo.css',
            'bar.css'
        ]
    } %}
    ...
</head>
```

## Include loadCSS scripts from another location than *node_modules*
loadcss.twig will include the loadCSS Javascript Functions from itself.
You can include the loadCSS Javascript files from another location by defining the *base* parameter.

Using the *base* parameter is optional since we asum you can access the node_modules directory.
The loadCSS javascript file will also be synced to your **dist**
When using this module within the Totem project structure.

```twig
<head>
    ...
    <link rel="stylesheet" href="main.css">
    {% include 'node_modules/totem.module.loadcss/partials/loadcss.twig' with {
        stylesheets: [
            'foo.css',
            'bar.css'
        ],
        base: 'dist/resources/' {# Lookup into: `dist/resources/totem.module.loadcss/` #}
    } %}
    ...
</head>
```

## loadCSS
This module uses the original loadCSS package created by [Filament group](https://www.filamentgroup.com/).
Any bugs related to the actual loadCSS functions should be reported at it's [Github Repository](https://github.com/filamentgroup/loadCSS/issues)
