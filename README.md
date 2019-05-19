#include <iostream>//PAULO HERNANDEZ. MONICA HUENUVIL, MARTIN HURTADO
#include <Libro.h>
#include <Pila.h>
using namespace std;
void OrdenarMisLecturas(Pila Libreria)
{
   Libro V[5];
   Libro aux;
   int i,j;
   for(i=0;i<5;i++)
   {
       V[i]=Libreria.pop();
   }
   for(i=0;i<5;i++)
   {
       for(j=0;j<5;j++)
       {
           if(V[i].getn_paginas()<V[j].getn_paginas())
           {
               aux=V[i];
               V[i]=V[j];
               V[j]=aux;
           }
       }
   }
   for(i=0;i<5;i++)
   {
       Libreria.push(V[i]);
   }
   Libro x;
   for(i=0;i<5;i++)
   {
       x=Libreria.pop();
       x.mostrar();
       cout<<"\n";
   }

}
int main()
{
   Libro principito(95,"antoine","EL Principito");
   Libro papelucho(65,"Marcela Paz","Papelucho");
   Libro odisea(448,"Homero","La odisea");
   Libro perfume(318,"Patrick Suskind","El Perfume");
   Libro ladrona(539,"Markus Zusak","La ladrona de libros");
   Pila Libreria;
   Libreria.push(principito);
   Libreria.push(papelucho);
   Libreria.push(odisea);
   Libreria.push(perfume);
   Libreria.push(ladrona);
   OrdenarMisLecturas(Libreria);


    return 0;
}
