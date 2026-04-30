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
