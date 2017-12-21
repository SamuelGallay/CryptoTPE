---
title: Voici une page d'exemple
permalink: /exemple/
---
# Comment écrire sur la page

### Petit titre

Chaque page du site est écrite dans un fichier ".md".
Pour lire la documentation de la syntaxe "kramdown" (une variante de "Markdown"), allez [**ici**](https://kramdown.gettalong.org/syntax.html) ! 

N'hésitez pas à lire le code de cette page, le fichier "/pages/exemple.md", on peut y voir tout ce qui est intéressant de savoir faire pour une page web ([liens](), **gras**, *italique*, titres...).

## Créer une nouvelle page
Il faut ajouter un en-tête comme celui-ci.

~~~ Markdown
---
title: Voici une page d'exemple
permalink: /exemple/
---
~~~

Le titre est le titre de la page et permalink est l'adresse de la page dans le site final. Le permalink est utile pour creer des liens sur cette page.

## Créer des liens

Pour créer un [lien](#) :

~~~
[nom du lien](adresse ex: https://kramdown.gettalong.org/syntax.html)
~~~

Si on veut faire un lien sur une autre page du site, le plus sûr est : 

~~~
[nom du lien]({{ "/permalink/" | relative_url }})
~~~

## Blocs de code

Si vous avez l'esprit réveillé, vous avez vu que j'ai mis toutes les commandes dans des blocs de code

~~~
Tels que celui-ci
~~~

Il suffit pour cela d'entourer le code de trois ~ en haut et en bas !

# Histoire de la Cryptographie !!!
Respecte les classiques **man** ! 

## Welcome to GitHub Pages **Yeah**

[Un Lien !](Page1.html)

You can use the [editor on GitHub](https://github.com/SamuelGallay/CryptoTPE/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/SamuelGallay/CryptoTPE/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

## Voici une première page de tests !!!

* *italic* 
* **gras** 


1. un
2. deux
3. trois  


Voici une citation célèbre
> Quand l'appetit va, tout va !

## Formules
$$
a^2 + b^2 = c^2
$$

$$
\begin{align*}
  & \phi(x,y) = \phi \left(\sum_{i=1}^n x_ie_i, \sum_{j=1}^n y_je_j \right)
  = \sum_{i=1}^n \sum_{j=1}^n x_i y_j \phi(e_i, e_j) = \\
  & (x_1, \ldots, x_n) \left( \begin{array}{ccc}
      \phi(e_1, e_1) & \cdots & \phi(e_1, e_n) \\
      \vdots & \ddots & \vdots \\
      \phi(e_n, e_1) & \cdots & \phi(e_n, e_n)
    \end{array} \right)
  \left( \begin{array}{c}
      y_1 \\
      \vdots \\
      y_n
    \end{array} \right)
\end{align*}
$$

## Images

![cervin]({{ "/assets/cervin.jpg" | relative_url }})

![alberti]({{ "/assets/cadran.jpg" | relative_url }} ){:width="300px"}

## Code 
~~~
def what?
  42
end
~~~
{: .language-ruby}

~~~
#include <iostream>

using namespace std;

int main()
{
	cout << "Hello World" << endl;
}
~~~
{: .language-c++}
En plus il y a de la coloration syntaxique (même pour le *C++* ! ).

# Les tableaux

C'est de loin ce qu'il y a de plus chiant à faire :

On peut essayer d'utiliser un "ASCII Table Generator" comme [celui-ci](https://www.tablesgenerator.com/markdown_tables#).


|       | A | D | F | G | V | X |
|-------|---|---|---|---|---|---|
| **A** | V | J | Y | Q | 1 | R |
| **D** | D | U | 2 | N | I | H |
| **F** | 9 | O | F | 6 | V | 8 |
| **G** | E | T | P | B | G | Z |
| **V** | X | A | 7 | 0 | 5 | M |
| **X** | K | 3 | C | S | L | 4 |

modif' par Manon
modif' par **Hugo**
