# LosTresMosqueteros
#include<iostream>
#include<conio.h>
using namespace std;
  
struct Nodo{
int dato; 
Nodo *der;
Nodo *izq;
};

//ENUMERACIONES
enum Localidad {Maldonado, CerroPelado, Piriapolis};
enum Asignatura {Matematica, IdiomaEspanol,EVP, Informatica, Historia, Geografia, CienciasFisicas, EducacionFisica, Biologia, Sonora, FormacionCristiana};

//Prototipos
void menu();
Nodo *crearNodo(int);
void insertarNodo(Nodo *&, int);

Nodo *arbol = NULL;

int main(){
menu();
return 0;
}

//Funcion de menu
void menu(){

cout <<" --------------------------------------------------------------\n|\t\tBIENVENIDO AL MENU PRINCIPAL                   |\n --------------------------------------------------------------\n|                                                              |\n| Ingrese una opción para navegar.                             |\n|                                                              |\n|\t1)Agregar                                              |\n|\t2)Modificar                                            |\n|\t3)Buscar                                               |\n|\t4)Eliminar                                             |\n|\t5)Salir                                                |\n|                                                              |\n --------------------------------------------------------------\n\n";
cin >> opcion;

switch(opcion){
case 1: cout<<"\nDigite un numero: ";
cin>>dato;
insertarNodo(arbol,dato); //Insertamos un nuevo nodo
cou<<"\n";
system("pause");
break;
}
system("cls");
}
while(opcion !=2);
}

//Funcion para crear un nuevo nodo
Nodo *crearNodo(int n){
Nodo *nuevo_nodo = new Nodo();

nuevo_nodo->dato = n;
nuevo_nodo->der = NULL;
nuevo_nodo->izq = NULL;

return nuevo_nodo;
}

//Funcion para insertar elemntos en el arbol
void insertarNodo(Nodo *&arbol,int n){
if(arbol == NULL){//Si el arbol esta vacio
Nodo *nuevo_nodo = crearNodo(n);
arbol = nuevo_ nodo;
}
else{//Si el arbol tiene un nodo o mas
int valorRaiz = arbol->dato;//Obtenemos el valor de la raíz
if (n<valorRaiz){//Si el elemento es menor a la raiz, insertamos en izq
insertarNodo(arbol->izq,n);
}
else{//Si el elemento es menor a la raiz, insertamos en der
insertarNodo(arbol->der,n);
}
}
