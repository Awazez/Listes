# Books

- La technique pomodoro 
- Deep work
- System Design Interview – An insider's guide
- The Road to React: Your journey to master plain yet pragmatic React.js
- Clean code 

Clean Code : un code propre lors du contrôle
Le Clean Code nous vient de Robert Cecil Martin, qui a inventé ce terme dans son livre « Clean Code: Rafactoring, Patterns, Testen und Techniken für sauberen Code »pour décrire un code écrit de façon propre. Les principes du Clean Code sont toutefois nettement plus anciens et ne trouvent pas leur origine dans le développement logiciel. Nous vous expliquons ce qui distingue un code propre, quels sont ses avantages et comment vous pouvez écrire du Clean Code.

Sommaire
Le Clean Code, c’est quoi ?
Aperçu des principes du Clean Code
Le Clean Code, c’est quoi ?
Le Clean Code n’est pas un ensemble de règles strictes mais désigne plutôt une série de principes pour produire un code compréhensible de façon intuitive et facile à modifier. Compréhensible signifie dans ce cas un code immédiatement intelligible par n’importe quel développeur qualifié. Les caractéristiques suivantes augmentent la lisibilité du Clean Code :

Le processus d’exécution de l’ensemble de l’application est logique et structuré de façon simple.
Le rapport entre les différentes parties du code est transparent.
La tâche ou le rôle de chaque classe, fonction, méthode et variable est immédiatement compréhensible.
Un code est facile à modifier lorsqu’il peut être facilement ajusté et complété. À l’inverse, il est également plus simple de corriger les erreurs dans le code. Par conséquent, le Clean Code est très facile à entretenir. Un code facilement modifiable comporte les attributs suivants :

Les classes et les méthodes sont petites et, dans la mesure du possible, ont une seule et unique tâche.
Les classes et les méthodes sont prévisibles, fonctionnent de la façon attendue et sont accessibles au grand public grâce à des API bien documentées (interfaces).
Le code dispose de tests d'unité.
Les avantages d’une telle programmation sont évidents : le Clean Code n’est pas dépendant du développeur initial. En principe, n’importe quel programmeur peut ainsi travailler avec un tel code. Ceci permet par exemple d’éviter les problèmes survenant lorsque l’on travaille avec un legacy code. L’entretien du logiciel s’en trouve également facilité puisque les bugs peuvent être trouvés et corrigés facilement.

Aperçu des principes du Clean Code
Mais comment écrire un code propre ? Pour écrire du Clean Code, il convient de respecter certains principes de base de la programmation. Ce ne sont pas des instructions concrètes sur la façon de programmer tel élément dans telle situation mais plutôt une vision réfléchie du travail d’un développeur. Ceci explique pourquoi les développeurs de la communauté ont une vision différente de ce qu’est un Clean Code : certains programmeurs pourront considérer un code comme « clean » et d’autres non. Déterminer à quel point un code est clean est toujours un peu subjectif. Nous vous présentons ci-après plusieurs principes établis du Clean Code qui sont reconnus par la plupart des développeurs.

Un code aussi simple que possible : KISS
KISS (Keep it simple, stupid)est l’un des plus anciens principes du Clean Code. Il fut appliqué par l’armée américaine dès les années 1960. KISS rappelle aux programmeurs de construire leur code de façon aussi simple que possible. Toute complexité inutile doit être évitée. En programmation, il n’y a jamais une seule méthode pour résoudre un problème. Une tâche peut toujours être exprimée dans différents langages et formulée avec différentes commandes. Par conséquent, les programmeurs observant le principe KISS doivent constamment se demander s’ils ne peuvent pas résoudre un problème plus facilement.

Éviter les répétitions inutiles : DRY
DRY(Don’t repeat yourself) est en quelque sorte la concrétisation du principe KISS. Un Clean Code respectant ce principe implique que chaque fonctionnalité doit avoir une seule et unique représentation au sein du système global.

 Note
Le contraire de DRY est WET(We enjoy typing). On appelle WET un code comportant des répétitions inutiles.

L’exemple suivant illustre le principe d’un Clean Code DRY : le nom d’utilisateur et le mot de passe sont appelés à deux reprises dans le code afin d’être utilisés pour différentes actions. Au lieu de programmer les deux processus séparément, ils peuvent être rassemblés dans une même fonctionnalité. Ceci permet de transformer un code WET (« humide ») comportant des répétitions en code DRY (« sec »).

Code WET :

//Variante A
let username = getUserName();
let password= getPassword();
let user = { username, password};
client.post(user).then(/*Variante A*/);

//Variante B
let username = getUserName();
let password= getPassword();
let user = { username, password};
client.get(user).then(/*Variante B*/);
Code DRY :

function getUser(){
  return {
    user:getUserName();
    password:getPassword();
  }
}

//Variante A
client.post(getUser()).then(/*Variante A*/ );

//Variante B
client.get(getUser()).then(/*Variante B*/);
Supprimer ce qui est inutile : YAGNI
Le principe de Clean Code YAGNI(You aren’t gonna need it) exprime l’idée suivante : un développeur devrait uniquement ajouter des fonctionnalités supplémentaires au code lorsqu’elles sont nécessaires. Le principe YAGNIest étroitement lié aux méthodes de développement agile. Au lieu de partir d’un concept global dans le développement, une programmation selon le principe YAGNI consiste à élaborer l’architecture du logiciel par de petites étapes afin de pouvoir réagir aux problèmes de façon dynamique et ciblée. Par conséquent, un Clean Code est toujours généré lorsque le problème sous-jacent est résolu d’une façon aussi efficace que possible.

La lisibilité avant la concision
Le code doit être opérationnel et pouvoir être lu par la machine qui l’exécutera. Mais lorsque plusieurs personnes travaillent sur un même projet, les autres développeurs doivent également pouvoir comprendre le code. C’est pourquoi dans le développement logiciel, la lisibilité prime toujours sur la concision du code. Écrire un code concis, mais incompréhensible pour les autres développeurs n’aurait aucun sens. La dénomination de variables constitue un bon exemple de lisibilité dans un Clean Code.

Un nom de variable doit toujours être compréhensible sans informations complémentaires. La variable suivante n’est pas compréhensible sans connaissances de base ni explications :

int d;
A contrario, le nom suivant, qui désigne la même variable, est évident :

int elapsedTimeinDays;

