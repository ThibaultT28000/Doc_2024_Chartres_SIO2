# **Commande md**
<br />


## Liste de commande


<details>
<br/>
<summary style="color: red;"><strong><u>Faire un effet déroulant :</u></strong></summary>
<br />
Les balises HTML <strong>< details ></strong> et <strong>< summary ></strong> sont utilisées pour créer des éléments déroulants dans une page web. Voici un résumé de leur utilisation :
<br /><br />
<strong>< details ></strong> : Cette balise HTML englobe le contenu que vous souhaitez rendre déroulant ou caché. Lorsque la page est chargée, le contenu à l'intérieur de <strong>< details ></strong> est généralement masqué par défaut et n'est pas visible.
<br /><br />
<strong>< summary ></strong> : Cette balise HTML est utilisée comme le titre ou le résumé de l'élément déroulant. Le texte à l'intérieur de <strong>< summary ></strong> est généralement affiché comme un lien ou un texte cliquable, qui permet d'ouvrir ou de fermer l'élément déroulant.
<br /><br /><br />
</details>

<details>
<summary style="color: red;"><strong><u>Mettre en gras :</u></strong></summary>
<br />
Utilisation de double astérisques (<strong>**</strong>) ou de double underscores (<strong>__</strong>) :
<br/><br/>
<strong>**</strong>Texte en gras<strong>**</strong> ou <strong>__</strong>Texte en gras<strong>__</strong>
Cette méthode est couramment utilisée et prend en charge le texte en gras à l'intérieur d'une ligne de texte.
<br/><br/>
Utilisation de balises HTML <strong>< strong ></strong> :
<br/><br/>
<strong>< strong ></strong> Texte en gras <strong>< /strong ></strong>
Vous pouvez également utiliser les balises HTML <strong>< strong ></strong> pour mettre en gras le texte. Cette méthode offre un contrôle précis sur le formatage.
<br/><br/>
Utilisation de la balise HTML <strong>< b ></strong> :
<br/><br/>
<strong>< b ></strong> Texte en gras <strong>< /b ></strong>
La balise HTML <strong>< b ></strong> peut également être utilisée pour mettre en gras le texte. Cependant, il est recommandé d'utiliser <strong>< strong ></strong> pour des raisons de sémantique.
<br /><br /><br />
</details>


#### Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.


#### Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
