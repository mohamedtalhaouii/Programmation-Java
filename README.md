## **Plan du Contenu :**
- **[Pourquoi Java ?](#pourquoi-java-)**
- **[Syntaxe de Base](#syntaxe-de-base)**
- **[Comparaison C++/Java](#comparaison-cjava)**
- **[Types de Données](#1-types-de-données)**
- **[Déclaration de Variables](#2-déclaration-de-variables)**
- **[Entrée/Sortie](#3-entréesortie)**
- **[Opérateurs](#4-opérateurs)**
- **[Structures Conditionnelles](#5-structures-conditionnelles)**
- **[Structures Répétitives](#6-structures-répétitives)**
- **[Tableaux](#7-tableaux)**
- **[Chaînes de Caractères](#8-chaînes-de-caractères)**
- **[Méthodes](#9-méthodes)**
- **[Classes et Objets](#10-classes-et-objets)**
    - **[Classe et Objet](#1-classe-et-objet-)**
    - **[Encapsulation](#2-encapsulation-)**
    - **[Constructeurs](#3-constructeurs-)**
    - **[Accesseurs et Mutateurs (Getters/Setters)](#4-accesseurs-et-mutateurs-getterssetters-)**
    - **[Héritage](#5-héritage-)**
    - **[Polymorphisme](#6-polymorphisme-)**
    - **[Abstraction](#7-abstraction-classe-abstraite-)**
    - **[Interfaces](#8-interfaces-)**
    - **[Membres statiques](#9-membres-statiques-)**
    - **[Modificateurs final et static](#10-modificateurs-final-et-static-)**
- **[Collections](#11-collections)**
- **[Exceptions](#12-exceptions)**
- **[Fichiers](#13-fichiers)**

---

<h3 align="center"><a href="https://github.com/mohamedtalhaouii/Programmation-Cpp" target="_blank">Lien de Language C++</a></h3>


---

## **Pourquoi Java ?**
| **Caractéristique** | **Avantage**                                  |
|---------------------|---------------------------------------------|
| **Garbage Collector** | Pas de `delete` → Mémoire gérée automatiquement |
| **Multiplateforme**   | Code exécuté sur JVM (Windows/Linux/Mac)    |
| **Orienté Objet**    | Tout est objet (sauf les primitifs)         |
| **Écosystème riche** | Android, Spring, Hadoop, etc.               |

---

## **Syntaxe de Base**
- **Structure d’un Programme Java**
```java
// Fichier : NomDuProgramme.java  
public class NomDuProgramme {      // Le nom de la classe DOIT correspondre au nom du fichier  
    public static void main(String[] args) {  // Méthode principale (point d'entrée)  
        // Votre code ici  
    }  
}  
```

- **Éléments Clés**
    - **Classes** : Chaque fichier `.java` contient une classe publique.
    - **`main()`** : Méthode obligatoire pour exécuter le programme.
    - **Points-virgules** : Requis après chaque instruction.
    - **Typage strict** : `int x = "texte"` → Erreur de compilation.

---

## **Comparaison C++/Java**
| **Concept**       | **C++**                          | **Java**                          |
|------------------|----------------------------------|----------------------------------|
| **Compilation**  | → Binaire natif                 | → Bytecode (JVM)                |
| **Pointeurs**    | `int* p = &x;`                  | Références uniquement (`Objet o = new Objet()`) |
| **Héritage**     | Multiple (`class A : public B, C`) | Simple (`extends`), interfaces pour multi-héritage |
| **Gestion Mémoire** | `new`/`delete`               | Garbage Collector (GC)          |


---

## **1. Types de Données**
| **Type**       | **Taille (en octets)** | **Description**                             |
|----------------|-----------------------|---------------------------------------------|
| byte        | 1                     | Entier signé (-128 à 127).                  |
| short       | 2                     | Entier signé (-32,768 à 32,767).            |
| int         | 4                     | Entier signé (-2^31 à 2^31-1).              |
| long        | 8                     | Entier long signé (-2^63 à 2^63-1).         |
| float       | 4                     | Nombre flottant simple précision.           |
| double      | 8                     | Nombre flottant double précision.           |
| char        | 2                     | Caractère Unicode (0 à 65,535).             |
| boolean     | 1 (environ)           | Valeur booléenne (true ou false).           |

---

## **2. Déclaration de Variables**
```java
// Primitive (stockée dans la pile)
int x = 10;  

// Objet (stocké dans le tas)
String texte = new String("Hello");  

// Constante (final = const en C++)
final double PI = 3.14159;  
```

---

## **3. Entrée/Sortie**

- **Lecture :**
```java
import java.util.Scanner;  // Nécessaire pour les opérations de lecture

public class Main {
    public static void main(String[] args) {
        // Création d'un objet Scanner
        Scanner scanner = new Scanner(System.in);
        
        // Lecture des différents types de données
        System.out.print("Entrez votre nom complet : ");
        String nomComplet = scanner.nextLine();  // Lit toute la ligne
        
        System.out.print("Entrez votre âge : ");
        int age = scanner.nextInt();            // Lit un entier
        
        System.out.print("Entrez votre taille (en m) : ");
        double taille = scanner.nextDouble();   // Lit un nombre décimal
        
        // Nettoyage du buffer
        scanner.nextLine();
        
        // Fermeture du scanner (bonne pratique)
        scanner.close();
    }
}
```

- **Écriture :**
```java
// Affichage simple
System.out.println("Bonjour " + nomComplet + "!");  // println = saut de ligne

// Formatage avancé avec printf()
System.out.printf("Âge : %d ans | Taille : %.2f m%n", age, taille);

// Formatage avec String.format()
String message = String.format("Vous vous appelez %s et vous avez %d ans", nomComplet, age);
System.out.println(message);
```

## **4. Opérateurs**

- **Opérateurs Arithmétiques**

| **Opérateur** | **Description**                     | **Exemple**         |
|---------------|-------------------------------------|---------------------|
| +           | Addition                            | a + b             |
| -           | Soustraction                        | a - b             |
| *           | Multiplication                      | a * b             |
| /           | Division                            | a / b             |
| %           | Modulo (reste de la division)       | a % b             |
| ++          | Incrémentation (ajoute 1)           | a++ ou ++a      |
| --          | Décrémentation (soustrait 1)        | a-- ou --a      |

- **Opérateurs de Comparaison**

| **Opérateur** | **Description**                     | **Exemple**         |
|---------------|-------------------------------------|---------------------|
| ==          | Égal à                              | a == b            |
| !=          | Différent de                        | a != b            |
| >           | Supérieur à                         | a > b             |
| <           | Inférieur à                         | a < b             |
| >=          | Supérieur ou égal à                 | a >= b            |
| <=          | Inférieur ou égal à                 | a <= b            |

- **Opérateurs Logiques**

| **Opérateur** | **Description**                     | **Exemple**         |
|---------------|-------------------------------------|---------------------|
| &&          | ET logique                          | a && b            |
| \|\|        | OU logique                          | a \|\| b          |
| !           | NON logique (inverse)               | !a                |

- **Opérateurs d'Affectation**

| **Opérateur** | **Description**                     | **Exemple**         |
|---------------|-------------------------------------|---------------------|
| =           | Affectation simple                  | a = b             |
| +=          | Ajoute et affecte                   | a += b            |
| -=          | Soustrait et affecte                | a -= b            |
| *=          | Multiplie et affecte                | a *= b            |
| /=          | Divise et affecte                   | a /= b            |
| %=          | Modulo et affecte                   | a %= b            |

---

## **5. Structures Conditionnelles**
```java
// Condition simple
if (condition) {
    // instructions;
}

// Alternative
if (condition) {
    // instructions;
} else {
    // instructions;
}

// Imbriquée
if (condition1) {
    // instructions;
} else if (condition2) {
    // instructions;
} else {
    // instructions;
}

// Switch (Java 14+ avec syntaxe moderne)
switch (expression) {
    case valeur1 -> // instruction;
    case valeur2 -> {
        // instructions;
    }
    default -> // instruction;
}
```

---

## **6. Structures Répétitives**
```java
// Boucle for
for (int i = 0; i < 10; i++) {
    // instructions;
}

// Boucle while
while (condition) {
    // instructions;
}

// Boucle do...while
do {
    // instructions;
} while (condition);

// Boucle for-each
for (Type element : collection) {
    // instructions;
}
```

---

## **7. Tableaux**
```java
Type[] tableau = new Type[taille];       // Tableau 1D
Type[][] matrice = new Type[lignes][cols]; // Tableau 2D

// Initialisation directe
int[] nombres = {1, 2, 3};
```

---

## **8. Chaînes de Caractères**
```java
String chaine = "texte"; // Chaîne immuable

// Méthodes utiles
chaine.length();
chaine.charAt(index);
chaine.substring(debut, fin);
chaine.equals(autreChaine); // Pour comparer
```

---

## **9. Méthodes**
```java
typeRetour nomMethode(type param1, type param2) {
    // Code
    return valeur; // si typeRetour n'est pas void
}
```

---

## **10. Classes et Objets**

### **1. Classe et Objet :**
```java
class NomClasse {
    // Attributs
    private int attribut;

    // Méthodes
    public void methode() {
        // Code
    }
}

// Instanciation
NomClasse objet = new NomClasse();
objet.methode();
```

### **2. Encapsulation :**
```java
class Compte {
    private double solde; // Privé

    public void deposer(double montant) {
        if (montant > 0) solde += montant;
    }

    public double getSolde() { return solde; }
}
```

### **3. Constructeurs :**
```java
class Personne {
    private String nom;

    // Constructeur
    public Personne(String nom) {
        this.nom = nom;
    }

    // Constructeur par défaut (si aucun constructeur n'est défini)
    public Personne() {
        this("Inconnu");
    }
}
```

### **4. Accesseurs et Mutateurs (Getters/Setters) :**
```java
public class Voiture {
    private String marque;

    // Getter
    public String getMarque() {
        return marque;
    }

    // Setter
    public void setMarque(String marque) {
        this.marque = marque;
    }
}
```

### **5. Héritage :**
```java
class Animal {
    public void manger() {
        System.out.println("L'animal mange");
    }
}

class Chien extends Animal {
    @Override
    public void manger() {
        System.out.println("Le chien mange");
    }
}
```

### **6. Polymorphisme :**
```java
Animal monAnimal = new Chien();
monAnimal.manger(); // Appelle la méthode de Chien
```

### **7. Abstraction (Classe Abstraite) :**
```java
abstract class Forme {
    abstract double calculerAire();
}

class Cercle extends Forme {
    double rayon;
    
    @Override
    double calculerAire() {
        return Math.PI * rayon * rayon;
    }
}
```

### **8. Interfaces :**
```java
interface Remboursable {
    void rembourser();
}

class Produit implements Remboursable {
    @Override
    public void rembourser() {
        System.out.println("Remboursement effectué");
    }
}
```

### **9. Membres statiques :**
```java
class Utils {
    public static final double PI = 3.14159;
    
    public static int carre(int x) {
        return x * x;
    }
}

// Utilisation
double pi = Utils.PI;
int result = Utils.carre(5);
```

### **10. Modificateurs final et static :**
- `final` : Variable constante ou méthode/classe non modifiable/étendable
- `static` : Membre de classe plutôt que d'instance

---

## **11. Collections**
```java
import java.util.ArrayList;
import java.util.HashMap;

ArrayList<String> liste = new ArrayList<>();
liste.add("élément");

HashMap<String, Integer> map = new HashMap<>();
map.put("clé", 42);
```

---

## **12. Exceptions**
```java
try {
    // Code risqué
} catch (ExceptionType e) {
    // Gestion
} finally {
    // Code exécuté toujours
}
```

---

## **13. Fichiers**
```java
import java.io.File;
import java.nio.file.Files;

// Lecture
String contenu = Files.readString(Path.of("fichier.txt"));

// Écriture
Files.writeString(Path.of("fichier.txt"), "Contenu");
```

---

## **Bibliothèques Utiles**
```java
import java.util.*;       // Collections, Scanner
import java.io.*;         // Fichiers
import java.nio.file.*;   // Nouvelle API fichiers
import java.time.*;       // Dates modernes
```

---


<h3 align="center"> 🧑🏻‍💻 | Made By : <a href="https://github.com/mohamedtalhaouii" target="_blank">Mohamed Talhaoui</a></h3>
