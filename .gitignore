#include <conio.h>
#include <iostream>
#include <stdio.h>
#include <stdlib.h>
#include <windows.h>
using namespace std;
class nodo {
	//dESDE OTRA CLASE SE PUEDEN acceder a estos atributos
   public:
    nodo(int v, nodo *sig, nodo *ante)
    {
       valor = v;
       siguiente = sig;
       anterior=ante;
    }
    //Desde otra clase/funcion no de puede acceder a los atributos o metodos privados.
   private:
    int valor;
    nodo *siguiente;
    nodo *anterior;

   //Una funcion externa puede acceder a los atributos privados.
   friend class lista;
};

//PROTOTIPOS
void menu();
void mostrar();
nodo *crearnodo(int,nodo *,nodo *);


nodo *arbol = NULL; //incializa el arbol en NULL

typedef nodo *pnodo;

class lista {
   public:
   	void insertarnodo(nodo *&,int,nodo *);
   	void mostrararbol(nodo *); //funcion para mostrar el arbol con recursividad
   	void mostrararbol2(nodo *); //FUNCIOIN PARA RECCORER EL arbol con while
   private:
    pnodo primero;
    pnodo actual;
};

void mostar(){
	
}

int main() {
	menu();
   system("pause");
   return 0;
}

void menu(){
	int opcion=0,val=0,contador=0;
	do {
		system("cls");
		cout<<"--------------ARBOLES---------------------"	<<endl;
		cout<<"1. Insertar un nodo"<<endl;
		cout<<"2. listar nodos usando while"<<endl;
		cout<<"3. listar nodos usando recursividad"<<endl;
		cout<<"4. salir"<<endl<<endl;
		cout<<"ingrese una opcion: ";
		cin>>opcion;
			switch(opcion){
				case 1:
						system("cls");
						cout<<"--------INGESANDO UN NODO--------"<<endl;
						cout<<"ingrese el valor del nodo: ";
						cin>>val;
						lista Lista;
						Lista.insertarnodo(arbol,val,NULL);
						system("pause");
						break;
				case 3: 
						system("cls");
						cout<<"--------MOSTRANDO EL ARBOL RECURSIVO--------"<<endl;
						lista Lista2;
						Lista2.mostrararbol(arbol);
						system("pause");
						break;
				case 2: 
						system("cls");
						cout<<"--------MOSTRANDO EL ARBOL usando while--------"<<endl;
						lista Lista6;
						Lista6.mostrararbol2(arbol);
						system("pause");
						break;
			}	
	}while(opcion != 4);
}

//funcion para crear nodos nuevos
nodo *crearnodo(int n,nodo *anterior){
     nodo *nuevo_nodo= new nodo(n,NULL,anterior);
     return nuevo_nodo;
}

//funcion para insertar nodos en el arbol
void lista::insertarnodo(nodo *&arbol, int n, nodo *anterior){
     if(arbol==NULL)
     {
            nodo *nuevo_nodo=crearnodo(n,anterior);
            arbol=nuevo_nodo;
     }else //si el arbol tiene uno o mas nodos
     {
  			insertarnodo(arbol->siguiente,n,arbol);
         	//arbol->anterior=arbol->siguiente;
     }
}

//funcon para mostrar el arbol con recursividad
void lista::mostrararbol(nodo *arbol){
     if(arbol== NULL)
     {
                return ;
     }
     else
     {
         cout<<"codigo de nodo: "<<arbol<<" , valor de nodo: "<<arbol->valor<<" , nodo siguiente: "<<arbol->siguiente<<endl;
		 mostrararbol(arbol->siguiente);
        
     }
}

//funcon para mostrar el arbol USANDO ITERACIONES
void lista::mostrararbol2(nodo *arbol){
     if(arbol== NULL)
     {
                return ; //SI no encuentra nodos retorno sin hacer nada
     }
     else
     {
     	//contador difine cuantos espacios dejar del margen
     	//nodo *arbol2;
     while(arbol!= NULL){
     			cout<<"codigo de nodo: "<<arbol<<" , valor de nodo: "<<arbol->valor<<" , nodo siguiente: "<<arbol->siguiente<<endl;
     			arbol=arbol->siguiente;
		 }
     }
}
