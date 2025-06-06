# 🚗 Autonomiczny Pojazd z STM32

Projekt semestralny z przedmiotu **Systemy Wbudowane i Mikrokontrolery**  
Autorzy: **Magdalena Czyżewska 21227, Adrian Witów 21319, Michał Lepak 21255**  
Data rozpoczęcia: 16.03.2025  
Repozytorium zawiera kod, dokumentację oraz materiały projektowe.

---

## 📌 Opis projektu

Celem projektu jest opracowanie modelu autonomicznego pojazdu sterowanego za pomocą mikrokontrolera STM32. Pojazd porusza się w trybie manualnym oraz automatycznym, gdzie omija przeszkody. Komunikacja z użytkownikiem odbywa się przez UART (Bluetooth). Pojazd jest zasilony 6 bateriami AA, generującymi łącznie 9V co umożliwia w pełni zasilenie pojazdu wraz z jego komponentami.

---

## 🛠️ Zastosowane technologie i narzędzia

- **Podwozie:** Wycięty panel podłogowy
- **Mikrokontroler:** STM32F3DISCOVERY
- **IDE:** STM32CubeIDE
- **Sensor:** HC-SR04 (ultradźwiękowy)
- **Zasilanie:** Baterie AA 6x1.5V
- **Sterownik silników:** L298N
- **Komunikacja:** UART (Bluetooth HC-05)
- **Wyświetlacz:** OLED 0,96' 128x64
- **Silniki:** 4x zestaw silników elektrycznych DC 3-6V z podwójnym wałem i przekładnią magnetyczną wraz z kołami
- **Koszyki na baterie:** Pojemnik na 6 baterii 1.5V (łącznie 9V)
- **Oświetlenie:** 2x Pierścień LED RGB 8 bits
- **Przewody:** męsko-żeńskie 20cm, 7 sztuk
- **Przewody:** żeńsko-żeńskie 20cm, 16 sztuk
- **Aplikacja do sterowania:** Serial Bluetooth Terminal

---

## 🔌 Schemat układu

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/schemat_układu.png)

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/schemat_układu2.png)

## 🔌 Opis połączeń

- Silnik 1: L298N -> OUT1, OUT2
- Silnik 2: L298N -> OUT1, OUT2
- Silnik 3: L298N -> OUT3, OUT3
- Silnik 4: L298N -> OUT4, OUT4
- Zasilanie bateriami: + -> L298N 12V
- Zasilanie bateriami: - -> L298N GND
- Uziemienie płytki: L298N GND -> STM32 GND
- Zasilanie płytki: L298N 5V -> STM32 5V
- Wejście sterujące IN1: L298N -> STM32 PC8
- Wejście sterujące IN2: L298N -> STM32 PC9
- Wejście sterujące IN3: L298N -> STM32 PC6
- Wejście sterujące IN4: L298N -> STM32 PC7
- Czujnik odległościowy: HC-SR04  GND -> STM32 GND
- Czujnik odległościowy: HC-SR04  Echo -> STM32 PA1
- Czujnik odległościowy: HC-SR04  Trig -> STM32 PA4
- Czujnik odległościowy: HC-SR04  VCC -> STM32 5V
- Moduł bluetooth: HC-05 VCC -> STM32 5V
- Moduł bluetooth: HC-05 GND -> STM32 GND
- Moduł bluetooth: HC-05 TXD -> STM32 PA3
- Wyświetlacz: OLED GND -> STM32 GND
- Wyświetlacz: OLED VCC -> STM32 3V
- Wyświetlacz: OLED SCL -> STM32 PB6
- Wyświetlacz: OLED SDA -> STM32 PB7
- Pierścień 1: LED 5V -> L298N 5V
- Pierścień 1: LED GND -> STM32 GND
- Pierścień 1: LED DI -> STM32 PA8
- Pierścień 2: LED 5V -> L298N 5V
- Pierścień 2: LED GND -> STM32 GND
- Pierścień 2: LED DI -> Pierścień 1 LED DO

---

