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

# **Résumé Complet et Structuré de Java**  

## **1. Introduction à Java**  
- **Java** : Langage de programmation orienté objet, portable (JVM), robuste et sécurisé.  
- **JVM, JRE, JDK** :  
  - **JVM** (Machine Virtuelle Java) : Exécute le bytecode.  
  - **JRE** (Environnement d'exécution Java) : Contient JVM + bibliothèques.  
  - **JDK** (Kit de développement Java) : Outils de développement (compilateur `javac`, débogueur, etc.).  

---

## **2. Syntaxe de Base**  
### **Structure d'un programme**  
```java  
public class NomClasse {  
    public static void main(String[] args) {  
        System.out.println("Hello, World!");  
    }  
}  
```  

### **Variables et Types de Données**  
- **Primitifs** :  
  - `int`, `double`, `char`, `boolean`, `byte`, `short`, `long`, `float`.  
- **Références** :  
  - `String`, tableaux, objets.  

### **Opérateurs**  
- Arithmétiques (`+`, `-`, `*`, `/`, `%`).  
- Comparaison (`==`, `!=`, `>`, `<`, `>=`, `<=`).  
- Logiques (`&&`, `||`, `!`).  

### **Structures de Contrôle**  
- **Conditionnelles** :  
  ```java  
  if (condition) { ... }  
  else if (condition) { ... }  
  else { ... }  
  ```  
  ```java  
  switch (variable) {  
      case valeur1: ... break;  
      default: ...  
  }  
  ```  
- **Boucles** :  
  ```java  
  for (int i = 0; i < 10; i++) { ... }  
  while (condition) { ... }  
  do { ... } while (condition);  
  ```  

---

## **3. Structures de Données**  
### **Tableaux**  
```java  
int[] nombres = {1, 2, 3};  
String[] mots = new String[5];  
```  

### **Collections (Java Collections Framework)**  
- **Listes** (`ArrayList`, `LinkedList`) :  
  ```java  
  List<String> liste = new ArrayList<>();  
  liste.add("Java");  
  ```  
- **Ensembles** (`HashSet`, `TreeSet`) :  
  ```java  
  Set<Integer> ensemble = new HashSet<>();  
  ensemble.add(10);  
  ```  
- **Maps** (`HashMap`, `TreeMap`) :  
  ```java  
  Map<String, Integer> map = new HashMap<>();  
  map.put("clé", 100);  
  ```  

---

## **4. Programmation Orientée Objet (POO)**  
### **Concepts Clés**  
- **Classe** : Modèle pour créer des objets.  
- **Objet** : Instance d'une classe.  
- **Encapsulation** : Protection des données (`private`, `getters/setters`).  
- **Héritage** : `extends` (réutiliser le code d'une classe parente).  
- **Polymorphisme** : Surcharge (`overloading`) et redéfinition (`overriding`).  
- **Abstraction** : Classes abstraites (`abstract`) et interfaces (`interface`).  

### **Exemple de Classe**  
```java  
public class Personne {  
    private String nom; // Attribut privé  

    // Constructeur  
    public Personne(String nom) {  
        this.nom = nom;  
    }  

    // Getter  
    public String getNom() { return nom; }  

    // Setter  
    public void setNom(String nom) { this.nom = nom; }  
}  
```  

### **Héritage et Polymorphisme**  
```java  
public class Etudiant extends Personne {  
    private int matricule;  

    public Etudiant(String nom, int matricule) {  
        super(nom); // Appel du constructeur parent  
        this.matricule = matricule;  
    }  

    @Override  
    public String getNom() { // Redéfinition  
        return "Étudiant: " + super.getNom();  
    }  
}  
```  

### **Interfaces**  
```java  
public interface Calculable {  
    double calculer();  
}  

public class Calcul implements Calculable {  
    @Override  
    public double calculer() { return 42; }  
}  
```  

---

## **5. Gestion des Erreurs (Exceptions)**  
```java  
try {  
    int res = 10 / 0;  
} catch (ArithmeticException e) {  
    System.out.println("Erreur: Division par zéro");  
} finally {  
    System.out.println("Exécuté dans tous les cas");  
}  
```  

---

## **6. Entrées/Sorties (I/O)**  
### **Lecture Fichier**  
```java  
try (BufferedReader br = new BufferedReader(new FileReader("fichier.txt"))) {  
    String ligne;  
    while ((ligne = br.readLine()) != null) {  
        System.out.println(ligne);  
    }  
} catch (IOException e) {  
    e.printStackTrace();  
}  
```  

### **Écriture Fichier**  
```java  
try (BufferedWriter bw = new BufferedWriter(new FileWriter("sortie.txt"))) {  
    bw.write("Bonjour Java !");  
} catch (IOException e) {  
    e.printStackTrace();  
}  
```  

---

## **7. Multithreading**  
```java  
public class MonThread extends Thread {  
    @Override  
    public void run() {  
        System.out.println("Thread en cours...");  
    }  

    public static void main(String[] args) {  
        MonThread thread = new MonThread();  
        thread.start();  
    }  
}  
```  

---

## **8. Bonnes Pratiques**  
- **Nommage** : `camelCase` pour variables/méthodes, `PascalCase` pour classes.  
- **Commentaires** : `//` pour une ligne, `/* ... */` pour plusieurs.  
- **Modularité** : Utiliser des packages (`com.monprojet.utils`).  

---

## **9. Outils et Frameworks Importants**  
- **Build Tools** : Maven, Gradle.  
- **Frameworks** : Spring, Hibernate.  
- **Tests** : JUnit.  
