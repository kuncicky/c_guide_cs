# Kompletní průvodce programováním v C

## 1. Datové typy v C

C nabízí několik základních datových typů, které se dělí do následujících kategorií:

1. **Celočíselné typy**:

   - `int`: Základní celočíselný typ, obvykle 4 byty (32 bitů)
   - `short`: Krátké celé číslo, obvykle 2 byty (16 bitů)
   - `long`: Dlouhé celé číslo, obvykle 4 nebo 8 bytů
   - `long long`: Velmi dlouhé celé číslo, minimálně 8 bytů
   - `char`: Nejmenší adresovatelná jednotka, 1 byte

   Každý z těchto typů může být `signed` (se znaménkem) nebo `unsigned` (bez znaménka).

2. **Typy s plovoucí desetinnou čárkou**:

   - `float`: Jednoduchá přesnost, obvykle 4 byty
   - `double`: Dvojitá přesnost, obvykle 8 bytů
   - `long double`: Rozšířená přesnost, obvykle 10 nebo 16 bytů

3. **Void**:

   - `void`: Označuje absenci typu nebo hodnoty

4. **Booleovský typ**:

   - `_Bool`: Logický typ (C99 a novější), může nabývat hodnot 0 nebo 1

5. **Komplexní typy** (C99 a novější):
   - `_Complex`: Pro komplexní čísla
   - `_Imaginary`: Pro imaginární čísla

Příklady deklarace a použití:

```c
int a = 10;
unsigned long b = 1000000UL;
float c = 3.14f;
double d = 3.14159265359;
char e = 'A';
_Bool f = 1;  // true
_Complex float g = 1.0 + 2.0*I;
```

Důležité poznámky:

- Velikost datových typů může záviset na architektuře a kompilátoru.
- Použití `sizeof()` operátoru vám pomůže zjistit přesnou velikost typu na vaší platformě.
- Při práci s čísly s plovoucí desetinnou čárkou buďte opatrní kvůli možným chybám zaokrouhlování.
- Vždy zvažte rozsah hodnot, které budete ukládat, a vyberte vhodný datový typ.
- Používejte vhodné přípony pro literály (např. `UL` pro unsigned long, `f` pro float).

## 2. Proměnné v C

Proměnné v C jsou pojmenované místa v paměti, kde můžeme ukládat data. Jsou základním stavebním kamenem každého programu v C.

### Definice proměnných

Definice proměnné zahrnuje specifikaci datového typu a názvu proměnné. Například:

```c
int age;
float salary;
char initial;
```

### Inicializace proměnných

Inicializace je proces přiřazení počáteční hodnoty proměnné při její definici:

```c
int count = 0;
float pi = 3.14159;
char grade = 'A';
```

### Pravidla pro pojmenování proměnných

1. Mohou obsahovat písmena, číslice a podtržítka.
2. Musí začínat písmenem nebo podtržítkem.
3. Jsou case-sensitive (rozlišují velká a malá písmena).
4. Nemohou být klíčovými slovy jazyka C.

### Rozsah a životnost proměnných

1. **Lokální proměnné**: Deklarované uvnitř funkce, existují pouze v rámci této funkce.
2. **Globální proměnné**: Deklarované mimo všechny funkce, přístupné z celého programu.
3. **Statické proměnné**: Zachovávají svou hodnotu mezi voláními funkce.

### Konstanty

Konstanty jsou proměnné, jejichž hodnotu nelze měnit:

```c
const int MAX_STUDENTS = 100;
#define PI 3.14159
```

### Modifikátory typu

- `const`: Vytvoří proměnnou jen pro čtení
- `volatile`: Označuje proměnnou, která se může neočekávaně změnit
- `static`: Mění životnost a viditelnost proměnné
- `extern`: Deklaruje proměnnou definovanou v jiném souboru

### Typové přetypování

Změna typu proměnné:

```c
int x = 10;
float y = (float)x / 3;
```

Pamatujte, že správné použití proměnných je klíčové pro efektivní a bezpečné programování v C. Vždy inicializujte proměnné před použitím a vybírejte vhodné datové typy pro vaše potřeby.

## 3. Operátory v C

Operátory v C jsou symboly, které říkají kompilátoru, aby provedl specifické matematické nebo logické manipulace. C je bohatý na vestavěné operátory a poskytuje následující typy:

### Aritmetické operátory

- `+` (sčítání)
- `-` (odčítání)
- `*` (násobení)
- `/` (dělení)
- `%` (zbytek po dělení)

Příklad:

```c
int a = 10, b = 3;
int sum = a + b;  // 13
int diff = a - b;  // 7
int product = a * b;  // 30
int quotient = a / b;  // 3
int remainder = a % b;  // 1
```

### Relační operátory

- `==` (rovná se)
- `!=` (nerovná se)
- `>` (větší než)
- `<` (menší než)
- `>=` (větší nebo rovno)
- `<=` (menší nebo rovno)

Příklad:

```c
int x = 5, y = 7;
if (x < y) {
    printf("x je menší než y");
}
```

### Logické operátory

- `&&` (logické AND)
- `||` (logické OR)
- `!` (logické NOT)

Příklad:

```c
int a = 5, b = 10;
if (a > 0 && b < 20) {
    printf("Obě podmínky jsou splněny");
}
```

