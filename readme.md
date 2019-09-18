# JSPrintManager implementation for Angular 8

This is the Angular 8 adaptation of the sample of JSPrintManager you can find here:
https://www.neodynamic.com/articles/How-to-print-raw-ESC-POS-commands-from-Javascript/

Example can be found at: ./index.html using ./JSPrintManager

**DISCLAIMER**: I Am Not An Angular Expert, So I Think This Implementation Is The Simplest Way To Use The Documentation Example In An Angular Context. I used the default template provided by running `ng new`

## Highlights
 - No modifications over original JS files
    - printer/src/assets/js/deflate.js 
    - printer/src/assets/js/deflate.js
    - printer/src/assets/js/zip-ext.js
    - printer/src/assets/js/zip.js

 - Declarations added:
    - printer/src/assets/js/JSPrintManager.d.ts
    - printer/src/assets/js/zip.js.d.ts
	
## Things added for Angular version
 - All scripts are stored at: ./printer/src/assets/js/
 - File: ./angular.json: Reference to all scripts at:
    projects.printer.architect.build.options.scripts
    (Lines 30~33)
 - File: ./printer/src/app/app.module.ts: Reference to FormsModule (Line 15)
 - New files for TS declarations:
    - printer/src/assets/js/JSPrintManager.d.ts
        Taken from: 
        https://github.com/neodynamic/JSPrintManager/blob/master/scripts/JSPrintManager.d.ts
    - printer/src/assets/js/zip.js.d.ts
        Taken from:
        https://github.com/slavovojacek/adbrain-typescript-definitions/blob/master/zip.js/zip.js.d.ts

- Html  at: ./printer/src/app/app.component.html
- Logic at: ./printer/src/app/app.component.ts
  Small change: Adding 4 lines and paper cut (check doPrint method. Lines 85~87) for my Epson TM-T20II thermal printer

## How to build
### Minimal reqs
 - Angular 8, npm and typescript (latest versions)

### Build and run
- Restoring packages. Navigate to ./printer and run:
` npm install`
- Build
` ng build`
- Run (to localhost:4200)
` ng serve`