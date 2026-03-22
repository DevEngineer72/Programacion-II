# 📘 Plan de Estudio Paralelo — C++ (14 Semanas)

> Este documento es tu guía personal de estudio.
> Cada sesión tiene lo que verás en la universidad **más lo que debes estudiar por tu cuenta** para ir un paso adelante.

---

## 📌 Cómo usar este documento

Cada semana sigue este ciclo:

```
Lunes - Jueves   →  Asiste a clases y toma apuntes a mano
Esa misma noche  →  Reproduce el código que viste sin mirar apuntes
Fin de semana    →  Estudia el tema adicional de esa sesión
```

> 💡 **Regla de oro:** No pases a la siguiente sesión sin entender la actual.
> Es mejor ir lento con base sólida que rápido con huecos.

---

## 🛠️ Antes de empezar — Configura tu entorno (Semana 0)

Haz esto **antes del lunes**, no te tomará más de 2 horas.

**1. Instala las herramientas:**
- [CLion](https://www.jetbrains.com/clion/) — tu IDE de la universidad (pide licencia estudiantil gratuita en jetbrains.com/student)
- CLion incluye compilador, debugger y todo lo necesario — no necesitas instalar nada extra

**2. Familiarízate con CLion antes de la primera clase:**

| Atajo | Acción |
|---|---|
| `Shift + F10` | Ejecutar el programa |
| `Shift + F9` | Ejecutar en modo debug |
| `F9` | Poner/quitar breakpoint |
| `F8` | Avanzar línea por línea en debug |
| `Ctrl + /` | Comentar/descomentar línea |
| `Ctrl + Alt + L` | Formatear el código automáticamente |
| `Shift + Shift` | Buscar cualquier cosa en el proyecto |

**3. Aprende Git desde el día 1:**
```bash
git init                       # iniciar repositorio en tu carpeta
git add .                      # agregar todos los cambios
git commit -m "sesion-01"      # guardar punto de control
git log                        # ver historial de cambios
```

CLion tiene Git integrado: ve a `VCS → Enable Version Control Integration` y nunca más necesitas la terminal para Git.

Crea una cuenta en [github.com](https://github.com) y sube tu código cada semana. Es tu portafolio — guarda todo ahí desde el primer día.

**4. Crea esta estructura de carpetas:**
```
cpp-universidad/
├── sesion-01/
├── sesion-02/
├── ...
└── sesion-14/
```

---

## 📅 Sesión 1 — Algoritmos, Variables y Estructuras de Control Selectivas

### 🎓 Lo que enseña la universidad
- Diseño de algoritmos y estructura de un programa en C++
- Variables, tipos de datos primitivos y operadores
- Estructuras de control selectivas (`if`, `else`, `switch`)

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Pseudocódigo antes de escribir código

Antes de abrir CLion, escribe la solución en papel con palabras.
Es el hábito más importante que puedes desarrollar ahora.

```
Problema: Saber si un número es par o impar

Pseudocódigo:
  leer número
  si número % 2 == 0:
      mostrar "es par"
  sino:
      mostrar "es impar"
```

Solo cuando tengas claro el pseudocódigo, escríbelo en C++.

---

#### ✏️ Clean Code — Cómo nombrar variables correctamente

El nombre de una variable debe decir exactamente qué contiene, sin necesidad de adivinar.

```cpp
// ❌ Lo que acepta la universidad pero es mala práctica
int x, y, z;
int a = 5;
float t = 15.99;

// ✅ Clean Code — el nombre explica todo
int edadEstudiante = 20;
float precioProducto = 15.99;
bool esMayorDeEdad = true;
int cantidadAlumnos = 30;
```

**Convenciones de nombres en C++:**

| Tipo | Convención | Ejemplo |
|---|---|---|
| Variables y funciones | `camelCase` | `edadEstudiante`, `calcularPromedio()` |
| Clases | `PascalCase` | `Estudiante`, `ListaNotas` |
| Constantes | `UPPER_SNAKE_CASE` | `MAX_ALUMNOS`, `PI` |
| Archivos | `snake_case` | `estudiante.cpp`, `lista_notas.h` |

---

#### 💬 Cómo comentar el código correctamente

Comentar no significa explicar cada línea. Significa explicar el **por qué**, no el **qué**.

```cpp
// ❌ Comentario inútil — el código ya dice lo mismo
int edad = 20; // asigna 20 a edad

// ❌ Comentario que miente (el peor tipo)
int precio = 100; // precio en dólares
// (pero en realidad está en soles)

// ✅ Comentario útil — explica el por qué
// El límite es 18 por regulación universitaria peruana
const int EDAD_MINIMA = 18;

// ✅ Comentario útil — explica una decisión no obvia
// Usamos int en vez de float para evitar errores de redondeo en el conteo
int totalEstudiantes = 0;
```

**Regla simple:** Si el código se explica solo, no comentes. Si hay algo no obvio, comenta el porqué.

---

#### 🔍 Cómo leer errores del compilador en CLion

CLion muestra los errores en la pestaña inferior. Aprende a leerlos desde el primer día.

```
// Error típico que verás:
error: 'edad' was not declared in this scope

// Traducción: estás usando una variable que no existe o está fuera de su alcance
// Solución: revisa si la declaraste, si está en el lugar correcto y si escribiste bien el nombre
```

**Los errores más comunes en esta semana:**

| Error | Causa más probable |
|---|---|
| `was not declared in this scope` | Variable no declarada o mal escrita |
| `expected ';'` | Te faltó un punto y coma |
| `no match for operator` | Estás comparando tipos incompatibles |

**Consejo:** Lee siempre el **primer error** de la lista. CLion a veces muestra 10 errores cuando en realidad solo hay 1. Arregla el primero y los demás pueden desaparecer.

---

**Recursos para esta semana:**
- 📺 YouTube: busca "algoritmos pseudocódigo para principiantes español"
- 🔧 Práctica: resuelve 3 problemas en papel con pseudocódigo antes de escribir código
- 🔧 Aplica convenciones de nombres desde el primer ejercicio

---

## 📅 Sesión 2 — Estructuras de Control Repetitivas

### 🎓 Lo que enseña la universidad
- Estructuras de control repetitivas (`for`, `while`, `do while`)

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Cuándo usar cada ciclo

```cpp
// FOR → cuando sabes exactamente cuántas veces vas a repetir
for (int i = 0; i < 10; i++) { }

// WHILE → cuando no sabes cuántas veces, pero hay una condición
while (usuarioNoCerro) { }

// DO WHILE → cuando necesitas ejecutar al menos una vez sí o sí
do {
    pedirContrasena();
} while (contrasenaIncorrecta);
```

---

#### ✏️ Clean Code — Cómo nombrar correctamente en ciclos

```cpp
// ❌ Nombres sin significado
for (int i = 0; i < a; i++) {
    x += b[i];
}

// ✅ Nombres que se explican solos
for (int indice = 0; indice < cantidadNotas; indice++) {
    sumaTotal += notas[indice];
}
```

La excepción aceptada: usar `i`, `j`, `k` en ciclos simples y cortos está bien si el contexto es obvio.

---

#### 🐛 Cómo usar el Debugger de CLion — tu herramienta más poderosa

El debugger te permite pausar el programa y ver qué está pasando dentro.

**Paso a paso:**
1. Haz clic a la izquierda del número de línea → aparece un punto rojo (breakpoint)
2. Presiona `Shift + F9` para ejecutar en modo debug
3. El programa se pausa en esa línea
4. En el panel inferior ves el valor de todas las variables en ese momento
5. Presiona `F8` para avanzar línea por línea

```cpp
int suma = 0;
for (int i = 1; i <= 5; i++) {
    suma += i;   // ← pon un breakpoint aquí y ve cómo crece suma
}
```

Úsalo en al menos un ejercicio esta semana. Te ahorrará horas de frustración en todo el ciclo.

---

#### 🔍 Errores comunes en ciclos

```cpp
// ❌ Ciclo infinito — el programa se congela
int i = 0;
while (i < 10) {
    cout << i;
    // olvidaste i++ ← nunca termina
}

// ✅ Correcto
int i = 0;
while (i < 10) {
    cout << i;
    i++;  // la condición eventualmente se vuelve falsa
}
```

**En CLion:** si tu programa se congela, presiona el botón rojo de stop en la barra superior. Luego usa el debugger para encontrar el ciclo infinito.

---

**Recursos para esta semana:**
- 🔧 Práctica: resuelve al menos 5 problemas con ciclos
- 🔧 Usa el debugger en al menos un ejercicio para ver cómo cambian las variables

---

## 📅 Sesión 3 — Funciones y Recursividad

### 🎓 Lo que enseña la universidad
- Variables globales y su alcance (scope)
- Paso de parámetros por valor y por referencia
- Funciones recursivas vs iterativas

### ➕ Lo que debes estudiar adicionalmente

---

#### ✏️ Clean Code — Una función = una sola responsabilidad

```cpp
// ❌ Función que hace demasiado — difícil de entender y probar
void procesarEstudiante() {
    leerDatos();
    calcularPromedio();
    mostrarResultado();
    guardarArchivo();
}

// ✅ Cada función hace exactamente una cosa
float calcularPromedio(float notas[], int cantidad) {
    float sumaTotal = 0;
    for (int i = 0; i < cantidad; i++) {
        sumaTotal += notas[i];
    }
    return sumaTotal / cantidad;
}
```

**Reglas de Clean Code para funciones:**
- El nombre debe ser un verbo que describe exactamente qué hace
- Si necesitas escribir un comentario para explicar qué hace, el nombre está mal
- Si hace más de una cosa, divídela

```cpp
// ❌ Nombres vagos
void hacer();
void proceso();
void funcion1();

// ✅ Nombres que se explican solos
void calcularPromedio();
void mostrarResultados();
void guardarEstudiante();
```

---

#### ⚠️ Variables globales — úsalas lo menos posible

```cpp
// ❌ Variable global — cualquier función puede cambiarla sin que te des cuenta
int contador = 0;

void incrementar() { contador++; }   // cambia la global
void reiniciar()   { contador = 0; } // también la cambia

// ✅ Pásala como parámetro — más controlado y predecible
void incrementar(int& contador) {
    contador++;
}
```

La universidad te enseña que existen. En el mundo real se evitan porque hacen el código difícil de seguir.

---

#### 💡 Por valor vs por referencia — la diferencia real

```cpp
// Por VALOR → recibe una copia, el original no cambia
void duplicarValor(int numero) {
    numero = numero * 2;  // solo cambia la copia local
}

// Por REFERENCIA → recibe el original, sí lo modifica
void duplicarReferencia(int& numero) {
    numero = numero * 2;  // modifica el original
}

int main() {
    int x = 5;
    duplicarValor(x);      // x sigue siendo 5
    duplicarReferencia(x); // x ahora es 10
}
```

---

#### 🔍 Cómo leer errores de funciones en CLion

```
error: too few arguments to function 'float calcularPromedio(float*, int)'
// Traducción: estás llamando la función con menos parámetros de los que necesita

error: invalid conversion from 'int' to 'float*'
// Traducción: el tipo de dato que pasas no coincide con lo que la función espera
```

---

**Recursos para esta semana:**
- 📺 YouTube: "funciones C++ valor referencia español"
- 🔧 Práctica: escribe la misma función de dos formas — con ciclo y con recursión — y compara cuál es más legible

---

## 📅 Sesión 4 — Introducción a Punteros

### 🎓 Lo que enseña la universidad
- Definición y manejo de punteros
- Análisis de punteros en código

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Entiende la memoria antes de tocar punteros

La RAM de tu computadora es como una calle con casas numeradas. Cada variable ocupa una casa y tiene una dirección.

```cpp
int edad = 25;
// "edad"  → nombre de la variable
// 25      → contenido
// &edad   → dirección de memoria (como el número de la casa)

int* puntero = &edad;
// puntero guarda la DIRECCIÓN de edad, no el contenido
```

Visualízalo en papel antes de escribir código:
```
Dirección    Variable     Contenido
────────────────────────────────────
0x001        edad         25
0x002        puntero      0x001     ← apunta a la dirección de edad
```

---

#### ✏️ Clean Code — Cómo nombrar punteros

```cpp
// ❌ No se entiende qué apunta
int* p;
int* ptr;

// ✅ El nombre describe qué contiene
int* punteroEdad;
Estudiante* ptrEstudiante;

// Convención común: agregar "ptr" o "p" como prefijo
Estudiante* ptrEstudiante = new Estudiante();
```

---

#### 🔑 Los dos operadores que más confunden

```cpp
int edad = 25;
int* p = &edad;

&edad   // dirección de memoria de "edad"    → 0x001
*p      // contenido de lo que apunta p      → 25
p       // la dirección que guarda p         → 0x001
```

---

#### 🔍 Errores comunes con punteros en CLion

```
Segmentation fault (core dumped)
// Traducción: intentaste acceder a memoria que no te pertenece
// Causa más común: puntero no inicializado o ya liberado

warning: 'puntero' is used uninitialized
// Traducción: declaraste el puntero pero no le asignaste una dirección
// Solución: siempre inicializa → int* p = nullptr; o int* p = &variable;
```

---

**Recursos para esta semana:**
- 📺 YouTube: "punteros C++ visualizado español" — busca uno con diagramas de memoria
- 🔧 Práctica: dibuja en papel la memoria antes de escribir cada ejercicio con punteros

---

## 📅 Sesión 5 — Memoria Dinámica con Punteros

### 🎓 Lo que enseña la universidad
- Manejo de memoria dinámica (`new` y `delete`)

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Stack vs Heap — las dos zonas de memoria

```
Stack (pila)               Heap (montón)
───────────────────        ───────────────────
Variables normales         Memoria dinámica (new)
Se libera automática       Tú la liberas con delete
Tamaño fijo                Tamaño flexible
Más rápida                 Más grande
```

---

#### ⚠️ Memory Leak — el error más peligroso

Un memory leak ocurre cuando reservas memoria y nunca la liberas. El programa consume cada vez más RAM hasta que el sistema colapsa.

```cpp
// ❌ Memory leak — la memoria nunca se libera
void funcion() {
    int* numero = new int(5);
    // la función termina, el puntero desaparece
    // pero la memoria en el Heap sigue ocupada para siempre
}

// ✅ Correcto — siempre libera lo que reservaste
void funcion() {
    int* numero = new int(5);
    // ... usas el número ...
    delete numero;       // liberas la memoria
    numero = nullptr;    // evitas usar un puntero ya liberado
}
```

**Regla que nunca debes olvidar:**
> Por cada `new` debe haber exactamente un `delete`.

---

#### ✏️ Clean Code — Manejo seguro de punteros

```cpp
// ❌ Puntero sin inicializar — comportamiento impredecible
int* p;
*p = 5;   // error: p apunta a algún lugar desconocido de la memoria

// ✅ Siempre inicializa antes de usar
int* p = nullptr;    // inicializa como vacío
p = new int(5);      // ahora sí apunta a algo válido
// ...
delete p;
p = nullptr;         // después de delete, vuelve a nullptr
```

---

#### 🔍 Usando el Debugger de CLion para detectar memory leaks

CLion tiene una herramienta integrada llamada **Valgrind** (en Linux/Mac) o **Address Sanitizer**:

Ve a `Run → Edit Configurations → Add → Valgrind` para detectar memory leaks automáticamente.

En Windows, activa Address Sanitizer agregando esto en tu `CMakeLists.txt`:
```
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fsanitize=address")
```

---

**Recursos para esta semana:**
- 📺 YouTube: "memory leak C++ explicado español"
- 🔧 Práctica: en cada ejercicio cuenta que tienes el mismo número de `new` y `delete`

---

## 📅 Sesión 6 — Arreglos Dinámicos

### 🎓 Lo que enseña la universidad
- Arrays dinámicos, vectores y matrices con punteros

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Array estático vs dinámico

```cpp
// Array ESTÁTICO → tamaño fijo, definido antes de ejecutar
int notas[30];           // siempre 30 espacios, aunque uses 5

// Array DINÁMICO → tamaño definido cuando el programa corre
int cantidad;
cin >> cantidad;
int* notas = new int[cantidad];   // el usuario decide el tamaño
// ...
delete[] notas;    // ojo: delete[] con corchetes para arrays
```

---

#### ✏️ Clean Code — El error más común con arrays dinámicos

```cpp
// ❌ Error grave: delete sin corchetes en un array
int* arr = new int[10];
delete arr;     // solo libera el primer elemento, memory leak en el resto

// ✅ Correcto: siempre delete[] para arrays
delete[] arr;
arr = nullptr;
```

---

#### 💬 Cómo comentar matrices y arrays complejos

```cpp
// ❌ Sin comentarios — nadie entiende para qué sirve
int** m = new int*[filas];
for (int i = 0; i < filas; i++) {
    m[i] = new int[columnas];
}

// ✅ Con comentarios útiles que explican la estructura
// Matriz de calificaciones: filas = estudiantes, columnas = cursos
int** calificaciones = new int*[cantidadEstudiantes];
for (int i = 0; i < cantidadEstudiantes; i++) {
    calificaciones[i] = new int[cantidadCursos];
}
```

---

#### 🔍 Errores comunes con arrays en CLion

```
Segmentation fault
// Causa más probable: accediste a un índice fuera del rango del array
// Ejemplo: array de 5 elementos, accediste al índice 5 (el último válido es 4)

// Usa el debugger: pon un breakpoint en el ciclo y observa el valor de i
```

---

**Recursos para esta semana:**
- 🔧 Práctica: implementa una matriz dinámica de notas y libera toda la memoria correctamente
- 🔧 Verifica que usas `delete[]` para todos los arrays

---

## 📅 Sesión 7 — Vectores

### 🎓 Lo que enseña la universidad
- Definición, construcción y operadores básicos de vectores

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Vector vs Array — en el mundo real casi siempre usarás vector

```cpp
#include <vector>
using namespace std;

// Array → tamaño fijo, tú gestionas la memoria
int arr[10];

// Vector → tamaño flexible, se gestiona solo
vector<int> notas;
notas.push_back(15);    // agrega elemento al final
notas.push_back(18);
notas.size();           // cuántos elementos tiene
notas[0];               // acceder por índice
notas.pop_back();       // eliminar último elemento
notas.clear();          // vaciar todo el vector
```

---

#### ✏️ Clean Code — Nombres descriptivos en vectores

```cpp
// ❌ No se entiende qué contiene
vector<int> v;
vector<string> s;

// ✅ El nombre dice exactamente qué guarda
vector<int> notasFinales;
vector<string> nombresEstudiantes;
vector<float> preciosProductos;
```

---

#### 🔢 Algoritmos de ordenamiento — búscalos esta semana

Son preguntas clásicas en exámenes y entrevistas. Entiende **por qué** funcionan, no solo los copies.

```cpp
// Bubble Sort — el más simple de entender
// Compara pares adyacentes y los intercambia si están en orden incorrecto
void bubbleSort(vector<int>& notas) {
    int cantidad = notas.size();
    for (int pasada = 0; pasada < cantidad - 1; pasada++) {
        for (int i = 0; i < cantidad - pasada - 1; i++) {
            if (notas[i] > notas[i + 1]) {
                swap(notas[i], notas[i + 1]);
            }
        }
    }
}
```

Úsa el debugger de CLion con un `breakpoint` dentro del ciclo para ver cómo se van ordenando los elementos paso a paso.

---

**Recursos para esta semana:**
- 📺 YouTube: "bubble sort visualizado español" — busca uno con animación
- 🔧 Práctica: ordena un vector de notas de menor a mayor y muestra el resultado

---

## 📅 Sesión 8 — POO: Clases, Objetos y Encapsulamiento

### 🎓 Lo que enseña la universidad
- Abstracción y encapsulamiento
- Relación clase-objeto
- Constructores, destructores, getters y setters
- Objetos dinámicos y arreglos de objetos

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Antes de escribir código: aprende UML básico

Un diagrama UML es el plano de tu clase. Dibújalo en papel **siempre** antes de escribir código.

```
┌─────────────────────┐
│      Estudiante     │   ← nombre de la clase (PascalCase)
├─────────────────────┤
│ - nombre: string    │   ← atributos privados (- = private)
│ - edad: int         │
│ - promedio: float   │
├─────────────────────┤
│ + getNombre()       │   ← métodos públicos (+ = public)
│ + setPromedio()     │
│ + calcularNota()    │
└─────────────────────┘
```

---

#### ✏️ Clean Code — Cómo escribir clases bien

```cpp
// ❌ Clase con todo público y nombres vagos
class Est {
public:
    string n;
    int e;
    float p;
    void calc() { }
};

// ✅ Clean Code aplicado a clases
class Estudiante {
private:                          // datos protegidos
    string nombre;
    int edad;
    float promedio;

public:
    // Constructor con nombres descriptivos
    Estudiante(string nombreCompleto, int edadActual) {
        nombre = nombreCompleto;
        edad = edadActual;
        promedio = 0.0;           // siempre inicializa todos los atributos
    }

    // Destructor
    ~Estudiante() { }

    // Getters — solo lectura
    string getNombre()  { return nombre; }
    int    getEdad()    { return edad; }
    float  getPromedio(){ return promedio; }

    // Setters — con validación
    void setPromedio(float nuevoPromedio) {
        // Valida antes de asignar — escala peruana 0-20
        if (nuevoPromedio >= 0 && nuevoPromedio <= 20) {
            promedio = nuevoPromedio;
        }
    }
};
```

---

#### 💬 Los 4 pilares de POO — tenlos claros desde ahora

```
Encapsulamiento  → ocultar los datos internos (private + getters/setters)
Abstracción      → mostrar solo lo necesario, esconder lo complejo
Herencia         → clase hija hereda características de clase madre
Polimorfismo     → misma acción, comportamiento diferente según el objeto
```

Los dos últimos los verás en sesiones siguientes, pero entiéndelos en concepto desde ahora.

---

#### 🔍 Errores comunes al crear clases en CLion

```
error: 'nombre' is private within this context
// Traducción: intentas acceder a un atributo privado desde fuera de la clase
// Solución: usa el getter → estudiante.getNombre()

error: no matching function for call to 'Estudiante::Estudiante()'
// Traducción: intentas crear un objeto sin pasar los parámetros que el constructor necesita
// Solución: Estudiante est("Angel", 19); en vez de Estudiante est;
```

---

**Recursos para esta semana:**
- 📺 YouTube: "POO C++ clases objetos español HolaMundo"
- 🔧 Práctica: dibuja el diagrama UML en papel ANTES de escribir cualquier clase

---

## 📅 Sesión 9 — POO: Optimización con Objetos y Arreglos Dinámicos

### 🎓 Lo que enseña la universidad
- Optimización del código con objetos dinámicos y arreglos de objetos

### ➕ Lo que debes estudiar adicionalmente

---

#### ✏️ Clean Code — Principio de responsabilidad única

Cada clase debe tener **una sola razón para cambiar**.

```cpp
// ❌ Clase con demasiadas responsabilidades
class Estudiante {
public:
    void calcularPromedio() { }
    void guardarEnArchivo() { }   // esto no le corresponde a Estudiante
    void enviarCorreo()     { }   // ni esto
    void imprimirReporte()  { }   // ni esto
};

// ✅ Cada clase tiene una responsabilidad
class Estudiante {
public:
    void calcularPromedio() { }   // solo lo que es propio del estudiante
};

class RepositorioEstudiantes {
public:
    void guardar(Estudiante& est) { }   // maneja persistencia
};

class NotificadorEstudiantes {
public:
    void enviarCorreo(Estudiante& est) { }   // maneja comunicación
};
```

---

#### 🧠 Objetos dinámicos — sintaxis con flecha

```cpp
// Crear objeto dinámico
Estudiante* ptrEstudiante = new Estudiante("Angel", 19);

// Con objeto dinámico se usa -> en vez de .
cout << ptrEstudiante->getNombre() << endl;   // flecha para punteros
// cout << ptrEstudiante.getNombre();         // punto es para objetos normales

// Siempre liberar
delete ptrEstudiante;
ptrEstudiante = nullptr;
```

---

#### 💬 Cómo comentar la estructura de tus clases

```cpp
/**
 * Representa a un estudiante universitario.
 * Gestiona sus datos personales y calificaciones.
 * No maneja persistencia ni comunicación externa.
 */
class Estudiante {
private:
    string nombre;     // nombre completo del estudiante
    float promedio;    // promedio en escala 0-20

public:
    // Inicializa el estudiante con datos básicos
    Estudiante(string nombre, float promedio);

    // Calcula el promedio ponderado de todas las notas
    float calcularPromedioFinal(vector<float>& notas);
};
```

---

**Recursos para esta semana:**
- 🔧 Práctica: crea un sistema de registro de estudiantes con arreglo dinámico de objetos
- 🔧 Aplica el principio de una sola responsabilidad en cada clase que escribas

---

## 📅 Sesión 10 — Relación entre Clases

### 🎓 Lo que enseña la universidad
- Asociación, composición y agregación entre clases

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Las tres relaciones en palabras simples

```
Asociación  → dos clases se conocen, son independientes
              Estudiante usa Biblioteca — ambas existen por separado

Composición → una no puede existir sin la otra
              Corazón dentro de Persona — si muere Persona, muere Corazón

Agregación  → una contiene a la otra, pero la contenida puede existir sola
              Salón tiene Estudiantes — si se elimina el Salón, los Estudiantes siguen
```

---

#### ✏️ Herencia vs Composición — el debate más importante de POO

```
Usa herencia cuando:    "X ES UN tipo de Y"
                        Perro ES UN Animal ✅

Usa composición cuando: "X TIENE UN Y"
                        Carro TIENE UN Motor ✅
```

```cpp
// COMPOSICIÓN → el Motor solo existe dentro del Carro
class Carro {
private:
    Motor motor;    // Motor nace y muere con el Carro
};

// AGREGACIÓN → el Estudiante existe fuera del Salón
class Salon {
private:
    vector<Estudiante*> estudiantes;   // apunta a objetos que existen por su cuenta
};
```

**Regla en el mundo real:** prefiere composición sobre herencia. La herencia se vuelve muy compleja en proyectos grandes.

---

#### 💬 Cómo documentar las relaciones entre clases

```cpp
// Relación: Salon AGREGA Estudiantes (agregación)
// Un Salon puede existir sin estudiantes
// Los Estudiantes pueden existir sin estar en un Salon
class Salon {
private:
    string codigo;
    vector<Estudiante*> estudiantes;  // no son dueños del objeto, solo lo referencian
};
```

---

**Recursos para esta semana:**
- 📺 YouTube: "composición vs herencia POO C++ español"
- 🔧 Práctica: dibuja en papel las relaciones con flechas antes de escribir código

---

## 📅 Sesión 11 — Herencia y Funciones Virtuales

### 🎓 Lo que enseña la universidad
- Herencia de clases
- Funciones virtuales

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Herencia — la clase hija hereda todo lo público de la madre

```cpp
// Clase base (madre)
class Animal {
public:
    string nombre;
    void respirar() { cout << "Respirando..." << endl; }
};

// Clase derivada (hija) — hereda de Animal
class Perro : public Animal {
public:
    void ladrar() { cout << "Guau!" << endl; }
};

// El perro puede hacer todo lo de Animal más lo suyo propio
Perro miPerro;
miPerro.respirar();  // heredado ✅
miPerro.ladrar();    // propio de Perro ✅
```

---

#### ✏️ Clean Code — Funciones virtuales con override

```cpp
class Animal {
public:
    virtual void hacerSonido() {    // virtual = puede ser reemplazada por la hija
        cout << "Sonido genérico" << endl;
    }
    virtual ~Animal() { }           // destructor virtual — siempre ponlo si usas herencia
};

class Perro : public Animal {
public:
    void hacerSonido() override {   // override = reemplaza la versión del padre
        cout << "Guau!" << endl;    // CLion te avisa si escribes mal el nombre
    }
};
```

**Siempre escribe `override`** al reemplazar funciones virtuales. CLion te mostrará un error si el nombre no coincide exactamente con la función del padre, lo que evita bugs difíciles de encontrar.

---

#### 🔍 Errores comunes con herencia en CLion

```
error: cannot declare variable of abstract type 'Animal'
// Traducción: intentas crear un objeto de una clase que tiene funciones virtuales puras (=0)
// Solución: solo puedes crear objetos de las clases hijas concretas

warning: deleting object of polymorphic class type 'Animal' which has non-virtual destructor
// Traducción: te falta el destructor virtual en la clase base
// Solución: agrega virtual ~Animal() { } en la clase madre
```

---

**Recursos para esta semana:**
- 📺 YouTube: "herencia C++ funciones virtuales español"
- 🔧 Práctica: crea una jerarquía de 3 niveles (Animal → Perro → Labrador)

---

## 📅 Sesión 12 — Polimorfismo

### 🎓 Lo que enseña la universidad
- Polimorfismo paramétrico, de inclusión y con Override

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Polimorfismo en palabras simples

Polimorfismo significa "muchas formas". Es usar objetos diferentes a través de la misma interfaz.

```cpp
// Sin polimorfismo — una función para cada tipo
void hacerHablarPerro(Perro p) { p.hacerSonido(); }
void hacerHablarGato(Gato g)   { g.hacerSonido(); }
void hacerHablarVaca(Vaca v)   { v.hacerSonido(); }

// Con polimorfismo — una sola función para todos
void hacerHablar(Animal* animal) {
    animal->hacerSonido();   // llama la versión correcta automáticamente
}

// Funciona con cualquier Animal
Perro perro;
Gato  gato;
hacerHablar(&perro);   // imprime "Guau!"
hacerHablar(&gato);    // imprime "Miau!"
```

---

#### ✏️ Clean Code — Polimorfismo bien aplicado

```cpp
// ❌ Sin polimorfismo — código que crece sin control
void procesarAnimal(Animal* a) {
    if (a->tipo == "perro")      { /* hacer cosas de perro */ }
    else if (a->tipo == "gato")  { /* hacer cosas de gato */  }
    else if (a->tipo == "vaca")  { /* hacer cosas de vaca */  }
    // cada nuevo animal agrega más ifs
}

// ✅ Con polimorfismo — agregar un animal nuevo no cambia esta función
void procesarAnimal(Animal* animal) {
    animal->hacerSonido();   // cada clase sabe cómo hacerlo
}
```

---

#### 💬 Documentar jerarquías de clases

```cpp
/**
 * Clase base para todos los animales del sistema.
 * Define la interfaz común que deben implementar las clases derivadas.
 *
 * Clases derivadas: Perro, Gato, Vaca
 */
class Animal {
public:
    // Cada animal implementa su propio sonido
    virtual void hacerSonido() = 0;   // función virtual pura — obliga a implementarla
    virtual ~Animal() { }
};
```

---

**Recursos para esta semana:**
- 🔧 Práctica: crea un arreglo de punteros `Animal*` con diferentes animales y llama `hacerSonido()` en un ciclo
- 🔧 Aplica polimorfismo para eliminar todos los `if/else` que dependan del tipo de objeto

---

## 📅 Sesión 13 — Sobrecarga de Operadores

### 🎓 Lo que enseña la universidad
- Funciones amigas (`friend`)
- Sobrecarga de operadores
- Casos particulares de sobrecarga

### ➕ Lo que debes estudiar adicionalmente

---

#### ✏️ Clean Code — Cuándo SÍ y cuándo NO sobrecargar

```cpp
// ✅ Tiene sentido — se lee natural
Vector2D resultado = vectorA + vectorB;
Fraccion mitad = Fraccion(1,4) + Fraccion(1,4);
if (estudianteA == estudianteB) { }   // comparar por legajo

// ❌ No tiene sentido — confunde a quien lee el código
Estudiante grupo = estudiante1 + estudiante2;   // ¿qué significa "sumar" estudiantes?
Salon resultado = salon1 * salon2;              // ¿multiplicar salones?
```

**Regla simple:** solo sobrecarga si el uso se lee de forma completamente natural y obvia.

---

#### 🧠 Ejemplo correcto y bien documentado

```cpp
class Fraccion {
private:
    int numerador;
    int denominador;

public:
    Fraccion(int num, int den) : numerador(num), denominador(den) { }

    // Sobrecarga del operador + para sumar fracciones
    // Resultado: (a/b) + (c/d) = (a*d + c*b) / (b*d)
    Fraccion operator+(const Fraccion& otra) const {
        int nuevoNum = numerador * otra.denominador + otra.numerador * denominador;
        int nuevoDen = denominador * otra.denominador;
        return Fraccion(nuevoNum, nuevoDen);
    }

    // Función amiga para imprimir con <<
    // Es amiga porque necesita acceder a los atributos privados
    friend ostream& operator<<(ostream& os, const Fraccion& f) {
        os << f.numerador << "/" << f.denominador;
        return os;
    }
};
```

---

#### 🔍 Errores comunes con sobrecarga en CLion

```
error: no match for 'operator+'
// Traducción: intentas usar + con una clase que no tiene ese operador sobrecargado
// Solución: implementa el operador o verifica que los tipos coincidan

error: passing 'const Fraccion' as 'this' discards qualifiers
// Traducción: tu función modifica el objeto pero lo declaraste const
// Solución: agrega const al final → Fraccion operator+(const Fraccion& otra) const
```

---

**Recursos para esta semana:**
- 🔧 Práctica: crea una clase `Vector2D` y sobrecarga `+`, `-`, `==` y `<<`
- 🔧 Antes de sobrecargar cualquier operador, pregúntate: "¿se lee completamente natural?"

---

## 📅 Sesión 14 — Templates y Archivos

### 🎓 Lo que enseña la universidad
- Plantillas genéricas (templates)
- Archivos: definición y modos de uso

### ➕ Lo que debes estudiar adicionalmente

---

#### 🧠 Templates — una función para cualquier tipo de dato

```cpp
// Sin template — función repetida para cada tipo
int    sumar(int a,    int b)    { return a + b; }
float  sumar(float a,  float b)  { return a + b; }
double sumar(double a, double b) { return a + b; }

// Con template — una sola función para todos los tipos
template <typename T>
T sumar(T a, T b) {
    return a + b;
}

// Funciona con cualquier tipo
cout << sumar(3, 5);         // int    → 8
cout << sumar(2.5, 1.5);    // float  → 4.0
cout << sumar(1.1, 2.2);    // double → 3.3
```

---

#### ✏️ Clean Code — Manejo correcto de archivos

```cpp
// ❌ Sin validación — el programa crashea si el archivo no existe
ifstream archivo("datos.txt");
string linea;
getline(archivo, linea);

// ✅ Con validación — el programa maneja el error con gracia
ifstream archivo("estudiantes.txt");

if (!archivo.is_open()) {
    cerr << "Error: no se pudo abrir el archivo 'estudiantes.txt'" << endl;
    return 1;   // código de error, no continúes
}

string linea;
while (getline(archivo, linea)) {
    cout << linea << endl;
}

archivo.close();   // siempre cierra el archivo al terminar
```

---

#### 💬 Documenta siempre el formato de tus archivos

```cpp
/**
 * Lee el archivo de estudiantes con el siguiente formato:
 * Cada línea contiene: nombre,edad,promedio
 * Ejemplo:
 *   Angel Gomez,19,16.5
 *   Maria Lopez,20,18.0
 *
 * Retorna un vector con todos los estudiantes leídos.
 * Si el archivo no existe, retorna un vector vacío.
 */
vector<Estudiante> leerEstudiantes(const string& nombreArchivo) {
    vector<Estudiante> estudiantes;
    ifstream archivo(nombreArchivo);

    if (!archivo.is_open()) {
        cerr << "Advertencia: no se encontró " << nombreArchivo << endl;
        return estudiantes;   // retorna vacío en vez de crashear
    }
    // ...
    archivo.close();
    return estudiantes;
}
```

---

#### 🌐 Conoce JSON — el formato de datos del mundo real

La universidad usa `.txt`, pero el mundo real usa JSON. Al menos entiende cómo luce:

```json
{
  "nombre": "Angel",
  "edad": 19,
  "notas": [15, 18, 16, 20],
  "activo": true
}
```

No necesitas usarlo ahora. Pero cuando empieces proyectos más grandes, lo verás en todas partes.

---

#### 🔍 Errores comunes con archivos en CLion

```
El programa no encuentra el archivo
// Causa: CLion ejecuta desde cmake-build-debug/, no desde la raíz del proyecto
// Solución: usa la ruta completa o configura el Working Directory en
//           Run → Edit Configurations → Working Directory
```

---

**Recursos para esta semana:**
- 🔧 Práctica: crea un sistema que guarde y lea estudiantes desde un archivo de texto
- 🔧 Aplica templates a funciones que hayas escrito en semanas anteriores

---

## 📚 Recursos generales recomendados

| Recurso | Para qué sirve |
|---|---|
| 📺 **Programación ATS** (YouTube) | C++ desde cero en español |
| 📺 **HolaMundo** (YouTube) | POO y conceptos avanzados |
| 📺 **MoureDev** (YouTube) | Git, GitHub y buenas prácticas |
| 🌐 **cppreference.com** | Documentación oficial de C++ |
| 🌐 **Stack Overflow** | Resolver errores específicos |
| 📖 **"Fundamentos de Programación"** — Luis Joyanes | Lógica y algoritmos en español |

---

## 🛠️ Herramientas que debes dominar este ciclo

| Herramienta | Para qué | Cuándo empezar |
|---|---|---|
| **CLion** | IDE principal con debugger integrado | Semana 0, antes de empezar |
| **Git + GitHub** | Versionar y guardar tu código | Semana 0, antes de empezar |
| **Debugger de CLion** | Encontrar errores paso a paso | Sesión 2 |
| **Draw.io** | Diagramas UML antes de escribir clases | Antes de sesión 8 |
| **Stack Overflow** | Buscar soluciones a errores concretos | Desde el día 1 |

---

## 🔍 Guía rápida: Cómo buscar ayuda en Stack Overflow

Cuando tengas un error que no entiendes, sigue este proceso:

1. **Copia el mensaje de error exacto** de CLion (sin los nombres de tus archivos)
2. **Pégalo en Google** con "C++" al inicio
3. **Busca la respuesta con más votos** en Stack Overflow
4. **Lee la pregunta completa** antes de copiar el código
5. **Entiende por qué funciona** la solución antes de aplicarla

```
// Ejemplo de búsqueda efectiva en Google:
C++ error: no matching function for call to constructor

// Búsqueda inefectiva:
mi código no funciona en CLion
```

---

## ✅ Checklist semanal

Antes de pasar a la siguiente sesión, verifica:

- [ ] Entendí el tema de la universidad sin mirar los apuntes
- [ ] Reproduje el código de clase desde cero
- [ ] Apliqué Clean Code: nombres descriptivos y comentarios útiles
- [ ] Estudié el tema adicional de esa sesión
- [ ] Guardé mi código en GitHub con un commit descriptivo
- [ ] Puedo explicarle el concepto a alguien más con mis propias palabras

> Si no puedes explicarlo con tus propias palabras, aún no lo entiendes del todo.
> Esa es la prueba real.

---

*Plan de estudio personal — 14 semanas — C++ y buenas prácticas de programación*
