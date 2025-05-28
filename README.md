# 🚗 Autonomiczny Pojazd z STM32

Projekt semestralny z przedmiotu **Systemy Wbudowane i Mikrokontrolery**  
Autor: Magdalena Czyżewska 21227, Adrian Witów 21319, Michał Lepak 21255  
Data rozpoczęcia: 16.03.2025  
Repozytorium zawiera kod, dokumentację oraz materiały projektowe.

---

## 📌 Opis projektu

Celem projektu jest opracowanie modelu autonomicznego pojazdu sterowanego za pomocą mikrokontrolera STM32. Pojazd porusza się w trybie manualnym oraz automatycznym, gdzie omija przeszkody. Komunikacja z użytkownikiem odbywa się przez UART (Bluetooth).

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
- **Aplikacja do sterowania:** UZUPELNIC

---

## 🔌 Schemat układu

![schemat](https://github.com/user-attachments/assets/f61a6a21-8109-4fa3-a82e-791766db3f4b)

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

## 🔌 Komendy UART

| Komenda | Opis                    |
|--------:|-------------------------|
| `START` | Uruchamia pojazd       |
| `STOP`  | Zatrzymuje pojazd      |
| `LEFT`  | Skręt w lewo           |
| `RIGHT` | Skręt w prawo          |
| `DIST?` | Zwraca odczyt z HC-SR04 |

## 🧪 Scenariusze testowe

- [x] Detekcja przeszkody z przodu (sensor HC-SR04)
- [x] Komunikacja przez Bluetooth
- [x] Test zasilania bateryjnego
- [x] Sterowanie ruchem w czasie rzeczywistym

## 📸 Demo i zdjęcia

- Zdjęcia pojazdu: [`/Media/Photos/`](./Media/Photos/)
- Nagranie testów: [`/Media/Videos/`](./Media/Videos/)


## 📄 Dokumentacja

Pełna dokumentacja projektu znajduje się w folderze [`/Proect/Docs/`](./Project/Docs/), w tym:
- Raport końcowy (PDF)
- Schematy układów
- Lista komponentów


## 🧠 Wnioski


## 📬 Kontakt

W razie pytań:
- Email: 21319@student.ans-elblag.pl
- GitHub: https://github.com/cytruseqq/

**Licencja:** MIT  