### Bitové operátory

- `&` (bitové AND)
- `|` (bitové OR)
- `^` (bitové XOR)
- `~` (bitový komplement)
- `<<` (bitový posun vlevo)
- `>>` (bitový posun vpravo)

Příklad:

```c
unsigned int a = 60;  // 0011 1100
unsigned int b = 13;  // 0000 1101
int c = a & b;  // 0000 1100
```

### Přiřazovací operátory

- `=` (základní přiřazení)
- `+=`, `-=`, `*=`, `/=`, `%=`, `<<=`, `>>=`, `&=`, `^=`, `|=` (složené přiřazení)

Příklad:

```c
int x = 10;
x += 5;  // ekvivalent x = x + 5;
```

### Operátory inkrementace a dekrementace

- `++` (zvýšení o 1)
- `--` (snížení o 1)

Příklad:

```c
int i = 5;
i++;  // i je nyní 6
```

### Podmínkový operátor

- `?:` (ternární operátor)

Příklad:

```c
int a = 10, b = 20;
int max = (a > b) ? a : b;  // max bude 20
```

### Operátor sizeof

Vrací velikost datového typu nebo proměnné v bytech.

Příklad:

```c
int size = sizeof(int);  // obvykle vrátí 4
```

### Operátory pro práci s pointery

- `&` (adresní operátor)
- `*` (dereferencující operátor)

Příklad:

```c
int x = 5;
int *ptr = &x;  // ptr obsahuje adresu x
int y = *ptr;  // y obsahuje hodnotu na adrese uložené v ptr
```

Porozumění operátorům a jejich prioritě je klíčové pro psaní správných a efektivních programů v C. Vždy mějte na paměti prioritu operátorů a v případě pochybností používejte závorky pro explicitní vyjádření zamýšleného pořadí operací.

## 4. Řízení toku programu v C

Řízení toku programu je základním aspektem programování v C. Umožňuje nám rozhodovat o průběhu programu na základě různých podmínek a opakovat určité části kódu. Zde jsou hlavní konstrukce pro řízení toku programu:

### Podmínkové příkazy

1. **if příkaz**
   Provede blok kódu, pokud je podmínka pravdivá.

   ```c
   if (podmínka) {
       // kód, který se provede, pokud je podmínka pravdivá
   }
   ```

2. **if-else příkaz**
   Přidává alternativní blok kódu, který se provede, pokud podmínka není pravdivá.

   ```c
   if (podmínka) {
       // kód, který se provede, pokud je podmínka pravdivá
   } else {
       // kód, který se provede, pokud podmínka není pravdivá
   }
   ```

3. **if-else if-else příkaz**
   Umožňuje testovat více podmínek.

   ```c
   if (podmínka1) {
       // kód pro podmínku1
   } else if (podmínka2) {
       // kód pro podmínku2
   } else {
       // kód, když žádná podmínka není splněna
   }
   ```

4. **switch příkaz**
   Umožňuje vybrat jeden z mnoha bloků kódu k provedení.

   ```c
   switch (výraz) {
       case hodnota1:
           // kód pro hodnotu1
           break;
       case hodnota2:
           // kód pro hodnotu2
           break;
       default:
           // kód, když žádná hodnota neodpovídá
   }
   ```

### Cykly

1. **for cyklus**
   Používá se, když víme, kolikrát chceme opakovat blok kódu.

   ```c
   for (inicializace; podmínka; aktualizace) {
       // kód, který se má opakovat
   }
   ```

   Příklad:

   ```c
   for (int i = 0; i < 5; i++) {
       printf("%d ", i);
   }
   ```

2. **while cyklus**
   Opakuje blok kódu, dokud je podmínka pravdivá.

   ```c
   while (podmínka) {
       // kód, který se má opakovat
   }
   ```

   Příklad:

   ```c
   int i = 0;
   while (i < 5) {
       printf("%d ", i);
       i++;
   }
   ```

3. **do-while cyklus**
   Podobný while cyklu, ale garantuje, že se blok kódu provede alespoň jednou.

   ```c
   do {
       // kód, který se má opakovat
   } while (podmínka);
   ```

   Příklad:

   ```c
   int i = 0;
   do {
       printf("%d ", i);
       i++;
   } while (i < 5);
   ```

### Příkazy pro změnu toku

1. **break**
   Ukončí aktuální cyklus nebo switch.

   ```c
   for (int i = 0; i < 10; i++) {
       if (i == 5) {
           break;  // ukončí cyklus, když i je 5
       }
       printf("%d ", i);
   }
   ```

2. **continue**
   Přeskočí zbytek aktuální iterace cyklu a pokračuje další iterací.

   ```c
   for (int i = 0; i < 5; i++) {
       if (i == 2) {
           continue;  // přeskočí iteraci, když i je 2
       }
       printf("%d ", i);
   }
   ```

3. **goto**
   Přesměruje tok programu na označené místo v kódu. Používejte opatrně, může vést k nepřehlednému kódu.

   ```c
   for (int i = 0; i < 5; i++) {
       if (i == 3) {
           goto konec;  // přeskočí na označené místo
       }
       printf("%d ", i);
   }
   konec:
   printf("Konec");
   ```

Efektivní použití těchto konstrukcí je klíčové pro vytváření logických a efektivních programů. Vždy se snažte o čitelný a dobře strukturovaný kód.

