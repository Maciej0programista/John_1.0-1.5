# John 1.0 JCL Interpreter - Przewodnik Użytkownika

Ten przewodnik jest przeznaczony dla użytkowników, którzy posiadają tylko skompilowaną wersję interpretera John 1.0 i nie mają dostępu do kodu źródłowego.

## Wprowadzenie

John 1.0 to interpreter poleceń (JCL) dla platformy Arduino, umożliwiający interaktywne wykonywanie funkcji matematycznych i sterowanie podstawowymi operacjami. System komunikuje się z użytkownikiem poprzez wyświetlacz LCD 20x4 oraz klawiaturę PS/2.

## Podstawowe Funkcje

System oferuje następujące funkcje:

### Funkcje Matematyczne

System obsługuje podstawowe operacje matematyczne, które można wywoływać za pomocą odpowiednich poleceń. Poniżej znajduje się lista dostępnych funkcji wraz z opisem argumentów i działania:

*   **`add <liczba1> <liczba2>`** - Dodaje dwie liczby.
    *   Argumenty:
        *   `<liczba1>` - Pierwsza liczba (zmiennoprzecinkowa).
        *   `<liczba2>` - Druga liczba (zmiennoprzecinkowa).
    *   Działanie: Wyświetla sumę dwóch podanych liczb na wyświetlaczu LCD.
*   **`subtract <liczba1> <liczba2>`** - Ode Jmuje dwie liczby.
    *   Argumenty:
        *   `<liczba1>` - Pierwsza liczba (zmiennoprzecinkowa).
        *   `<liczba2>` - Druga liczba (zmiennoprzecinkowa).
    *   Działanie: Wyświetla różnicę dwóch podanych liczb na wyświetlaczu LCD.
*   **`multiply <liczba1> <liczba2>`** - Mnoży dwie liczby.
    *   Argumenty:
        *   `<liczba1>` - Pierwsza liczba (zmiennoprzecinkowa).
        *   `<liczba2>` - Druga liczba (zmiennoprzecinkowa).
    *   Działanie: Wyświetla iloczyn dwóch podanych liczb na wyświetlaczu LCD.
*   **`divide <liczba1> <liczba2>`** - Dzieli dwie liczby.
    *   Argumenty:
        *   `<liczba1>` - Pierwsza liczba (zmiennoprzecinkowa).
        *   `<liczba2>` - Druga liczba (zmiennoprzecinkowa).
    *   Działanie: Wyświetla wynik dzielenia dwóch podanych liczb na wyświetlaczu LCD. W przypadku próby dzielenia przez zero, na wyświetlaczu pojawi się komunikat o błędzie.
*   **`power <liczba1> <liczba2>`** - Podnosi liczbę do potęgi.
    *   Argumenty:
        *   `<liczba1>` - Podstawa potęgi (zmiennoprzecinkowa).
        *   `<liczba2>` - Wykładnik potęgi (zmiennoprzecinkowa).
    *   Działanie: Wyświetla wynik podnoszenia liczby `<liczba1>` do potęgi `<liczba2>` na wyświetlaczu LCD.
*   **`squareRoot <liczba>`** - Oblicza pierwiastek kwadratowy z liczby.
    *   Argumenty:
        *   `<liczba>` - Liczba, z której ma być obliczony pierwiastek (zmiennoprzecinkowa).
    *   Działanie: Wyświetla pierwiastek kwadratowy z podanej liczby na wyświetlaczu LCD. W przypadku podania liczby ujemnej, na wyświetlaczu pojawi się komunikat o błędzie.
*   **`sine <kąt>`** - Oblicza sinus kąta.
    *   Argumenty:
        *   `<kąt>` - Kąt w radianach (zmiennoprzecinkowa).
    *   Działanie: Wyświetla sinus podanego kąta na wyświetlaczu LCD.
*   **`cosine <kąt>`** - Oblicza cosinus kąta.
    *   Argumenty:
        *   `<kąt>` - Kąt w radianach (zmiennoprzecinkowa).
    *   Działanie: Wyświetla cosinus podanego kąta na wyświetlaczu LCD.
*   **`tangent <kąt>`** - Oblicza tangens kąta.
    *   Argumenty:
        *   `<kąt>` - Kąt w radianach (zmiennoprzecinkowa).
    *   Działanie: Wyświetla tangens podanego kąta na wyświetlaczu LCD.
*   **`naturalLog <liczba>`** - Oblicza logarytm naturalny z liczby.
    *   Argumenty:
        *   `<liczba>` - Liczba, z której ma być obliczony logarytm naturalny (zmiennoprzecinkowa).
    *   Działanie: Wyświetla logarytm naturalny z podanej liczby na wyświetlaczu LCD. W przypadku podania liczby mniejszej lub równej zero, na wyświetlaczu pojawi się komunikat o błędzie.
