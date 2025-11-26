<!--
author:   Filippo Orsini

email:    filippo.orsini@savoiabenincasa.it

version:  0.0.1

language: it

narrator: IT Italian Male

comment:  Quaderno elettronico di Informatica. Classe 3za. Capitolo 4. Il linguaggio C++.

import: https://raw.githubusercontent.com/LiaScript/CodeRunner/master/README.md

import: https://raw.githubusercontent.com/liascript-templates/plantUML/master/README.md

-->

# Il linguaggio C++

[Visualizza su LiaScript](https://liascript.github.io/course/?https://raw.githubusercontent.com/Filippo-Orsini/Q.E-3-B-MOD/refs/heads/main/README.md#1)

Appunti del capitolo 4 del libro di testo pp. 86--121.

Per ogni programma presentato nel testo (pp. 86, 93, 98, 99, 103, 105, 106, 107, 109, 110, 112, 115, 118, 119, 121):

1. **Predict** Esamina il programma e cerca di capire cosa farà;
2. Copia il programma in modo da poterlo eseguire sul computer; eseguilo per verificare la previsione; 
3. **Investigate** Copia il programma su PythonTutor/linguaggio C++ ed esegui passo passo il programma per comprendere come evolve il processo generato dal programma. Controlla l'evoluzione della memoria ad ogni operazione di assegnamento; Copia il link dell'esecuzione del programma (Generate embed code).
4. **Modify** Modifica il codice cambiando prima qualcosa di semplice, quindi apportate sempre più modifiche per appropriarti poco alla volta del codice sorgente. Ad esempio, se il programma usa dati scritti nel codice sorgente, modifica il programma per chiedere i dati tramite un'istruzione di input; se un programma usa valori di tipo intero, prova a sostituirli con numeri in virgola mobile...
5. **Make** Scrivi un nuovo programma, in cui puoi prendere in prestito frammenti di codice dal programma originale, che realizza una funzione diversa, oppure la stessa funzione applicata in un contesto, o problema, diverso.

## Le basi del linguaggio


### PROGRAMMA A PAG 86 - Somma.cpp

``` c +Somma.cpp
// Somma.cpp
#include <iostream> 
using namespace std;

int main() {
    int a, b, s;
    cout << "Immetti un addendo intero: ";
    cin >> a;
    cout << "Immetti un altro addendo intero: ";
    cin >> b;
    s = a + b;
    cout << "La somma è: " << s << endl;

    return 0;
    
}
```
@LIA.cpp

#### 1. Predict (p. 86)

Il programma dichiara tre variabili intere, `a`, `b` e `s`.
Legge due numeri interi dati in ingresso memorizzandoli nelle variabili `a` e `b`, calcola la somma di queste due variabili memorizzandola in `s` e ne stampa il valore.

#### 2. Run (p. 86)

Il programma conferma la previsione

#### 3. Investigate (p. 86)

``` cpp +Somma.cpp
// Somma.cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, s;
    cin >> a;
    cin >> b;
    s = a + b;
    cout << s;

    return 0;
}
```
@LIA.evalWithDebug(`["Somma.cpp"]`, `g++ -g -Wall Somma.cpp -o a.out`, `./a.out`)


Per usare PythonTutor devo impostare dei valori alle variabili di input.
Uso 1 e 2.

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0A%0Aint%20main%28%29%20%7B%0A%20%20%20%20int%20a,%20b,%20s%3B%0A%20%20%20%20//cin%20%3E%3E%20a%3B%0A%20%20%20%20a%20%3D%201%3B%0A%20%20%20%20//cin%20%3E%3E%20b%3B%0A%20%20%20%20b%20%3D%202%3B%0A%20%20%20%20s%20%3D%20a%20%2B%20b%3B%0A%20%20%20%20cout%20%3C%3C%20s%3B%0A%0A%20%20%20%20return%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=6&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>


#### 4. Modify  (p. 86)

Voglio aggiungere informazioni all'utente per comunicare di immettere i numeri intero, voglio essere più descrittivo e andare a capo nell'output.

``` cpp +Somma.cpp
// Somma.cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, s;
    cout << "Immetti un addendo intero: ";
    cin >> a;
    cout << "Immetti un altro addendo intero: ";
    cin >> b;
    s = a + b;
    cout << "La somma di " << a << " e " << b << " e' pari a " << s << "." << endl;

    return 0;
}
```

#### 5. Make (p. 86)

Scrivo un nuovo programma che calcola il prodotto.

``` cpp +Prodotto.cpp
// Prodotto.cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, p;
    cout << "Immetti un moltiplicando intero: ";
    cin >> a;
    cout << "Immetti un altro moltiplicando intero: ";
    cin >> b;
    p = a * b;
    cout << "Il prodotto di " << a << " e " << b << " e' pari a " << p << "." << endl;

    return 0;
}
```
@LIA.cpp

#Il linguaggio C++
##Le basi del linguaggio
##PROGRAMMA A PAG.. 93 - Tipi.cpp
// Tipi.cpp:dimensioni     dei tipi
#include <iostream>
using namespace std;

int main() {
    cout << "Dimensioni di int: " << sizeof(int) << " byte\n";
    cout << "Dimensioni di short int: " << sizeof(short int) << " byte\n";
    cout << "Dimensioni di long int: " << sizeof(long int) << " byte\n";
    cout << "Dimensioni di long long int: " << sizeof(long long int) << " byte\n";
    cout << "Dimensioni di float: " << sizeof(float) << " byte\n";
    cout << "Dimensioni di double: " << sizeof(double) << " byte\n";
    cout << "Dimensioni di long double: " << sizeof(long double) << " byte\n";
    cout << "Dimensioni di char: " << sizeof(char) << " byte\n";
    cout << "Dimensioni di bool: " << sizeof(bool) << " byte\n";

    return 0;
}

@LIA.cpp

##### 1. Predict (p. 93)

Il programma stamperà sullo schermo la dimensione in byte dei vari tipi di dato in C++

##### 2. Run (p. 93)

eseguire il codice e osservare le dimensioni in byte dei diversi tipi di dato che vengono visualizzate riga per riga

#### 3. Investigate

#include <iostream>
using namespace std;

int main () {
    cout << "Dimensioni di int: " << sizeof(int) << " byte\n";
    cout << "Dimensioni di short int: " << sizeof(short int) << " byte\n";
    cout << "Dimensioni di long int: " << sizeof(long int) << " byte\n";
    cout << "Dimensioni di long long int: " << sizeof(long long int) << " byte\n";
    cout << "Dimensioni di float: " << sizeof(float) << " byte\n";
    cout << "Dimensioni di double: " << sizeof(double) << " byte\n";
    cout << "Dimensioni di long double: " << sizeof(long double) << " byte\n";
    cout << "Dimensioni di char: " << sizeof(char) << " byte\n";
    cout << "Dimensioni di bool: " << sizeof(bool) << " byte\n";
    return 0;
}

#### 4. Modify

#include <iostream>
using namespace std;

int main () {
    cout << "=== Dimensioni dei tipi di dato in C++ ===\n\n";

    cout << "int: " << sizeof(int) << " byte\n";
    cout << "short int: " << sizeof(short int) << " byte\n";
    cout << "long int: " << sizeof(long int) << " byte\n";
    cout << "long long int: " << sizeof(long long int) << " byte\n";
    cout << "float: " << sizeof(float) << " byte\n";
    cout << "double: " << sizeof(double) << " byte\n";
    cout << "long double: " << sizeof(long double) << " byte\n";
    cout << "char: " << sizeof(char) << " byte\n";
    cout << "bool: " << sizeof(bool) << " byte\n";
    cout << "unsigned int: " << sizeof(unsigned int) << " byte\n";

    return 0;

#### 5. Make

#include <iostream>
using namespace std;

int main () {
    cout << "Dimensioni dei tipi signed:\n";
    cout << "int: " << sizeof(int) << " byte\n";
    cout << "short int: " << sizeof(short int) << " byte\n";
    cout << "long int: " << sizeof(long int) << " byte\n";
    cout << "long long int: " << sizeof(long long int) << " byte\n";
    cout << "float: " << sizeof(float) << " byte\n";
    cout << "double: " << sizeof(double) << " byte\n";
    cout << "long double: " << sizeof(long double) << " byte\n";
    cout << "char: " << sizeof(char) << " byte\n";
    cout << "bool: " << sizeof(bool) << " byte\n\n";

    cout << "Dimensioni dei tipi unsigned:\n";
    cout << "unsigned int: " << sizeof(unsigned int) << " byte\n";
    cout << "unsigned short int: " << sizeof(unsigned short int) << " byte\n";
    cout << "unsigned long int: " << sizeof(unsigned long int) << " byte\n";

    return 0;

}

### File.cpp - pag. 94
c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () {
    double raggio= 10;
    double area = raggio * raggio * 3.14;
    int tempo_in_sec = 900;
    int durata_in_minuti = tempo_in_sec / 60;
    double spazio = 1000; // 1 km
    double tempo = 6 * 60; // 6 minuti
    double velocita= spazio / tempo;
    string nome = "Rossi";

returno 0;
}

@LIA.cpp

#### 1. Predict (p. 94)
Il programma dichiara di avere alcuni variabili e costamti con tipi primitivi e definiti dalla libreria standard ( string )

#### 2. Run l'esecuzione conferma quanto scritto del predict

#### 3. Investigate

Per usare PythonTutor devo impostare dei valori alle variabili di input.

<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=//%20asssegnazione.cpp%0A%23include%20%3Ciostream%3E%0Ausing%20namespace%20std%3B%0Aint%20main%20%28%29%20%7B%0A%20%20%20%20double%20raggio%3D%2010%3B%0A%20%20%20%20double%20area%20%3D%20raggio%20*%20raggio%20*%203.14%3B%0A%20%20%20%20int%20tempo_in_sec%20%3D%20900%3B%0A%20%20%20%20int%20durata_in_minuti%20%3D%20tempo_in_sec%20/%2060%3B%0A%20%20%20%20double%20spazio%20%3D%201000%3B%20//%201%20km%0A%20%20%20%20double%20tempo%20%3D%206%20*%2060%3B%20//%206%20minuti%0A%20%20%20%20double%20velocita%20%3D%20spazio%20/%20tempo%3B%0A%20%20%20%20string%20nome%20%3D%20%22Rossi%22%3B%0A%0Areturn%200%3B%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=nevernest&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

### 4. Modify
// Calcolo dell'età
    int anno_nascita = 2005;
    int anno_corrente = 2025;
    int eta = anno_corrente - anno_nascita;

    cout << "Nome: " << nome << endl;
    cout << "Età: " << eta << " anni" << endl;
}
### 5. Make

#include <iostream>
using namespace std;

int main () {
    string nome = "Rossi";
    double altezza = 1.75; // metri
    double peso = 70;       // kg

    double imc = peso / (altezza * altezza);

    int anno_nascita = 2005;
    int anno_corrente = 2025;
    int eta = anno_corrente - anno_nascita;

    cout << "Nome: " << nome << endl;
    cout << "Età: " << eta << " anni" << endl;
    cout << "IMC: " << imc << endl;
}

#Il linguaggio C++
##Le basi del linguaggio
##PROGRAMMA A PAG.. 98 - Tipi.cpp



### File.cpp - pag. 98
c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main () 
{
    int a= 5;
    float b = 3.56;
    b = a;
    cout << b;

return 0;
}

@LIA.cpp

#### 1. Predict (p.98)
a è un intero con valore 5, b è un float inizialmente 3.56, ma poi diventa uguale a a (b = a) , quindi b diventerà 5.

#### 2. Run
Il programma stamperà il numero 5

#### 3. Investigate 

#### 4. Modify
#include <iostream>
using namespace std;

int main () 
{
    int a = 5;
    float b = 3.56;
    b = a;

    float somma = a + b;
    cout << "b = " << b << endl;
    cout << "Somma a+b = " << somma << endl;

    return 0;
}

##### 5. Make 
#include <iostream>
using namespace std;

int main()
{
    float a = 7.5;
    float b = 2.5;

    float risultato = a / b;

    cout << "Risultato della divisione: " << risultato << endl;

    return 0;
}

#Il linguaggio C++
##Le basi del linguaggio
##PROGRAMMA A PAG.. 98 - Tipi.cpp

c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main ()
{
    int a = 5;
    float b = 3.56; 
    a = b;
    cout << a;

    return 0;
}

@Lia.cpp

#### 1. Predict (p.98)
a è un intero con valore 5, b è un float inizialmente 3.56, ma poi diventa uguale a b (a = b) , quindi b sarà troncato ad 3.

#### 2. Run
Il programma stamperà il numero 3

##### 3. Investigate

#### 4. Modify
#include <iostream>
using namespace std;

int main ()
{
    int a = 5;
    float b = 3.56;

    a = b; // assegnazione float -> int (troncamento)
    float somma = a + b; // somma tra int troncato e float

    cout << "a (troncato) = " << a << endl;
    cout << "b = " << b << endl;
    cout << "Somma a+b = " << somma << endl;

    return 0;
}

##### 5. Make
#include <iostream>
using namespace std;

int main ()
{
    int a = 7;
    float b;

    b = a; // int -> float (conversione automatica)
    float prodotto = a * b;

    cout << "a = " << a << endl;
    cout << "b (convertito in float) = " << b << endl;
    cout << "Prodotto a*b = " << prodotto << endl;

    return 0;
}

#Il linguaggio C++
##Le basi del linguaggio
##PROGRAMMA A PAG.. 98 - Tipi.cpp

c assegnazione.cpp
// asssegnazione.cpp
#include <iostream>
using namespace std;

int main() 
{
  int a = 5;
  int b = 2;
  float c = 3.56;
  float p;
  p = a/b + c;
  cout << p;

  return 0;
}

##### 1. Predict
 la divisione a/b dovrà essere 2 e la somma porterà 5.56

 ##### 2. Run
 il programma stamperà il numero 5.56

 #### 3. Investigate

 #### 4. Modify
#include <iostream>
using namespace std;

int main() 
{
    int a = 5;
    int b = 2;
    float c = 3.56;
    float p;

    p = float(a)/b + c;  // divisione reale
    cout << "a/b = " << float(a)/b << endl;
    cout << "c = " << c << endl;
    cout << "p = " << p << endl;

    return 0;
} 

##### 5. Make
#include <iostream>
using namespace std;

int main() 
{
    int a = 5;
    int b = 2;
    float c = 3.56;
    float p;

    p = (float(a)/b) * c;  
    cout << p;

    return 0;
}

#Il linguaggio C++
##Le basi del linguaggio
##PROGRAMMA A PAG.. 103 - Tipi.cpp

// Parcogiochi.cpp: divisione dei biglietti
#include <iostream>
using namespace std;

int main () 
{
  // input
  int biglietti, ragazzi;
  // output
  int quota, avanzo;

  cout << "Numero di biglietti e di ragazzi: ";
  cin >> biglietti >> ragazzi;
  quota = biglietti / ragazzi;
  avanzo = biglietti % ragazzi;
  cout << "Ad ogni ragazzo spettano " << quota << " biglietti " << endl;
  cput << "e ne avanzano " << avanzo << endl;

  return 0;
}

##### 1. Predict 
con quota si troverranno i numeri di biglietti che ha una persona e con l'avanzo è quello che rimane dolo pa divisione dei blieglietti / ragazzi

##### 2. Run
Il programma farà vedere il risultato trovato

##### 3. Investigate
##### 4. Modify
#include <iostream>
using namespace std;

int main () 
{
  int biglietti, ragazzi;
  int quota, avanzo;

  cout << "Numero di biglietti e di ragazzi: ";
  cin >> biglietti >> ragazzi;

  quota = biglietti / ragazzi;
  avanzo = biglietti % ragazzi;

  int distribuiti = quota * ragazzi;

  cout << "Ad ogni ragazzo spettano " << quota << " biglietti " << endl;
  cout << "e ne avanzano " << avanzo << endl;
  cout << "Totale biglietti distribuiti: " << distribuiti << endl;

  return 0;

#### 5. Make 
#include <iostream>
using namespace std;

int main () 
{
  int biglietti, ragazzi;
  int quota, avanzo;

  cout << "Numero di biglietti e di ragazzi: ";
  cin >> biglietti >> ragazzi;

  // Calcolo per gruppi di 2 ragazzi
  quota = biglietti / (2 * ragazzi);
  avanzo = biglietti % (2 * ragazzi);

  cout << "Ad ogni coppia di ragazzi spettano " << quota << " biglietti " << endl;
  cout << "e ne avanzano " << avanzo << endl;

  return 0;
}


#Il linguaggio C++
##Le basi del linguaggio
##PROGRAMMA A PAG.. 103 - Tipi.cpp

// Quoziente.cpp : divisione di due numeri
#include <iostream>
using namespace std;

int main () 
{
 int a, b, q;
 cin >> a >> b;
 q = a / b;
 cout << q;

 return 0;
}

##### 1. Predict
a, b, avranno due numeri interi e la quota mi darà la divisione dei due numeri

##### 2. Run
il programma stamperà il valore della quota

#### 3. Investigate 

#### 4. Modify
#include <iostream>
using namespace std;

int main () 
{
    int a, b, q, resto;
    cin >> a >> b;
    q = a / b;
    resto = a % b;

    cout << q <<;
    cout << resto;

    return 0;
}

#### 5. Make 
#include <iostream>
using namespace std;

int main () 
{
    float a, b, q;
    cin >> a >> b;
    q = a / b;
    cout <<  q;

    return 0;
}

#Il linguaggio C++
##Le basi del linguaggio
##PROGRAMMA A PAG.. 106 - Tipi.cpp















