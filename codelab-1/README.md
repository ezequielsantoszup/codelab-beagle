# Implementando uma Tabbar com Beagle

Para iniciar o codelab, baixe o projeto da pasta `inicio` e utilizando a IDE InteliJ abra o terminal e digite:

```
$ mvn spring-boot:run
```

### TabBar

Neste codelab, trabalharemos com o componente TabBar.

A TabBar é responsável por definir um menu inferior que permite a navegação entre as telas. Ele exibe as guias correspondentes às diferentes visualizações que podem ser acessadas por meio dele.


### Como funciona


### Propriedades


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

