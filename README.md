 codepath_homeworks
# Weeks 7 & 8 Project: WordPress vs. Kali

Time spent: 40 hours spent in total

> Objective: Find, analyze, recreate, and document three vulnerabilities affecting an old version of WordPress

## Pentesting Report

### 1. CVE 2017-6817
  - [ ] Summary: In WordPress before 4.7.3 (wp-includes/embed.php), there is authenticated Cross-Site Scripting (XSS) in YouTube URL Embeds.
    - Vulnerability types:XXS
    - Tested in version:4.2
    - Fixed in version: 4.2.13
  - [ ] GIF Walkthrough: ![](https://github.com/apaudel2055/codepath_homework/blob/WordPressvsKali/Vulnerability1.gif)
  - [ ] Steps to recreate: By creating a youtube embedded into the post. A simple script is injected using the post. The script is shown below: 
  
  [embed src='https://youtube.com/embed/123\x3csvg onload=alert(69)\x3e'][/embed]
  - [ ] Affected source code:
    - [shortcode_parse_atts](https://developer.wordpress.org/reference/functions/shortcode_parse_atts/)
### 2. CVE 2019-17671
  - [ ] Summary: In WordPress before 5.2.4, unauthenticated viewing of certain content is possible because the static query property is mishandled.
    - Vulnerability types: IDOR/BYPASS
    - Tested in version:4.2
    - Fixed in version: 4.2.25
  - [ ] GIF Walkthrough: ![](https://github.com/apaudel2055/codepath_homework/blob/WordPressvsKali/Vulnerability2.gif)
  - [ ] Steps to recreate: Add ?static=1&order=asc to a wordpress URL. It will show all the draft, private and deleted pages.
  - [ ] Affected source code:
    - [class-wp-query.php](https://developer.wordpress.org/reference/files/wp-includes/class-wp-query.php/)
### 3. WordPress User Enumeration
  - [ ] Summary: User Enumeration is an attack, where an attacker thoroughly scans a web application to discover the login name of the WordPress based web application.
    - Vulnerability types:User Enumeration/IDOR
    - Tested in version:4.2
    - Fixed in version: Unknown (fixed by plugin)
  - [ ] GIF Walkthrough:https://github.com/apaudel2055/codepath_homework/blob/WordPressvsKali/Vulnerability2.gif 
  - [ ] Steps to recreate: Open the wordpress site. Add "?author=" without the quote following up with a number starting from 0. Open/inspect the source page and the username is visible.
  - [ ] Affected source code:
    - [htaccess](https://wordpress.org/support/article/htaccess/)

## Assets

N/A

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [screentogif](https://www.screentogif.com/).

## Notes
I tried so hard, got so far and in the end it apparently matters.

## License

    Copyright [2022] [Anup Paudel]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
