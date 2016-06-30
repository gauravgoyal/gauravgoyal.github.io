---
title:  "Sublime Text 3 Setup for Drupal"
subtitle: "Change in the era of editors and IDE's."
author: "Gaurav"
avatar: "img/authors/gaurav.jpg"
image: "img/ST.jpg"
date:   2016-06-23 12:12:12
comments: true
---

## Download Sublime text.
  - Download latest version / build of sublime text from [website]. At the time of writing this blog we have build 3114 of ST3.
  - Install [Package Installer], this is the most important thing for sublime text.

## Plugins:

* ### Sublime PHP Companion
  - An important thing which sets IDE's apart from text editors is there goto definition functionality which was kind of missing in sublime text 2 but now it is included into the core of ST3.
  - In the top navigation goto tab, we'll see a goto definition link and which works like any IDE's out there.
  - Apart from the above [Sublime PHP Companion] plug-ins lots of other IDE's functionality out of the box.
  - Now, I want to have my `cmd + click` key binded to goto definition action so for that I followed the instruction given [in this gist].
  - _Until you create a project, sublime's inbuilt indexing does not works._

* ### Sublime PHP CS
  - Install [sublime phpcs].
  - Install [Code Sniffer and Drupal].
    - If you are installing codesniffer for the first time, it works well. But when you try to upgrade the previous version 
    you may end up in lots of issues.
    - In my case, I wanted to install `Coder` for `Drupal 8`  and I ended up in `dependency` problems.
    - Solution in my case was to remove install instructions (manually) from `composer.lock` file and then reinstall.
  - _We can do the sniffing work by creating a build but PHP CS comes with lots of things which works out of the box._

* ### Xdebug Client
  - `Xdebug` is a brilliant tool for debugging and it seamlessly integrates with Sublime Text.
  - Install [Xdebug Client] to start debugging.
  - Now, Let's configure `Xdebug Client`
    - Open your project file. `foobar.sublime-project`.
    - Add the following snippet:     
    _NOTE:_ YOUR_REMOTE_PATH & YOUR_LOCAL_PATH will be same if you are not debugging remotely. If you debug remotelyit is mandatory to specify path mapping otherwise you will end up in no result.
  
  - Install `Xdebug`:
    - `sudo apt-get install php5-dev`
    - `pecl install xdebug`
    - For other methods, checkout [Xdebug Install]
    - Configure Xdebug.
    
    ```javascript
        {
            "folders":
            [
                {
                    "follow_symlinks": true,
                    "path": "."
                }
            ],
            "settings": {
                "xdebug": {
                     "url": "YOUR_URL",
                     "path_mapping": {"YOUR_REMOTE_PATH" : "YOUR_LOCAL_PATH"},
                }
            }
        } 
    ```
    
    - _NOTE:_ You can configure configure `Xdebug` to work remotely also and locally also. Depending on your need configuration will change.
  
* ### Other Plug-ins:
  - [Bracket Guard]
  - [Bracket Highlighter]
  - [DocBlockr]
  - [Git]
  - [Sass Beautify]
  - [Pretty YAML]
  - [SyncedSidebar]
  - [Markdown Editing]

* Drupal Configuration
  - Follow the instruction given here in the [documentation].

### Reference Links:
- [RealityLoop Article](http://realityloop.com/blog/2014/03/05/drupal-development-using-sublime-text-3-5-steps)
- [Mattstuaffer's Blog](https://mattstauffer.co/blog/sublime-text-3-for-php-developers)
- [Xdebug Install on Ubuntu](http://purencool.com/installing-xdebug-on-ubuntu)

_NOTE:_ Please let me know in comments if you face any problem is sublime text configuration or if you know any
interesting plugin which everyone should use. :)

[website]: https://www.sublimetext.com/3
[Package Installer]: https://packagecontrol.io/installation
[Sublime PHP Companion]: https://github.com/erichard/SublimePHPCompanion
[in this gist]: https://gist.github.com/kendellfab/6135193
[sublime phpcs]: http://benmatselby.github.io/sublime-phpcs
[Code Sniffer and Drupal]: https://www.drupal.org/node/1419988
[Xdebug Client]: https://github.com/martomo/SublimeTextXdebug
[Xdebug Install]: https://xdebug.org/docs/install
[Bracket Guard]: https://packagecontrol.io/packages/BracketGuard
[Bracket Highlighter]: https://github.com/facelessuser/BracketHighlighter
[DocBlockr]: https://github.com/Warin/Sublime/tree/master/DocBlockr
[Sass Beautify]: https://packagecontrol.io/packages/SassBeautify
[Pretty YAML]: https://packagecontrol.io/packages/Pretty%20YAML
[Git]: https://packagecontrol.io/packages/Git
[SyncedSidebar]: https://packagecontrol.io/packages/SyncedSideBar
[Markdown Editing]: https://packagecontrol.io/packages/MarkdownEditing
[Git]: https://packagecontrol.io/packages/Git
[documentation]: https://www.drupal.org/node/1346890
