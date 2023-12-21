> Une activité ou un fragment est constitué de 2 fichiers : une classe Java et un fichier XML.

> La classe Java appelée `R` permet de référencer les ressources depuis le code Java.

> Le lien entre une classe de type Activity et son XML est effectué via la fonction `setContentView()` . Pour un fragment, c’est au cœur de la fonction `onCreateView()` que la liaison est faite.

Une bonne pratique sur Android consiste à avoir une activité unique qui est le point d’entrée de l’application, et qui visuellement occupe tout l’écran de l’appareil. À cette activité sont ajoutés à tour de rôle des fragments. Un fragment occupe soit tout l’écran de l’application, soit une portion de l’écran.

> Une activité ou un fragment utilise un fichier layout pour pouvoir positionner ses éléments graphiques à l’écran.

> Il y a plusieurs types de layouts permettant d’agencer différemment les éléments graphiques d’un écran : de manière relative aux autres éléments, de manière horizontale, de manière verticale ou en superposition.

> Pour bien affiner la position et l’espace occupé par des éléments à l’écran, il faut utiliser les différents attributs disponibles, par exemple margin  , padding  , layout_gravity  , etc.

> Pour dynamiser un élément graphique déclaré dans un layout, il faut d’abord lui associer un identifiant unique grâce à l’attribut android:id  .

> Pour accéder à un élément graphique déclaré en XML depuis du code Java, la solution la plus simple et la plus populaire s’appelle View Binding.

> Pour utiliser View Binding, il faut tout d’abord l’activer dans le fichier build.gradle  de son application. 

> Avec la fonctionnalité View Binding, pour chaque fichier XML de type layout présent dans le projet, une classe de liaison est générée automatiquement.

> Au sein du code Java, il faut déclarer une variable globale du type de cette classe de liaison. Le nom de cette classe correspond au nom du layout converti en Pascal Case et suffixé par Binding.

> Au sein d’un fragment, il faut spécifier que nous utilisons la classe de liaison pour lier le code XML au code Java dans la fonction onCreateView  . Au sein d’une activité, cela se fait dans la fonction onCreate  .

> Enfin, pour accéder aux éléments d’interface dans le code Java, il suffit de saisir binding.nomDeLelement  , où binding correspond au nom de la variable globale, et nomDeLelement  est l’identifiant d’un élément graphique du layout présent dans l’attribut android:id.

> Il est possible de gérer les attributs des composants dans le fragment (ou l’activité) pour les dynamiser à la suite d’une action de l’utilisateur.

> Pour détecter que l'utilisateur a cliqué sur le bouton, il est nécessaire d'implémenter un View.OnClickListener

> La méthode à utiliser pour détecter un changement de texte dans un EditText  est afterTextChanged()

> Pour créer un nouveau fragment dans un projet, il faut créer la classe Java et le layout XML associé.

> Pour naviguer vers ce fragment, il faut utiliser le FragmentManager  . 

> Le FragmentManager  permet de définir quel fragment ajouter, supprimer ou remplacer, via une transaction.

> Appliquer un patron d’architecture permet de structurer le code d’une application dans le but de le rendre plus lisible, maintenable et testable.

> Il existe différents patrons d’architecture, mais Google préconise aujourd’hui l’architecture MVVM. 

> MVVM signifie Model-View-ViewModel.

> MVVM applique le principe de conception de séparation des préoccupations en structurant le code d’une application en deux couches : Vue et Données, avec une classe de type ViewModel pour faire la liaison entre ces deux couches et personnaliser les données en fonction des besoins de la vue.

> Une classe de type ViewModel expose à la vue les données à afficher, appelé états, et expose des fonctions permettant de manipuler l’état en réponses aux événements qui ont lieu sur l’interface. 

> Pour concevoir la couche Données d’une fonctionnalité, il faut identifier les modèles de données spécifiques à l’application, et créer un objet Java pour chaque modèle.

> Il est d’usage de positionner tous les fichiers relatifs à la couche Données au même endroit, par exemple dans un package data  .

> Les données d’une application peuvent provenir de différentes sources : un fichier, une base de données locale, une API externe, etc.

> Une fois la provenance des données déterminée, la logique permettant d’arbitrer quelles données utiliser se trouve dans une classe de type Repository. 

> Le Repository est le seul à pouvoir accéder aux données.

> Il convient de créer un Repository par type de donnée dont l’application a besoin.

> Il est d’usage de positionner tous les fichiers relatifs à l’interface d’une application au même endroit, par exemple un package nommé ui  . 

> Le ViewModel  contient la logique spécifique à l’affichage d’un écran sous forme d’états et d’événements.

> Google fournit une classe ViewModel  spécifique à Android, qui permet de stocker les variables qu’elle contient en tenant compte des changements de configuration de la vue qui la manipule.

> Google fournit les LiveData  pour exposer les états à la vue sous forme d’observables.

> On initialise un LiveData  via la classe MutableLiveData. Pour lire sa valeur, on utilise la fonction getValue()  ; pour remplacer sa valeur, on utilise la fonction postValue().

> La classe Dialog  permet d’afficher une popup. Pour créer une instance de Dialog  avec un style par défaut, nous pouvons utiliser AlertDialog.Builder.

> Pour utiliser un ViewModel depuis une vue, il faut l’instancier via la classe ViewModelProvider  fournie par Google. 

> Pour observer un LiveData et réagir à ses changements de valeur, il faut appeler la fonction observe().

