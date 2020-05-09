# Redux em um projeto React

## Configurando o Redux em um projeto react

``yarn add redux react-redux``

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

```javascript
export default function nomeDaFunction(state = [], action) {
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

```javascript
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

```javascript
function nomeDaFunction() {
    return [];
}

```

A importação do  combineReducer combina todos os reducer em um único reducer.

```javascript
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

```javascript
function Header({ nomeDaFunctionSize }) {
 ...
}

export default connect((state) => ({
  nomeDaFunctionSize: state.nomeDaFunction.length,
}))(Header);

```

## Immer

Uma ferramenta para facilitar a lidar com objetos e arrays que são imutáveis,
como o estado no redux.

``yarn add immer``

Exemplo de uso dentro do reducer:

```javascript
switch (action.type) {
  case '@nomeDoType/ADD':
    return produce(state, (draft) => {
      const index = draft.findIndex((i) => i.id === action.obj.id);

      if (index >= 0) {
        draft[index].amount += 1;
      } else {
        draft.push({
          ...action.obj,
          amount: 1,
        });
      }
    });
    default:
      return state;
  }
}
```

## bindActionCreators()

**Converte actions do redux em props do meu componente.**

:collision: A única coisa que meu componente deve fazer é discaparar uma ação.
:collision: :collision: O redux lida com as validações dentro do reducer.

## Reactotron + Redux

Ajudar a debugar o estado do redux

``yarn add reactotron-react-js reactotron-redux``

Os snapshots é útil para aplicações que o estado do redux deve ter uma action pelo menos.

## mapStateProps()

Melhor lugar para realizar os calculos que vão ser mostrados em tela. No qual, está baseado em
uma informação que está no estado do redux, logo dentro do reducer.

## Redux Saga

Aplica o conceito de middlewares dentro do redux, quando dispara uma action o middleware entra em ação,
como se fosse um pipe para entre a actions e o reducer.

``yarn add redux-saga``

## function*

Asterisco na function é uma funcionalidade do JavaScript que se chama generator, seria como uma async, só que mais
"potente" que o async await, por exemplo, **yield é o await do generator**.

Ela que vai lidar com as chamadas api, seria um passo a mais entre a action e o reducer.

### Métodos

* call() -> responsável para lidar com métodos assíncronos
* put() -> dispara uma action
* all() -> cadastra listener / junta todos os sagas
* takeLatest -> espera a chamada na api, caso o usuário faça muitas chamadas

## Reactotron + Saga

Ajuda a entender melhor o fluxo da aplicação

``yarn add reactotron-redux-saga``

Ao trabalhar com saga, dividimos as actions em duas, são elas: request (ouvida pelo saga) e success.

## Hooks com Redux

### dispatch(action)

* Coloca-se dispatch toda vez que chama uma action no redux.
* Toda vez que precisar acessr o estado do redux usa-se o **useSelector()**