## 5. Funkce v C

Funkce jsou základními stavebními bloky programů v C. Umožňují rozdělit kód do menších, znovupoužitelných částí, což zlepšuje čitelnost, údržbu a modularitu programu.

### Definice funkce

Obecná syntax definice funkce:

```c
návratový_typ název_funkce(parametr1, parametr2, ...) {
    // tělo funkce
    return hodnota;  // volitelné
}
```

Příklad:

```c
int soucet(int a, int b) {
    return a + b;
}
```

### Deklarace funkce (prototyp)

Deklarace funkce informuje kompilátor o existenci funkce před její definicí:

```c
int soucet(int a, int b);
```

### Volání funkce

Funkci voláme použitím jejího názvu a poskytnutím argumentů:

```c
int vysledek = soucet(5, 3);
```

### Parametry funkce

- **Předávání hodnotou**: Funkce pracuje s kopií hodnoty.
- **Předávání odkazem**: Funkce pracuje přímo s originální proměnnou (pomocí pointerů).

```c
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

// Použití:
int x = 5, y = 10;
swap(&x, &y);
```

### Návratové hodnoty

Funkce může vracet hodnotu pomocí klíčového slova `return`. Pokud funkce nic nevrací, použijeme typ `void`.

```c
int getNásobek(int číslo, int násobitel) {
    return číslo * násobitel;
}

void pozdrav() {
    printf("Ahoj, světe!\n");
}
```

### Rekurze

Funkce může volat sama sebe:

```c
int faktoriál(int n) {
    if (n <= 1) return 1;
    return n * faktoriál(n - 1);
}
```

### Inline funkce

Klíčové slovo `inline` naznačuje kompilátoru, že má zvážit vložení těla funkce přímo do místa volání:

```c
inline int max(int a, int b) {
    return (a > b) ? a : b;
}
```

### Funkční ukazatele

Ukazatele na funkce umožňují dynamicky vybírat, která funkce se má zavolat:

```c
int (*funkce_ptr)(int, int);
funkce_ptr = soucet;  // přiřazení adresy funkce
int výsledek = (*funkce_ptr)(5, 3);  // volání funkce přes ukazatel
```

### Variadic funkce

Funkce s proměnným počtem argumentů:

```c
#include <stdarg.h>

int suma(int počet, ...) {
    va_list args;
    va_start(args, počet);
    int součet = 0;
    for (int i = 0; i < počet; i++) {
        součet += va_arg(args, int);
    }
    va_end(args);
    return součet;
}

// Použití:
int výsledek = suma(3, 10, 20, 30);
```

Funkce jsou klíčové pro organizaci kódu a znovupoužitelnost. Správné použití funkcí může výrazně zlepšit čitelnost a udržovatelnost vašeho programu.

## 6. Pole a řetězce v C

Pole a řetězce jsou důležité datové struktury v C, které umožňují efektivně pracovat s kolekcemi dat.

### Pole

Pole je kolekce prvků stejného datového typu uložených v souvislé paměti.

#### Deklarace a inicializace pole:

```c
int čísla[5];  // deklarace pole o 5 prvcích
int sudá[] = {2, 4, 6, 8, 10};  // inicializace při deklaraci
```

#### Přístup k prvkům pole:

```c
čísla[0] = 1;  // přiřazení hodnoty prvnímu prvku
int třetí = sudá[2];  // získání hodnoty třetího prvku
```

#### Vícedimenzionální pole:

```c
int matice[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

### Řetězce

V C jsou řetězce reprezentovány jako pole znaků ukončené nulovým znakem '\0'.

#### Deklarace a inicializace řetězců:

```c
char pozdrav[] = "Ahoj";  // implicitně přidá '\0' na konec
char jméno[20];  // deklarace řetězce s maximální délkou 19 znaků
```

#### Operace s řetězci:

Pro práci s řetězci se často používá knihovna `<string.h>`.

```c
#include <string.h>

char str1[20] = "Hello";
char str2[] = " World";

strcat(str1, str2);  // spojení řetězců
int délka = strlen(str1);  // zjištění délky řetězce
int porovnání = strcmp(str1, "Hello World");  // porovnání řetězců
```

#### Bezpečné funkce pro práci s řetězci:

```c
char cíl[20];
strncpy(cíl, zdroj, sizeof(cíl) - 1);  // kopírování s omezením délky
cíl[sizeof(cíl) - 1] = '\0';  // zajištění ukončovacího znaku
```

### Dynamická alokace polí

Použití funkce `malloc()` pro dynamickou alokaci paměti:

```c
int *pole = (int *)malloc(5 * sizeof(int));
if (pole == NULL) {
    // Ošetření chyby alokace
}
// Použití pole
free(pole);  // Uvolnění alokované paměti
```

### Předávání polí funkcím

Při předávání pole funkci se ve skutečnosti předává ukazatel na první prvek:

```c
void tiskniPole(int *pole, int velikost) {
    for (int i = 0; i < velikost; i++) {
        printf("%d ", pole[i]);
    }
}

