# LosTresMosqueteros
#include<iostream>

using namespace std;

//DECLARACION DE VARIABLES GLOBALES
int opcion, dato, contador=0;

//ENUMERACIONES
enum Localidad {Maldonado, CerroPelado, Piriapolis};
typedef enum {Matematica, IdiomaEspanol,EVP, Informatica, Historia, Geografia, CienciasFisicas, EducacionFisica, Biologia, Sonora, FormacionCristiana} Asignatura;
enum Liceo {Liceo_1 = 1, Liceo_2, Liceo_3, Liceo_4};

//ESTRUCTURAS
struct Profesores
{
	string cedula[15];
	string PrimerNombre[20];
	string PrimerApellido[20];
	string Telefono[15];
	int escalafon;
	int puntaje;
	//string localidad[30]; //aqui podemos ver lo de la enumeracion para que ingrese por ejemplo 1 para Maldonado y 2 para Cerro Pelado
	int horasQuiere;
	int horasTiene;
}unProfesor;
struct Nodo
{
	int dato; 
	Nodo *der;
	Nodo *izq;
};
struct Horas
{
	Asignatura materiaIngresada;
	int Tipo;//determina la cantidad de horas que tiene el grupo asignado
	Liceo NumLiceo;
};

//Prototipos
void menu();
Nodo *crearNodo(int);
void insertarNodo(Nodo *&, int);
void mostrarArbol(Nodo *;int);

Nodo *arbol = NULL;

int main()
{
	do
	{
		menu();
	} while(opcion != 5);
	return 0;
}

//Funcion de menu
void menu()
{
	cout <<" --------------------------------------------------------------\n|\t\tBIENVENIDO AL MENU PRINCIPAL                   |\n --------------------------------------------------------------\n|                                                              |\n| Ingrese una opción para navegar.                             |\n|                                                              |\n|\t1)Agregar                                              |\n|\t2)Modificar                                            |\n|\t3)Buscar                                               |\n|\t4)Eliminar                                             |\n|\t5)Salir                                                |\n|                                                              |\n --------------------------------------------------------------\n\n";
	cin >> opcion;

/*	do{
cout<<"\t.:Menu:."<<endl;
cout<<"1. Insertar un nuevo nodo"<<endl;
cout<<"2. Mostrar el arbol completo"<<endl;
cout<<"3. Salir"<<endl;
cout<<"Opcion: ";
cin>>opcion;
*/
switch(opcion){
case 1: cout<<"\nDigite un numero: ";
cin>>dato;
insertarNodo(arbol,dato); //Insertamos un nuevo nodo
cou<<"\n";
system("pause");
break;
case 2: cout<<"\nMostrando el arbol completo:\n\n";
mostrarArbol(arbol,contador);
cout<<"\n";
system("pause");
break;
}
system("cls");
}
while(opcion !=3);
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

//Función para mostrar arbol completo
void mostrarArbol Nodo *arbol, int cont){
if(arbol == NULL){//Si el arbol esta vacio
return;
}
else{
mostrarArbol(arbol->der,cont+1);
for(int i=0;i<cont;i++){
cout<<"   ";
}
cout<<arbol->dato<<endl;
mostrarArbol(arbol->izq,cont+1);
}
}
