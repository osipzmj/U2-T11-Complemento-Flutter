# U2-T11-Complemento-Flutter
## ***Ejercicios Flutter y Dart***

### ***TABLA DE CONTENIDO***
- [01: Hello World.](#01-Hello-world)
- [02: Variables.](#02-variables)
- [03: Maps.](#03-maps)
- [04: List, maps and Iterables.](#04-list-maps-iterables)
- [05: Functions.](#05-functions)
- [06: Classes.](#06-classes)
- [07: Constructors and names.](#07-constructors-names)
- [08: get and set.](#08-get-and-set)
- [09: Abstract class.](#09-abstract-class)
- [10: Mixins.](#10-mixins)
- [11: Futures.](#11-futures)
- [12: Async Await.](#12-async-await)
- [13: Try catch finally.](#13-try-and-catch)
- [ 14: Streams.](#14-streams)
- [15: Stream await.](#15-stream-await)

## 01: Hello World.
### Código
```
import 'package:dart_basics/dart_basics.dart' as dart_basics;

void main(List<String> arguments) {
  print('Hello world: ${dart_basics.calculate()}!');
  print(dart_basics.saludar());
}

```
### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/066d549c-879d-4f87-98de-4a373c35d48c)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/11d5d73c-663f-425d-a8f2-1a93ba4685d3)



## 02: Variables.
### Código
```
int suma(int n1, int n2){
  print("Función Suma");
  return n1 + n2;
}

double promedio(double c1, double c2, double c3){
  return (c1+c2+c3/3);
}
void main() {
  int numero = 1000;
  int numero2 = 3000;
  int s = suma(numero, numero2);
  print("La suma de $numero más $numero2 es igual a: $s");

  double calificacion = 10.0;
  double calificacion1 = 6.3;
  double calificacion2 = 8.9;
  print(promedio(calificacion, calificacion1, calificacion2));

  String miCrush = 'Nayeli';
  print('$miCrush me ama <5');


  bool isValid = true;

  print("Me quiere $miCrush? ${isValid==true?'Si':'No'}");
}
```

### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/550bcbee-a98a-42f2-bf25-8db1363e64d8)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/9cf2adc4-d894-4f7a-b493-d0e949294a6a)


## 03: Maps. 
### Código
```
void main(){
  //Crear un mapa
  Map<String,int> notas = {'ddi':10, 'bd':8, 'iot':7, 'in':10};
  print(notas);

//IMPRIMIR CALIFICACION DE BD
  print(notas['bd']);
  notas['bd'] = 10;
  print(notas['bd']);

  notas.remove('iot');
  print(notas);

  for(var nota in notas.keys){
    print("$nota: ${notas[nota]}");
  }

  notas.forEach((key, value) => print('$key: $value'));
}
```
### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/6a3efa24-d2b0-4a10-98f7-576920085912)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/a07a70ff-aca6-4e18-b68e-8b668cf69bcc)


## 04: List, maps and Iterables.
### Código
```
void main(){
  //Declaramos una lista
  List<int> scores = [10,20,30];
  print(scores[0]);

  for(var i=0; i < 3; i++){
    print(scores[i]);
  }

  print(scores);

  scores.remove(10);

  print(scores);

  scores.add(40);

  print(scores);

  print("El primer elemento es ${scores.first}");
  print("El primer elemento es ${scores.last}");

  for (var s in scores){
    print(s);
  }

  scores.forEach((s)=> print(s));
}
```
### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/65596e15-8dfd-44d7-9ea9-30ff3c195826)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/22e186a7-9e8e-44ce-8af9-c34f6fa24b1d)

## 05: Functions.
### Código
```
import 'dart:io';

int suma(int a, int b){
  return a + b;
}

void saludar(String nombre){
  print("Hola $nombre!");
}

//Declaramos función con parametros opcionales
// void imprimirTicket(String producto, [int cantidad = 1, int monto = 10]){
//   print("$producto, $cantidad, $monto");  
// }

void imprimirCorreo(String correo, {String remitente="Anónimo"}){
  print("$correo, $remitente");  
}

var miResta = (int a, int b) => a - b;

void main(List<String> arguments) {
/*int n1, n2;
  print("Favor de teclear un número: ");
  n1 = int.parse(stdin.readLineSync()!);
  print("Favor de teclear un segundo número: ");
  n2 = int.parse(stdin.readLineSync()!);
  print("La suma es: ${suma(n1, n2)}");
*/
  saludar("Oscar Pérez");
  // imprimirTicket("Jabon zote");
  // imprimirTicket("Jabon zote", 3, 45);
  imprimirCorreo("ossytres8@gmail.com", remitente: "Oscar Pérez");

  var miFuncion = (int a, int b) => a + b;
  print(miFuncion(53,5));

  print (miResta(5,78));

  var numeros = [1,2,3,4];
  numeros.forEach((num){print("Número: $num");});
}



```
### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/014b3301-bad7-411f-bc72-383d8d0070b7)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/b34d7c9a-52fc-4ad1-a9ee-579408920dcd)

## 06: Classes.
### Código
```
class Animal {
  String _nombre = "Sin nombre";
  int _edad = 0;

  //Constructor
// Animal(){
//   print("Constructor fue llamado");
// }

//Constructor con parametros
Animal({String nombre = "Anónimo", int edad = 0}){
  _nombre = nombre;
  _edad = edad;
}

  void comer(){
    print("Comiendo");
  }

  void cambiarEstado(String _nombre, int edad){
    _nombre;
    _edad;
  }

  void imprimir(){
     print("Animal $_nombre, Edad $_edad");
  }
}

void main(){
  var a = Animal();
  print(a._nombre);
  print(a._edad);

  a._nombre = "Hipopotamo";
  a._edad = 3;

  print("Animal: ${a._nombre}, Edad: ${a._edad}");
  a.comer();

  int x = 0;
  print(a is Animal);

  a.cambiarEstado("Gatito", 0);

  a.imprimir();

  var a2 = Animal();
  var a3 = Animal(nombre: "Pantera", edad: 5);

  a3.imprimir();
}
```
### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/ab470476-3849-4392-871c-81c2f84dcbd7)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/7744c77d-a90c-4b29-8431-ae465d6f6603)

## 07: Constructors and names.
### Código
```

```
### Imágenes

## 08: get and set.
### Código
```
```
### Imágenes

## 09: Abstract class.
### Código
Código clases_abstractas.dart
```
import 'figura.dart';

// CREAR LA FUNCIÓN MAIN 
void main(){
  var circulo = Circulo(5);
  circulo.calcularArea();

  print("El área del circulo con radio ${circulo.radio} es: ${circulo.calcularArea()}");
  
  var rectangulo = Rectangulo(10, 50);

  print("El área del rectangulo con altura ${rectangulo.altura} y base ${rectangulo.base} es: ${rectangulo.calcularArea()}");
}
```

Código figura.dart
```
// CREAR UNA CLASE ABSTRACTA LLAMADA FIGURA

abstract class Figura{
  // CREAR UN MÉTODO ABSTRACTO
  double calcularArea();
}

// CLASE RECTANGULO QUE HEREDA DE FIGURA
class Rectangulo extends Figura{
  
  //Atributos
  double base, altura;
  //Constructor
  Rectangulo(this.base, this.altura);
  
  @override
  double calcularArea(){
    return base * altura;
  }
}

// CLASE CIRCULO QUE HEREDA DE FIGURA
class Circulo extends Figura{
  //Atributo radio
  double radio = 0;

  //Constructor
  Circulo(this.radio);

  @override
  double calcularArea(){
    return 3.14 * radio * radio;
  }
}
```
### Imágenes
Código clases_abstractas

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/8813ad3f-06ed-414c-88bc-5e87576676f9)

Código figura

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/2ae49daf-f9a3-459d-8b8a-a891ed3949da)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/a08e5889-0045-4add-8225-cd4bceb5f6ab)

## 10: Mixins.
### Código
```
//Crear un mixin
mixin Volador{
  void volar(){
    print("Estoy volando!");
  }
}

mixin Corredor{
  void correr(){
    print("Estoy corriendo!");
  }
}

mixin Nadador{
  void nadar(){
    print("Estoy nadando!");
  }
}

class Pato with Volador, Corredor, Nadador{}

void  main(){

var pato = Pato();
pato.volar();
pato.nadar();
pato.correr();
}
```
### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/ff0c9c1d-e0c6-467d-9c38-c0f0fa9a680c)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/658d6a7d-f91d-43a5-bcc2-7bd87460c753)

## 11: Futures.
### Código

- futures_error.dart
```
void main(){
  // Future que lanza una excepción
  Future((){
    throw Exception("Algo salió mal");
  },).then((_){print("Operación exitosa");})
  .catchError((e){print("Error: $e");});
}
```
- futures_dart.dart
```
void main(){
  print("Inicio de programa");

  //Crear un future (valor o error disponible en el futuro)
  Future((){
    return "Hola mundo";
}).then((resultado){print(resultado);});

print("Fin del programa");
}
```
- future_delayed.dart
```
void main(){
  print("Inicio del programa");

  Future.delayed(Duration(seconds: 3), (){return 'Hola despues de 3 segundos!';}).then((resultado)
  => print(resultado));

  print("Fin del programa");
}
```
### Imágenes

Código futures_error

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/b781a75d-877e-4079-a357-db25e33547a2)

Resultado futures_error

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/a5e93ff3-6a6c-4df2-9d45-672446e25ab7)

Código futures_dart

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/3035bb69-083c-4b1e-9fde-4ea3a6c67f85)

Resultado futures_dart

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/7b95ebd0-62b6-45b7-93fb-49d66dcd6357)

Código futures_delayed

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/69be9f6e-6f1a-4cc0-af8d-a62c5101ba74)

Resultado futures_delayed

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/d137d306-3e56-43f5-99d6-ed5ff936e5a8)

## 12: Async Await.
### Código
```
//Archivo asynsc_await.dart

void main() async{
  print("Inicio de programa");

  String resultado = await Future((){
    return 'Hola mundo';
  });

  print(resultado);

  print("Fin del programa");
}
```
### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/7abdf2ed-32d4-49a4-8f6b-54889e448a1e)


Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/12595871-0ccf-46d8-9b01-08dcca2c1fb0)

## 13: Try catch finally.
### Código
```
void main() {
  try{
  int resultado = 10 ~/3;
  print("La división es $resultado");
  }on Exception{
  print("Se produjo una excepción de divisón entre 0");
  } finally{
    print("No dividas entre 0");
  }

  try{
  List<int> lista = [1,2,3];
  print(lista[2]);
  } catch(e){
    print("Hubo una excepción $e");
  } finally{
    print("Operación completada");
  }
}
```
### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/884191d6-ed16-4f45-a203-09ea16065c1c)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/55cb3856-8974-447b-a0d9-1eb799ef0ea4)


## 14: Streams.
### Código
```
void main(){
  Stream<int> stream = Stream.periodic(Duration(seconds: 1),(contador)=>
  contador).take(10);
  
  stream.listen((datos)=>print("Dato recibido: $datos"));

  Stream<int> otroStream = Stream.fromIterable([1,3,5,7,9,11]);
  otroStream.listen((data)=>print("Dato recibido: $data"));
}
```
### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/027f7ee2-f2cc-40e7-895a-4ea0885dea0f)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/a5b34495-60ea-412e-a7e5-5127ed6b891e)

## 15: Stream await.
### Código
```
void main() async{
    Stream<int> stream = Stream.periodic(Duration(seconds: 1),(contador)=>
  contador).take(10);

  await for(var data in stream){
    print("Dato recibido: $data");
  }  
  print("Fin del stream");
}
```
### Imágenes

Código

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/43b94130-8ddc-4fe5-aca2-d3057d8647ba)

Resultado

![image](https://github.com/osipzmj/U2-T11-Complemento-Flutter/assets/99992053/32baa504-c049-4944-b6a3-87577b3f70eb)
