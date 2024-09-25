# Parcial_DataEstructures-2024-2
Data structures - 1st exam
- Pregunta 1.

R/: 
1) Es necesario para poder aumentar la capacidad actual del vector para que asi los datos almacenados no estén dispersos en la memoria, por eso, tambien al momento de hacer un resize() se le asigna un nuevo espacio en la memoria al vector con un mayor tamaño para luego eliminar el vector anterior, asi, poder ahorrando tiempo. Y es necesario seguir ingresando datos  por el espacio que puede llegar a sobrar en vector, asi no se desperdiciará memoria.
No es mejor ya que aumentaria la complejidad al estar buscando registros en diferentes lugares de la memoria. Además, como se dijo anterioremente, conlleva a un desgaste mayor de memoria
que solo almacenando un arreglo en un espacio de memoria.
2) 

- Pregunta 2.

  - Para la capacidad final del vector x será de 10240.
  Este vector tendrá un desperdicio de 240 espacios en el vector.

  - Para la capacidad final del vector y será de 11568.
  Este vector tendrá un desperdicio de 1568 espacios en el vector.

  - Para la capacidad final del vector z será de 12800.
  Este vector tendrá un desperdicio de 2800 espacios en el vector.


El vector x resulto siendo el más eficiente para el programa, ya que no presentó un desperdicio de memoria tan grande como el de los otros vectores,
llegando a estos tener 5 veces más desperdicio de memoria en comparación al vector x. A pesar de que el vector z incurra a un tiempo menor de ejecución
debido a su capacidad inicial, llega a ser el vector con mayor desperdicio.

- Pregunta 3

  1) 
```
  template <typename T> class list {
private:
    class Node {
    T data;
    Node* Connect1;
    Node* Connect2;
    Node* Connect3;
    Node* Connect4;
    public:
      Node() : data(), Connect1(nullptr), Connect2(nullptr), Connect3(nullptr), Connect4(nullptr) {}
      Node(T d) : data(d), Connect1(nullptr), Connect2(nullptr), Connect3(nullptr), Connect4(nullptr) {}
      void setConnect1(Node* n) { Connect1 = n; } // sera un next en una nodo normal
      void setConnect2(Node* n) { Connect2 = n; } // sera un prev en un nodo normal
      void setConnect3(Node* n) { Connect3 = n; } // posible conexion con alguna ciudad
      void setConnect4(Node* n) { Connect4 = n; } // posible conexion
      Node* getC1() { return Connect1; }
      Node* getC2() { return Connect2; }
      Node* getC3() { return Connect3; }
      Node* getC4() { return Connect4; }
      T getData() { return data; }
      };

private:   
    Node* first;
    Node* last;
    unsigned int NumberOfCities;

public:
  list() : first(nullptr), last(nullptr), size(0) {}
  unsigned int getCities() const { return NumberOfCities; }
  bool empty() const { return first == nullptr; }
  //Suponiendo que las ciudades están consecutivas, se tomará como lista circular
  void push(T elem) {
    Node* n = new Node(elem);
        if (empty()) {
            first = n;
        } else {
            last->setConnect1(n);
            n->setConnect2(last);
            n->setConnect1(first);
            first->setConnect2(n);
        }
        last = n;
        NumberOfCities++;
    }
  void connect(T cityfrom, T cityTo) {
    if(Connect3 == nullptr) {

    }
  }

};
```