## 🖨️ Model 3D

- Projekt obudowy jest wykonany na bazie gotowego modelu, który został publicznie udostępniony do kopiowania oraz edytowania, źródło: [Model 3D](https://www.tinkercad.com/things/fXfpehDFToz-copy-of-car-car-car)
- Z modelu zostały usunięte koła oraz znaczna część podwozia w celu zmieszczenia podzespołów robota

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/model3D_11.png)
![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/model3D_2.png)

- Wymiary modelu: długość – 35cm, szerokość – 24cm, wysokość – 14cm
---
## 🛠️ Uruchomienie projektu

1. Kluczowym krokiem jest pobranie programu [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) - zalecana jest najnowsza wersja oprogramowania.

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/Zrzuty/0.png)

2. Następnie należy pobrać plik [RC-CAR.zip](https://github.com/cytruseqq/RC-CAR/blob/main/RC-CAR.zip), który znajduje się w repozytorium.

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/Zrzuty/9.png)
![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/Zrzuty/10.png)

3. W programie STM32CubeIDE przechodzimy do zakładki File, a następnie klikamy przycisk "Import".

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/Zrzuty/1.png)

4. W okienku "Import" należy rozwinąć zakładke "General", a później zaznaczyć opcję "Exitsting Projects into Workspace", a następnie kliknąć "Next".

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/Zrzuty/2.png)

5. W dalszym kroku za pomocą przycisku "Browse" wybieramy ścieżke, w której znajduje się nasz projekt i klikamy przycisk "Finish".

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/Zrzuty/3.png)


6. Po udanym imporcie, możemy rozwinąć nasz projekt, a następnie przejść do pliku projektowego, aby zobaczyć jak są skonfigurowane poszczególne piny.

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/Zrzuty/4.png)

7. Następnie przechodzimy do "Core", które rozwijamy, dalej rozwijamy, zakładke "Src", tam przechodzimy do pliku "main.c", w którym znajduje się główny kod projektu.

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/Zrzuty/5.png)

8. Przed wgraniem konfiguracji na mikrokontroler należy wykonać build programu, aby sprawdzić czy nasz kod nie zawiera błędów. Wykonujemy to za pomocą ikony "młoteczka".

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/Zrzuty/6.png)

9. Następnie przechodzimy do "Debugowania" konfiguracji i wgrania jej na mikrokontroler. Wszystko odbywa się za pomocą przycisku "Debug"

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/Zrzuty/77.png)

---

## 📱 Aplikacja sterująca

---

