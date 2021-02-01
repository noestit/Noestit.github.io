---
layout: single
title: 'EditorConfig Core options'
permalink: /editorconfig/core-options

sidebar:
  nav: "editorconfig"

toc: true
toc_sticky: true
---

## Core EditorConfig Options

### Set as root 
Remove the line below if you want to inherit .editorconfig settings from higher directories
````
root = true
````
### Indentation and spacing
#### Global
````
indent_style    = space
insert_final_newline = true
````
#### Code files (.CS, .CSX, .VB, .VBX)
````
charset = utf-8
end_of_line = crlf
indent_size = 4
tab_width = 4
````
#### XML files (.csproj, .vbproj, .vcxproj, .vcxproj. .filters, .proj, .projitems, .shproj)
````
indent_size     = 2
````
#### XML Config files (.props, .targets, .ruleset, .config, .nuspec, .resx, .vsixmanifest, .vsct)
````
indent_size     = 2
````
#### JSON files
````
indent_size     = 2
````
### Severity level of formatting violations
To set the rule severity for a single rule, use the following syntax.
````
dotnet_diagnostic.<rule ID>.severity = <severity value>
````
To set the default rule severity for a category of analyzer rules, use the following syntax.
````
dotnet_analyzer_diagnostic.category-<rule category>.severity = <severity value>
````
To set the default rule severity for all analyzer rules, use the following syntax.
````
dotnet_diagnostic.IDE0055.severity = error
````
