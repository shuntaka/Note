## setup Google Apps Script project
---
### authenticate for Google Drive API
[official Doc](https://github.com/danthareja/node-google-apps-script#quickstart)
-   create client credential key for Google Drive API
-   download & store the client credential key to anywhere in the local computer
-   authenticate the client
-   .gapps will be created under ~/
-   once this process is done, the local computer gets authenticated & the same
    process is not necessary when starting a new project

---
### create a Google Apps Script project
>[here](https://developers.google.com/apps-script/managing_projects)

-   navigate to
    create > others > + add apps
-   search for 'script'
-   add Google Apps Script
-   navigate to
    create > others > Google Aopps Script
-   record the projectID for the project from the URL
    >confusing it is, but this is NOT project-id shown in 'Cloud Platform Project' window

    **_e.g._**
    <pre>
    https://script.google.com/d/abcdef1234/edit?usp=drive_web
    </pre>
---
### scafold the project
>[scafolding tool](http://dackdive.hateblo.jp/entry/2017/05/01/202717)


-   git clone [this repository](https://github.com/zaki-yama/webpack-google-apps-script-template.git)
-   install dependencies
-   link the project to the Google Apps Script project.

-   on completion of the linking, gapps.config.json will be created


## create mail-reply script for a concert

---
### copy the script
from the last project


### add several columns to the spreadsheet
-   firstly, add "price" colum
-   secondly, add "isEmailSent" colum

---
### edit the consts
-   SPREADSHEET_ID
    -   the string between ...d/ and /edit#...
    -   e.g.
```
if the URL is
https://docs.google.com/spreadsheets/d/1234abcdef/edit#gid=12345

spreadsheet ID is
1234abcdef
```

-   consts - keys
-   consts - for email body template
-   consts - for email title template
-   consts - for calculating ticket price
