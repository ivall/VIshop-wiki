---
icon: repo
order: -1
---
# Konfiguracja Dpay
## Zakładanie konta
Aby skorzystać z operatora Dpay najpierw musimy założyć konto - zrobimy to na stronie dpay.pl. Po rejestracji musimy zweryfikować
nasze konto wysyłając przelew w celu zweryfikowania podanych danych, pełne informacje znajdziesz w panelu Dpay. Wymagana
jest również weryfikacja dowodu osobistego w Dpay.

## Dodawanie usługi
Należy teraz dodać punkt płatności w panelu Dpay, zrobimy to klikająć Punkty płatności -> Serwisy -> Utwórz. Wypełniamy
formularz, w polu Strona WWW wpisujemy adres strony internetowej pod którą prowadzimy sprzedaż. Jeżeli chodzi o regulamin - 
w VIshop tworzymy go za pomocą podstron i nawigacji. Umieszczamy link do niego podczas tworzenia punktu płatności. Regulamin
musi zawierać takie informacje jak jak m.in. właściciel sklepu, informacje o zwrotach, informacje o pośredniku płatności.

Po dodaniu nowego punktu płatności należy poczekać kilka roboczych na weryfikację utworzonego punktu płatności. Zweryfikowany sklep, 
który będzie gotowy do działania będzie posiadał status "Aktywny" w liście serwisów, w panelu Dpay.

## Konfiguracja usługi
Przechodzimy do panelu VIshop, do zakładki "Operatorzy płatności" i dodajemy nowego. Wybieramy Dpay, w polu "Sekret"
wpisujemy Hash z serwisu utworzonego z Dpay, znajduje się on w panelu Dpay w serwisie. W polsu "Nazwa serwisu" podajemy 
natomiast nazwę serwisu z panelu Dpay.

Po uzupełnieniu formularzu dodawania operatora na VIshop dodajemy operatora i ustawiamy ceny produktów dla danego operatora.
Jeżeli wszystko zrobiliśmy poprawnie to płatność powinna działać.

### Paysafecard
Paysafecard jest dostępny tylko i wyłącznie dla działalności zarejestrowanych - jest to odgórny wymóg firmy Paysafecard i tyczy się
każdego innego operatora płatności.
