<h1 align="center">PEyOO Proyecto (Segunda Parcial)</h1>
Crear un directorio de profesores y que contenga los datos de personas y negocios. Debe tener llenado automatico de la DB in memory las opciones CRUD, donde:C: Create, crear nuevos registros, R: Read, leer y presentar los registros de manera individual, por alumnos y/o profesores, U: Update, actualizar registros, D: Delete, eliminar registros.  

import 'dart:io';
 import 'dart:async';
void main(List<String> args) {
  var directorio = Directorio();
runZonedGuarded(() async {
  while (true) {
    print('--- MENÚ ---');
    print('1. Agregar profesor');
    print('2. Agregar alumno');
    print('3. Mostrar profesores');
    print('4. Mostrar alumnos');
    print('5. Salir');

    var opcion = stdin.readLineSync();
    if (opcion == '1') {
      agregarProfesores(directorio);
    } else if (opcion == '2') {
      agregarAlumnos(directorio);
    } else if (opcion == '3') {
      print('Profesores:');
      directorio.mostrarProfesores();
    } else if (opcion == '4') {
      print('Alumnos:');
      directorio.mostrarAlumnos();
    } else if (opcion == '5') {
      break;
    } else {
      print('Opción inválida. Por favor, elija una opción válida.');
    }
  }
}, (e, s) {
    print('Error: $e');
  });



  // Agregar profesores y alumnos
  agregarProfesores(directorio);
  agregarAlumnos(directorio);

  // Mostrar profesores y alumnos
  print('Profesores:');
  directorio.mostrarProfesores();

  print('Alumnos:');
  directorio.mostrarAlumnos();
}

void agregarProfesores(Directorio directorio) {
  while (true) {
    print('Ingrese los datos del profesor:');
    print('Nombre:');
    var name = stdin.readLineSync();
    print('Materia:');
    var materia = stdin.readLineSync();
    print('Fecha de nacimiento (Formato: yyyy-mm-dd):');
    var dateBirthStr = stdin.readLineSync();
    var dateBirth = DateTime.parse(dateBirthStr!);
    print('Correo electrónico:');
    var correoElectronico = stdin.readLineSync();

    var profesor = Profesor(
        name: name,
        materia: materia,
        dateBirth: dateBirth,
        correoElectronico: correoElectronico);

    directorio.agregarProfesor(profesor);

    print('¿Desea agregar otro profesor? (s/n)');
    var answer = stdin.readLineSync();
    if (answer?.toLowerCase() != 's') {
      break;
    }
  }
}

void agregarAlumnos(Directorio directorio) {
  while (true) {
    print('Ingrese los datos del alumno:');
    print('Nombre:');
    var name = stdin.readLineSync();
    print('Grado:');
    var gradoStr = stdin.readLineSync();
    var grado = int.tryParse(gradoStr!);
    print('Grupo:');
    var grupo = stdin.readLineSync();
    print('Fecha de nacimiento (Formato: yyyy-mm-dd):');
    var dateBirthStr = stdin.readLineSync();
    var dateBirth = DateTime.parse(dateBirthStr!);
    print('Correo electrónico:');
    var correoElectronico = stdin.readLineSync();

    var alumno = Alumno(
        name: name,
        grado: grado,
        grupo: grupo,
        dateBirth: dateBirth,
        correoElectronico: correoElectronico);

    directorio.agregarAlumno(alumno);

    print('¿Desea agregar otro alumno? (s/n)');
    var answer = stdin.readLineSync();
    if (answer?.toLowerCase() != 's') {
      break;
    }
  }
}



class Persona {
  String? name;
  DateTime? dateBirth;
  String? correoElectronico;
  

  Persona({this.name, this.dateBirth, this.correoElectronico});

  void validarDateBirth() {
    dateBirth = DateTime.parse(dateBirth.toString());
  }

bool validarCorreoElectronico() {
    if (correoElectronico == null) {
      return false; // El correo electrónico es nulo, no es válido
    }
  if (!correoElectronico!.contains('@')) {
    print('El correo electrónico no contiene el símbolo \'@\'. No es válido.');
    return false;
  }

  if (!correoElectronico!.endsWith('.com' '.es' '.org' '.net')) {
    print('El correo electrónico no termina en \'.com\'. No es válido.');
    return false;
  }

  return true; // El correo electrónico es válido
}
}

class Profesor extends Persona {
  String? materia;

  Profesor({this.materia, String? name, DateTime? dateBirth, String? correoElectronico})
  : super(name: name, dateBirth: dateBirth, correoElectronico: correoElectronico);
}

class Alumno extends Persona {
  int? grado;
  String? grupo;

  Alumno({this.grado, this.grupo, String? name, DateTime? dateBirth, String? correoElectronico})
  : super(name: name, dateBirth: dateBirth, correoElectronico: correoElectronico);
}

class Directorio {
  List<Profesor> profesores = [];
  List<Alumno> alumnos = [];

  // CRUD: Crear
  void agregarProfesor(Profesor profesor) {
    profesores.add(profesor);
  }

  void agregarAlumno(Alumno alumno) {
    alumnos.add(alumno);
  }

  // CRUD: Leer
  void mostrarProfesores() {
    for (var profesor in profesores) {
      print('Nombre: ${profesor.name}');
      print('Materia: ${profesor.materia}');
      print('Fecha de nacimiento: ${profesor.dateBirth}');
      print('Correo electrónico: ${profesor.correoElectronico}');
      print('---------------------');
    }
  }

  void mostrarAlumnos() {
    for (var alumno in alumnos) {
      print('Nombre: ${alumno.name}');
      print('Grado: ${alumno.grado}');
      print('Grupo: ${alumno.grupo}');
      print('Fecha de nacimiento: ${alumno.dateBirth}');
      print('Correo electrónico: ${alumno.correoElectronico}');
      print('---------------------');
    }
  }

  // CRUD: Actualizar
  void actualizarProfesor(int index, Profesor nuevoProfesor) {
    if (index >= 0 && index < profesores.length) {
      profesores[index] = nuevoProfesor;
    } else {
      print('El índice es inválido.');
    }
  }

  void actualizarAlumno(int index, Alumno nuevoAlumno) {
    if (index >= 0 && index < alumnos.length) {
      alumnos[index] = nuevoAlumno;
    } else {
      print('El índice es inválido.');
    }
  }

  // CRUD: Eliminar
  void eliminarProfesor(int index) {
    if (index >= 0 && index < profesores.length) {
      profesores.removeAt(index);
    } else {
      print('El índice es inválido.');
    }
  }

  void eliminarAlumno(int index) {
    if (index >= 0 && index < alumnos.length) {
      alumnos.removeAt(index);
    } else {
      print('El índice es inválido.');
    }
  }
}