*   **`base10Log <liczba>`** - Oblicza logarytm dziesiętny z liczby.
    *   Argumenty:
        *   `<liczba>` - Liczba, z której ma być obliczony logarytm dziesiętny (zmiennoprzecinkowa).
    *   Działanie: Wyświetla logarytm dziesiętny z podanej liczby na wyświetlaczu LCD. W przypadku podania liczby mniejszej lub równej zero, na wyświetlaczu pojawi się komunikat o błędzie.
*   **`absoluteValue <liczba>`** - Oblicza wartość bezwzględną z liczby.
    *   Argumenty:
        *   `<liczba>` - Liczba, z której ma być obliczona wartość bezwzględna (zmiennoprzecinkowa).
    *   Działanie: Wyświetla wartość bezwzględną z podanej liczby na wyświetlaczu LCD.
*   **`ceilValue <liczba>`** - Zaokrągla liczbę w górę.
    *   Argumenty:
        *   `<liczba>` - Liczba, która ma być zaokrąglona (zmiennoprzecinkowa).
    *   Działanie: Wyświetla liczbę zaokrągloną w górę na wyświetlaczu LCD.
*   **`floorValue <liczba>`** - Zaokrągla liczbę w dół.
    *   Argumenty:
        *   `<liczba>` - Liczba, która ma być zaokrąglona (zmiennoprzecinkowa).
    *   Działanie: Wyświetla liczbę zaokrągloną w dół na wyświetlaczu LCD.
*   **`modulo <liczba1> <liczba2>`** - Oblicza resztę z dzielenia (modulo).
    *   Argumenty:
        *   `<liczba1>` - Liczba, która ma być dzielona (całkowita).
        *   `<liczba2>` - Dzielnik (całkowita).
    *   Działanie: Wyświetla resztę z dzielenia liczby `<liczba1>` przez `<liczba2>` na wyświetlaczu LCD. W przypadku próby dzielenia przez zero, na wyświetlaczu pojawi się komunikat o błędzie.

### Interakcja z Systemem

#### Wprowadzanie Poleceń

Użytkownik wprowadza polecenia za pomocą klawiatury PS/2. Wprowadzony tekst pojawia się w drugiej linii wyświetlacza LCD. Po zakończeniu wprowadzania polecenia, należy wcisnąć klawisz Enter.

#### Wyświetlanie Wyników

Wyniki obliczeń oraz komunikaty systemowe są wyświetlane w trzeciej linii wyświetlacza LCD.

#### Usuwanie Znaków

Do usuwania wprowadzonych znaków służy klawisz Backspace.

## Konfiguracja Sprzętowa

Aby system działał poprawnie, należy odpowiednio skonfigurować połączenia sprzętowe:

*   **Wyświetlacz LCD**: Podłącz wyświetlacz LCD 20x4 zgodnie z poniższymi pinami:
    *   RS: Pin 8 Arduino
    *   Enable: Pin 9 Arduino
    *   D4: Pin 4 Arduino
    *   D5: Pin 5 Arduino
    *   D6: Pin 6 Arduino
    *   D7: Pin 7 Arduino
*   **Klawiatura PS/2**: Podłącz klawiaturę PS/2 zgodnie z poniższymi pinami:
    *   Data: Pin 2 Arduino
    *   IRQ: Pin 3 Arduino

## Znane Ograniczenia

*   System obsługuje tylko podstawowe operacje matematyczne.
*   System nie obsługuje zmiennych.
*   System nie obsługuje złożonych wyrażeń matematycznych.
*   System nie obsługuje plików zewnętrznych.
*   System nie obsługuje polskich znaków.
*   System ma ograniczoną ilość pamięci RAM, co może ograniczać długość wprowadzanych poleceń i złożoność wykonywanych operacji.
*   Wyświetlacz LCD 20x4 ma ograniczoną ilość miejsca, co może powodować obcinanie długich wyników.

## Rozwiązywanie Problemów

*   **Brak wyświetlania**: Sprawdź, czy wyświetlacz LCD jest poprawnie podłączony i zasilany. Sprawdź kontrast wyświetlacza LCD.
*   **Brak reakcji na klawiaturę**: Sprawdź, czy klawiatura PS/2 jest poprawnie podłączona. Sprawdź, czy klawiatura jest sprawna.
*   **Nieprawidłowe wyniki**: Sprawdź, czy wprowadzone polecenia są poprawne i czy argumenty są poprawnego typu.

## Podsumowanie

John 1.0 to prosty, ale funkcjonalny interpreter poleceń dla platformy Arduino. Mimo pewnych ograniczeń, system może być użyteczny do wykonywania podstawowych operacji matematycznych i eksperymentowania z programowaniem.

---
