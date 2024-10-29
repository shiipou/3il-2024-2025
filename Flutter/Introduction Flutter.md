## Flutter qu'est-ce que c'est ?

Flutter est un framework open-source développé par Google, qui permet de créer des applications natives pour plusieurs plateformes à partir d'une seule base de code et peut fournir des applications à l'apparence et au comportement identiques, quel que soit l'appareil ou le système d’exploitation. Avec Flutter, les développeurs peuvent créer des applications pour Android, iOS, Windows, macOS, Linux, ainsi que des applications web, le tout en utilisant le langage de programmation Dart.

## Mais qu'est-ce que dart ?

Dart, le language de programmation derrière le Framework Flutter est aussi un projet Open-Source de Google conçu pour le développement d'applications web et mobiles.
Il visait a remplacer le JavaScript dans les navigateurs web par un language compilé **Just-In-Time (JIT)** et **Ahead-Of-Time (AOT)** plus moderne centré autours de la Programmation Objet tout en restant simple a apprendre pour tous types de profiles.

> [!info] 
> - **JIT** *(utilisé pendant le développement avec Flutter)* permet le hot reload, une fonction de mise à jour rapide du code pour voir les changements en temps réel.
> - **AOT** est utilisé pour la version finale de l’application, ce qui permet de compiler directement en code machine natif pour une meilleure performance.

## A quoi ça ressemble ? 

### Dart VS JavaScript

```dart nums
// Create a new class Person that define what's a person is.
class Person {
  String name;
  
  // Constructor
  Person(this.name);
  
  // Method
  void greet() {
    print('Hello, my name is $name.');
  }
}

void main() {
  // Create a new person instance using the constructor.
  var person = Person('Alice');
  // Call the greet function from Person class
  person.greet();
}
```

<center>***Versus***</center>

```js nums
// Create a person instance from a new JS object.
const person = {
	name: 'Alice',
	greet: function() {
		console.log(`Hello, my name is ${name}.`)
	}
}

// Call the greet function from the previously created object.
person.greet();
```

## Des Widgets, encore des Widgets

Dans Flutter, l'interface utilisateur est construite à partir de composants visuels nommés *widgets*. Un widget est l'élément de base de toute application Flutter, représentant des éléments visuels tels que des boutons, du texte, des images ou même des mises en page. En fait, tout dans Flutter est un widget et composé ensemble, ils définissent la forme ainsi que le comportement de votre application.

Il existe deux types de widgets principaux dans Flutter :

- **Stateless Widgets** : Ce sont des widgets immuables. Une fois créés, leur état ne change jamais. Ils sont utilisés pour des éléments d'interface simple qui ne nécessitent pas de mise à jour.

- **Stateful Widgets** : Ce sont des widgets qui ont un état mutable. Ils peuvent être mis à jour dynamiquement, permettant ainsi des interactions et des animations complexes.

### Exemple : Un Widget en Flutter

Voici un exemple d'un *Stateless Widget* simple qui affiche une carte contenant un message `Hello, Flutter with Card!`, suivie d'un texte stylisé `This is a Flex example.`

```dart nums
class CardExample extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Flex(
      direction: Axis.vertical,
      mainAxisAlignment: MainAxisAlignment.center,
      children: <Widget>[
        Card(
          elevation: 4,
          color: Colors.lightBlue[50],
          child: Padding(
            padding: const EdgeInsets.all(16.0),
            child: Text(
              'Hello, Flutter with Card!',
              style: TextStyle(fontSize: 20, color: Colors.blueAccent),
            ),
          ),
        ),
        Padding(
          padding: const EdgeInsets.only(top: 16.0),
          child: Text(
            'This is a Flex example.',
            style: TextStyle(fontSize: 18),
          ),
        ),
      ],
    );
  }
}
```

> [!hint] 
> ### Explication du code
> 
> 1. **CardExample** : C'est un *StatelessWidget* qui utilise `Flex` pour aligner les widgets verticalement.
> 2. **Flex** : Ce widget organise ses enfants selon une direction (ici verticale).
> - `direction: Axis.vertical` : Définit l'axe de disposition.
> - `mainAxisAlignment: MainAxisAlignment.center` : Centre le contenu verticalement.
> 3. **Card** : Ce widget affiche un conteneur avec une ombre et un style de carte par défaut.
> - `elevation: 4` : Définit la profondeur de l’ombre sous la carte pour donner un effet de relief.
> - `color` : Change la couleur de fond de la carte en bleu clair.
> - **Padding** : Ajoute un espacement interne autour du texte pour améliorer l'apparence visuelle.
> 4. **Text Widgets** : Chaque `Text` affiche une chaîne avec des styles spécifiques (couleur, taille de la police) pour personnaliser l'affichage.

## Avantages de Flutter

Flutter se distingue par plusieurs avantages :

- **Performance native** : En utilisant la compilation AOT pour le code de production, Flutter est optimisé pour exécuter du code directement sur le processeur de l'appareil, offrant des performances proches des applications natives contrairement aux solution comme Cordova.
- **Hot-Reload** : Pendant le développement, le Hot-Reload permet de voir instantanément les modifications de code dans l'application sans la redémarrer, accélérant le cycle de développement.
- **Portabilité multiplateforme** : Une seule base de code peut être utilisée pour créer des applications pour Android, iOS, le Web, et même le bureau sur Linux, MacOs et Windows.
- **Communauté active et vaste** : La communauté autour de Flutter est grande et croissante, fournissant une large base de widgets et de bibliothèques pour répondre à divers besoins.

