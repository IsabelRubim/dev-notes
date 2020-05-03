# Hooks

* **useState()** - cria estado nas funções, sem escrever ela no formato de classe.

Exemplo:

```
const [o estado em si, uma função que serve para atualizar o estado] = useState(Valor inicial para o estado);

```

:warning: Para cada tipo de informação dentro do componente vai ter um estado separado.

* **useEffect()** - sobrepõe os métodos de ciclo de vida

Exemplo:

```
useEffect(() => 
  função é executada toda vez que a variável (no array de dependências) monitorada é alterada, 
[array de dependências]);

```
* **useMemo()** - indicado quando se faz um tipo de cálculo mais complexo no componente, 
retornando um valor único.

* **useCallback()** - muito útil, pois evita o uso de memória desnecessário, porque ela só vai
ser criada na memória do computador quando as variáveis das dependências sofrer alguma alteração.