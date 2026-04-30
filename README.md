# Examen Parcial - Estructuras de Datos

## Información del Estudiante
- **Nombre:** Gracia Alexandra Carrillo Santizo  
- **Carné:** 202504126  
- **Curso:** Estructura de Datos  
- **Catedrático:** Ing. Brandon Chitay  
- **Universidad:** Universidad Da Vinci de Guatemala  

## Descripción del Proyecto
Implementación en Java de una lista doblemente enlazada circular con operaciones de inserción, eliminación, búsqueda e impresión, además de un menú interactivo.

## Video Explicativo
(https://youtu.be/nkn9TxpxUTA)

## Instrucciones de Compilación y Ejecución
```bash
javac Nodo.java ListaDobleCircular.java Main.java
java Main

javac Nodo.java ListaDobleCircular.java Main.java
java Main


javac Nodo.java ListaDobleCircular.java Main.java
java Main






# parcial-dos
código base.

// Nodo.java
public class Nodo {
    int dato;
    Nodo anterior;
    Nodo siguiente;

    public Nodo(int dato) {
        this.dato = dato;
        this.anterior = null;
        this.siguiente = null;
    }
}


// ListaDobleCircular.java (fragmento)
public class ListaDobleCircular {
    Nodo head;

    public void insertarInicio(int dato) {
        Nodo nuevo = new Nodo(dato);
        if (head == null) {
            head = nuevo;
            head.siguiente = head;
            head.anterior = head;
        } else {
            Nodo ultimo = head.anterior;
            nuevo.siguiente = head;
            nuevo.anterior = ultimo;
            ultimo.siguiente = nuevo;
            head.anterior = nuevo;
            head = nuevo;
        }
    }

    public void imprimir() {
        if (head == null) {
            System.out.println("Lista vacía");
            return;
        }
        Nodo actual = head;
        do {
            System.out.print(actual.dato + " <-> ");
            actual = actual.siguiente;
        } while (actual != head);
        System.out.println("(circular -> " + head.dato + ")");
    }
}


// Main.java (fragmento)
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        ListaDobleCircular lista = new ListaDobleCircular();
        Scanner sc = new Scanner(System.in);
        int opcion;
        do {
            System.out.println("1. Insertar al inicio");
            System.out.println("2. Insertar al final");
            System.out.println("3. Eliminar al inicio");
            System.out.println("4. Eliminar al final");
            System.out.println("5. Buscar elemento");
            System.out.println("6. Imprimir lista");
            System.out.println("7. Salir");
            opcion = sc.nextInt();

            switch(opcion) {
                case 1: lista.insertarInicio(sc.nextInt()); break;
                case 6: lista.imprimir(); break;
                // aquí completas las demás operaciones
            }
        } while(opcion != 7);
    }
}

## Resultados



LISTA DOBLEMENTE ENLAZADA CIRCULAR
1. Insertar al inicio
2. Insertar al final
3. Eliminar al inicio
4. Eliminar al final
5. Buscar elemento
6. Imprimir lista
7. Salir
Seleccione una opción: 3
Error: Lista vacía
La lista está vacía

LISTA DOBLEMENTE ENLAZADA CIRCULAR
1. Insertar al inicio
2. Insertar al final
3. Eliminar al inicio
4. Eliminar al final
5. Buscar elemento
6. Imprimir lista
7. Salir
Seleccione una opción: 2
Dato a insertar: dato
Exception in thread "main" java.util.InputMismatchException
        at java.base/java.util.Scanner.throwFor(Scanner.java:977)
        at java.base/java.util.Scanner.next(Scanner.java:1632)
        at java.base/java.util.Scanner.nextInt(Scanner.java:2297)
        at java.base/java.util.Scanner.nextInt(Scanner.java:2251)
        at Main.main(Main.java:139)


...Program finished with exit code 1
Press ENTER to exit console.
