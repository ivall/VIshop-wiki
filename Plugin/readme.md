---
icon: server
---

# Plugin VIshop

## Minecraft

### Instalacja
Pobieramy najnowszą wersję pluginu z [tej strony](https://github.com/ivall/VIshop-plugin/releases). 
Dokładne informacje na temat wspieranych przez plugin wersji i silników dostępne sa w ReadME pluginu, które możesz 
sprawdzić [tutaj](https://github.com/ivall/VIshop-plugin/blob/main/README.md).  
Następnie dodajemy plugin na nasz serwer Minecraft. Po dodaniu pluginu na serwer należy **zrestartować serwer**.

### Konfiguracja
Nieskonfigurowany plugin będzie wyświetlał się na czerwono w liście pluginów. Do poprawnego działania musimy skonfigurować plugin.

W folderze `plugins` przechodzimy do folderu `ViShopPlugin`, a następnie otwieramy plik `config.yml`. Znajdują się tam trzy
zmienne, które musimy uzupełnić.

Nazwa pola   | Wymagana wartość pola
---    | ---
apiKey | Klucz API, który znajduje się w panelu VIshop, w zakładce ustawienia.
shopId | ID sklepu, znajdziesz je w głównej zakładce panelu VIshop.
serverId | ID serwera, znajduje się w panelu VIshop, w zakładce serwery.

Po skonfigurowaniu pluginu zapisujemy plik `config.yml` i **restartujemy serwer**.

!!!warning Restart serwera
Bardzo ważne jest, aby serwer został zrestartowany. Nie używamy do tego komendy `/reload`, ani innych pluginów
odpowiedzialnych za "restartowanie" serwera.
!!!

### Testowanie pluginu

W celu przetestowania pluginu należy wygenerować voucher w sklepie i go wykorzystać. Jeżeli w produkcie, dla którego został
wygenerowany voucher jest zaznaczony wymóg bycia online to gracz z podanym w realizacji vouchera nickiem musi być na serwerze. 
Po zrealizowaniu vouchera status transakcji zmieni się na wykonywanie, a następnie po maksymalnie 30 sekundach na wykonano.
Jeżeli tak się nie stało oznacza to, że plugin VIshop nie działa poprawnie.

### Naprawianie pluginu

W przypadku, gdy plugin nie działa poprawnie to w konsoli pokazują się odpowiednie komunikaty. Komunikaty te znajdują się 
również w logach serwera. Należy poprawić konfigurację pluginu.

### Itemshop w GUI

Zachęcamy również do użycia pluginu [VIshopGUI](https://www.spigotmc.org/resources/vishopgui.116786/), który umożliwia stworzenie itemshopu w GUI. 
Do działania wymagane jest premium.

## FiveM

### Dodawanie skryptu
Skrypt pobierzesz z [tego miejsca](https://github.com/ivall/VIshopPluginFivem). W celu dodania skryptu w folderze resources 
swojego serwera umieść folder vishop zawierający plik server.lua itd.

### Konfiguracja pluginu
Do poprawnego działania pluginu wymagane jest jego poprawne skonfigurowanie. W tym celu otwórz plik config.lua i uzupełnij
pola według podanej w pliku instrukcji.

### Wsparcie Steam
VIshop do poprawnego działania **wymaga używania Steam przez graczy**. Każdy gracz **musi** mieć dostępny identyfikator Steam 
podczas wchodzenia na serwer i gry na nim.

W tym celu przejdź do pliku konfiguracyjnego swojego serwera (server.cfg) i uzupełnij pole `steam_webApiKey` według podanej
instrukcji. Zalecane jest również użycie skryptu, który zablokuje graczy niekorzystających ze Steam.

### Baza danych
Skrypt VIshop korzysta z [fivem-mysql-async](https://github.com/brouznouf/fivem-mysql-async). Pobierz fivem-mysql-async, a
następnie utwórz folder [essential] w resources, w nim umieść folder fivem-mysql-async i zmień nazwę folderu na mysql-async.

Następnie utwórz bazę danych MySQL i uruchom w niej plik database.sql w celu stworzenia tabeli
wykorzystywanej przez skrypt VIshop.

Przejdź teraz do pliku konfiguracyjnego server.cfg i dopisz do niego poniższy kod zmieniając dane do połączenie się do bazy danych.
```
set mysql_connection_string "server=ADRES_POLACZENIA;database=NAZWA_BAZY;userid=NAZWA_UZYTKOWNIKA;password=HASLO" 
ensure mysql-async
```

### Identyfikatory
Skrypt VIshop udostępnia 2 identyfikatory, steam oraz license podawane w formacie z prefixem (np. steam:xxxxxxxxx). Placeholdery
z identyfikatorami znajdziesz w polu z komendami w okienku dodawania produktu, tam też ich użyj.