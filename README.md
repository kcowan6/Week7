# Project 7 - WordPress Pentesting

Time spent: **5** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Unauthenticated Stored Cross-Site Scripting (XSS)
  - [X] Summary:  
    - Vulnerability types: Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2
  - [X] GIF Walkthrough: <img src='https://media.giphy.com/media/3ohhwq1IRiHm6TLHgY/giphy.gif' title='GIF Walkthrough 1' width='' alt='GIF Walkthrough 1' />
  - [X] Steps to recreate: Create a comment, and in the text body, type <script>while(1){alert(document.cookie);}</script>. Once you submit and attempt to reload the page, the alert messages will continue infinitely.  This can only be fixed by going back into the admin page and deleting the comment.
  - [X] Affected source code:
    - [Link 1](http://www.smeegesec.com/2012/06/collection-of-cross-site-scripting-xss.html)
2. (Required) Authenticated Cross-Site Scripting (XSS) via Media File Data
  - [X] Summary:
    - Vulnerability types: Cross-Site Scripting (XSS) Injection
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [X] GIF Walkthrough: <img src='https://media.giphy.com/media/3ohhwLzrakf17PLmJG/giphy.gif' title='GIF Walkthrough 2' width='' alt='GIF Walkthrough 2' />
  - [X] Steps to recreate: First insert multiple media files.  Then, as their descriptions, type "Whoop <noscript/><script>alert(document.cookie);</script>".  This vulnerability is similar to the one found before, where an alert message repeatedly pops up and cannot be disabled until the user has re-entered the admin console and removed the post.
  - [X] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/28f838ca3ee205b6f39cd2bf23eb4e5f52796bd7)
3. (Required) Authenticated Stored Cross-Site Scripting (XSS) via Image Filename
  - [X] Summary:
    - Vulnerability types: Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2.10
  - [X] GIF Walkthrough: <img src='https://media.giphy.com/media/l1J9NWTLm2WwgCFkQ/giphy.gif' title='GIF Walkthrough' width='' alt='GIF Walkthrough' />
  - [X] Steps to recreate: Download an image, and name if a<img src=a onerror=alert(document.cookie)>.jpg.  Upload it as a new media file, and click to view its attachment page. An alert message will pop up before the page is loaded.
  - [X] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/c9e60dab176635d4bfaaf431c0ea891e4726d6e0)

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2017] [KC Cowan]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
