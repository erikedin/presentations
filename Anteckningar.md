Anteckningar
============
Viktiga bitar från cppreference.com:

> If an optional<T> contains a value, the value is guaranteed to be allocated as part of the 
> optional object footprint, i.e. no dynamic memory allocation ever takes place. Thus, an optional 
> object models an object, not a pointer, even though the operator*() and operator->() are defined.

> [...] contextually converted to a bool, [...]

    std::optional<int> a(0);
    if (a) {
        [...]
    }

Exempel med bool:

    std::optional<bool> a(false);
    if (a) {
        // Will happen, because a is true, while a.value() is false.
    }

Det finns en `std::nullopt`.

Hämta värdet med `value()`. Den kastar exceptions om den är tom.

Finns en `make_optional`.

Boost har en optional, som std::optional är baserad på.

Struktur på presentationen
==========================
- Titel: std::optional (C++17)
- Förklaring på en mening
- Kodexempel för optional med värde och utan
- Nullopt är en tom optional
- När ska man använda den?
    + När en funktion kan returnera ett tomt värde
    + När man kan ha ett tomt värde i en collection
- Finns i boost, _nästan_ samma som std::optional.

- Finns -> och * tror jag

- Kommer från funktionell programmering
    + I funktionell programmering används den med transformation
    + Type monader i Haskell
