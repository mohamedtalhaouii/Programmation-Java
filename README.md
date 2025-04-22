## **Plan du Contenu :**
- **[Types de Données](#1-types-de-données)**
- **[Déclaration de Variables](#2-déclaration-de-variables)**
- **[Entrée/Sortie](#3-entréesortie)**
- **[Opérateurs](#4-opérateurs)**
- **[Structures Conditionnelles](#5-structures-conditionnelles)**
- **[Structures Répétitives](#6-structures-répétitives)**
- **[Tableaux](#7-tableaux)**
- **[Chaînes de Caractères](#8-chaînes-de-caractères)**
- **[Méthodes (Fonctions)](#9-méthodes-fonctions)**
- **[Programmation Orientée Objet (POO)](#10-programmation-orientée-objet-poo)**
    - **[Classe et Objet](#1-classe-et-objet)**
    - **[Encapsulation](#2-encapsulation)**
    - **[Constructeur](#3-constructeur)**
    - **[Accesseurs et Mutateurs (Getters/Setters)](#4-accesseurs-et-mutateurs-getterssetters)**
    - **[Héritage](#5-héritage)**
    - **[Polymorphisme](#6-polymorphisme)**
    - **[Abstraction (Classe Abstraite et Interface)](#7-abstraction-classe-abstraite-et-interface)**
    - **[Membres Statiques](#8-membres-statiques)**
    - **[Final et Constantes](#9-final-et-constantes)**
- **[Collections](#11-collections)**
- **[Exceptions](#12-exceptions)**
- **[Fichiers](#13-fichiers)**

---

<h3 align="center"><a href="https://docs.oracle.com/en/java/" target="_blank">Documentation Officielle Java</a></h3>

---

## **1. Types de Données**
| **Type**       | **Taille**       | **Description**                          |
|----------------|------------------|------------------------------------------|
| `byte`         | 1 octet          | Entier signé (-128 à 127).               |
| `short`        | 2 octets         | Entier signé (-32 768 à 32 767).         |
| `int`          | 4 octets         | Entier signé (-2^31 à 2^31-1).           |
| `long`         | 8 octets         | Entier signé (-2^63 à 2^63-1).           |
| `float`        | 4 octets         | Nombre flottant (simple précision).      |
| `double`       | 8 octets         | Nombre flottant (double précision).      |
| `char`         | 2 octets         | Caractère Unicode (0 à 65 535).          |
| `boolean`      | 1 bit (virtuel)  | `true` ou `false`.                       |

---

## **2. Déclaration de Variables**
```java
type nomVariable = valeur;          // Variable
final type NOM_CONSTANTE = valeur;  // Constante
```

---

## **3. Entrée/Sortie**
```java
import java.util.Scanner;

Scanner sc = new Scanner(System.in);
System.out.print("Message");  // Affichage sans saut de ligne
System.out.println("Message"); // Affichage avec saut de ligne
int x = sc.nextInt();         // Lecture d'un entier
String s = sc.nextLine();     // Lecture d'une chaîne
```

---

## **4. Opérateurs**
- **Arithmétiques** : `+`, `-`, `*`, `/`, `%`, `++`, `--`
- **Comparaison** : `==`, `!=`, `>`, `<`, `>=`, `<=`
- **Logiques** : `&&` (ET), `||` (OU), `!` (NON)
- **Affectation** : `=`, `+=`, `-=`, `*=`, `/=`, `%=`

---

## **5. Structures Conditionnelles**
```java
// Condition simple
if (condition) {
    // Instructions
}

// Alternative
if (condition) {
    // Instructions
} else {
    // Instructions
}

// Imbriquée
if (condition1) {
    // Instructions
} else if (condition2) {
    // Instructions
} else {
    // Instructions
}

// Switch (Java 14+)
switch (variable) {
    case valeur1 -> System.out.println("Cas 1");
    case valeur2 -> System.out.println("Cas 2");
    default -> System.out.println("Cas par défaut");
}
```

---

## **6. Structures Répétitives**
```java
// Boucle for
for (int i = 0; i < 10; i++) {
    // Instructions
}

// Boucle while
while (condition) {
    // Instructions
}

// Boucle do-while
do {
    // Instructions
} while (condition);
```

---

## **7. Tableaux**
```java
int[] tableau = new int[5];          // Tableau 1D
int[][] matrice = new int[3][3];     // Tableau 2D
```

---

## **8. Chaînes de Caractères**
```java
String s = "Java";
System.out.println(s.length());      // Longueur
System.out.println(s.charAt(0));     // Caractère à l'index 0
System.out.println(s.substring(1)); // Sous-chaîne
```

---

## **9. Méthodes (Fonctions)**
```java
typeRetour nomMethode(type param1, type param2) {
    // Instructions
    return valeur;
}
```

---

## **10. Programmation Orientée Objet (POO)**

### **1. Classe et Objet**
```java
class Personne {
    String nom;
    int age;

    void afficher() {
        System.out.println(nom + " a " + age + " ans.");
    }
}

Personne p = new Personne();
p.nom = "Alice";
p.afficher();
```

### **2. Encapsulation**
```java
class Personne {
    private String nom;  // Privé

    public String getNom() { return nom; }      // Getter
    public void setNom(String nom) { this.nom = nom; } // Setter
}
```

### **3. Constructeur**
```java
class Personne {
    Personne(String nom, int age) {  // Constructeur
        this.nom = nom;
        this.age = age;
    }
}
```

### **4. Accesseurs et Mutateurs (Getters/Setters)**
```java
public String getNom() { return nom; }
public void setNom(String nom) { this.nom = nom; }
```

### **5. Héritage**
```java
class Etudiant extends Personne {
    String universite;
}
```

### **6. Polymorphisme**
```java
@Override
void afficher() {
    System.out.println("Étudiant: " + nom);
}
```

### **7. Abstraction (Classe Abstraite et Interface)**
```java
abstract class Animal {
    abstract void faireDuBruit();
}

interface Volant {
    void voler();
}
```

### **8. Membres Statiques**
```java
class MathUtils {
    static double PI = 3.14;
    static int carre(int x) { return x * x; }
}
```

### **9. Final et Constantes**
```java
final double PI = 3.14;  // Constante
```

---

## **11. Collections**
```java
List<String> liste = new ArrayList<>();  // Liste
Set<Integer> ensemble = new HashSet<>(); // Ensemble
Map<String, Integer> map = new HashMap<>(); // Dictionnaire
```

---

## **12. Exceptions**
```java
try {
    int x = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Division par zéro !");
} finally {
    System.out.println("Bloc final");
}
```

---

## **13. Fichiers**
```java
import java.io.File;
import java.io.FileWriter;

File fichier = new File("test.txt");
FileWriter fw = new FileWriter(fichier);
fw.write("Bonjour Java !");
fw.close();
```