// Použití:
int čísla[] = {1, 2, 3, 4, 5};
tiskniPole(čísla, 5);
```

Pole a řetězce jsou základními nástroji pro práci s daty v C. Je důležité pamatovat na omezení statických polí a vždy kontrolovat hranice pole, aby se předešlo přetečení bufferu. Při práci s dynamicky alokovanými poli nezapomeňte vždy uvolnit paměť pomocí `free()`, abyste předešli únikům paměti.

## 7. Pointery v C

Pointery (ukazatele) jsou jedním z nejdůležitějších a zároveň nejnáročnějších konceptů v C. Umožňují přímou manipulaci s pamětí a jsou základem pro mnoho pokročilých technik programování.

### Základy pointerů

Pointer je proměnná, která obsahuje adresu jiné proměnné v paměti.

#### Deklarace pointeru:

```c
int *p;  // pointer na int
char *c;  // pointer na char
```

#### Operátory související s pointery:

- `&`: Získá adresu proměnné
- `*`: Dereferencuje pointer (získá hodnotu, na kterou pointer ukazuje)

```c
int x = 10;
int *p = &x;  // p obsahuje adresu x
printf("Hodnota x: %d\n", *p);  // vypíše 10
```

### Aritmetika pointerů

Pointery lze inkrementovat, dekrementovat a provádět s nimi další aritmetické operace.

```c
int pole[] = {10, 20, 30, 40};
int *p = pole;

printf("%d\n", *p);     // vypíše 10
printf("%d\n", *(p+1)); // vypíše 20
p++;                    // p nyní ukazuje na druhý prvek pole
```

### Pointery a pole

Pole a pointery jsou v C úzce propojeny. Název pole je ve skutečnosti pointer na jeho první prvek.

```c
int pole[] = {1, 2, 3, 4, 5};
int *p = pole;  // ekvivalentní s int *p = &pole[0];

for (int i = 0; i < 5; i++) {
    printf("%d ", *(p + i));  // alternativně: p[i]
}
```

### Pointery na pointery

Můžeme mít pointery, které ukazují na jiné pointery.

```c
int x = 10;
int *p = &x;
int **pp = &p;  // pointer na pointer na int

printf("%d\n", **pp);  // vypíše 10
```

### Funkce a pointery

Pointery jsou často používány pro efektivní předávání velkých datových struktur funkcím a pro funkce, které potřebují modifikovat své argumenty.

```c
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

// Použití:
int x = 5, y = 10;
swap(&x, &y);
```

### Dynamická alokace paměti

Pointery jsou klíčové pro dynamickou alokaci paměti pomocí funkcí jako `malloc()`, `calloc()`, `realloc()` a `free()`.

```c
int *p = (int *)malloc(5 * sizeof(int));
if (p == NULL) {
    // Ošetření chyby alokace
}
// Použití alokované paměti
free(p);  // Uvolnění paměti
```

### Pointery na funkce

V C můžeme mít i pointery na funkce, což umožňuje dynamický výběr funkce k volání.

```c
int sčítání(int a, int b) { return a + b; }
int odčítání(int a, int b) { return a - b; }

int (*operace)(int, int);
operace = sčítání;
printf("%d\n", operace(5, 3));  // vypíše 8

operace = odčítání;
printf("%d\n", operace(5, 3));  // vypíše 2
```

### Bezpečnost při práci s pointery

- Vždy inicializujte pointery.
- Kontrolujte návratové hodnoty funkcí pro alokaci paměti.
- Vyvarujte se přístupu mimo alokovanou paměť.
- Používejte `const` pro pointery, které by neměly modifikovat data.
- Po použití `free()` nastavte pointer na `NULL`.

Pointery jsou mocným nástrojem, ale vyžadují opatrnost. Správné použití pointerů může vést k efektivnějšímu a flexibilnějšímu kódu, ale nesprávné použití může způsobit vážné chyby a bezpečnostní rizika.

## 8. Struktury a unie v C

Struktury a unie jsou uživatelsky definované datové typy, které umožňují seskupovat související data různých typů.

### Struktury

Struktura je kolekce proměnných (možná různých typů) pod jedním názvem.

#### Definice struktury:

```c
struct Osoba {
    char jméno[50];
    int věk;
    float výška;
};
```

#### Deklarace a inicializace struktury:

```c
struct Osoba jan = {"Jan Novák", 30, 180.5};

struct Osoba petra;
strcpy(petra.jméno, "Petra Svobodová");
petra.věk = 25;
petra.výška = 165.0;
```

#### Přístup k členům struktury:

```c
printf("Jméno: %s, Věk: %d\n", jan.jméno, jan.věk);
```

#### Pointery na struktury:

```c
struct Osoba *p = &jan;
printf("Výška: %.1f\n", p->výška);  // ekvivalentní s (*p).výška
```

#### Struktury jako argumenty funkcí:

```c
void tiskniOsobu(struct Osoba o) {
    printf("%s, %d let, %.1f cm\n", o.jméno, o.věk, o.výška);
}

// Efektivnější předání pomocí pointeru:
void tiskniOsobuPtr(const struct Osoba *o) {
    printf("%s, %d let, %.1f cm\n", o->jméno, o->věk, o->výška);
}
```

#### Vnořené struktury:

```c
struct Adresa {
    char ulice[50];
    char město[30];
};

struct Zaměstnanec {
    struct Osoba info;
    struct Adresa adresa;
    int id;
};
```

### Unie

Unie je speciální datový typ, který umožňuje uložit různé datové typy ve stejné paměťové lokaci.

#### Definice unie:

```c
union Data {
    int i;
    float f;
    char str[20];
};
```

#### Použití unie:

```c
union Data data;

