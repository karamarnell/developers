---
title: Qordoba Extract
---

# Qordoba Extract `beta`

The Qordoba String Extractor is AI that reads your code, extracts strings and replaces them with keys. It’s smart enough to understand what frameworks and programming languages you are using, and learns from your coding patterns.

Download latest version

```
pip install qordoba==0.2.0a1
```

##Extract

Use the Qordoba ‘extract’ command to identify the local directory path where you have files that need to be localized.

`qor extract -i input_dir -r report_dir -l customized_lexer`

The extract command pulls all the files from the given directory path and its subdirectories. 
Our lexer will parse your files and extract all the strings. The strings are saved in a generated JSON report.

report elements:
  * filename
  * string
  * start_line
  * end_line
  * code_snippet
    <div class="alert alert-warning">
      <div class="text-center">
        <strong>Note</strong>: The report can be edited (delete values, add) at this step. Not later.
      </div>
    </div>


##Generate

Use the Qordoba ‘generate’ command to generate the keys (QUIDs) for the content that was extracted. The extraction can be modifed to exclude content that you don’t want in your resource file.

`qor generate -r report_dir -e report_key_dir`

The generate command will pick up your reports in the report_dir and generate new keys for every string by calling our API.
Keys are added to a new report which is stored in a new directory. The reason: while processing many reports there may occur connectivity issues. This way you know which reports have been processed.

Optional:
Flag `--existing_strings managementfiles directory_path`. 
The generate command will look for JSON localization files in the directory_path and scan for existing keys or values.

report elements:
  * filename
  * string
  * start_line
  * end_line
  * code_snippet
  * generated_key
  * existing_key



##Execute

Use the Qordoba ‘execute’ command to replace the strings in your source code with the generated keys.


`qor execute -i input_dir -r report_key_dir -k key_format`

key format:
if keys should be replaced with a custom format, add it as a flag or within the configuration file.

The "KEY" characters will be replaced by the generated key within your report:

**Option 1: **

add a custom key flag to execute the command: -k {{KEY}}

**Option 2: **

add a custom key format in your configuration file **.ml.yml**


```
key_format:
  html: '$KEY' #file extension: format
```
 
 
 **Example**

 ```
 "/Users/Qordoba/Desktop/demo/deep/translate.html": {
         "0": {
             "end_line": 5,
             "generated_key": {
                 "key": "qor_5A8DDC25_example_domain"
             },
             "snippet": "    <title>Example Domain</title>",
             "start_line": 5,
             "value": "Example Domain"
         },
 ```
 
 status        | snippet
 ---         | ---    
not localized        |   &lt;title&gt;`Example Domain`&lt;/title&gt;    
execution - default|      &lt;title&gt;`qor_5A8DDC25_example_domain`&lt;/title&gt;
execution - custom key format |        &lt;title&gt; `$qor_5A8DDC25_example_domain`&lt;/title&gt;

 ----
 
 [Back to TOC](#table-of-contents)
##Supported languages

####Programming languages

  * ActionScript
  * Ada
  * ANTLR
  * AppleScript
  * Assembly (various)
  * Asymptote
  * Awk
  * Befunge
  * Boo
  * BrainFuck
  * C, C++
  * C#
  * Clojure
  * CoffeeScript
  * ColdFusion
  * Common Lisp
  * Coq
  * Cryptol (incl. Literate Cryptol)
  * Crystal
  * Cython
  * D
  * Dart
  * Delphi
  * Dylan
  * Elm
  * Erlang
  * Ezhil Ezhil - A Tamil programming language
  * Factor
  * Fancy
  * Fortran
  * F#
  * GAP
  * Gherkin (Cucumber)
  * GL shaders
  * Groovy
  * Haskell (incl. Literate Haskell)
  * IDL
  * Io
  * Java
  * JavaScript
  * Lasso
  * LLVM
  * Logtalk
  * Lua
  * Matlab
  * MiniD
  * Modelica
  * Modula-2
  * MuPad
  * Nemerle
  * Nimrod
  * Objective-C
  * Objective-J
  * Octave
  * OCaml
  * PHP
  * Perl
  * PovRay
  * PostScript
  * PowerShell
  * Prolog
  * Python 2.x and 3.x (incl. console sessions and tracebacks)
  * REBOL
  * Red
  * Redcode
  * Ruby (incl. irb sessions)
  * Rust
  * S, S-Plus, R
  * Scala
  * Scheme
  * Scilab
  * Smalltalk
  * SNOBOL
  * Tcl
  * Vala
  * Verilog
  * VHDL
  * Visual Basic.NET
  * Visual FoxPro
  * XQuery
  * Zephir

[Back to TOC](#table-of-contents)
####Template languages

  * Cheetah templates
  * Django / Jinja templates
  * ERB (Ruby templating)
  * Genshi (the Trac template language)
  * JSP (Java Server Pages)
  * Myghty (the HTML::Mason based framework)
  * Mako (the Myghty successor)
  * Smarty templates (PHP templating)
  * Tea

[Back to TOC](#table-of-contents)
###Other markup

  * Apache config files
  * Bash shell scripts
  * BBCode
  * CMake
  * CSS
  * Debian control files
  * Diff files
  * DTD
  * Gettext catalogs
  * Gnuplot script
  * Groff markup
  * HTML
  * HTTP sessions
  * INI-style config files
  * IRC logs (irssi style)
  * Lighttpd config files
  * Makefiles
  * MoinMoin/Trac Wiki markup
  * MySQL
  * Nginx config files
  * POV-Ray scenes
  * Ragel
  * Redcode
  * ReST
  * Robot Framework
  * RPM spec files
  * SQL, also MySQL, SQLite
  * Squid configuration
  * TeX
  * tcsh
  * Vim Script
  * Windows batch files
  * XML
  * XSLT
  * YAML
[Back to TOC](#table-of-contents)
