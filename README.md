# Ayuda
Hola, buenas tardes tengo duda en un proyecto escolar donde me piden sacar suma y promedio de un archivo .txt, pero se deben sumar las columnas ejemplo:
Pero lo necesito en lenguaje rubí o  Rust ayuda
#include <stdio.h> 
#include <stdlib.h>

/* Suma reales. 
El programa lee cadenas de caracteres de un archivo, detecta aquellas que 
-comienzan con nï¿½meros, los suma y calcula el promedio de los mismos. */

void sumypro(FILE *);	/*Prototipo de funciï¿½n*/

void main(void){
	FILE *ap;
	if ((ap=fopen("arc2.txt", "r")) !=NULL)
	{
		sumypro(ap);
		/*Se llama a la funcion sumypro. Se pasa el archivo ap como pï¿½rametro. */
		fclose(ap);
	}
	else
	printf("No se puede abrir el archivo");
}

void sumypro(FILE *ap1)
/* Esta funciï¿½n lee cadenas de caracteres de un archivo, detecta aquellas 
-que comienzan con nï¿½meros, y obtiene la suma y el promedio de dichos -nï¿½meros. */
{
	char cad[30];
	int i = 0;
	float sum = 0.0, r;
	while (!feof (ap1))
	{
		fgets(cad,30,ap1);	/*Se lee la cadena del archivo. */
		r = atof(cad);
		/* Recuerda que la funciï¿½n atof convierte una cadena de caracteres que 
		-contiene nï¿½meros reales a un valor de tipo d double. Si la cadena comienza 
		-con otro caracter o no contiene nï¿½meros, regresa 0 o el valor queda 
		-indefinido. */ 
		if (r)
		{
			i++;
			sum += r;
		}
	}
	printf("\nSuma: %.2f", sum);
	if (i)	/* Si el valor de i es distinto de cero, calcula el promedio. */ 
		printf("\nPromedio: %.2f", sum/i);
}