data.i = 10;
printf("data.i : %d\n", data.i);

data.f = 220.5;
printf("data.f : %.1f\n", data.f);

strcpy(data.str, "C Programming");
printf("data.str : %s\n", data.str);
```

Důležité: V unii sdílejí všechny členy stejnou paměť. Změna hodnoty jednoho členu ovlivní ostatní.

### Bitová pole

Bitová pole umožňují přesně specifikovat počet bitů pro členy struktury nebo unie:

```c
struct Příznaky {
    unsigned int je_aktivní : 1;
    unsigned int má_oprávnění : 1;
    unsigned int úroveň : 4;
};
```

### Typedef

`typedef` umožňuje vytvářet aliasy pro datové typy, včetně struktur a unií:

```c
typedef struct Osoba Osoba;
typedef union Data Data;

// Nyní můžeme používat:
Osoba jan;
Data moje_data;
```

### Anonymní struktury a unie

C11 zavádí podporu pro anonymní struktury a unie uvnitř jiných struktur:

```c
struct Komplexní {
    union {
        struct {
            float x, y;
        };
        float komponenty[2];
    };
};

struct Komplexní c = {{1.0, 2.0}};
printf("x: %.1f, y: %.1f\n", c.x, c.y);
printf("komponenty: %.1f, %.1f\n", c.komponenty[0], c.komponenty[1]);
```

Struktury a unie jsou klíčové pro organizaci souvisejících dat v C. Struktury se často používají pro reprezentaci objektů reálného světa v programech, zatímco unie jsou užitečné v situacích, kdy potřebujeme flexibilně pracovat s různými interpretacemi stejných dat.

## 9. Práce se soubory v C

Práce se soubory je důležitou součástí mnoha programů v C. Umožňuje nám ukládat a načítat data z externích zdrojů.

### Základní operace se soubory

Pro práci se soubory v C používáme funkce z knihovny `<stdio.h>`.

#### Otevření souboru:

```c
FILE *fptr;
fptr = fopen("soubor.txt", "r");  // otevření pro čtení
// nebo
fptr = fopen("soubor.txt", "w");  // otevření pro zápis
// nebo
fptr = fopen("soubor.txt", "a");  // otevření pro přidávání

if (fptr == NULL) {
    printf("Chyba při otevírání souboru!\n");
    return 1;
}
```

Módy otevření souboru:

- "r" - čtení
- "w" - zápis (vytvoří nový soubor nebo přepíše existující)
- "a" - přidávání (přidá na konec existujícího souboru)
- "r+" - čtení a zápis
- "w+" - čtení a zápis (vytvoří nový soubor nebo přepíše existující)
- "a+" - čtení a přidávání

#### Čtení ze souboru:

```c
char buffer[100];
while (fgets(buffer, sizeof(buffer), fptr) != NULL) {
    printf("%s", buffer);
}
```

#### Zápis do souboru:

```c
fprintf(fptr, "Toto je text zapsaný do souboru.\n");
fputs("Další řádek textu.\n", fptr);
```

#### Zavření souboru:

```c
fclose(fptr);
```

### Binární soubory

Pro práci s binárními soubory používáme módy "rb", "wb", "ab" atd.

```c
FILE *fptr = fopen("data.bin", "wb");
int data[] = {1, 2, 3, 4, 5};
fwrite(data, sizeof(int), 5, fptr);
fclose(fptr);

fptr = fopen("data.bin", "rb");
int read_data[5];
fread(read_data, sizeof(int), 5, fptr);
fclose(fptr);
```

### Pozicování v souboru

```c
fseek(fptr, 0, SEEK_SET);  // přesun na začátek souboru
fseek(fptr, 10, SEEK_CUR);  // přesun o 10 bytů vpřed
fseek(fptr, -5, SEEK_END);  // přesun 5 bytů před konec souboru

long pozice = ftell(fptr);  // získání aktuální pozice
```

### Kontrola chyb

Vždy kontrolujte návratové hodnoty funkcí pro práci se soubory:

```c
if (ferror(fptr)) {
    perror("Chyba při práci se souborem");
}

if (feof(fptr)) {
    printf("Dosažen konec souboru.\n");
}
```

### Příklad: Kopírování souboru

```c
#include <stdio.h>

#define BUFFER_SIZE 1000

int main() {
    FILE *source, *destination;
    char buffer[BUFFER_SIZE];
    size_t bytes;

    source = fopen("zdrojovy_soubor.txt", "rb");
    if (source == NULL) {
        perror("Chyba při otevírání zdrojového souboru");
        return 1;
    }

    destination = fopen("cilovy_soubor.txt", "wb");
    if (destination == NULL) {
        perror("Chyba při otevírání cílového souboru");
        fclose(source);
        return 1;
    }

    while ((bytes = fread(buffer, 1, BUFFER_SIZE, source)) > 0) {
        fwrite(buffer, 1, bytes, destination);
    }

    fclose(source);
    fclose(destination);

    printf("Soubor byl úspěšně zkopírován.\n");

    return 0;
}
```

Práce se soubory je klíčová pro mnoho aplikací, od jednoduchých textových editorů po komplexní databázové systémy. Je důležité vždy správně ošetřit chyby a zavírat soubory po dokončení práce s nimi.

## 10. Preprocesor a makra v C

Preprocesor je důležitou součástí kompilačního procesu v C. Zpracovává zdrojový kód před samotnou kompilací, provádí textové substituce a podmíněnou kompilaci.

### Direktivy preprocesoru

Všechny direktivy preprocesoru začínají znakem `#`.

