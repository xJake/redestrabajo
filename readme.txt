Instrucciones :
Como no hay direccion se repite el origen y distancia 2 veces obteniendo 2 caminos de mismo peso que equivalen a un solo camino sin direccion
por lo que se debe repetir el origen y destino ejemplo:
g.agr_arista(1, 2 ,5)
g.agr_arista(2, 1,5)
del 1 al 2 y del 2 al 1 tienen el mismo peso
el formato es 
g.agr_arista(origen, destino, peso) para agregar aristas