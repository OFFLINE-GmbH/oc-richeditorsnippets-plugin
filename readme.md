# Snippets Anywhere

- [Introduction](#introduction)
- [Example usage for Rainlab Syntax Fields](#syntaxFields)
- [Example usage for Rainlab Pages Content Blocks](#contentBlocks)

<a name="introduction"></a>
## Introduction

One of the great features of Rainlab Pages plugin is the `Snippets` feature. It allows the developer to hand over management of complex items, such as forms, maps, widgets, etc to the client. For more information on what a Snippet is, please see https://github.com/rainlab/pages-plugin#snippets.

This plugin simply extends the ability to re-use these snippets from any `richeditor` by providing an additional dropdown to the Froala Richeditor with a list of available snippets (supports partial and component based snippets). It also provides a twig filter to allow the parsing of implemented snippets.

For documentation regarding creating snippets, please see https://github.com/rainlab/pages-plugin#snippets-created-from-partials

<a name="syntaxFields"></a>
## Example usage for Rainlab Pages Syntax Fields

Option 1 (offset to variable)
```
{variable type="richeditor" tab="Content" name="text" label="Text"}{/variable}
{{ text | parseSnippets }}
```

Option 2 (wrap in filter)
```
{% filter parseSnippets %}
    {richeditor tab="Content" name="text" label="Text"}{/richeditor}
{% endfilter %}
```

<a name="contentBlocks"></a>
## Example usage for Rainlab Pages Content Blocks

```
{% filter parseSnippets %}
    {% content 'company-details.htm' %}
{% endfilter %}
```
