---
icon: repo
---
# Konfiguracja CashBill
## Zakładanie konta
Aby skorzystać z operatora CashBill najpierw musimy założyć konto - robimy to używając <a href=https://panel.cashbill.pl/aff/ivsystems rel="nofollow">tego linku</a>.
Jeżeli prowadzimy działalność nierejestrowaną, to w polu NIP wpisujemy 10 zer, w REGION wpisujemy 9 zer, a w nazwie firmy
"imię nazwisko działalność nierejestrowana".

## Dodawanie usługi
Przechodzimy w panelu CashBill do zakładki Nowy Sklep Internetowy, w polu adres URL sklepu wpisujemy link do sklepu na VIshop, 
sklep musi znajdować się na naszej domenie. W polu adres reklamacji wpisujemy adres e-mail, na który klienci będą mogli
wysyłać reklamacje. Platformę sklepową wybieramy jako inna (na samym dole). Resztę zostawiamy niezmiennie (chyba, że prowadzisz firmę
i chcesz płatności Paysafecard - wtedy je zaznacz), akceptujemy regulamin i klikamy uruchom usługę.

Sklep będzie teraz w trakcie weryfikacji przez pracowników CashBill - zazwyczaj trwa to do 2 dni roboczych.

## Konfiguracja usługi
Przechodzimy do panelu VIshop, do zakładki "Operatorzy płatności" i dodajemy nowego, wybieramy CashBill przelewy. Przechodzimy
teraz do panelu CashBill, w liście usług klikamy ikonę konfiguracji i kopiujemy wartość pola Identyfikator Punktu płatności.
Wklejamy go w VIshop w polu ID punktu płatności, teraz kopiujemy Klucz Punktu Płatności z usługi z CashBill i wklejamy w
VIshop w polu sekret.

Musimy jeszcze ustawić w panelu CashBill w usłudze rodzaj interfejsu komunikacji na Web Service i w polu z adresem serwerowego
potwierdzenia transakcji wklejamy wartość podaną z panelu VIshop, która wyświetla się podczas dodawania/edycji operatora CashBill 
(komunikat u góry).


Jeżeli wszystko zrobiliśmy poprawnie, to po zweryfikowaniu przez pracowników CashBill sklepu wszystko powinno działać poprawnie.

### Paysafecard
Paysafecard jest dostępny tylko i wyłącznie dla działalności zarejestrowanych - jest to odgórny wymóg firmy Paysafecard i tyczy się
każdego innego operatora płatności.
