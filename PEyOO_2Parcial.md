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

### Clase 19 de abril 2023 (también ejemplos anteriores):
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


## Clase 20 de abril 2023:
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

## Clase 26 de abril 2023:  
  
#### **_Ejercicio 1_**
Crearemos un archivo donde crearemos una clase con el nombre _Animal_, la cual debe contener las características de _'nombre'_ y _'sonido'_.
En un segundo archivo crearemos nuestro archivo _main_, que se encargara de ejecutar nuestro programa. Es importante que en nuestro archivo main 
importemos nuestro archivo de clase. En nuestro archivo main podemos ver un **_import 'animal.dart'_** lo cual indica que nuestra clase se ha importado a
nuestro archivo principal.
#### **archivo de clase 'animal.dart'
```dart
class Animal {
  String? nombre;
  String? sonido;
  Animal(String nombre, String sonido) {
    this.nombre = nombre;
    this.sonido = sonido;
    print('Constructor de Animal');
  }
}
```
#### **archivo principal 'main.dart'
```dart
import 'animal.dart';
void main(List<String> args) {
  Animal a1 = new Animal('Perro', 'Guau');
  print(a1.nombre);
  print(a1.sonido);
  print("-"*20);
  Animal a2 = new Animal('Gato', 'Miau');
  print(a2.nombre);
  print(a2.sonido);
  print("-"*20);
  Animal a3 = new Animal('Pato', 'Cuac');
  print(a3.nombre);
  print(a3.sonido);
  print("-"*20);
}
```
#### **Salida:**
```
Constructor de Animal
Perro
Guau
--------------------
Constructor de Animal
Gato
Miau
--------------------
Constructor de Animal
Pato
Cuac
--------------------
```

#### **_Ejercicio 2_**
En este ejercicio veremos los **_Métodos._** Los _métodos_ son funciones que nos ayudan a poder manipular los métodos de las clases.
En nuestro ejercicio calcularemos la edad de una persona mediante su año de nacimiento. Crearemos un archivo llamado **_persona.dart_**, el cual va a contener nuestra clase _Persona_, donde también incluiremos nuestro método, el cual vamos a usar para calcular la edad de una persona por medio de su año de nacimiento.
#### **_Archivo de clase 'persona.dart'_**
```dart
class Persona {
  String? name;
  int? a_nacimiento;

  Persona(String name, int a_nacimiento) {
    this.name = name;
    this.a_nacimiento = a_nacimiento; 
  }

  //Metodo para calcular la edad
  void getEdad (int aActual){
    print('La edad de ${this.name} es ${aActual - this.a_nacimiento!}');
  }
}
```

#### **_Archivo principal: 'main.dart'_**
```dart
import 'persona.dart';
void main(List<String> args) {
  Persona p1= new Persona('Luis', 2004);
}
```

#### **_Salida:_**
```
La edad de Luis es 18.
```

## Clase 26 de abril 2023:
En esta clase aprendimos dos funciones nuevas: **_los setters y getters_**. Los _setters_ nos ayudan a fijar el valor de un atributo, los _getters_ nos ayudan a acceder al valor del atributo. Estas funciones se usan para poder obtener y cambiar valores fuera de la clase.

#### **_Ejercicio 1_**
Crear un archivo con el nombre **_shape.dart_** en el que se incluiran las propiedades base, altura, un método para obtener el area y otro para calcularla, además de un set para poder ingresar los valores y un get para poder obtener la base y la altura de una figura.  
En un segundo archivo tendremos nuestro _main_ que nos ayudará a poder ejecutar nuestro programa, además será donde la forma por la que podremos cambiar los valores de base y altura, y leer estos datos.  
#### **_Archivo de clase 'shape.dart'_**  
```dart
class Shape {
  int? _base;
  int? _altura;

  Shape(this._base, this._altura);

  int getArea() {
    return _calcularArea();
  }

  int _calcularArea() {
    return _base! * _altura!; //Logica de negocio: la forma de resolver
  }

//setters
void set base(int? base) => _base = base;
void set altura(int? altura) => _altura = altura;
//getters
int? get base => _base;
int? get altura => _altura;
}
```
#### **_Archivo principal: 'main.dart'_**
```dart
import 'shape.dart';
void main(List<String> args) {
  Shape f1 = Shape(10, 5);
  print(f1.getArea());
  f1.base = 15;
  f1.altura = 10;
  print(f1.getArea());
  print('''
El area del rectangulo con base ${f1.base}
y altura ${f1.altura} es ${f1.getArea()}
''',);
}
```
#### **_Salida:_**
```dart
50
150
El area del rectangulo con base 15
y altura 10 es 150
```  

#### **_Ejercicio 2_**
Crearemos un archivo llamado **_vehiculo.dart_** el cual tendra las características de 'marca', 'nombre', 'color' y 'transmisión'. También lleva los _setters_ y _getters_. En un segundo archivo haremos nuestro _main_ el cual nos ayudará a poder usar nuestro código.
#### **_Archivo de clase: 'vehiculo.dart'_**
```dart
class Vehicle {
  String _brand;
  String _name;
  String _color;
  String _transmition;

  Vehicle(
    this._brand,
    this._name,
    this._color,
    this._transmition,
  );

  void set brand(String brand) => this._brand = brand;
  void set name(String name) => this._name = name;
  void set color(String color) => this._color = color;
  void set trasmition(String trasmition) => this._transmition = trasmition;
  
  String get brand => this._brand;
  String get name => this._name;
  String get color => this._color;
  String get transmition => this.transmition;

  void showVehicle() {
    print(
      '''\n
      Marca: ${this._brand}
      Nombre: ${this._name}
      Color: ${this._color}
      Transmision: ${this._transmition}
      ''',
      );
  }
}
```
#### **_Archivo principal: 'main.dart'_**
```
import 'vehiculo.dart';

void main(List<String> args) {
  Vehicle v1 = Vehicle(
    'Toyota',
    'Corolla',
    'Rojo',
    'Automatico',
  );

  Vehicle v2 = Vehicle(
    'Honda',
    'Civic',
    'Azul',
    'Manual',
  );

  List<Vehicle> vehicles = [v1, v2];
  
  vehicles.forEach(
    (vehicle) => vehicle.showVehicle(),
    );
} 
```
#### **_Salida:_**
```
 Marca: Toyota
      Nombre: Corolla
      Color: Rojo
      Transmision: Automatico
      

      Marca: Honda
      Nombre: Civic
      Color: Azul
      Transmision: Manual
```

## Clase 03 de mayo 2023:







