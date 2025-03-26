# L'éditeur terrain

L'éditeur de terrain, également appelé Fieldwork, est une application web optimisée
pour les smartphones et les tablettes.

Elle permet :

- la saisie d'attributs d'accessibilité
- la prise de photos
- l'ajout d'obstacles
- le découpage de tronçons
- la création de notes


## Présentation générale

L'éditeur de terrain repose sur les principes suivants :

- un fond de plan ou imagerie aérienne est affiché, avec la possibilité de
  centrer la carte sur la position courante.
- les éléments du graphe sont affichés par dessus
- les éléments du graphe sont colorés en fonction de leur complétion
- la sélection d'un élément du graphe ouvre un formulaire permettant la
  saisie des attributs et la prise de photos
- un appui long active les action supplémentaires (création d'obstacle,
  création de note...)


!!! info
    
    Les modifications sont envoyées automatiquement à chaque sauvegarde.
    Cependant en cas de perte de réseau, elles sont conservées et sont envoyées
    soit manuellement, soit automatiquement lors du retour du réseau.


## Connexion au compte Accèslibre Mobilités

L'affichage du graphe et l'envoi des modifications nécessite d'être connecté à son
compte Accèslibre Mobilités. Pour se connecter, ouvrir le menu en haut à gauche et
cliquez sur "Connexion"

![Capture d'écran du menu principal non connecté](../../img/fieldwork_logged_out.png)
![Capture d'écran du menu principal connecté](../../img/fieldwork_logged_in.png)


## Saisie d'attributs

Un clic sur un élément du graphe permet sa sélection et l'ouverture d'un menu. Choisir "Saisie"
pour ouvrir le formulaire de saisie.

![Capture d'écran du menu principal de sélection](../../img/fieldwork_select_menu.png)
![Capture d'écran du formulaire de saisie](../../img/fieldwork_attrs_form_expanded.png)

Si besoin de voir la carte lors de la saisie, cliquez sur le chevron en haut du formulaire
permet de le réduire à la moitié de l'écran.

![Capture d'écran du formulaire réduit](../../img/fieldwork_attrs_form_collapsed.png)


## Sauvegarder les modifications

Lorsqu'un champ est modifié sur le formulaire, deux actions sont possibles :

- sauvegarder les modifications (bouton bleu)
- annuler les modifications (bouton gris)

!!! info

    Si le réseau est défaillant au moment de la sauvegarde, la modification est conservée
    pour être appliquée plus tard. Le nombre de modifications en attente est affiché en haut de
    l'écran. Un clic sur le bouton permet de les synchroniser manuellement.

![Capture d'écran du formulaire avec modifications](../../img/fieldwork_attrs_form_save.png)
![Capture d'écran du bouton de synchronisation](../../img/fieldwork_synchronize_pending.png)

Lorsque tous les champs sont saisis sur un élément du graphe, celui-ci passe en bleu
sur la carte.


## Copie d'attributs

En saisissant "Copie" dans le menu d'édition, il est proposé de sélectionner sur la carte
l'élément dans lequel les attributs doivent être copiés. Il doit s'agit d'un élément semblable
(nœud ou tronçon).

L'élément choisi (en bleu) verra ses attributs vides remplis à partir du premier
élément sélectionné (en rouge) et son formulaire d'édition s'ouvrira pou permettre
de modifier avant sauvegarde.

![Capture d'écran du menu de copie](../../img/fieldwork_copy_menu.png)
![Capture d'écran du formulaire après copie](../../img/fieldwork_copy_form.png)


## Création de nœuds

Un appui long sur la carte permet d'ouvrir le menu de création de nœuds. Lorsque celui-ci
est ouvert, un simple clic permet de repositionner le point.

Lorsque le point est situé sur un tronçon, celui-ci est surligné en bleu et le nouveau
nœud sera intégré au tronçon.

![Capture d'écran du menu d'ajout de nœud isolé](../../img/fieldwork_create_point_menu.png)
![Capture d'écran du menu d'ajout de nœud connecté](../../img/fieldwork_create_vertex_menu.png)

Dans le second cas, une option "Couper le cheminement" est ajouté.


## Répondre aux notes

Les notes sont affichées sur la carte sous la forme de `?`. Un clic sur la note ouvre directement
son formulaire d'édition.

Le formulaire permet de consulter l'historique, d'ajouter un commentaire et une photo,
ainsi que de clôturer la note si nécessaire.

![Capture d'écran d'une note sur la carte](../../img/fieldwork_map_note.png)
![Capture d'écran du formulaire d'une note](../../img/fieldwork_note_form.png)

