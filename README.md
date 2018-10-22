# Project 7 - WordPress Pentesting

Time spent: 5 hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) OVE-20160724-0008
  - [ ] Summary:  I copied a link with SQL in it into the search bar, and it inputted an SQL Sleep attack.
    - Vulnerability types: SQL Injection
    - Tested in version: 4.0 WordPress, 1.05 FormBuilder
    - Fixed in version: 1.07 FormBuilder
  - [ ] GIF Walkthrough: <img src="https://imgur.com/AakQjyu"/>
  - [ ] Steps to recreate: I installed version 1.05 of FormBuilder as a Plugin to WordPress. I then copied a link with SQL in it (http://<target>/wp-admin/tools.php?page=formbuilder.php&fbtag&pageNumber&fbaction=exportForm&fbid=1 AND (SELECT * FROM (SELECT(SLEEP(5)))WSdS) into the search bar. 
  - [ ] Affected source code: formbuilder.php/formuilder_admin_functions.php and formbuilder/php/formbuilder_admin_pages.inc.php
 
2. (Required) OVE-20160714-0016
  - [ ] Summary: I copied a link into the searcher which inputs an XSS attack
    - Vulnerability types: XSS
    - Tested in version: 4.0 WordPress, 1.6.3 Tribulant Slideshow Galleries
    - Fixed in version: Not fixed
  - [ ] GIF Walkthrough: ![Walkthrough](https://imgur.com/hCyOvYu)
  - [ ] Steps to recreate: I installed version 1.6.3 of the Tribulant Slideshow Galleries extenstion for WordPress. I then copied a link  that inputs an XSS attack into the webpage: http://<target>/wp-admin/admin.php?page=slideshow-galleries&method=savegtlcq%5C%22%3E%3Cscript%3Ealert%281%29%3C%2Fscript%3Exsxa2
  - [ ] Affected source code: view/admin/galleries/index.php

3. (Required) OVE-20160719-0004
  - [ ] Summary: I copied a link into the URL which puts an XSS attack into the webpage
    - Vulnerability types: XSS
    - Tested in version: 4.0 WordPress, 0.9.4.1 W3 Total Cache
    - Fixed in version: 0.9.5 W3 Total Cache
  - [ ] GIF Walkthrough: ![Walkthrough](https://imgur.com/IR83Z2I)
  - [ ] Steps to recreate: I installed version 0.9.4.1 of W3 Total Cache for WordPress. I think copied a link which inputs an XSS attack into the webpage: http://<target>/wp-admin/admin.php?page=w3tc_support&request_type=bug_report&request_id="><script>alert('sumofpwn.nl');</script>
  - [ ] Affected source code: inc/options/support/form.php
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
## Assets

None

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Finding good attacks to recreate was a challenge, but once I found good ones, they were not too challenging to implement

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
