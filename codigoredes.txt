import timeit

class Grafo:

    def __init__(self, vertices):
        self.V = vertices   # Nro de vertice
        self.grafo = []     # Arreglo de aristas

    # Agregar aristas siendo o el origen d la Distancia y p el peso
    def agr_arista(self, o, d, p):
        self.grafo.append([o, d, p])

    # Imprimir la solucion
    def print_solucion(self, dist):
        print("Distancia de vertice desde el origen")
        for i in range(self.V):
            print("{0}\t\t{1}".format(i, dist[i]))

    def vector_distancia(self, origen):
        inicio = timeit.default_timer()
        # Paso 1: Se llena el arreglo de distancia y elarreglo del predecesor
        dist = [float("Inf")] * self.V
        # definir la distancaia del vertice origen
        dist[origen] = 0

        # Paso 2: Relajar aristas |V| - 1 veces
        for _ in range(self.V - 1):
            for o, d, p in self.grafo:
                if dist[o] != float("Inf") and dist[o] + p < dist[d]:
                    dist[d] = dist[o] + p

        # Paso 3 : Detectar ciclo negativo
        # Si el valor cambia entonces hay un ciclo negativo y no se puede encontrar las menores distancias
        for o, d, p in self.grafo:
            if dist[o] != float("Inf") and dist[o] + p < dist[d]:
                print("El grafo contiene ciclo negativo")
                return

        # No se encontro un ciclo negativo
        # Imprimir los arreglos de distancia y los predecesor
        self.print_solucion(dist)
        fin = timeit.default_timer()
        print('Tiempo: ', fin - inicio)  



g = Grafo(20)

g.agr_arista(0,1,8)
g.agr_arista(1,0,8)
g.agr_arista(0,18,4)
g.agr_arista(18,0,4)
g.agr_arista(18,17,11)
g.agr_arista(17,18,11)
g.agr_arista(17,16,25)
g.agr_arista(16,17,25)
g.agr_arista(16,15,9)
g.agr_arista(15,16,9)
g.agr_arista(15,14,21)
g.agr_arista(14,15,21)
g.agr_arista(14,13,14)
g.agr_arista(13,14,14)
g.agr_arista(13,12,4)
g.agr_arista(12,13,4)
g.agr_arista(12,11,25)
g.agr_arista(11,12,25)
g.agr_arista(11,10,15)
g.agr_arista(10,11,15)
g.agr_arista(10,9,22)
g.agr_arista(9,10,22)
g.agr_arista(9,8,18)
g.agr_arista(8,9,18)
g.agr_arista(8,7,7)
g.agr_arista(7,8,7)
g.agr_arista(7,6,26)
g.agr_arista(6,7,26)
g.agr_arista(6,5,21)
g.agr_arista(5,6,21)
g.agr_arista(5,4,4)
g.agr_arista(4,5,4)
g.agr_arista(4,3,19)
g.agr_arista(3,4,19)
g.agr_arista(3,2,8)
g.agr_arista(2,3,8)
g.agr_arista(2,1,17)
g.agr_arista(1,2,17)
g.agr_arista(0,19,19)
g.agr_arista(19,0,19)
g.agr_arista(1,19,24)
g.agr_arista(19,1,24)
g.agr_arista(2,19,10)
g.agr_arista(19,2,10)
g.agr_arista(3,19,1)
g.agr_arista(19,3,1)
g.agr_arista(4,19,19)
g.agr_arista(19,4,19)
g.agr_arista(5,19,4)
g.agr_arista(19,5,4)
g.agr_arista(6,19,22)
g.agr_arista(19,6,22)
g.agr_arista(7,19,7)
g.agr_arista(19,7,7)
g.agr_arista(8,19,22)
g.agr_arista(19,8,22)
g.agr_arista(9,19,8)
g.agr_arista(19,9,8)
g.agr_arista(10,19,17)
g.agr_arista(19,10,17)
g.agr_arista(11,19,22)
g.agr_arista(19,11,22)
g.agr_arista(12,19,15)
g.agr_arista(19,12,15)
g.agr_arista(13,19,22)
g.agr_arista(19,13,22)
g.agr_arista(14,19,13)
g.agr_arista(19,14,13)
g.agr_arista(15,19,4)
g.agr_arista(19,15,4)
g.agr_arista(16,19,19)
g.agr_arista(19,16,19)
g.agr_arista(17,19,12)
g.agr_arista(19,17,12)
g.agr_arista(18,19,19)
g.agr_arista(19,18,19)





g.vector_distancia(0)