1. Pobranie aplikacji [Bluetooth Serial Terminal](https://play.google.com/store/apps/details?id=de.kai_morich.serial_bluetooth_terminal&hl=pl) [Android]

2. Skonfigurowanie aplikacji - dodanie nowych przycisków z konkretną nazwą i indeksem

- Indeks a - tryb robota autonomiczny
- Indeks m - tryb robota manualny
- Indeks f - jazda do przodu z mocą PWM 700
- Indeks b - jazda do tyłu z mocą PWM 700
- Indeks r - skręt w prawo z mocą PWM 700
- Indeks l - skręt w lewo z mocą PWM 700
- Indeks s - stop
- Indeks 4 - jazda do tyłu z mocą PWM 900
- Indeks 5 - jazda do przodu z mocą PWM 600
- Indeks 9 - jazda do przodu z mocą PWM 900
- Indeks O - wyłączenie obu ringów LED
- Indeks 1 - animacja LED numer 1
- Indeks 3 - animacja LED numer 3

3. Gotowa aplikacja do połączenia za pomocą Bluetooth

![Schemat RC-CAR](https://github.com/cytruseqq/RC-CAR/raw/main/Project/Media/Photos/aplikacja_sterująca.jpg)

---

## ⚙️ Funkcjonalności

- ✅ Napęd sterowany przez PWM z użyciem Timerów
- ✅ Obsługa sensorów ultradźwiękowych (pomiar odległości)
- ✅ Detekcja kolizji i unikanie przeszkód
- ✅ Obsługa pierścieni LED
- ✅ Obsługa wyświetlacza OLED
- ✅ Sterowanie ruchem przez UART (komendy tekstowe)
- ✅ Zasilanie bateryjne – pełna autonomia

## 📁 Struktura repozytorium

```
├── Project/
│   ├── Docs/
│	├── Raport.docx/
│	├── STM32F3Discovery Documentation.pdf/
│	├── Schemat układu.pdf
│   ├── Media/
│          ├── Photos/
│          ├── Videos/
├── LICENSE.md/
├── RC-CAR.zip/
├── README.md/
```

## 🔌 Polecenia sterujące

| Komenda       | Opis                                  |
|--------------:|-------------------------------------|
| `PRZÓD`       | Jazda w przód                       |
| `TYŁ`         | Jazda w tył                         |
| `LEWO`        | Jazda w lewo                        |
| `PRAWO`       | Jazda w prawo                       |
| `MANUALNY`      | Przełączenie na sterowanie manualne |
| `STOP`      | Zatrzymanie się                     |
| `AUTONOMICZNY`| Jazda autonomiczna                  |
| `900 TYŁ`     | Moc PWM ustawiona na 900 do tyłu    |
| `600 PRZÓD`   | Moc PWM ustawiona na 600 do przodu  |
| `900 PRZÓD`   | Moc PWM ustawiona na 900 do przodu  |
| `LED1`   | Pierwszy tryb pierścieni LED  |
| `LED3`   | Trzeci tryb pierścieni LED  |

---

## 🧪 Scenariusze testowe

- [x] Detekcja przeszkody z przodu (sensor HC-SR04)
- [x] Komunikacja przez Bluetooth
- [x] Test zasilania bateryjnego
- [x] Sterowanie ruchem w czasie rzeczywistym

## 📸 Zdjęcia i nagrania

- Zdjęcia pojazdu: [`/Project/Media/Photos/`](./Project/Media/Photos/)
- Nagranie testów: [`/Project/Media/Videos/`](./Project/Media/Videos/)


## 📄 Dokumentacja

Pełna dokumentacja projektu znajduje się w folderze [`/Project/Docs/`](./Project/Docs/), w tym:
- Raport końcowy (PDF)
- Schematy układów
- Dokumentacja mikrokontrolera


## 🧠 Wnioski

Projekt RC-CAR pozwolił na praktyczne połączenie wiedzy z zakresu elektroniki, programowania mikrokontrolerów oraz komunikacji bezprzewodowej. Podczas realizacji projektu udało się osiągnąć kilka kluczowych celów:
- Integracja komponentów sprzętowych: Udało się z powodzeniem połączyć serwomechanizmy, moduł napędowy, czujniki oraz moduł komunikacji Bluetooth z mikrokontrolerem, co stanowi solidną bazę do dalszego rozwoju funkcjonalności pojazdu.
- Zdalne sterowanie: Dzięki zastosowaniu aplikacji mobilnej, samochód może być sterowany w czasie rzeczywistym za pomocą modułu Bluetooth, co czyni projekt interaktywnym i użytecznym w praktyce.
- Modularność i łatwość rozbudowy: Projekt został zbudowany w sposób umożliwiający łatwe dodawanie kolejnych funkcji, takich jak: unikanie przeszkód, tryb autonomiczny, czy streaming obrazu z kamery.
- Rozwijanie umiejętności: Praca nad projektem znacząco rozwinęła kompetencje w zakresie:
	- programowania mikrokontrolerów
	- debugowania układów elektronicznych
	- zarządzania zasilaniem i komunikacją bezprzewodową
- Możliwości edukacyjne: Projekt może służyć jako świetne wprowadzenie do robotyki mobilnej i być używany na zajęciach lub warsztatach edukacyjnych.

---

## 📬 Kontakt

W razie pytań:
- Email: 21319@student.ans-elblag.pl
- GitHub: https://github.com/cytruseqq/

**Licencja:** MIT - [`/LICENSE.md`](./LICENSE.md)
