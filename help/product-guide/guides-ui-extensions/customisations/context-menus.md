---
title: Menus contextuels
description: Personnalisation des menus contextuels
role: User, Admin
exl-id: 25aa76dd-ef05-41ed-b980-14bbc1626059
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 1%

---

# Personnalisation des menus contextuels

Les menus contextuels suivants peuvent être personnalisés :

- `file_options`
contrôleurs :
   - Vue Carte : `ditamap_viewer_controller`
   - Panneau Référentiel : `repository_panel_controller`
   - Panneau Favoris : `collection_tree_controller`
   - Liens de référence de propriétés de fichier : `file_references_links_controller`
   - Panneau de recherche du référentiel : `repository_search_controller`
   - Objet Schéma Panneau : `subject_scheme_tree_controller`

- `folder_options`
contrôleurs :
   - Panneau Référentiel : `repository_panel_controller`
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

Désormais, un `controller id` est associé à chaque menu contextuel. Ce contrôleur gère la fonctionnalité `on-event` pour les différentes options de menu contextuel.

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
            const path  = this.getValue('selectedItems')[0].path
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
2. `contextMenuWidget` est utilisé pour définir le `widget id` ou le `component` qui appelle le menu contextuel et gère le `events`.

Le reste reste identique, où `view` est utilisé pour définir les éléments, `target` identifie l’emplacement où remplacer, ajouter ou ajouter en préfixe l’option et le contrôleur `contextMenuWidget` gère les événements `on-click`.
