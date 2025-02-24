---
title: Barre d’outils et Barre d’outils
description: Personnalisation de la barre d’outils et de la barre d’outils
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: e1d6123991ddd8d25f76ee03befeb95f020a9834
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# Personnalisation de la barre d’outils et de la barre d’outils

Pour personnaliser les `topbar` et les `toolbar`, vous pouvez utiliser les identifiants : `topbar` ou `toolbar`, et suivre la même vue, structure du contrôleur.

>[!NOTE]
>
>Depuis la version 2502 de Experience Manager Guides, l’ID **toolbar** a été renommé **barre d’outils de l’éditeur**. Si vous utilisez les versions précédentes, vous pouvez personnaliser la barre d’outils à l’aide de l’identifiant **toolbar** . Nous n’avons plus d’ID en tant que **topbar** et nous disposons désormais d’un **editor_tab_bar**.

Vous trouverez ci-dessous un exemple trivial de personnalisation de barre d’outils. Ici, nous avons supprimé le bouton `Insert Numbered List` et remplacé le bouton `Insert Paragraph` par notre propre composant à l’aide d’un gestionnaire en un clic personnalisé.

>[!TIP]
>
>Étant donné que **editor_toolbar** est conçu pour effectuer le rendu des boutons, son ajout de widgets peut perturber son CSS et sa réactivité. Il est recommandé d’inclure uniquement des boutons ou des composants de base, tels qu’un libellé.

Pour accéder à la fonctionnalité exposée sous l’objet `proxy`, vous devez y accéder à l’aide de `this.getValue`, par exemple pour récupérer une valeur.

Pour la version AEM Guides 2502 et ultérieure, vous pouvez vous reporter à l’exemple ci-dessous pour la personnalisation de la barre d’outils.

```js title = toolbar_customization.js
const toolbarExtend = {
    id: "editor_toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Numbered List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                "component": "button",
                "icon": "textParagraph",
                "variant": "action",
                "quiet": true,
                "title": "Insert Paragraph",
                "on-click": "INSERT_P",
                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                "component": "button",
                "icon": "fileHTML",
                "variant": "action",
                "quiet": true,
                "title": "URL Link Customization",
                "on-click": "openExternalLinkDialog",
                target: {
                key: "title", value: "Insert Bulleted List",
                viewState: VIEW_STATE.REPLACE
                }
            }
        ]
    },
    controller: {
        init: function() {
            console.log(this.getValue("canUndo"))
            this.subscribeAppEvent({
              key: "editor.preview_rendered",
              next: async function (e) {
                console.log(this.getValue("canUndo"))
              }.bind(this)
            })
        },
        INSERT_P(){
            this.appEventHandlerNext("AUTHOR_INSERT_ELEMENT",  "p" )
        },
        openExternalLinkDialog() {
            this.appEventHandlerNext("AUTHOR_INSERT_ELEMENT",
                {
                args: "<xref href='' scope='external' format = 'dita' ></xref>", activeTabId: "conkey_reference"
                }
            )
        }
    }
}
```


Une fois personnalisé, le résultat final peut être affiché comme suit :

![editor_toolbar](imgs/editor_toolbar.png)

Reportez-vous à l’exemple ci-dessous si vous personnalisez la barre d’outils dans AEM Guides version 4.6.x et version précédente.

```js title = toolbar_customization.js
const topbarExtend = {
    id: "toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Element",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Numbered List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Bulleted List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                "component": "button",
                "extraclass": "insert-multimedia",
                "icon": "more",
                "variant": "action",
                "quiet": true,
                "holdAffordance": true,
                "title": "More Insert Options",
                "elementID": "toolbar_insert",
                "on-click": {
                    "name": "APP_SHOW_OPTIONS_POPOVER",
                    "args":{
                        "target": "toolbar_insert",
                        "extraclass": "new_options_buttons",
                        "items": [
                            {
                                "component": "button",
                                "icon": "add",
                                "variant": "action",
                                "quiet": true,
                                "title": "Insert Element",
                                "on-click": "AUTHOR_SHOW_INSERT_ELEMENT_UI"
                            },
                            {
                                "component": "button",
                                "icon": "textParagraph",
                                "variant": "action",
                                "quiet": true,
                                "title": "Insert Paragraph",
                                "on-click": "INSERT_P"
                            },
                            {
                                "component": "button",
                                "icon": "textNumbered",
                                "variant": "action",
                                "quiet": true,
                                "title": "Insert Numbered List",
                                "on-click": "AUTHOR_INSERT_REMOVE_NUMBERED_LIST"
                            },
                            {
                                "component": "button",
                                "icon": "textBulleted",
                                "variant": "action",
                                "quiet": true,
                                "title": "Insert Bulleted List",
                                "on-click": "AUTHOR_INSERT_REMOVE_BULLETED_LIST"
                            },
                            {
                                "component": "button",
                                "icon": "table",
                                "variant": "action",
                                "quiet": true,
                                "title": "Insert Table",
                                "on-click": "AUTHOR_INSERT_ELEMENT",
                            }
                        ]
                    },
                },
                target: {
                    key:"title",value: "Insert Table",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
        ]
    },
    controller: {
        init() {
            console.log(this.proxy.getValue('canUndo'))
            this.proxy.subscribeAppEvent({
                key: "editor.preview_rendered",
                next: async function (e) {
                    console.log(this.proxy.getValue('canUndo'))
                }.bind(this)
            })
        },
        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```

Une fois personnalisé, le résultat final peut être affiché comme suit :

![toolbar](imgs/toolbar.png)


Dans un autre exemple, nous allons créer un bouton de barre d’outils personnalisé qui peut accéder directement aux sous-options souhaitées de **Référence croisée** telles que E-mail, Référence de fichier, Lien web, etc.


```js title = toolbar_customisation.js
const toolbarExtend = {
    id: "editor_toolbar",
    view: {
        items: [
            
                {
                    "component": "button",
                    "icon": "fileHTML",
                    "variant": "action",
                    "quiet": true,
                    "title": "External URL Link",
                    "on-click": "openExternalLinkDialogP",
            
                target: {
                    key:"title",value: "Insert Bulleted List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            }
        ]
    },
    controller: {
        openExternalLinkDialog() {
            tcx.eventHandler.next ("AUTHOR_INSERT_ELEMENT")
            t{
          args:"<xref href='' scope='external' format = 'dita' ></xref>",activeTabId:"conkey_reference"
        }
    }
  }
}
```

Ici, `activeTabId` est l’énumération permettant de sélectionner l’onglet approprié. Par défaut, la sélection de l&#39;onglet Référence croisée ouvre `file_link`. Vous pouvez modifier les valeurs `activeTabId` en `content_reference`, `conkey_reference`, `key_reference`, `file_link`, `web_link` et ` email_link` en fonction des besoins.
