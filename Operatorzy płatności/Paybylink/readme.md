---
icon: repo
---
# Konfiguracja Paybylink
## Zakładanie konta
Aby skorzystać z operatora Paybylink najpierw musimy założyć konto - zrobimy to <a href="https://paybylink.pl/user/access/invite/11104527e581a6cfe16d5e7826d83dc3/" target="_blank" rel="nofollow noopener">tutaj</a>.
Jeżeli prowadzimy działalność nierejestrowaną to w polu NIP wpisujemy 10 zer, w REGION wpisujemy 9 zer, a w nazwie firmy
"imię nazwisko działalność nierejestrowana". Po rejestracji musimy zweryfikować nasze konto wysyłając przelew w celu zweryfikowania
podanych danych, pełne informacje znajdziesz w panelu Paybylink.
## Dodawanie usługi
Teraz pora dodać pierwszą usługę, w tym przypadku będą to przelewy i opcjonalnie PayPal, ta funkcja jest w przelewach i wystarczy
podać adres e-mail naszego konta PayPal.

Przechodzimy do zakładki "Przelewy internetowe", wybieramy "Sklepy" i klikamy "Dodaj nowy kanał". Teraz uzupełniamy formularz.


Nazwa pola   | Co wpisać
---    | ---
Strona internetowa | Adres naszej strony internetowej pod którą będzie prowadzona sprzedaż usług (np. sklep.superserwer123.pl)
Adres regulaminu | Link do regulaminu płatności, który będzie obowiązywał na stronie. W regulaminie muszą być takie informacje jak m.in. właściciel sklepu, informacje o zwrotach, informacje o pośredniku płatności.
Nazwa odbiorcy | Nazwa, która będzie wyświetlała się kupującym, np. superserwer123

Po dodaniu nowego sklepu należy poczekać zazwyczaj do 2-3 dni roboczych na zweryfikowanie sklepu przez obsługę Paybylink.
Zweryfikowany sklep, który będzie gotowy do działania będzie posiadał plakietkę "AKTYWNA".
## Konfiguracji usługi
Przechodzimy do panelu VIshop, do zakładki "Operatorzy płatności" i dodajemy nowego. Wybieramy Paybylink Przelewy, w polu "Sekret"
wpisujemy Hash z usługi stworzonej w serwisie Paybylink. W "Id serwisu" podajemy ID naszej usługi (znajduje się pod nazwą usługi) z panelu Paybylink.
Po uzupełnieniu formularzu dodawania operatora na VIshop dodajemy operatora i ustawiamy ceny produktów dla danego operatora.
Jeżeli wszystko zrobiliśmy poprawnie to płatność powinna działać.

### Paysafecard
Paysafecard jest dostępny tylko i wyłącznie dla działalności zarejestrowanych - jest to odgórny wymóg firmy Paysafecard i tyczy się
każdego innego operatora płatności.