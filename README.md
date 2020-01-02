# FM Docs : LiveSwitch, LiveSwitch Cloud

## How it Works

* All content in _Static_ is copied as is into the root directory, folders included.
* _static/index.html_ is the overall landing page as seen here: https://docs.liveswitch.io/
* _markdown_ contains the platform folders.
* _markdown/<platform>/index.md_ is the platform landing page.
* _markdown/<platform>/toc.yml_ is the top level nav for the given platform - to ensure the nav gets updated you must update the toc.yml file for the given platform anytime you add something to a platform markdown folder.
* _markdown/<platform>/guides_ is a folder for grouping the guides for the given platform.
* Inside the guides folder is another toc.yml - this is the side nav for the platform guides.
* Currently the top level toc is saying to use the guides _overview.md_ page as the guide's landing page **(topicHref: guides/overview.md)**, and to use the namespace markdown for the api docs landing page (FM.LiveSwitch).
* The guides toc is hierarchal as seen here: markdown/net/guides/toc.yml

## Supported Markdown Flavour

Docfx uses the _markdig_ engine: https://github.com/lunet-io/markdig
