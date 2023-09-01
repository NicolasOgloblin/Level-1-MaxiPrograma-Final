# Level-1-MaxiPrograma-Final

class Program
{
    static void Main(string[] args)
    {
        /*TP Final Nivel 1 : 
            Hacer un programa que permita ingresar una lista de números que corta cuando se ingresa un cero. 
            A partir de dichos datos informar:

                a. El mayor de los números pares.
                b. La cantidad de números impares.
                c. El menor de los números primos.

            Nota: evaluar el uso de una función que analice si un número dado es primo o no y 
            que devuelva true o false según corresponda.*/

            int n;
            int contadorImpar=0;
            int contadorPrimos=0;
            int primoMin=0;
            int contadorPar=0;
            int parMax=0;
                
            Console.WriteLine("Ingrese un número: ");
             n=int.Parse(Console.ReadLine());

            while (n!=0)
            {
                
                
                //A
                if(esPar(n)){
                    if(contadorPar==0){
                        parMax=n;
                        contadorPar++;

                    }
                    else if(n > parMax)
                        parMax=n;

                }
                //B
                if(esImpar(n))
                    contadorImpar++;

                //C
                if(esPrimo(n)){
                    if (contadorPrimos==0){
                        primoMin=n;
                        contadorPrimos++;
                    }else if (n<primoMin)
                        primoMin=n;
                }
                Console.WriteLine("Ingrese otro: ");
                n=int.Parse(Console.ReadLine());
            }

            //Punto A
            if(contadorPar==0)
            Console.WriteLine("No hubo números pares");
            else
            Console.WriteLine("El número par máximo es:  " + parMax);

            //Punto B
            if (contadorImpar==0)
            Console.WriteLine("No hubo números impares");
            else
            Console.WriteLine("La cantidad de impares es:  " + contadorImpar);

            //Punto C
            if (contadorPrimos == 0)
                Console.WriteLine("No hubo números primos" );
            else
            Console.WriteLine("El primo mínimo es:" + primoMin );
    }   

            //A
            static bool esPar (int n){
                if(n % 2 == 0)
                    return true;
                else 
                    return false;
            }


            //B
            static bool esImpar (int n){
                if(n<0)
                    n=n*-1;
                if (n % 2 == 1)
                    return true;
                else 
                    return false;
            }


            //C
            static bool esPrimo (int n){
                int contador = 0;
                for (int i =1 ; i <= n; i++){
                        if(n%i==0)
                            contador++;
                }
                if(contador == 2)
                    return true;
                else 
                    return false;
            }
            

}
