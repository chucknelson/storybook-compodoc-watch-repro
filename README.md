# Storybook Compodoc Watch Reproduction Project

This was created for the Github issue [storybook > Addon-docs: Dynamically update props tables for Angular #8672](https://github.com/storybookjs/storybook/issues/8672).

Do the following to see the webpack reload issue:
1. Clone this repo
2. Run `yarn` to install packages
3. Run `yarn storybook`, which will start storybook and compodoc in watch mode.
4. When the Storybook UI shows up in your browser, view the Button > Primary story.
5. Open the browser console so you can see errors/warnings.
6. Make a simple change to the Button component - for example, add a new size value like "supersize" in `src/stories/button.component.ts`:
```js
...
@Input()
size: 'small' | 'medium' | 'large' | 'supersize' = 'medium';
...
```
7. Save the change, watch compodoc and storybook rebuild, and see the following warning in the browser console:
```
Ignored an update to unaccepted module ./documentation.json -> ./.storybook/preview.js -> ./.storybook/preview.js-generated-config-entry.js
```

To see the new size you added, you'll need to manually refresh the browser.

---

# Angular Boilerplate

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 12.2.4.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
