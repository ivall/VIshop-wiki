---
icon: server
---

# Plugin VIshop

## Instalacja
Pobieramy najnowszą wersję pluginu z [tej strony](https://github.com/ivall/VIshop-plugin/releases). Wspieramy wersje od 1.8 do 1.19.3 na pochodnych Bukkita (Spigot, Paper, itp..) oraz pochodnych BungeeCorda i Velocity.
Następnie dodajemy plugin na nasz serwer Minecraft. Po dodaniu pluginu na serwer należy **zrestartować serwer**.

## Konfiguracja
Nieskonfigurowany plugin będzie wyświetlał się na czerwono w liście pluginów. Do poprawnego działania musimy skonfigurować plugin.

W folderze plugins przechodzimy do folderu ViShopPlugin, a następnie otwieramy plik config.yml. Znajdują się tam trzy
zmienne, które musimy uzupełnić.

Nazwa pola   | Wymagana wartość pola
---    | ---
apiKey | Klucz api, który znajduje się w panelu VIshop, w zakładce ustawienia.
shopId | ID sklepu, znajdziesz je w głównej zakładce panelu VIshop.
serverId | ID serwera, znajduje się w panelu VIshop, w zakładce serwery.

Po skonfigurowaniu pluginu zapisujemy plik config.yml i **restartujemy serwer**.

!!!warning Restart serwera
Bardzo ważne jest, aby serwer został zrestartowany. Nie używamy do tego komendy /reload, ani innych pluginów
odpowiedzialnych za "restartowanie" serwera.
!!!

## Testowanie pluginu

W celu przetestowania pluginu należy wygenerować voucher w sklepie i go wykorzystać. Jeżeli w produkcie, dla którego został
wygenerowany voucher jest zaznaczony wymóg bycia online to gracz z podanym w realizacji vouchera nickiem musi być na serwerze. 
Po zrealizowaniu vouchera status transakcji zmieni się na wykonywanie, a następnie po maksymalnie 30 sekundach na wykonano.
Jeżeli tak się nie stało oznacza to, że plugin VIshop nie działa poprawnie.

## Naprawianie pluginu

W przypadku, gdy plugin nie działa poprawnie to w konsoli pokazują się odpowiednie komunikaty. Komunikaty te znajdują się 
również w logach serwera. Należy poprawić konfigurację pluginu.
