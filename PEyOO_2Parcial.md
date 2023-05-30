<h1 align="center">Programación Estructurada y Orientada a Objetos en Dart (Segunda Parcial)</h1>

## **_Clases_**
Una **_clase_** es un elemento característico de la Programación Orientada a Objetos que funciona como una plantilla donde se definen las características
y los comportamientos que tendra una entidad.

En Dart, las clases se crean usando la palabra reservada **_"Class"_** y el nombre que le asignamos a la clase _siempre debe de empezar con mayúscula._ El siguiente es un ejemplo
de cómo crear una clase, la cual se llamará "Persona":
```dart
void main(List<String> args) {
  print("Clase: ${Persona().runtimeType}");
}
class Persona {}
```
#### **Salida:**
```
Clase: Persona
```


Ahora que sabemos cómo podemos crear una clase, ahora haremos una instancia de clase. Las instancias son las características y atributos que una entidad tiene y
se encuentran dentro de la clase.
usaremos el siguiente ejemplo: Crearemos una clase Estudiante con los atributos 'nombre' y 'edad', nuestra instancia de clase estara en nuestro archivo main.
```dart
void main(){
// instancia 
var e1 = Estudiante();
Estudiante e2 = Estudiante();
e1.nombre = "Juan";
e1.aNacimiento = 1990;
print(e1);
print(e2);
e2.nombre = "Pedro";
e2.aNacimiento = 1941;

print(e1.nombre);
print(e1.aNacimiento);
print(e2.nombre);
print(e2.aNacimiento);
reporte(e1);
reporte(e2);
}

class Estudiante{
  // atributos 
  String nombre = "";
  int? aNacimiento;
}

void reporte(Estudiante e ) {
  print("Nombre: ${e.nombre}");
  print("Edad: ${2023 - e.aNacimiento!}");
}
```
#### **Salida:**
```
Instance of 'Estudiante'
Instance of 'Estudiante'
Juan
1990
Pedro
1941
Nombre: Juan
Edad: 33
Nombre: Pedro
Edad: 82
```

### Ejemplo de clases (19 de abril 2023).
Crear una clase animal que tenga dos propiedades, nombre y sonido
```dart
void main(List<String> args) {
  animal perro = animal();
  perro.nombre = "Firulais";
  perro.sonido = "Guagua";
  animal gato = animal();
  gato.nombre = "Garfiel";
  gato.sonido = "Miau";
  animal Pato = animal();
  Pato.nombre = "Donald";
  Pato.sonido = "Cuac";
}

class animal{
  String nombre = "";
  String sonido = "";
}

void reporte(animal a ) {
  print("Nombre: ${a.nombre}");
  print("Sonido: ${a.sonido}");
}
```

### Ejemplo (clase 20 de abril 2023):
```dart
import 'animal.dart';
void main(List<String> args) {
  Animal a1 = new Animal('Gato', 'Miau');
  Animal a2 = new Animal('Perro', 'Guau'); 

  print(a1.name);
  print(a1.sonido);
  print(a2.name);
  print(a2.sonido);

  a1.name = "Perro";
  a1.sonido = "Guau";
  a2.name = "Gato";
  a2.sonido = "Miau";

  Animal a3 = new Animal("Pato", "cuac");
  print(a3.name);
  print(a3.sonido);
} 
```
#### 'animal.dart'
```dart
class Animal {
  String? name;
  String? sonido;
  Animal(String name, String sonido) {
    this.name = name;
    this.sonido = sonido;
    print('Constructor de Animal');
  }
}
```

#### Salida:
```
Constructor de Animal
Constructor de Animal
Gato
Miau
Perro
Guau
Constructor de Animal
Pato
cuac
```

###








