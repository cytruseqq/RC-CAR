# 🚗 Autonomiczny Pojazd z STM32

Projekt semestralny z przedmiotu **Systemy Wbudowane i Mikrokontrolery**  
Autor: Magdalena Czyżewska 21227, Adrian Witów 21319, Michał Lepak 21255  
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
- **Aplikacja do sterowania:** Serial Bluetooth Terminal

---

## 🔌 Schemat układu

![schemat](https://github.com/user-attachments/assets/f61a6a21-8109-4fa3-a82e-791766db3f4b)

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
- Moduł bluetooth: HC-05 VCC -> 5V
- Moduł bluetooth: HC-05 GND -> STM32 GND
- Moduł bluetooth: HC-05 TXD -> STM32 PA3
- Wyświetlacz: OLED GND -> STM32 GND
- Wyświetlacz: OLED VCC -> STM32 3V
- Wyświetlacz: OLED SCL -> STM32 PB6
- Wyświetlacz: OLED SDA -> STM32 PB7

---

## ⚙️ Funkcjonalności

- ✅ Napęd sterowany przez PWM z użyciem Timerów
- ✅ Obsługa sensorów ultradźwiękowych (pomiar odległości)
- ✅ Detekcja kolizji i unikanie przeszkód
- ✅ Sterowanie ruchem przez UART (komendy tekstowe)
- ✅ Zasilanie bateryjne – pełna autonomia

## 📁 Struktura repozytorium

```
├── Project/
│   ├── Docs/
│   ├── Media/
│          ├── Photos/
│          ├── Videos/
├── LICENSE.md/
├── README.md/
```

## 🔌 Polecenia sterujące

| Komenda       | Opis                                |
|--------------:|-------------------------------------|
| `Przód`       | Jazda w przód                       |
| `Tył`         | Jazda w tył                         |
| `Lewo`        | Jazda w lewo                        |
| `Prawo`       | Jazda w prawo                       |
| `Manual`      | Przełączenie na sterowanie manualne |
| `Stop  `      | Zatrzymanie się                     |
| `Autonomiczna`| Jazda autonomiczna                  |
| `400 tył`     | Moc PWM ustawiona na 400 do tyłu    |
| `500 przód`   | Moc PWM ustawiona na 500 do przodu  |
| `900 przód`   | Moc PWM ustawiona na 900 do przodu  |

---

## 🧪 Scenariusze testowe

- [x] Detekcja przeszkody z przodu (sensor HC-SR04)
- [x] Komunikacja przez Bluetooth
- [x] Test zasilania bateryjnego
- [x] Sterowanie ruchem w czasie rzeczywistym

## 📸 Demo i zdjęcia

- Zdjęcia pojazdu: [`/Project/Media/Photos/`](./Project/Media/Photos/)
- Nagranie testów: [`/Project/Media/Videos/`](./Project/Media/Videos/)


## 📄 Dokumentacja

Pełna dokumentacja projektu znajduje się w folderze [`/Project/Docs/`](./Project/Docs/), w tym:
- Raport końcowy (PDF)
- Schematy układów
- Lista komponentów


## 🧠 Wnioski


## 📬 Kontakt

W razie pytań:
- Email: 21319@student.ans-elblag.pl
- GitHub: https://github.com/cytruseqq/

**Licencja:** MIT - [`/LICENSE.md`](./LICENSE.md)
