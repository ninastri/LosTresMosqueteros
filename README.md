# LosTresMosqueteros
#include "Lista.h"

void Lista::insertar(Nodo * n){
	cout<<"Insertar "<<n->valor()<<"("<<n<<")->"<<n->siguiente()<<endl;
	n->nuevoSiguiente(primero);
	primero = n;
}
void Lista::mostrar(){
	cout<<endl<<"Mostrar"<<endl;
	Nodo * tmp = primero;
	while(tmp!=0){
		cout<<tmp->valor()<<" ("<<tmp<<") "<<tmp->siguiente()<<endl;
		tmp=tmp->siguiente();
	}
	cout<<"-FIN-"<<endl<<endl;
}
void Lista::quitar(int i){
	cout<<"Quitar"<<i;
	Nodo * tmp = primero;
	while (tmp!=0){
		if(tmp->siguiente()!=0){
			if(i==tmp->siguiente()->valor()){
				tmp->nuevoSiguiente(tmp->siguiente()->siguiente());
				cout<<" Borrado";
				tmp=0;
			}else
				tmp=tmp->siguiente();
		}else
		   tmp=tmp->siguiente();
		}
	cout<<endl;
	}
bool Lista::pertenece(int i){
	bool b = false;
	Nodo * tmp=primero;
	while(tmp!=0){
		if(i==tmp->valor()){
			tmp=0;
			b=true;
		}else
			tmp=tmp->siguiente();
		}
	return b;
	}
