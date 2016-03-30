#include<stdio.h>
#include<conio.h>
#include<string.h>//agrego la libreria
#include<ctype.h>//agrego libreria


#define A 1000
#define B 1200
#define C 1350
#define pf printf//corrigo q la primera letra de printf estaba en mayuscula
#define sc scanf
#define ff fflush(stdin)


int menu();
char val_zona(char z,char a,char b,char c);
//char clac_zona(char a,char b, char c);

void main(void)//borro el ;
{
	clrscr();
	int op,flag=0,metro,m1,m2,m3,rta;
	char nomb[25],aux[100],mxnomb[25],resp,zona;
	float imp,mximp;

	do
	{
		clrscr();
		//pf("MENU DE OPCIONES\n1-CARGAR DATOS\n2-MOSTRAR\n3-SALIR");
		//sc("%d",op);
      op=menu();
		switch(op)//agrego op
		{
			case 1:
				clrscr();
				do
				{
               clrscr();
					pf("Ingrese el nombre: ");
					ff;
					gets(aux);
					while(strlen(aux)>24)
					{
						pf("Re Ingrese");
						ff;
						gets(aux);
               }
					strcpy(nomb,aux);
					pf("Ingrese metros cuadrados de la propiedad: ");
					sc("%d",&metro);//corrijo los "" por que la segunda " va despues de %d y antes de la coma, corrijo la palabra mentro por metro ya q la variable es metro
					pf("Ingrese Zona: ");
               ff;
					zona=tolower(getche());
					toupper(zona);
               val_zona(zona,'a','b','c');
               //calc_zona(zona,metro);
					switch(zona)//quito ; sino no entra a la funcion switch
					{

						case 'A':
								imp=(float)metro*A*.005;
								m1=metro;
								break;
						case 'B':
								imp=(float)metro*B*.005;
								m2= metro;
                        break;
						case 'C':
								imp=(float)metro*C*.005;
								m3=metro;
								break;
					}

               flag=1;
               pf("\nEl impuesto a pagar es %d",imp);
          //  }

					if(flag==1 && mximp<imp)
					{
						flag=1;
						mximp=imp;
						strcpy(mxnomb,nomb);
					}
               if(mximp<imp)
					{
						flag=1;
						mximp=imp;
						strcpy(mxnomb,nomb);
					}

            	pf("\nDesea ingresar otra propiedad mas? s/n: ");
               ff;
					resp=tolower(getche());
					while(resp!='s' && resp!='n')
               {
						pf("Re Ingrese");
						resp=tolower(getch());
					}
            }while(resp!='n');
            break;
			case 2:
         	clrscr();
				if(flag==0)//agrego otro = asi puede comparar
					pf("No ha ingresado información, vuelve al menu de opciones");
				else
				{
					pf("1-MOSTRAR NOMBRE DE LA PROPIEDAD QUE MAS PAGA");
					pf("\n2-MOSTRAR LA ZONA QUE MENOS METROS TIENE EDIFICADOS\n\n");
               sc("%d",&rta);
					switch(rta)
					{
						case 1:
                  		pf("\nel sr. %c es el que mas paga en el municipio",mxnomb);//corrijo  y saco &
								break;
						case 2:
								if(m1<m2 && m1<m3)
									pf("\nLa zona 1 es la de menos metros edificados");
								if(m2<m1 && m2<m3)
									pf("\nLa zona 2 es la de menos metros edificados");
								if(m3<m2 && m3<m1)
									pf("\nLa zona 3 es la de menos metros edificados");
								break;

					}
				}
				getch();
				break;
			case 3:
				pf("Hasta luego");
				break;
			default:
				pf("Ha ingresado un valor no esperado para el menu de opciones");
				break;
			getch();
      }
	}
   while(op!=3);
}



int menu()
{
	int op;
   pf("\nMENU DE OPCIONES\n1-CARGAR DATOS\n2-MOSTRAR\n3-SALIR\nIngrese opcion: ");
   sc("%d",&op);
   return op;
}

char val_zona(char z,char a,char b,char c)
{

   while (z!='a' && z!='b' && z!='c')
   {
   	pf("\nError, Reingrese zona A, B o C: ");
      ff;
		z=tolower(getche());
   }
   return z;
}

/*char clac_zona(char a, char b)
{
   char imp;
   int m1, m2, m3,impuesto;
   float imp;
 	switch(a)
					{

						case 'A':
								imp=(float)b*A*.005;
								m1=metro;
								break;
						case 'B':
								imp=(float)b*B*.005;
								m2= metro;
                        break;
						case 'C':
								imp=(float)b*C*.005;
								m3=metro;
								break;
					}

   impuesto=imp;
   return impuesto;
}*/
