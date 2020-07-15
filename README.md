# polyglot-reference-data
This utility aims to provide a solution to some ploblems when using [Polyglot](https://github.com/untra/polyglot) to make multi-language Jekyll websites:
- No native way to know what languages a page/post is localized to. 
- No native way to have a list of what pages/posts are localized for every language.

## Feature
- Generate *polyglot-index* and *polyglot-map* in your `_data` folder, so you access them with Liquid.
    - **polyglot-index**: page/post -> localizations
    - **polyglot-map**: localizatio -> pages/posts
- One click to use, could be added to Travis scripts.
- Read your `_config.yml` to automatically know your `languages` and the `default_lang`.
- Fully customizable, the script is easy to modify:
    - **map_file_path**: where the map store.
    - **index_file_path**: where the index store.
    - **file_regex**: what file extensions to scan, for example you can add .pug support if you use some pug plugin.
    - **exclude_regex**: what to ignore, all the defined folder/subfolder/nestedFiles will not shows up in the data file.
    - Run with `--lang_from_path`: to have exact same behaviour with [Polyglot](https://github.com/untra/polyglot)'s `lang_from_path`.

## Installation
Place stuff to whereever you want:
- **_utils/polyglot-indexing.rb**: The script file. 
- **gen-polyglot-references.bat**: Batch file to run the script.
- **gen-polyglot-references-lang-from-path.bat**: `lang_from_path` version.

Actually only the script is needed here, the batch files are just provided for convenience.
**The script is designed to be run from the root path of your Jekyll site (where _data, _post resides). Running from elsewhere is not bug-free guaranteed.**

## Copyright
Copyright (c) Ren Chen 2020. License: MIT