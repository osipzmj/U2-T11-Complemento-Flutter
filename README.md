# U2-T11-Complemento-Flutter
## ***Ejercicios Flutter y Dart***

## 01: Hello World
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



## 02: Variables
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

```
### Imágenes

## 06: Classes.
### Código
```
```
### Imágenes

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
```
```
### Imágenes

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
```
### Imágenes

## 13: Try catch finally.
### Código
```
```
### Imágenes

## 14: Streams.
### Código
```
```
### Imágenes

## 15: Stream await.
### Código
```
```
### Imágenes
