# **_Programación Estructurada y Orientada a Objetos (Segunda Parcial)_**  


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
```dart
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
#### **_Ejercicio 1:_**
Este ejercicio se realizó en varias ocaciones, con la finalidad de poder mejorar el código.
#### **_Código 1:_**
```dart
void main(List<String> args) {
  Mueble m1 = Mueble();
  print(m1.counter);
  print(Mueble.counterStatic);
  Mueble m2 = Mueble();
  print(m2.counter);
  print(Mueble.counterStatic);
}
class Mueble {
  //propiedad de instancia
  int counter = 0;

  //propiedad de clase
  static int counterStatic = 0;
  Mueble() {
    counter++;
    counterStatic++;
  }
  //Método de instancia
}
```
#### **_Salida:_**
```
1
1
1
2
```

#### **_Código 2:_**
```dart
void main(List<String> args) {
  Mueble m1 = Mueble();
  print("Propiedad de instancia m1: ${m1.counter}");
  print("Propiedad de clase Mueble: ${Mueble.counterStatic}");
  print("-" * 28);
  Mueble m2 = Mueble();
  print("Propiedad de instancia m2: ${m2.counter}");
  print("Propiedad de clase Mueble: ${Mueble.counterStatic}");
}
class Mueble {
  //propiedad de instancia
  int counter = 0;

  //propiedad de clase
  static int counterStatic = 0;
  Mueble() {
    counter++;
    counterStatic++;
  }
  //Método de instancia
  void showCounter() {
    print("Propiedad de instancia: $counter");
  }

  //Método de clase
  static void showCounterStatic() {
    print("Propiedad de clase: $counterStatic");
  }
}
```
#### **_Salida:_**
```
Propiedad de instancia m1: 1
Propiedad de clase Mueble: 1
----------------------------
Propiedad de instancia m2: 1
Propiedad de clase Mueble: 2
```
#### **_Código 3:_**
```dart
void main(List<String> args) {
  Mueble m1 = Mueble();
  m1.showCounter();
  Mueble.showCounterStatic();
  print("-" * 28);
  Mueble m2 = Mueble();
  m2.showCounter();
  Mueble.showCounterStatic();
}
class Mueble {

  //propiedad de instancia
  int counter = 0;

  //propiedad de clase
  static int counterStatic = 0;
  Mueble() {
    counter++;
    counterStatic++;
  }
  //Método de instancia
  void showCounter() {
    print("Propiedad de instancia: $counter");
  }

  //Método de clase
  static void showCounterStatic() {
    print("Propiedad de clase: $counterStatic");
  }
}
```
#### **_Salida:_**
```
Propiedad de instancia m1: 1
Propiedad de clase Mueble: 1
----------------------------
Propiedad de instancia m2: 1
Propiedad de clase Mueble: 2
```  
#### **_Ejercicio 2_**
Crear la clase animal con la propiedad tipo de animal y cantidad. Crear un método de instancia que muestre el tipo de animal y la cantidad. Crear un metodo de clase que muestre la cantidad de tipos de animales de la granja. Crear instancias de la clase animal y mostrar la cantidad de tipos de animales de la granja. ¿Cuántos animales hay en la granja?
#### **_Código:_**
```dart
void main(List<String> args) {
  var animales = [
    Animal('vaca', 10),
    Animal('cerdo', 20),
    Animal('pollo', 50),
  ];
  
  Animal.mostrarCantidadTipos(animales);
  
  animales.forEach((animal) => animal.mostrar());
  
  var cantidadAnimales = animales.fold(0, (total, animal) => total + animal.cantidad);
  print('Hay un total de $cantidadAnimales animales en la granja.');
}

class Animal {
  String tipo;
  int cantidad;
  
  Animal(this.tipo, this.cantidad);
  
  void mostrar() {
    print('Hay $cantidad $tipo en la granja.');
  }
  
