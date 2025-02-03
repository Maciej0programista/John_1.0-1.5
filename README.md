# John 1.0 - JCL Interpreter

**John 1.0** to system operacyjny dla mikrokontrolerów Arduino, wyposażony w prosty interpreter poleceń o nazwie **JCL (John's Command Language)**. Umożliwia on interakcję z urządzeniem za pomocą klawiatury PS/2 i wyświetlacza LCD, oferując zestaw wbudowanych funkcji.

## Cechy systemu:

*   **Interpreter JCL:** Umożliwia wykonywanie poleceń wprowadzanych za pomocą klawiatury PS/2.
*   **Obsługa klawiatury PS/2:** Pełna obsługa standardowej klawiatury PS/2.
*   **Wyświetlacz LCD:** Wyświetlanie komend, wyników i komunikatów na ekranie LCD 16x4.
*   **Wbudowane funkcje:**  System zawiera zestaw podstawowych funkcji, w tym:
    *   `add <liczba1> <liczba2>`: Dodaje dwie liczby zmiennoprzecinkowe.
    *   `subtract <liczba1> <liczba2>`: Odejmuje dwie liczby zmiennoprzecinkowe.
    *   `clearScreen`: Czyści ekran LCD.
    *   `floatToInt <liczba>`: Konwertuje liczbę zmiennoprzecinkową na całkowitą.
*   **Możliwość rozszerzenia:** System został zaprojektowany z myślą o łatwym dodawaniu nowych funkcji. (Informacja dla ciebie jako developera, użytkownik nie musi tego wiedzieć)

## Wymagania sprzętowe:

*   Płytka Arduino Uno (lub kompatybilna, np. Nano, Mega z mikrokontrolerem Atmega328p).
*   Klawiatura PS/2.
*   Wyświetlacz LCD 16x4 ze sterownikiem HD44780.
*   Przewody połączeniowe.
*   Rezystory podciągające (pull-up) dla klawiatury PS/2 (opcjonalnie, w zależności od modelu klawiatury - sprawdź dokumentację).
*   Potencjometr do regulacji kontrastu LCD (opcjonalnie, w zależności od modelu LCD).

## Instalacja:

1. **Skompiluj kod źródłowy:** Użyj Arduino IDE, aby skompilować dostarczony kod.
2. **Wgraj program na Arduino:** Podłącz Arduino do komputera i wgraj skompilowany program (plik `.hex`) na płytkę za pomocą Arduino IDE lub innego programatora (np. `avrdude`).

## Uruchomienie:

1. **Podłącz klawiaturę PS/2** do pinów cyfrowych 2 (Data) i 3 (IRQ) w Arduino oraz do zasilania (5V i GND).
2. **Podłącz wyświetlacz LCD** do Arduino zgodnie ze schematem:
    *   LCD RS -> Pin 8
    *   LCD Enable -> Pin 9
    *   LCD D4 -> Pin 4
    *   LCD D5 -> Pin 5
    *   LCD D6 -> Pin 6
    *   LCD D7 -> Pin 7
    *   LCD VSS -> GND
    *   LCD VDD -> 5V
    *   LCD V0 -> Potencjometr (środkowy pin)
    *   Potencjometr (skrajne piny) -> 5V i GND
    *   LCD R/W -> GND
    *   LCD A -> 5V (przez rezystor ~220 Ohm, jeśli podświetlenie jest zbyt jasne)
    *   LCD K -> GND
3. **Podłącz zasilanie do Arduino.**
4. **Uruchom system.** Na ekranie LCD powinien pojawić się tekst powitalny:

```
John 1.0
JCL Interpreter
>
```

## Używanie JCL:

*   Wprowadź polecenia za pomocą klawiatury PS/2.
*   Zatwierdź polecenie klawiszem **Enter**.
*   Obserwuj wyniki na ekranie LCD.
*   Możesz wprowadzać kilka poleceń w jednym wierszu, oddzielając je średnikami (`;`).

**Dostępne polecenia:**

*   `add <liczba1> <liczba2>`: Dodaje dwie liczby. Przykład: `add 5.5 2.7`
*   `subtract <liczba1> <liczba2>`: Odejmuje dwie liczby. Przykład: `subtract 10 3`
*   `clearScreen`: Czyści ekran LCD. Przykład: `clearScreen`
*   `floatToInt <liczba>`: Konwertuje liczbę zmiennoprzecinkową na całkowitą. Przykład: `floatToInt 7.8`

**Przykład użycia:**

```
>clearScreen;add 5 3;subtract 10 2;floatToInt 25.6
```

**Uwagi:**

*   Interpreter JCL jest prosty i nie obsługuje zaawansowanych funkcji, takich jak zmienne, pętle czy instrukcje warunkowe.
*   Błędy (np. nieznane polecenie, nieprawidłowa liczba argumentów) są sygnalizowane na LCD.

## Rozwiązywanie problemów:

*   **Brak tekstu na LCD:** Sprawdź połączenia LCD i regulację kontrastu (potencjometr).
*   **Brak reakcji na klawiaturę:** Sprawdź połączenia klawiatury, upewnij się, że używasz klawiatury PS/2, a nie USB, oraz sprawdź, czy potrzebne są rezystory podciągające.
*   **Nieoczekiwane wyniki:** Upewnij się, że wprowadzasz poprawne polecenia i argumenty.

## Przyszłe Rozszerzenia:

*   Wsparcie dla większej liczby funkcji.
*   Możliwość definiowania własnych funkcji (zmienne lokalne, parametry).
*   Dodanie instrukcji warunkowych i pętli.

---

**Zastrzeżenie:**

John 1.0 i JCL są prostym systemem stworzonym w celach edukacyjnych i demonstracyjnych. Nie jest on przeznaczony do zastosowań krytycznych ani profesjonalnych. Twórca nie ponosi odpowiedzialności za ewentualne szkody wynikłe z użytkowania systemu.
