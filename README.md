# PROYECTO-ICC
def inicializar(lista):

 Prendas=["Polos","Camisas","Cuellos"]

 for i in range(3):

   a=int(input("Ingrese la cantidad de "+Prendas[i]+": "))

   b=float(input("Ingrese el peso por prenda de "+Prendas[i]+": "))

   lista.append((a,b,a*b))

 return lista


def Calculo_tiempos(lista,b):

 if b==1:

   Vconfeccion=[0.20,0.50,0.05]

 if b==2:

   Vconfeccion=[0.22,0.33,0.04]

 if b==3:

   Vconfeccion=[0.25,0.50,0.05]

 Ttiempo=0

 for i in range(len(lista)):

   Ttiempo=(lista[i][2]*(1/1+1/10+1/20+1/Vconfeccion[i]))+Ttiempo

 return Ttiempo


def Calculo_materia_prima(lista,b):

 Mprima=0

 for i in range (len(lista)):

   Mprima=lista[i][2]/b+ Mprima

 return Mprima


def Calculo_ganancia_esperada(lista,b):

 if b==1:

   Precio=[30,50,5]

 if b==2:

   Precio=[60,75,10]

 if b==3:

   Precio=[60,80,15]

 Ingresos=0

 Costoventa=Calculo_materia_prima(lista,b)*10

 for i in range(len(lista)):

   Ingresos=(lista[i][0]*Precio[i])+Ingresos

 return Ingresos-Costoventa



def main():

 Jersey=[]

 Pique=[]

 Franela=[]

 print("\nJersey")

 Jersey=inicializar(Jersey)

 print("\nPique")

 Pique=inicializar(Pique)

 print("\nFranela")

 Franela=inicializar(Franela)

 print("\n\n")

 print("\nTiempo total de producción de Jersey: ",round(Calculo_tiempos(Jersey,1),2))

 print("\nTiempo total de producción de Pique: ",round(Calculo_tiempos(Pique,2),2))

 print("\nTiempo total de producción de Franela: ",round(Calculo_tiempos(Franela,3),2))

 print("\nCantidad de materia prima: ", round(Calculo_materia_prima(Jersey,0.7)+Calculo_materia_prima(Pique,0.5)+Calculo_materia_prima(Franela,0.3),2))

 print("\nGanancias esperadas de Jersey: ", round(Calculo_ganancia_esperada(Jersey,1),2))

 print("\nGanancias esperadas de Pique: ",round(Calculo_ganancia_esperada(Pique,2),2))

 print("\nGanancias esperadas de Franela: ",round(Calculo_ganancia_esperada(Franela,3),2))


main()
