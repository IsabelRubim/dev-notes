# Redux em um projeto React

## Configurando o Redux em um projeto react

```
yarn add redux react-redux

```
Todos os aquivos relacionado ao redux ficam em uma pasta dentro da src chamada store.

Função dispatch é um método do redux no qual ele dispara.

O que isso dispara você deve está se perguntando...

Então, este método dispara uma action que deve conter um type e o objeto 
(esses são os dois elementos que compõe uma action).

Outro ponto, quando se usa o método dispatch, todos os reducer da aplicação são
ativados.

Logo, todo reducer recebe por padrão duas variáveis, são elas (state, action).

* state: é o estado anterior da modificação, isto é antes que a action enviar uma modificação.

:warning: O estado do redux é imutável.

reducer.js exemplo: 

```
export default function nomeDaFunction(state = [], action) {
  console.log(state);
  switch (action.type) {
    case 'NOME_DO_TYPE':
      return [...state, action.object];
    default:
      return state;
  }
}

```

A importação do Provider deixa o store da aplicação disponível para todos os
componentes.

App.js exemplo:

```
import { Provider } from 'react-redux';

function App() {
  return (
    <Provider store={store}>
      <BrowserRouter>
        <Header />
        <Routes />
        <GlobalStyle />
      </BrowserRouter>
    </Provider>
  );
}

export default App;

```

## Reducer

```
function nomeDaFunction() {
    return [];
}

```
A importação do  combineReducer combina todos os reducer em um único reducer.

```
import { combineReducers } from 'redux';

import nomeDaFunction from './folderDoReducer/reducer';

export default combineReducers({
  nomeDaFunction,
});

```

A função connect dentro de um componente, serve para conectar o estado do redux,
com o redux em si. Ela também retorna uma outra função que é usada para passar 
o componente, com isso o componente pode receber o estado do redux.

Exemplo:

```

function Header({ nomeDaFunctionSize }) {
 ...   
}

export default connect((state) => ({
  nomeDaFunctionSize: state.nomeDaFunction.length,
}))(Header);

```