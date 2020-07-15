# polyglot-reference-data
This utility aims to provide a solution to some ploblems when using [Polyglot](https://github.com/untra/polyglot) to make multi-language Jekyll websites:
- No native way to know what languages a page/post is localized to. 
- No native way to have a list of what pages/posts are localized for every language.

You can check the [simple demo page](https://no3371.github.io/blog/polyglot-index-example.html) rendered with Liquid to grt the map/index generated, and [the source of the page](polyglot-index-example.html).

## Feature
- It checks files in your path, looks for pages/posts interested by [Polyglot](https://github.com/untra/polyglot), then generate *polyglot-index* and *polyglot-map* in your `_data` folder, so you access them with Liquid.
    - **polyglot-index**: page/post -> localizations
    - **polyglot-map**: localizatio -> pages/posts
- Simple to use, `ruby _utils/polyglot-indexing.rb`could be added to Travis scripts.
- Read your `_config.yml` to automatically know your `languages` and the `default_lang`.
- Fully customizable, the script is easy to modify:
    - **map_file_path**: where the map store.
    - **index_file_path**: where the index store.
    - **file_regex**: what file extensions to scan, for example you can add .pug support if you use some pug plugin.
    - **exclude_regex**: what to ignore, all the defined folder/subfolder/nestedFiles will not shows up in the data file.
    - Run with `--lang_from_path`: to have exact same behaviour with [Polyglot](https://github.com/untra/polyglot)'s `lang_from_path`.

## Installation
- **_utils/polyglot-indexing.rb**: The script file. 
- **gen-polyglot-references.bat**: Batch file to run the script. Optional.
- **gen-polyglot-references-lang-from-path.bat**: `lang_from_path` version. Optional.

Actually only the script is needed here, the batch files are just provided for convenience.

:warning:**The script is designed to be run from the root path of your Jekyll site (where _data, _post resides), that's why the batch file calls `./_utils/polyglot-indexing.rb`. Running from elsewhere is not tested.**

## Contribution
I was just started to build my blogs, trying to make it multilingual and encountered the problems myself and saw others need this too, so I made this.

The tool is made within 1 day, and I was totally new to Jekyll, Travis & Ruby, so maybe there are bugs in there, I don't know :smile:

If you encountered any behaviour inconsistent with what described here, please let me know by creating a issue. 

I have no plan to make it more convienient like add some external file to config the behaviour, it is designed to be altered by editing the script.

If you are interested to make it better or share new cool feature you make, feel free to send a PR! 

## Copyright
Copyright (c) Ren Chen 2020. License: MIT
