# Angular PWA
This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 7.2.3.

## Steps to create the application
1. Global installation of the Angular CLI: 

    `$ npm install @angular/cli@7.2.3 --global` or `$ npm i @angular/cli@7.2.3 -g`

2. Create a new angular default application:

    `$ ng new angular-pwa`

3. Open the project folder: 

    `$ cd .\angular-pwa\`

4. Adding a service worker to your project: 

    `$ ng add @angular/pwa --project=angular-pwa`

    More information:
    - [Getting started with service workers](https://angular.io/guide/service-worker-getting-started)

5. Install a lite-server:

    `$ npm install lite-server --save-dev`

6. Add NPM run script to the file `package.json`:

    `"start:prod": "ng build --prod && lite-server --baseDir dist/angular-pwa"`

7. Start the angular application:

    `$ npm run start:prod`

## Informing the user about a new version of the application
1. Add a version number to the environment files:

    `version: '1.0.0'`

2. Add service-worker to the file `app.component.ts`:

    `import { SwUpdate } from '@angular/service-worker';`

3. Add the following code to the file `app.component.ts`:

    ```ts
    ngOnInit(): void { 
        if (this.swUpdate.isEnabled) {
            this.swUpdate.available.subscribe(() => {
                if (confirm('A new version of the application is available. Do you want to load the new version?')) {
                    window.location.reload();
                }
            });
        }
    }
    ```


---
## More helpful links
- [Developing a PWA Using Angular 7](https://dzone.com/articles/developing-pwa-using-angular-7)