  static void mostrarCantidadTipos(List<Animal> animales) {
    var tipos = <String>{};
    animales.forEach((animal) => tipos.add(animal.tipo));
    print('Hay ${tipos.length} tipos de animales en la granja.');
  }
}
```  

#### **_Salida:_**
```
Hay 3 tipos de animales en la granja.
Hay 10 vaca en la granja.
Hay 20 cerdo en la granja.
Hay 50 pollo en la granja.
Hay un total de 80 animales en la granja.
```
## Clase 04 de mayo 2023:
En esta clase aprendimos sobre las herencias en Dart. Las _herencias_ no son nada más que apoyo para poder reutilizar una parte del código que ya hemos realizado. En Dart se usa la palabra reservada **_extends_** para heredar una clase.  

En esta actividad se usaran un total de cinco archivos distintos, uno es para nuesto archivo _main_ que nos ayudará a poder ejecutar nuestro programa, los otros cuatro los usaremos para las clases los archivos llevaran los nombres _'animal.dart'_, _'caballo.dart'_, _'pato.dart'_, _'vaca.dart'_. El archivo _animal.dart_ será nuestra clase padre y heredaremos las demás clases con esta.

#### **_Archivo de clase: 'animal.dart':_**
```dart
class Animal {
  String? _breed;
  int? _quantity;

  Animal(this._breed, this._quantity);

  set breed(String? breed) => _breed = breed;
  set quantity(int? quantity) => _quantity = quantity;

  void showProperties() {
    print('Breed: $_breed');
    print('Quantity: $_quantity');
  }
}
```
#### **_Archivo de clase: 'caballo.dart':_**
```dart
import 'animal.dart';

class Caballo extends Animal {
  String? _color_crin;
  
  Caballo(super._breed, super._quantity, this._color_crin);

  int get quantity => null;
  set _quantity (int quantity) {}

    @override
  void showProperties() {
    super.showProperties();
    print('Color de crin: $_color_crin');
  }
 } 
```
#### **_Archivo de clase: 'pato.dart':_**
```dart
import 'animal.dart';

class Pato extends Animal {
  String? _tipo_pico;

  set _quantity(int quantity) {}

  @override
  void showProperties() {
    super.showProperties();
    print('Tipo de pico: $_tipo_pico');
  }

  Pato(super._breed, super._quantity, this._tipo_pico);
} 
```
#### **_Archivo de clase: 'vaca.dart':_**
```dart
import 'animal.dart';
class Vaca extends Animal {
  String? _color_manchas;

  Vaca(super._breed, super._quantity, this._color_manchas);

  @override
  void showProperties() {
    super.showProperties();
    print('Color de manchas: $_color_manchas');
  }
}
```


Nuestro archivo _main_ lo modificamos un par de veces, estos son los distintos códigos. Las mejoras fueron para poder hacer mejor uso de la optimización del código, tener un programa más limpio.

#### **_archivo: 'main.dart' (Código 1)_**
```dart
import 'pato.dart'; import 'animal.dart'; import 'caballo.dart'; import 'vaca.dart';

void main(List<String> args) {
  Pato pato1 = Pato();
  pato1.breed = 'Pekines';
  pato1.quantity = 10;
  pato1.tipo_pico = 'curvo';
  pato1.showProperties();
  print("-"*20);
  Animal a1 = Animal();
  a1.breed = 'Animal';
  a1.quantity = 100;
  a1.showProperties();
  print("-"*20);
  Caballo c1 = Caballo();
  c1.breed = 'Azteca';
  c1.quantity = 50;
  c1.tipo_melena = 'Blanca';
  c1.showProperties();
  print("-"*20);
  Vaca v1 = Vaca();
  v1.breed = 'Holstein';
  v1.quantity = 30;
  v1.color_manchas = 'negras';
  v1.showProperties();
  print("-"*20);
}
```
#### **_Salida:_**
```
Pato breed: Pekines
Tipo de pico: Curvo
Cantidad: 10
____________________
Caballo breed: Azteca
Color de melena: Blanca
Cantidad: 50
____________________
Vaca breed: Holstein
Color de manchas: Negras
Cantidad: 30
____________________
```
#### **_archivo: 'main.dart' (Código 1)_**
```dart
import 'pato.dart'; import 'animal.dart'; import 'caballo.dart'; import 'vaca.dart';

void main(List<String> args) {
  Pato pato1 = Pato('Pekines', 30, 'Curvo');
  pato1.showProperties();
  pato1.quantity = 60;
  print("-"*20);
  Animal a1 = Animal('Animal', 100);
  a1.showProperties();
  print("-"*20);
  Caballo c1 = Caballo('Azteca', 50, 'Blanco');
  c1.showProperties();
  c1.quantity = 100;
  print(c1.quantity);
  print("-"*20);
  Vaca v1 = Vaca('Holstein', 20, 'Cafe');
  v1.showProperties();
  print("-"*20);
} 
```
#### **_Salida:_**
```
Breed: Pekines
Quantity: 30
Tipo de pico: Curvo
--------------------
Breed: Animal
Quantity: 100
--------------------
Breed: Azteca
Quantity: 50
Color de crin: Blanco
```

## **_Clase 17 de mayo 2023:_**
```dart
void main(List<String> args) {
  final vehiculo = Vehiculo('Rojo', 100);
  vehiculo.showVehiculo();
  print('Maxima velocidad: ${vehiculo.maxVelocidad()}');

  final Carro carro = Carro('Azul', 200, 'Toyota');
  carro.showVehiculo();
  print('Maxima velocidad: ${carro.maxVelocidad()}');

  final Carro carroTipo = Carro.tipo('Azul', 200, 'Toyota', 'Sedan');
  carroTipo.showTipo();
  print('---------');
  carroTipo.showTipo2();
  print('Maxima velocidad: ${carroTipo.maxVelocidad()}');
}


