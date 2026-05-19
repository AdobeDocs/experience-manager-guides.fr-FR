---
title: Menus contextuels
description: Personnalisation des menus contextuels
role: User, Admin
exl-id: 25aa76dd-ef05-41ed-b980-14bbc1626059
TQID: https://experienceleague.adobe.com/TJyqos515-hGMn2S0fG4Nqs-kKz2MDF7cM40PSuZFMY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 154
ht-degree: 1%

---

# Personnalisation des menus contextuels

Les menus contextuels suivants peuvent être personnalisés :

- `file_options`
contrôleurs :
   - Vue Carte : `ditamap_viewer_controller`
   - Panneau Référentiel : `repository_panel_controller`
   - Panneau Favoris : `collection_tree_controller`
   - Liens de référence des propriétés du fichier : `file_references_links_controller`
   - Panneau de recherche de référentiel : `repository_search_controller`
   - Panel du schéma d&#39;objet : `subject_scheme_tree_controller`

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

Désormais, chaque menu contextuel est associé à un `controller id`. Ce contrôleur gère la fonctionnalité `on-event` pour les différentes options du menu contextuel

Prenons un exemple pour comprendre

```js title=customise_context_menu.js"
const loadDitaFile = (filePath, uuid) =>{
  return $.ajax({
    type: 'POST',
    url: '/bin/referencelistener',
    data: {
        operation: 'getdita',
        path: filePath,
        type: uuid ? 'UUID' : 'PATH',
        cache: false,
    },
  })
}

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
            loadDitaFile(path).then((file) => {
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

Maintenant, comprenons ce que fait ce code.

1. `id` est utilisé pour identifier le menu contextuel que nous voulons personnaliser.
2. `contextMenuWidget` est utilisé pour définir le `widget id` ou le `component` qui appelle le menu contextuel et gère le `events`.

Le reste reste reste le même, où `view` est utilisé pour définir les éléments, `target` identifie où remplacer, ajouter ou ajouter l’option et le contrôleur de `contextMenuWidget` gère les événements `on-click`.
