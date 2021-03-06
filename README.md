# the-catalin notes:
Detailed issue that is fixed in this repo: https://stackoverflow.com/questions/60741145/sharding-to-multiple-databases-with-angularfire2<br><br>
Original angularfire repo is this https://github.com/angular/angularfire, branch 2.0.0-beta.8<br>
Was installed previously by running<br>
npm i --save angularfire@2.0.0-beta.8<br><br>
The contents of this repository are obtained by running locally these commands:<br>
git clone https://github.com/the-catalin/angularfire<br>
cd angularfire<br>
git checkout sharding-fix<br>
yarn install<br>
npm run build_npm<br><br>
The build result was taken from dist folder and put here, in this repo.<br><br>
Then, it can be used in the project like this:<br>
npm i --save the-catalin/angularfire2<br>
which results in<br>
"angularfire2": "github:the-catalin/angularfire2"<br>
in package.json file<br>

<p align="center">
  <h1 align="center">AngularFire2</h1>
  <p align="center">The official library for Firebase and Angular 2</p>
</p>

[![Build Status](https://travis-ci.org/angular/angularfire2.svg?branch=master)](https://travis-ci.org/angular/angularfire2) [![Join the chat at https://gitter.im/angular/angularfire2](https://badges.gitter.im/angular/angularfire2.svg)](https://gitter.im/angular/angularfire2?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Status: Beta

## What is AngularFire2?

- **Observable based** - Use the power of rxjs, Angular 2, and Firebase.
- **Realtime bindings** - Synchronize database collections as objects or lists.
- **Authentication** - Monitor authentication state in realtime.

#### Quick links
[Contributing](https://github.com/angular/angularfire2/blob/master/CONTRIBUTING.md)

[Plunker Template](http://plnkr.co/edit/8yY4tH?p=preview) - Requires to set your Firebase credentials in `app.module.ts`.

## Install

```bash
npm install firebase angularfire2 --save
```

## Example use:

```ts
import {Component} from '@angular/core';
import {AngularFire, FirebaseListObservable} from 'angularfire2';

@Component({
  selector: 'project-name-app',
  template: `
  <ul>
    <li *ngFor="let item of items | async">
      {{ item.name }}
    </li>
  </ul>
  `
})
export class MyApp {
  items: FirebaseListObservable<any[]>;
  constructor(af: AngularFire) {
    this.items = af.database.list('/items');
  }
}
```

## Developer Guide
If you want to get started quickly on building with AngularFire2, check out our
5 step developer guide that will teach you everything you need to know to be 
productive with AngularFire2.

1. [Installation & Setup](docs/1-install-and-setup.md)
2. [Retreiving data as objects - FirebaseObjectObservable](docs/2-retrieving-data-as-objects.md)
3. [Retreiving data as lists - FirebaseListObservable](docs/3-retrieving-data-as-lists.md)
4. [Querying lists](docs/4-querying-lists.md)
5. [User Authentication - FirebaseAuthentication](docs/5-user-authentication.md)
6. [Using AngularFire2 with Ionic 2](docs/Auth-with-Ionic2.md)
