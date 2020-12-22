# Implementando uma Tabbar com Beagle

Para iniciar o codelab, baixe o projeto da pasta `inicio` e utilizando a IDE InteliJ abra o terminal e digite:

```
$ mvn spring-boot:run
```

### TabBar

Neste codelab, trabalharemos com o componente TabBar.

### Como funciona

A TabBar é responsável por definir um menu inferior que permite a navegação entre as telas. Ele exibe as guias correspondentes às diferentes visualizações que podem ser acessadas por meio dele.

### Propriedades

|Atributo   | Tipo   | Obrigatório  | Definição   |   
|---|---|---|---|
| `items`  | `TabBarItem`  | Sim  | Recebe uma lista de `TabBarItems` que definirá as tabs do TabBar  |   
| `styleId`  | `String`   | Não  | O styleId identifica um estilo a ser aplicado na `TabBar`  |   
| `currentTab`  | `Bind<Int>`   | Não   | Número inteiro que identifica qual `TabBarItem` foi selecionado  |   
| `onTabSelection`  | `List<Action>`  | Não   | Lista de ações que serão realizadas quando um `TabBarItem` é selecionado. Ele pode ser usado para carregar uma view específica de acordo com o `TabBarItem` selecionado.|   

#### TabbarItem

| Atributo  | Tipo  | Obrigatório  | Definição  |
|---|---|---|---|
|`title`   |  `String` |  não | Exibe o texto no título do item da TabBar. Se não for declarado ou se estiver definido como nulo, não aparecerá na tela. A tab não será exibida.  |
| `icon`  | `Path`  | não  | Exibe uma imagem local como um ícone no item da TabBar. Se não for declarado ou estiver definido como nulo, não aparecerá na tela.   |



### Exemplo
```json
{
    "_beagleComponent_": "beagle:screenComponent",
    "child": {
        "_beagleComponent_": "beagle:container",
        "children": [
            {
                "_beagleComponent_": "beagle:tabBar",
                "items": [
                    {"title": "Tab 1"},
                    {"title": "Tab 2"}
                ],
                "styleId": "TabBarStyle",
                "onTabSelection": [
                    {
                        "_beagleAction_": "beagle:setContext",
                        "contextId": "contestTabId",
                        "value": "@{onTabSelection}"
                    }
                ]
            },
            {
                "_beagleComponent_": "beagle:pageView",
                "children": [
                    {
                        "_beagleComponent_": "beagle:text",
                        "text": "Tab 1"
                    },
                    {
                        "_beagleComponent_": "beagle:text",
                        "text": "Tab 2"
                    }
                ],
                "currentPage": "@{contestTabid}"
            }
        ],
        "context": {
            "id": "contestTabid",
            "value": 0
        }
    }
}
```