#### #include

Vkládá obsah jiného souboru do aktuálního souboru.

```c
#include <stdio.h>  // Systémový hlavičkový soubor
#include "moje_funkce.h"  // Uživatelský hlavičkový soubor
```

#### #define

Definuje makro nebo konstantu.

```c
#define PI 3.14159
#define SQUARE(x) ((x) * (x))

printf("Plocha kruhu s poloměrem 5: %.2f\n", PI * SQUARE(5));
```

#### Podmíněná kompilace

```c
#define DEBUG

#ifdef DEBUG
    printf("Debug: Hodnota x je %d\n", x);
#endif

#ifndef BUFFER_SIZE
    #define BUFFER_SIZE 1024
#endif

#if PLATFORM == WINDOWS
    // kód specifický pro Windows
#elif PLATFORM == LINUX
    // kód specifický pro Linux
#else
    // kód pro ostatní platformy
#endif
```

#### #undef

Ruší definici makra.

```c
#define MAX 100
// ...
#undef MAX
```

### Předdefinovaná makra

C poskytuje několik předdefinovaných maker:

```c
printf("Tento soubor: %s\n", __FILE__);
printf("Na řádku: %d\n", __LINE__);
printf("Zkompilováno: %s %s\n", __DATE__, __TIME__);
printf("Standart C: %ld\n", __STDC_VERSION__);
```

### Operátory v makrech

#### Operátor `#` (stringifikace)

Převádí argument makra na řetězec.

```c
#define PRINT_VAR(x) printf(#x " = %d\n", x)

int a = 5;
PRINT_VAR(a);  // Vypíše: a = 5
```

#### Operátor `##` (konkatenace)

Spojuje dva tokeny.

```c
#define CONCAT(a, b) a ## b

int xy = 10;
printf("%d\n", CONCAT(x, y));  // Vypíše 10
```

### Variadic makra

Makra s proměnným počtem argumentů.

```c
#define DEBUG_PRINT(format, ...) fprintf(stderr, format, __VA_ARGS__)

DEBUG_PRINT("Error in %s: %s\n", __func__, strerror(errno));
```

### Příklad: Bezpečné makro pro maximální hodnotu

```c
#define MAX(a, b) \
    ({ __typeof__ (a) _a = (a); \
       __typeof__ (b) _b = (b); \
     _a > _b ? _a : _b; })

int x = 5, y = 7;
printf("Maximum: %d\n", MAX(x++, y++));
```

### Dobré praktiky při používání maker

1. Používejte závorky kolem argumentů a celého výrazu v definici makra.
2. Pro komplexnější makra zvažte použití inline funkcí (pokud je to možné).
3. Buďte opatrní s makry, která používají své argumenty vícekrát.
4. Používejte velká písmena pro názvy maker pro lepší čitelnost.
5. Omezte použití maker na případy, kdy jsou opravdu potřeba (konstanty, podmíněná kompilace).

Preprocesor je mocný nástroj, ale jeho nadměrné nebo nesprávné použití může vést k obtížně čitelnému a udržovatelnému kódu. Vždy zvažte, zda nelze dosáhnout stejného cíle použitím běžných jazykových konstrukcí C.

## 11. Pokročilé koncepty v C

### Více-dimenzionální pole

C podporuje více-dimenzionální pole, která jsou užitečná pro reprezentaci tabulek, matic a více-rozměrných dat.

```c
int matice[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// Přístup k prvkům
printf("%d\n", matice[1][2]);  // Vypíše 6

// Procházení 2D pole
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        printf("%d ", matice[i][j]);
    }
    printf("\n");
}
```

### Vícerozměrné dynamické pole

```c
int rows = 3, cols = 4;
int **arr = (int **)malloc(rows * sizeof(int *));
for (int i = 0; i < rows; i++) {
    arr[i] = (int *)malloc(cols * sizeof(int));
}

// Použití pole
arr[1][2] = 10;

// Uvolnění paměti
for (int i = 0; i < rows; i++) {
    free(arr[i]);
}
free(arr);
```

### Složité deklarace

C umožňuje vytvářet složité deklarace, které mohou být obtížné na čtení, ale jsou velmi expresivní.

```c
int (*func_ptr)(int, int);  // Ukazatel na funkci
int *arr[10];  // Pole 10 ukazatelů na int
int (*arr_ptr)[10];  // Ukazatel na pole 10 intů
int (*(*fun_arr)())[10];  // Pole ukazatelů na funkce vracející ukazatel na pole 10 intů
```

### Bitové operace

Bitové operace jsou užitečné pro nízkoúrovňové programování a optimalizace.

