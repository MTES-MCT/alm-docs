# Imports

Accèslibre Mobilités propose plusieurs modules d'imports de données, qui permettent d'initialiser le [graphe piéton](../web/graphe.md) avec les données dont vous disposez déjà en interne.

La phase d'import est facultative : il est possible de créer l'intégralité des données dans Accèslibre Mobilités sans recourir à des imports.
Cependant, lorsque des données sont préexistantes, il est pertinent de s'appuyer dessus afin :

- de ne pas réinventer la roue et d'éviter de refaire un travail de collecte et de création de données qui a déjà été réalisé
- de s'appuyer sur des identifiants communs, pour faciliter l'interopérabilité des données et la coopération entre les services

Accèslibre Mobilités propose trois catégories d'imports :

* [l'import de données transport](transport/index.md)
* [l'import de données de cheminement](cheminement/index.md)
* [l'import d'ERP](ERP/index.md)

Il est possible de réaliser plusieurs imports (par exemple un import de données transport et un import d'ERP), et également plusieurs imports d'une même catégorie (par exemple un import des données transport du réseau urbain, puis un import des données transport du réseau départemental).

!!! info "Remarque"

    L'import n'est pas une solution de synchronisation : cela signifie que si vous commencez à créer des arrêts dans l'éditeur web, puis que vous realisez un import de données de transport, certains arrêts seront présents en double, et il vous faudra les dédupliquer manuellement dans l'éditeur web.

    De même, si vous réalisez deux fois de suite le même import, les données seront importées deux fois et présentes en doublon.

    En conséquence, il est vivement conseillé d'étudier les jeux de données dont vous disposez et leur qualité (de positionnement, attributaire, etc) puis de réaliser les imports au début du projet uniquement.

Enfin, en complément des aspects techniques, des questions de propriété privée et de licence sont également à considérer avant de réaliser un import.

En effet, les données créées dans Accèslibre Mobilités ont vocation à être publiées en open data. Cela interdit a priori l'utilisation et l'import de données privées qui n'ont pas vocation à être mises à disposition du public (par exemple données achetées à des opérateurs de mobilité type Waze, Strava).

Les données de votre SIG ou créées par vos services sont a priori utilisables dans Accèslibre Mobilités, mais il vous revient de vous assurer qu'elles sont effectivement diffusables.

De plus, la licence ou les conditions d'utilisation des données importées peuvent avoir un impact sur la licence finale de publication des données d'Accèslibre Mobilités. Le cas typique est la présence d'une clause d'attribution (présente dans les données sous licence ouverte et sous licence ODbL), qui impose d'afficher le nom du fournisseur de données dans les données finales.

Plus d'information sur la page dédiée aux [licences](../publish/licence.md)
