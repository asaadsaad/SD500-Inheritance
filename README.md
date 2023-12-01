# SD500-Inheritance
Create a class `PersistedStorage` which extends `MyStorage` class (from hw4) and persist all state changes to the hard drive.
* When the class instantiate, read and set the state from the hard disk into memory
* Every time the state changes you will have to update the persisted storage state back into the hard drive.
  
Because Node does not have a native `localStorage` object, you may use the `node-localstorage` package, which you can install using:
1. `npm i node-localstorage`
2. `npm i @types/node-localstorage -D`
  
Check the [package documentation](https://github.com/lmaccherone/node-localstorage) to learn more about the API. Here is an example on how to use it to write/read key/value pairs
```typescript
import { LocalStorage } from 'node-localstorage';

const localStorage = new LocalStorage('./scratch');

localStorage.setItem('name', 'Asaad');
const name = localStorage.getItem('name');
if (name) {
    console.log(name); // Asaad
}

localStorage.setItem('state', JSON.stringify({ name: 'Asaad' }));
const state = localStorage.getItem('state');
if (state) {
    JSON.parse(state); // { name : "Asaad" }
}
```
