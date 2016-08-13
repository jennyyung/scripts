# buildreport
Aggregates all data from each tool report and summarize them in html format in order to use it via email. Following information is provided:

- **Pull request info**: Which commits are in the pull request
- **Apk info**: All information about the apk. Comparison is also shown between prior the pull request and after
 - **Method count**: Current, Diff, New and Remaining count
 - **Apk Size in mb**: Current, Diff, New
 - **Min sdk version**
 - **Target sdk version**
 - **Permissions**: New added permission are shown in green and annotated. Removed permissions are shown in red and annotated
- **Lint summary**
- **Checkstyle summary**
- **Unit tests summary**: Grouped by test classes. Some test classes are highligted regarding to status
 - **Red**: Failure tests
 - **Orange**: Ignored tests
 - **Blue**: These tests take longer than 1 second, usually unit tests should be super fast

# Build Report sample
<img src='https://github.com/orhanobut/buildreport/blob/master/art/screenshot.png'/>

# Usage
Add the following commands to your execute shell in post build. build-report script uses assembleRelease in order to compare and fetch information about apk. If you want to use for debug build, you need to change build-report.sh. 

```shell
$ mkdir app/build/report
$ curl https://raw.githubusercontent.com/orhanobut/buildreport/master/build-report.sh -o app/build/report/build-report.sh
$ sh app/build/report/build-report.sh
```

### Prerequisities
in order to fetch information from html files, [Python 2.7+](https://www.python.org/downloads/)  and [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/#) must be installed in the machine.


# Generated html file
app/build/report/build-report.html

### Licence
```
Copyright 2016 Orhan Obut

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
