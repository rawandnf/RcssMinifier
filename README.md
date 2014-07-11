# RcssMinifier
_Copyright (c) 2014 Rawand Fatih_, 
_Licensed under MIT License (MIT)_

Bash script/program to merge and minify css files.
You can minify a single file, or merge and minify multiple files.

For minifing the CSS, this script uses a minifier from [cssminifier.com](http://cssminifier.com/)

Usage
------------
### Using File Name Sequence
- You can use the command with a sequence of files and it will merge and minifiy all the files in order of the argument sequence.
  - Two files will be created (style.css and style.min.css).
  - Example:
```csharp
    // Ouputs 'style.css' and 'style.min.css'
    sh RcssMinifier.sh test.css test2.css

    // You can also minify single files
    sh RcssMinifier.sh test.css
```
### Using Option Arguments
- You can specify parameters, once you use parameters the -n and -f arguments are required.
  - Params:
    - [ -n ] To specify the file name.
    - [ -f ] The list of files. It SHOULD be wrapped in double quotes [ " ].
    - [ -r ] To remove the merged (but not minified) filed.
  - Examples:
```csharp
    // This outputs 'king.css' and 'king.min.css'
    sh RcssMinifier.sh -n king -f "test.css test2.css"

    // This outputs only the minified file, 'queen.min.css'
    sh RcssMinifier.sh -r -n queen -f "test.css test2.css"
    
    // You can also use if for single files, outputs 'prince.min.css'
    sh RcssMinifier.sh -r -n prince -f "test.css"
    
    // You can also specify paths along the file names
    // This outputs princess.css and princess.min.css in the home folder.
    sh RcssMinifier.sh -n "~/princess" -f "test.css test2.css"
```
------------

### Good Practices
It's always better and cleaner to create an alias for the bash script so that you can use it easier.
```csharp
    // Use the path of your script instead.
    // It's good to have a folder for all the scripts in one place.
    alias csscomp='~/bashscripts/RcssMinifier.sh'
```
You can also add this alias initialization to your `.bash_profile` on Mac, or `.bashrc` on Linux so that the alias will be created each time you use terminal.