class Vehiculo {
  String? _color;
  int? _velocidad;

  Vehiculo(this._color, this._velocidad){
    print('Constructor padre Vehiculo');
  }

  set color(String? color) => this._color = color;
  set velocidad(int? velocidad) => this._velocidad = velocidad;

  String? get color => _color;
  int? get velocidad => _velocidad;

  int maxVelocidad() => _velocidad! *2;

  void showVehiculo(){
    print('Color: $_color');
    print('Velocidad: $_velocidad');
  }

}

class Carro extends Vehiculo{
  String? _marca;
  String? _tipo;

  Carro(super._color, super._velocidad, this._marca) {
    print('Constructor hijo Carro');
  }

    Carro.tipo(super._color, super._velocidad, this._marca, this._tipo) {
    print('Constructor nombrado tipo hijo Carro');
  }

  @override 
  void showVehiculo() {
    super.showVehiculo();
    print('Marca: $_marca');
  }

  void showTipo() {
    super.showVehiculo();
    print('Marca: $_marca');
    print('Tipo: $_tipo');
  }

  void showTipo2() {
    this.showVehiculo();
    print('Tipo: $_tipo');
  }
}
```

#### **_Salida:_**
```
Maxima velocidad: 200
Constructor padre Vehiculo
Constructor hijo Carro
Color: Azul
Velocidad: 200
Marca: Toyota
Maxima velocidad: 400
Constructor padre Vehiculo
Constructor nombrado tipo hijo Carro
Color: Azul
Velocidad: 200
Marca: Toyota
Tipo: Sedan
---------
Color: Azul
Velocidad: 200
Marca: Toyota
Tipo: Sedan
Maxima velocidad: 400
```

## **_Clase 18 de mayo 2023:_**
**_Interfaces_**. Las _interfaces_ son los métodos definidos que existen para un objetos. En Dart no existe una sintaxis para declarar interfaces, pero usamos la palabra reservada **_extends_**.  
En el siguiente ejercicio crearemos una clase llamada _'Control Remoto'_ con las características subir y bajar volumen, después haremos tres diferentes clases, una de Televisión, otra para un Ipod y otra para un Radio. Estás clases usarán la interfaz de la clase _Control Remoto_.

#### **_Código:_**
```dart
void main(List<String> args) {
  ControlRemoto control = ControlRemoto();
  control.subirVolumen();
  control.bajarVolumen();

  Television tv = Television();
  tv.subirVolumen();
  tv.bajarVolumen();

  Ipod ipod = Ipod();
  ipod.subirVolumen();
  ipod.bajarVolumen();

  Radio radio = Radio();
  radio.subirVolumen();
  radio.bajarVolumen();
}


class ControlRemoto {
  void subirVolumen() {
    print('Subir Volumen');
  }

  void bajarVolumen() {
    print('Bajar Volumen');
  }
}

class Television implements ControlRemoto {
  @override
  void subirVolumen() {
    print('Subir Volumen de la TV');
  }

  void bajarVolumen() {
    print('Bajar Volumen de la TV');
  }
}

class Ipod implements ControlRemoto {
  @override
  void subirVolumen() {
    print('Subir Volumen del Ipod');
  }

  void bajarVolumen() {
    print('Bajar Volumen del Ipod');
  }
}

class Radio implements ControlRemoto {
  @override
  void subirVolumen() {
    print('Subir Volumen de la Radio');
  }

  void bajarVolumen() {
    print('Bajar Volumen de la Radio');
  }
}
```
#### **Salida:_**
```
Subir Volumen
Bajar Volumen
Subir Volumen de la TV
Bajar Volumen de la TV
Subir Volumen del Ipod
Bajar Volumen del Ipod
Subir Volumen de la Radio
Bajar Volumen de la Radio
```




