---
title: Menus contextuels
description: Personnalisation des menus contextuels
source-git-commit: 5962414dfc065543b946cac1468a5f62013073cf
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 1%

---


# Personnalisation des menus contextuels

Les menus contextuels suivants peuvent être personnalisés :

- `file_options`
contrôleurs :
   - Vue Carte : `ditamap_viewer_controller`
   - Repository Panel : `repository_panel_controller`
   - Panneau Favoris : `collection_tree_controller`
   - Liens de référence des propriétés du fichier : `file_references_links_controller`
   - Panneau de recherche du référentiel : `repository_search_controller`
   - Objet Schéma Panneau : `subject_scheme_tree_controller`

- `folder_options`
contrôleurs :
   - Repository Panel : `repository_panel_controller`
   - Panneau Favoris : `collection_tree_controller`

- `collection_options`
contrôleurs :
   - Panneau Favoris : `collection_tree_controller`

- `map_view_options`
contrôleurs :
   - Vue Carte : `ditamap_viewer_controller`

- `baseline_panel_menu`
contrôleurs :
   - Panneau de ligne de base : `baseline_panel`

- `preset_item_menu`
contrôleurs :
   - Panneau de paramètres prédéfinis : `preset_panel`

Vous pouvez également créer votre propre menu contextuel en définissant un nouvel identifiant unique.

Désormais, chaque menu contextuel comporte une `controller id` qui lui est associée. Ce contrôleur gère la variable `on-event` fonctionnalité des différentes options du menu contextuel

Prenons un exemple pour comprendre

```js title=customise_context_menu.js"
const fileOptions = {
    id: "file_options",
    contextMenuWidget: "repository_panel",
    view: {
            items: [
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Delete",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Edit",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    "displayName": "Download",
                    "data": {
                      "eventid": "downloadFile"
                    },
                    "icon": "downloadFromCloud",
                    "class": "menu-separator",         
                    target: {
                        key:"displayName",value: "Duplicate",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
            ]

    },

    controller: {
        downloadFile(){
            const path  = this.model.selectedItem.path
            this.loader.loadDitaFile(path).then((file) => {
              function download_file(name, contents) {
                const mime_type = "text/plain";
        
                const blob = new Blob([contents], {type: mime_type});
        
                const dlink = document.createElement('a');
                dlink.download = name;
                dlink.href = window.URL.createObjectURL(blob);
                dlink.onclick = function() {
                    // revokeObjectURL needs a delay to work properly
                    const that = this;
                    setTimeout(function() {
                        window.URL.revokeObjectURL(that.href);
                    }, 1500);
                };
        
                dlink.click();
                dlink.remove();
            }
            download_file(path,file.xml)
            });
          }
    }
}
```

Maintenant, comprenons ce que ce code fait.

1. `id` est utilisé pour identifier le menu contextuel que nous voulons personnaliser.
2. `contextMenuWidget` est utilisé pour définir la variable `widget id` ou le `component` qui appelle le menu contextuel et gère l’événement `events`.

Le reste reste est le même, où `view` est utilisé pour définir les éléments, `target` identifie où remplacer, ajouter ou ajouter en préfixe l’option et l’ `contextMenuWidget` Le contrôleur gère les `on-click` événements .