```c
unsigned int a = 60;  // 0011 1100
unsigned int b = 13;  // 0000 1101

printf("a & b = %d\n", a & b);   // 12 (0000 1100)
printf("a | b = %d\n", a | b);   // 61 (0011 1101)
printf("a ^ b = %d\n", a ^ b);   // 49 (0011 0001)
printf("~a = %d\n", ~a);         // -61 (1100 0011)
printf("a << 2 = %d\n", a << 2); // 240 (1111 0000)
printf("a >> 2 = %d\n", a >> 2); // 15 (0000 1111)
```

### Volatile proměnné

Klíčové slovo `volatile` se používá pro proměnné, které se mohou změnit neočekávaně, například při práci s hardwarem nebo ve více-vláknových aplikacích.

```c
volatile int sensor_value;

while (1) {
    if (sensor_value > threshold) {
        // Reaguj na změnu
    }
}
```

### Inline funkce

Inline funkce jsou návrh kompilátoru pro optimalizaci malých, často volaných funkcí.

```c
inline int max(int a, int b) {
    return (a > b) ? a : b;
}
```

### Restrict ukazatele

Klíčové slovo `restrict` (C99) informuje kompilátor, že pointer je jediným způsobem přístupu k objektu, což umožňuje agresivnější optimalizace.

```c
void copy(int n, int * restrict src, int * restrict dst) {
    for (int i = 0; i < n; i++) {
        dst[i] = src[i];
    }
}
```

### Flexibilní pole členy (C99)

Umožňují vytvářet struktury s polem proměnné délky jako posledním členem.

```c
struct packet {
    int type;
    int length;
    unsigned char data[];
};

struct packet *p = malloc(sizeof(struct packet) + 100);
p->length = 100;
```

### \_Atomic typy (C11)

C11 přidává podporu pro atomické operace, což je užitečné pro více-vláknové programování.

```c
#include <stdatomic.h>

atomic_int shared_variable = ATOMIC_VAR_INIT(0);

// V různých vláknech:
atomic_fetch_add(&shared_variable, 1);
```

### Anonymní struktury a unie (C11)

```c
struct {
    union {
        struct {
            int x, y;
        };
        int coords[2];
    };
    int z;
} point;

point.x = 5;
printf("%d\n", point.coords[0]);  // Vypíše 5
```

Tyto pokročilé koncepty rozšiřují možnosti jazyka C a umožňují psát efektivnější a expresivnější kód. Nicméně, s větší mocí přichází i větší odpovědnost - tyto funkce by měly být používány s rozmyslem a s dobrou znalostí jejich chování a omezení.

## 12. Správa paměti v C

Správa paměti je kritickou součástí programování v C. Na rozdíl od mnoha moderních jazyků, C neposkytuje automatickou správu paměti (garbage collection), což dává programátorovi plnou kontrolu, ale také odpovědnost za alokaci a uvolňování paměti.

### Statická alokace

Paměť je alokována při kompilaci a existuje po celou dobu běhu programu.

```c
int x = 10;
static int y = 20;
```

### Automatická alokace

Paměť je alokována na zásobníku při vstupu do bloku a automaticky uvolněna při opuštění bloku.

```c
void funkce() {
    int a = 5;  // 'a' je automaticky alokováno a uvolněno
}
```

### Dynamická alokace

Paměť je alokována za běhu programu na haldě a musí být explicitně uvolněna programátorem.

```c
#include <stdlib.h>

int *p = (int *)malloc(sizeof(int));
if (p == NULL) {
    // Ošetření chyby alokace
    return;
}
*p = 10;
// Použití p
free(p);  // Uvolnění paměti
p = NULL;  // Prevence použití po uvolnění
```

#### Funkce pro dynamickou alokaci:

- `malloc()`: Alokuje blok paměti specifikované velikosti.
- `calloc()`: Alokuje blok paměti pro pole prvků a inicializuje je na nulu.
- `realloc()`: Změní velikost dříve alokovaného bloku paměti.
- `free()`: Uvolní dříve alokovaný blok paměti.

```c
int *arr = (int *)calloc(5, sizeof(int));
arr = (int *)realloc(arr, 10 * sizeof(int));
free(arr);
```

### Časté chyby při správě paměti

1. **Únik paměti**: Nastává, když alokovaná paměť není uvolněna.

```c
void memory_leak() {
    int *p = (int *)malloc(sizeof(int));
    // Chybí free(p);
}
```

2. **Použití po uvolnění**: Přístup k paměti po jejím uvolnění.

```c
int *p = (int *)malloc(sizeof(int));
free(p);
*p = 10;  // Chyba: použití po uvolnění
```

3. **Dvojité uvolnění**: Pokus o uvolnění již uvolněné paměti.

```c
int *p = (int *)malloc(sizeof(int));
free(p);
free(p);  // Chyba: dvojité uvolnění
```

4. **Přetečení bufferu**: Zápis mimo hranice alokované paměti.

```c
char *str = (char *)malloc(5);
strcpy(str, "Hello, World!");  // Přetečení bufferu
```

### Nástroje pro detekci chyb paměti

- Valgrind: Nástroj pro detekci úniků paměti a dalších chyb.
- AddressSanitizer: Rychlý detektor chyb paměti (součást GCC a Clang).

### Správné praktiky

1. Vždy kontrolujte návratovou hodnotu `malloc()` a dalších alokačních funkcí.
2. Uvolňujte veškerou dynamicky alokovanou paměť pomocí `free()`.
3. Nastavte pointery na `NULL` po uvolnění paměti.
4. Používejte nástroje pro detekci chyb paměti během vývoje.
5. Zvažte použití chytrých pointerů nebo vlastních alokátorů pro komplexní projekty.

