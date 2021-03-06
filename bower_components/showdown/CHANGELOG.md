<a name"1.1.0"></a>
## 1.1.0 (2015-06-18)


#### Bug Fixes

* **converter.js:** add error if the passed constructor argument is not an object ([d86ed450](http://github.com/showdownjs/showdown/commit/d86ed450))
* **output modifiers:** fix for output modifiers running twice ([dcbdc61e](http://github.com/showdownjs/showdown/commit/dcbdc61e))


#### Features

* **headerLevelStart:** add support for setting the header starting level ([b84ac67d](http://github.com/showdownjs/showdown/commit/b84ac67d), closes [#69](http://github.com/showdownjs/showdown/issues/69))
* **image dimensions:** add support for setting image dimensions within markdown syntax ([af82c2b6](http://github.com/showdownjs/showdown/commit/af82c2b6), closes [#143](http://github.com/showdownjs/showdown/issues/143))
* **noHeaderId:** add option to suppress automatic generation of ids in headers ([7ac893e9](http://github.com/showdownjs/showdown/commit/7ac893e9))
* **showdown.getDefaultOptions:** add method to retrieve default global options keypairs ([2de53a7d](http://github.com/showdownjs/showdown/commit/2de53a7d))


#### Breaking Changes

* Deprecates `showdown.extensions` property. To migrate, extensions should use the new method `showdown.extension(<ext name>, <extension>)` to register.
  For more information on the new extension loading mechanism, please check the wiki pages.
  ([4ebd0caa](http://github.com/showdownjs/showdown/commit/4ebd0caa))


<a name"1.0.2"></a>
### 1.0.2 (2015-05-28)

#### Bug Fixes

* **Gruntfile.js** add missing comma in footer. This bug prevented concatenating other js scripts and libraries
  with showdown([5315508](http://github.com/showdownjs/showdown/commit/5315508). Credits to Alexandre Courtiol.


<a name"1.0.1"></a>
### 1.0.1 (2015-05-27)


#### Bug Fixes

* **bower.json:** update bower.json main attribute to point to dist directory ([bc3a092f](http://github.com/showdownjs/showdown/commit/bc3a092f))


<a name"1.0.0"></a>
## 1.0.0 (2015-05-27)

#### Release Information
This is a major code refactor with some big changes such as:
  - showdown.js file was split in several files, called sub-parsers. This should improve code maintainability.
  - angular integration was removed from core and move to its own repository, similar to what was done with extensions
  - A new extension registering system is on the "cooks" that should reduce errors when using extensions. The old mechanism
  is kept so old extensions should be compatible.

#### Bug Fixes

* **extensions:** support for old extension loading mechanism ([95ed7c68](http://github.com/showdownjs/showdown/commit/95ed7c68))
* **helpers:** fix wrong function call 'escapeCharacters' due to old strayed code ([18ba4e75](http://github.com/showdownjs/showdown/commit/18ba4e75))
* **showdown.js:**
  - fix showdown extension loader ([a38c76d2](http://github.com/showdownjs/showdown/commit/a38c76d2)),
  closes [#50](http://github.com/showdownjs/showdown/issues/50),[#56](http://github.com/showdownjs/showdown/issues/56),
  [#104](http://github.com/showdownjs/showdown/issues/104), [#108](http://github.com/showdownjs/showdown/issues/108),
  [#109](http://github.com/showdownjs/showdown/issues/109), [#111](http://github.com/showdownjs/showdown/issues/111),
  [#118](http://github.com/showdownjs/showdown/issues/118), [#122](http://github.com/showdownjs/showdown/issues/122)
  - add unique id prefix and suffix to headers ([c367a4b9](http://github.com/showdownjs/showdown/commit/c367a4b9), closes [#81](http://github.com/showdownjs/showdown/issues/81), [#82](http://github.com/showdownjs/showdown/issues/82))
* **options.omitExtraWLInCodeBlocks:** fix for options.omitExtraWLInCodeBlocks only applying in gitHub flavoured code b ([e6f40e19](http://github.com/showdownjs/showdown/commit/e6f40e19))
* **showdown:** fix for options merging into globalOptions ([ddd6011d](http://github.com/showdownjs/showdown/commit/ddd6011d), closes [#153](http://github.com/showdownjs/showdown/issues/153))

#### Features

* **registerExtension():** new extension loading mechanism. Now extensions can be registered using this function.
  The system, however, is not final and will probably be changed until the final version([0fd10cb] (http://github.com/showdownjs/showdown/commit/0fd10cb))
* **allowBlockIndents:** indented inline block elements can now be parsed as markdown ([f6326b84](http://github.com/showdownjs/showdown/commit/f6326b84))
* **omitExtraWLInCodeBlocks:**  add option to omit extra newline at the end of codeblocks ([141e3f5](http://github.com/showdownjs/showdown/commit/141e3f5))
* **prefixHeaderId:** add options to prefix header ids to prevent id clash ([141e3f5](http://github.com/showdownjs/showdown/commit/141e3f5))
* **Converter.options:** add getOption(), setOption() and getOptions() to Converter object ([db6f79b0](http://github.com/showdownjs/showdown/commit/db6f79b0))

#### Breaking Changes
* **NAMESPACE:** showdown's namespace changed.

   To migrate your code you should update all references to `Showdown` with `showdown`.

* **Converter:** converter reference changed from `converter` to `Converter`.

   To migrate you should update all references to `Showdown.converter` with `showdown.Converter`

* **angular:** angular integration was removed from core and now lives in it's own [repository](http://github.com/showdownjs/angular/).

   If you're using angular integration, you should install ng-showdown. Ex: `bower install ng-showdown`

* **extensions:** showdown extensions were removed from core package and now live in their own repository. See the [project's github page](https://github.com/showdownjs) for available extensions
