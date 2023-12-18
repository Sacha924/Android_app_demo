> Une activité ou un fragment est constitué de 2 fichiers : une classe Java et un fichier XML.
> La classe Java appelée `R` permet de référencer les ressources depuis le code Java.
> Le lien entre une classe de type Activity et son XML est effectué via la fonction `setContentView()` . Pour un fragment, c’est au cœur de la fonction `onCreateView()` que la liaison est faite.

Une bonne pratique sur Android consiste à avoir une activité unique qui est le point d’entrée de l’application, et qui visuellement occupe tout l’écran de l’appareil. À cette activité sont ajoutés à tour de rôle des fragments. Un fragment occupe soit tout l’écran de l’application, soit une portion de l’écran.

> Une activité ou un fragment utilise un fichier layout pour pouvoir positionner ses éléments graphiques à l’écran.
> Il y a plusieurs types de layouts permettant d’agencer différemment les éléments graphiques d’un écran : de manière relative aux autres éléments, de manière horizontale, de manière verticale ou en superposition.
> Pour bien affiner la position et l’espace occupé par des éléments à l’écran, il faut utiliser les différents attributs disponibles, par exemple margin  , padding  , layout_gravity  , etc.