## 13. Vícevláknové programování v C

Vícevláknové programování umožňuje paralelní zpracování úloh v rámci jednoho procesu. V C je možné využít knihovnu POSIX threads (pthreads) pro práci s vlákny.

### Základy pthreads

```c
#include <pthread.h>
#include <stdio.h>

void *thread_function(void *arg) {
    printf("Hello from thread\n");
    return NULL;
}

int main() {
    pthread_t thread;
    int result = pthread_create(&thread, NULL, thread_function, NULL);
    if (result != 0) {
        perror("Thread creation failed");
        return 1;
    }
    pthread_join(thread, NULL);
    return 0;
}
```

Pro kompilaci použijte: `gcc -pthread program.c`

### Předávání argumentů vláknu

```c
struct thread_args {
    int id;
    char *message;
};

void *thread_function(void *arg) {
    struct thread_args *args = (struct thread_args *)arg;
    printf("Thread %d says: %s\n", args->id, args->message);
    return NULL;
}

int main() {
    pthread_t thread;
    struct thread_args args = {1, "Hello"};
    pthread_create(&thread, NULL, thread_function, &args);
    pthread_join(thread, NULL);
    return 0;
}
```

### Mutex pro synchronizaci

Mutex (mutual exclusion) se používá k ochraně sdílených zdrojů před současným přístupem z více vláken.

```c
#include <pthread.h>
#include <stdio.h>

int shared_variable = 0;
pthread_mutex_t mutex = PTHREAD_MUTEX_INITIALIZER;

void *increment(void *arg) {
    for (int i = 0; i < 1000000; i++) {
        pthread_mutex_lock(&mutex);
        shared_variable++;
        pthread_mutex_unlock(&mutex);
    }
    return NULL;
}

int main() {
    pthread_t thread1, thread2;
    pthread_create(&thread1, NULL, increment, NULL);
    pthread_create(&thread2, NULL, increment, NULL);
    pthread_join(thread1, NULL);
    pthread_join(thread2, NULL);
    printf("Final value: %d\n", shared_variable);
    return 0;
}
```

### Podmínkové proměnné

Podmínkové proměnné umožňují vláknům čekat na určitou podmínku.

```c
#include <pthread.h>
#include <stdio.h>

pthread_mutex_t mutex = PTHREAD_MUTEX_INITIALIZER;
pthread_cond_t cond = PTHREAD_COND_INITIALIZER;
int done = 0;

void *waiter(void *arg) {
    pthread_mutex_lock(&mutex);
    while (!done) {
        pthread_cond_wait(&cond, &mutex);
    }
    printf("Waiter: condition met\n");
    pthread_mutex_unlock(&mutex);
    return NULL;
}

void *signaler(void *arg) {
    pthread_mutex_lock(&mutex);
    done = 1;
    pthread_cond_signal(&cond);
    pthread_mutex_unlock(&mutex);
    return NULL;
}

int main() {
    pthread_t thread1, thread2;
    pthread_create(&thread1, NULL, waiter, NULL);
    pthread_create(&thread2, NULL, signaler, NULL);
    pthread_join(thread1, NULL);
    pthread_join(thread2, NULL);
    return 0;
}
```

### Deadlock

Deadlock nastává, když dvě nebo více vláken čekají na sebe navzájem, aby uvolnily prostředky.

```c
pthread_mutex_t mutex1 = PTHREAD_MUTEX_INITIALIZER;
pthread_mutex_t mutex2 = PTHREAD_MUTEX_INITIALIZER;

void *thread1_function(void *arg) {
    pthread_mutex_lock(&mutex1);
    sleep(1);  // Zvyšuje šanci na deadlock
    pthread_mutex_lock(&mutex2);
    // Kritická sekce
    pthread_mutex_unlock(&mutex2);
    pthread_mutex_unlock(&mutex1);
    return NULL;
}

void *thread2_function(void *arg) {
    pthread_mutex_lock(&mutex2);
    sleep(1);  // Zvyšuje šanci na deadlock
    pthread_mutex_lock(&mutex1);
    // Kritická sekce
    pthread_mutex_unlock(&mutex1);
    pthread_mutex_unlock(&mutex2);
    return NULL;
}
```

Pro prevenci deadlocku:

1. Vždy zamykejte mutexy ve stejném pořadí ve všech vláknech.
2. Používejte `pthread_mutex_trylock()` místo `pthread_mutex_lock()`.
3. Používejte hierarchii zámků.

### Důležité poznámky k vícevláknovému programování

1. Vícevláknové programy mohou být obtížné na ladění kvůli nedeterministickému chování.
2. Vždy se snažte minimalizovat sdílení dat mezi vlákny.
3. Buďte opatrní při používání globálních proměnných ve vícevláknových programech.
4. Používejte atomické operace pro jednoduché sdílené proměnné, kde je to možné.
5. Zvažte použití nástrojů pro analýzu vícevláknových programů, jako je Helgrind (součást Valgrind).

Vícevláknové programování v C vyžaduje pečlivý návrh a implementaci, ale může výrazně zlepšit výkon aplikací, zejména na více-jádrových systémech.
