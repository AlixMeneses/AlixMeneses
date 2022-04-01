- 👋 Hi, I’m @AlixMeneses
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
//yo entendi esto de tu problema
#include <iostream>
#include <stdlib.h>
using namespace std;
/* run this program using the console pauser or add your own getch, system("pause") or input loop */
 
int main(int argc, char** argv) {
 
	float total[105], ji = 0,jf = 15, indice = 0,numSala = 0,numPeli = 0,sum = 0, promedio = 0;
	int  indiceM = 0;
 
	for(int i=0; i<7; i++){
		cout<<"SALA "<<i+1<<": "<<endl;
		for(int j=ji; j<jf; j++){
			cout<<"Ingrese el total de asistentes para la pelicula "<<j-indice+1<<": ";cin>>total[j];
		}
		ji = jf;
		jf += 15;
		indice += 15;
		cout<<endl;
	}
	//hallando promedio
	for(int i=0; i<105; i++){
		sum += total[i];
	}
	promedio = sum/105;
	//ordenando
	for(int i=0; i<105; i++){
		if(total[i] > total[indiceM]){
			indiceM = i;
		}
	}
	//hallando sala con pelicula famosa
	indice = 0;
	ji = 0;
	jf = 15;
	for(int i=0; i<7; i++){
		for(int j=ji; j<jf; j++){
			if(indiceM == j){
				numSala = i + 1;
				numPeli = j-indice+1;
			}
		}
		ji = jf;
		jf += 15;
		indice += 15;
	}
 
	cout<<"Sala-pelicula mas vista: sala "<<numSala<<" - pelicula "<<numPeli<<endl;
	cout<<"Pelicula mas popular: pelicula "<<numPeli<<endl;
	cout<<"Promedio de personas que asistieron al cine en total: "<<promedio;
 
	cout<<endl;
	system("PAUSE");
	return 0;
}
