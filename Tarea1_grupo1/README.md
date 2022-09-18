># Algoritmos 2022 - 2 ( Grupo 2 )
>
>## Tarea 1
>Se complement� el c�digo de implementaci�n de un �rbol binario en Python3, se genera un �rbol a trav�s de entradas de usuario y se propne un m�todo de graficaci�n m�s claro para �sta estructura de datos
>
>### Complejidad de impresi�n de arbol:
>

```python
def printBinaryTree(root, space, height): 	# O(n)
		# It is necesary to iterate over all nodes in tree, regardless it's a 
		# recursive algorithm. Also note that there is not a constant factor
		# which specifies how many nodes are in a subtree after a recursive
		# call (since tree can be unbalanced)
 
    # Base case
    if root is None:			 	# O(1)
        return

    # increase distance between levels
    space += height				# O(1)
 
    # print right child first
    printBinaryTree(root.right, space, height)  # O(n) [ O(n-1) en el peor de los casos: un arbol secuencial 
						# en orden ascendente por derecha ]
    print()
 
    # print the current node after padding with spaces

    for i in range(height, space):		# O( space-height ) m = space, p = height => O( m - p) 
        print(' ', end='')			# Sin embargo, no depende del n�mero de datos en el arbol, 
						# se considera O(1)
 
    print(root.data, end='')
 
    # print left child
    print()
    printBinaryTree(root.left, space, height)	# O(n) [ O(n-1) en el peor de los casos: un arbol secuencial 
						# en orden ascendente por izquierda ]
```
>La complejidad del algoritmo de impresi�n es de O(n) en general si se consideran height y space constantes para n incremental