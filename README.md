gdocs2md (FORKED)
========

*This repo is forked from [mangine/gdocs2md](https://github.com/mangini/gdocs2md), you should probably go there instead.*

My changes:
* Avoid overuse of new lines by grouping list items together while inserting new lines before every other element
* Use tabs instead of spaces for nested lists
* Prefix all ordered lists with 1 rather than incrementing

A simple Google Apps script to convert a properly formatted Google Drive Document to the markdown (.md) format. 

## Fork Notes
  * Added basic support for [MultiMarkdown](https://github.com/fletcher/MultiMarkdown/wiki/MultiMarkdown-Syntax-Guide#tables) tables (what the [plugin for IntelliJ](https://github.com/nicoulaj/idea-markdown) uses)
  * Since I use Ubuntu Mono so I used that font family instead

## Usage
  * Open your Google Drive document (http://drive.google.com)
  * Tools -> Script Editor. Ignore (close) if you see a popup, clear the myFunction() default empty function and paste the [converttomarkdown.gapps](https://raw.github.com/mangini/gdocs2md/master/converttomarkdown.gapps) contents into the code editor
  * File -> Save
  * Run -> ConvertToMarkdown (First run will require you to authorize it. Authorize and run again)

The converted Markdown will be immediately sent as an attachment to your email. Images will be attached as well.

You can run the script again in the same document whenever you want, just clicking in Tools -> Script Manager -> Run. Every run will send a new email.


## Interpreted formats
  * *NEW*: Numbered lists are converted correctly now, including nested lists
  * *NEW*: images are correctly extracted and sent as attachments
  * *NEW*: Table of contents is replaced by `[[TOC]]`
  * paragraphs are separated by two newlines
  * text styled as heading 1, 2, 3, etc is converted to Markdown heading: #, ##, ###, etc
  * text formatted with Courier New is backquoted: ``text``
  * links are converted to MD format: `[anchortext](url)`
  * bullet lists are converted to "`*`" MD format appropriately, including nested lists
  * blocks of text delimited by "--- class whateverclassnameyouwant" and "---" are converted to `<div class="whateverclassnameyouwant"></div>` 
  * blocks of text delimited by "--- source code" and "---" are converted to `<pre></pre>` and prefixed by 4 empty spaces
  * "--- jsperf `<testID>`" is replaced by an iframe that shows an interactive chart of a JSPerf test. The `<testID>` is the last part of the URL of the Browserscope anchor in your JSPerf test. Something like `"agt1YS1wcm9maWxlcnINCxIEVGVzdBjlm_EQDA"` in the URL `http://www.browserscope.org/user/tests/table/agt1YS1wcm9maWxlcnINCxIEVGVzdBjlm_EQDA`
 


## LICENSE

Use this script at your will, on any document you want and for any purpose, commercial or not. 
The MarkDown files generated by this script are not considered derivative work and 
don't require any attribution to the owners of this script. 

If you want to modify and redistribute the script (not the converted documents - those are yours), 
just keep a reference to this repo or to the license info below:

```
Copyright 2013 Google Inc. All Rights Reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
