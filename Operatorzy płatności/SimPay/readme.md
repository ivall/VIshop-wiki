---
icon: repo
---
# Konfiguracja SimPay

SimPay.pl to nowoczesny operator płatności umożliwiający przyjmowanie płatności przez Przelewy online, BLIK, PayPal, Skrill, PaySafeCard, SMS Premium oraz Direct Billing (SMS+).

SimPay umożliwia również rejestrację konta dla działalności nierejestrowanych.

## Dla kogo jest SimPay?

Z usług SimPay mogą korzystać:

- osoby prowadzące działalność gospodarczą,
- spółki, fundacje i stowarzyszenia,
- osoby prowadzące działalność nierejestrowaną.

Możliwe jest również założenie konta przez osoby niepełnoletnie. W takim przypadku podczas procesu weryfikacji wymagane będzie dostarczenie zgody rodzica lub opiekuna prawnego.

## Rejestracja konta SimPay

Jeżeli nie posiadasz jeszcze konta, zarejestruj się na stronie SimPay i przejdź proces weryfikacji.

Podczas rejestracji:

1. Utwórz konto klienta.
2. Uzupełnij dane właściciela konta.
3. Dodaj informacje o swojej działalności lub działalności nierejestrowanej.
4. Prześlij wymagane dokumenty weryfikacyjne.
5. Poczekaj na aktywację konta przez personel SimPay.

## Rejestracja usługi

W panelu Klienta SimPay przejdź do zakładki Płatności online > Lista usług. Naciśnij zielony przycisk "Dodaj nową usługę".
Wypełnij wymagane pola, pole Adres URL IPN na razie zostaw pusty. Pamiętaj, żeby Twój sklep posiadał regulamin.
Po utworzeniu usługi personel SimPay w przeciągu 1-2 dni roboczych zaktywuje usługę lub poinformuje mailowo czego brakuje w sklepie.

## Konfiguracja usługi
Krok 1. W panelu SimPay przejdź do zakładki Płatności online > Lista usług. Wybierz odpowiednią usługę i naciśnij przycisk "Szczegóły".
![Krok 1: Wybór usługi](https://i.imgur.com/qeBQHXL.png)

Krok 2. Skopiuj ID usługi oraz Klucz do sygnatury IPN. Po kroku 4 wróć tutaj, uzupełnij `Adres URL IPN` wartością z panelu Vishop (każdy sklep ma różny link).
![Krok 2](https://i.imgur.com/EmF5ZKG.png)

Krok 3. W panelu SimPay przejdź do Konto Klienta > API > Wybierz lub utwórz nowy dostęp oraz naciśnij przycisk "Szczegóły" na wybranym kluczu.
Zapisz wartość z pola "Hasło / Bearer Token"
![Krok 3](https://i.imgur.com/1spRIax.png)

Krok 4. W panelu Vishop przejdź do zakładki "Operatorzy płatności", następnie naciśnij "Nowy operator płatności", wybierz operatora płatności "Simpay".
Uzupełnij dane jak poniżej:
- Sekret: "Klucz do sygnatury IPN",
- ID Webhooka: ID usługi,
- Hasło notyfikacji: Wartość z pola "Hasło / Bearer Token"

Skopiuj URL notyfikacji i wklej go do miejsca zaznaczonego czerwonym kolorem na obrazku w kroku 2.
Upewnij się również, że pole "Wersja IPN" jest ustawiona na V2. (w ustawieniach usługi w panelu SimPay)
![Krok 4](https://i.imgur.com/eDeeGQe.png)

### PaysafeCard, Direct Billing i SMS Premium
PaysafeCard, Direct Billing oraz SMS Premium wymagają posiadania zarejestrowanej działalności gospodarczej/spółki.
