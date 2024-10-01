## steep 1
```
install nodejs
```
virifie the installation and see if you hyave the last configuration

## steep 2
```
mkdir directory name
```
## steep 3
```
mkdir other name derictory
```
be into this last and run
```
sudo npx create-react-app frontend
```

### creat a componnets
To create a simple "Hello World" React component using `nano`, follow these steps:

1. Open the terminal and navigate to your project folder.
2. Use `nano` to create a new file called `redux.js`:

   ```bash
   sudo nano src/redux.js
   ```

3. Inside the file, write the following code for your "Hello World" component:

   ```javascript
   import React from 'react';

   const Redux = () => {
     return (
       <div>
         <h1>Hello World</h1>
       </div>
     );
   };

   export default Redux;
   ```

4. Save the file by pressing `CTRL + O`, then `Enter` to confirm. Exit `nano` by pressing `CTRL + X`.

5. To use this component in your application, open your `App.js` file and import the `Redux` component:

   ```javascript
   import React from 'react';
   import Redux from './redux';

   function App() {
     return (
       <div className="App">
         <Redux />
       </div>
     );
   }

   export default App;
   ```
## redux counte
Bien sûr ! Voici un projet très simple en **React et Redux** que tu peux réaliser pour te préparer à un entretien : un **compteur** avec des boutons pour incrémenter et décrémenter une valeur.

### Objectif :
- Créer un compteur qui commence à 0.
- Lorsque tu cliques sur le bouton "+", le compteur augmente de 1.
- Lorsque tu cliques sur le bouton "-", le compteur diminue de 1.

C'est un projet très simple qui te permettra de montrer que tu maîtrises les bases de **Redux** et **React**.

---

### Étape 1 : Installer Redux et React-Redux

Dans ton projet React, commence par installer **Redux** et **React-Redux** en utilisant cette commande :

```bash
npm install redux react-redux
```

### Étape 2 : Créer le store Redux

1. Crée un fichier `store.js` dans ton dossier `src` :

```bash
nano src/store.js
```

2. Ajoute le code suivant pour définir ton **state initial** et les **actions** du compteur :

```javascript
import { createStore } from 'redux';

// État initial du compteur
const initialState = {
  count: 0
};

// Réducteur (reducer) pour gérer les actions
const counterReducer = (state = initialState, action) => {
  switch (action.type) {
    case 'INCREMENT':
      return {
        ...state,
        count: state.count + 1
      };
    case 'DECREMENT':
      return {
        ...state,
        count: state.count - 1
      };
    default:
      return state;
  }
};

// Créer le store Redux
const store = createStore(counterReducer);

export default store;
```

### Étape 3 : Créer le composant Counter

1. Crée un fichier `Counter.js` dans le dossier `src` :

```bash
nano src/Counter.js
```

2. Ajoute ce code pour créer un composant simple qui affiche le compteur et les boutons pour l'incrémenter ou le décrémenter :

```javascript
import React from 'react';
import { useSelector, useDispatch } from 'react-redux';

const Counter = () => {
  const count = useSelector((state) => state.count);  // Récupère le state du store
  const dispatch = useDispatch();  // Pour envoyer des actions au store

  const increment = () => {
    dispatch({ type: 'INCREMENT' });
  };

  const decrement = () => {
    dispatch({ type: 'DECREMENT' });
  };

  return (
    <div>
      <h1>Compteur : {count}</h1>
      <button onClick={increment}>+</button>
      <button onClick={decrement}>-</button>
    </div>
  );
};

export default Counter;
```

### Étape 4 : Connecter Redux à React

1. Dans `index.js`, il faut connecter le store Redux à ton application React en utilisant le composant `Provider` de **react-redux**.

2. Ouvre le fichier `index.js` :

```bash
nano src/index.js
```

3. Modifie le fichier comme ceci :

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import { Provider } from 'react-redux';  // Importer Provider
import store from './store';  // Importer le store Redux

ReactDOM.render(
  <React.StrictMode>
    <Provider store={store}>
      <App />
    </Provider>
  </React.StrictMode>,
  document.getElementById('root')
);
```

### Étape 5 : Utiliser le composant Counter

1. Ouvre le fichier `App.js` :

```bash
nano src/App.js
```

2. Ajoute le composant `Counter` dans l'application principale :

```javascript
import React from 'react';
import Counter from './Counter';  // Importer le composant Counter

function App() {
  return (
    <div>
      <h1>Mon compteur avec Redux</h1>
      <Counter />
    </div>
  );
}

export default App;
```

### Étape 6 : Lancer le projet

Pour voir ton application en action, lance le serveur de développement avec la commande suivante :

```bash
npm start
```

### Résultat attendu :
Lorsque l'application se charge dans le navigateur, tu verras un compteur qui commence à 0, avec deux boutons `+` et `-`. En cliquant sur `+`, le compteur augmente de 1, et en cliquant sur `-`, il diminue de 1.

---

Ce projet est **très simple** et te permettra de montrer que tu comprends les concepts de base de **Redux** (state, actions, reducers) ainsi que l'intégration de **Redux** avec **React** en utilisant des hooks comme `useSelector` et `useDispatch`.

C'est une excellente démonstration pour un entretien ! 😊


6. Finally, run your project with:

   ```bash
   npm start
   ```

This will display "Hello World" on your React app page! Let me know if you need any more help.
