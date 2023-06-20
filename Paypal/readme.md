---
icon: repo
---

# Konfiguracja operatora PayPal

## Konfiguracja
### Zmiana trybu z sandbox na live
Pierwszym krokiem jest przejście do [panelu developera PayPal](https://developer.paypal.com/dashboard/) i zalogowano się.
Następnie w prawym górnym rogu przełączamy suwak z sandbox na live i klikamy upgrade now (jeżeli nam wyskoczy taka opcja). 
Teraz zostaliśmy przekierowani na kolejną stronę, wybieramy interesującą nas opcję dot. e-mail. Teraz wybieramy opcję
"rozszerz swoje konto". Teraz uzupełniamy pola tekstowe:
- oficjalna nazwa firmy - jeżeli prowadzimy działalność nierejestrowaną to wpisujemy "imię nazwisko działalność nierejestrowana"
- swój numer telefonu
- uzupełniamy swój adres zamieszkania 

Kontynuujemy, w rodzaj działalności wybieramy naszą działalność (w przypadku nierejestrowanej jest to "osoba fizyczna").
Teraz uzupełniamy pola odpowiednio do tego czym będziemy się zajmować i idziemy dalej. Teraz widoczne jest podsumowanie -
weryfikujemy dane i przesyłamy.
### Dodawanie operatora do VIshop
Wracamy na panel developera PayPal i wybieramy zakładkę "Apps & Credentials". Klikamy "Create App", w nazwie wpisujemy np.
nazwę naszego serwera, "Type" zostawiamy tak jak jest i klikamy "Create App".

Kopiujemy "Client ID" i wklejamy do panelu VIshop w oknie dodawania operatora PayPal w polu "ID klienta". Robimy to samo z
"Secret key 1" - kopiujemy i wklejamy do panelu VIshop w polu Sekret.


Teraz w panelu PayPal zjeżdżamy niżej i klikamy "Add webhook". W polu "Webhook URL" wklejamy link z okna dodawania operatora PayPal
z panelu VIshop, ma on w sobie słowo "webhooks". W "Event types" zaznaczamy "All Events" (możemy pojedynczo powybierać 
potrzebne, ale tak będzie prościej ;)). Teraz nasz "Webhook ID" z panelu PayPal kopiujemy i wklejamy w polu "ID webhooka".

:tada: Jeżeli poprawnie wykonałeś wszystkie kroki to płatność PayPal w twoim itemshopie powinna działać.