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


1. Insertar al inicio
Dato a insertar: 10
Lista: 10 <-> (circular -> 10)

2. Insertar al final
Dato a insertar: 20
Lista: 10 <-> 20 <-> (circular -> 10)

5. Buscar elemento
Dato a buscar: 20
Encontrado

## Estructura del Proyecto
- Nodo.java → clase del nodo
- ListaDobleCircular.java → operaciones de la lista
- Main.java → menú interactivo
