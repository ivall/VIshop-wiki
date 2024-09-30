---
icon: paintbrush
---
# Szablony
VIshop w pakiecie premium oferuje szablony, czyli strony internetowe połączone z VIshop, które utrzymywane są
po stronie klienta i można je w pełni edytować. Dostępne szablony znajdziesz w zakładce `Szablony` w panelu VIshop.

Istnieje również możliwość odpłatnego, prostego hostowania szablonów na [szablony.tems.pl](https://szablony.tems.pl).

## Konfiguracja
### Konfiguracja szablonu
Pobieramy wybrany szablon z panelu VIshop z zakładki "Szablony". Otwieramy plik `nuxt.config.js` i dostosowujemy podstawowe 
ustawienia pod siebie zgodnie z ich opisem.

### Zmiana zdjęć
Zdjęcia możemy podmieniać w folderze "assets".

W celu zmiany ikony strony przechodzimy do folderu `static` i podmieniamy plik o nazwie `favicon.ico` na swój z taką samą
nazwą.

## Instalacja szablonu
Do poprawnego działania szablonu wymagana jest:
- **obsługa node.js w wersji do 12 - 14**
- serwer WWW (polecamy nginx - w tym poradniku zostanie on wykorzystany)

Szablon będzie działał na:
- VPS (sprawdź polecany [hosting VPS](https://ivhost.pl))
- serwerze dedykowanym
- hostingu z obsługą node.js

### Instalacja z wykorzystaniem docker i docker-compose (zalecana)
#### Instalacja dockera
Automatyczna instalacja szablonu wykorzystuje dockera. Poniższe komendy zostały przygotowane dla systemu ubuntu, ale
docker będzie działał na każdym systemie. Najpierw zainstalujmy dockera, jeśli jeszcze go nie mamy - wystarczy wykonać poniższe polecenia.  

`curl -fsSL https://get.docker.com -o get-docker.sh`

`sudo sh ./get-docker.sh`

#### Wgrywanie szablonu

Należy teraz przejść do pliku `nginx/nginx.conf` znajdującego się w naszym szablonie i ustawić domenę sklepu w
wyznaczonym miejscu.

Teraz należy przejść do folderu, gdzie jest nasz szablon (tak, abyśmy mieli dostęp do plików dockera) i wpisać poniższe
polecenia

`docker compose up -d --build `

!!!warning Port 80
Na serwerze musi być wolny port 80 (http), aby zadziałało to poprawnie. Jeżeli takowy jest zajęty to albo go zwolnij, albo
z pliku docker-compose.yml usuń częśc odpowiedzialną za nginx i do swojego serwera WWW dodaj proxy_pass na `http://localhost:3000`.
Możesz też przenieść obecną konfigurację nginxa do dockera - wystarczy pododawać w pliku nginx/nginx.conf
!!!

Teraz nasza aplikacja działa poprawnie. Jeżeli będziemy chcieli coś zmienić wystarczy dokonać zmian i wpisać  
`docker stop vishop`  
`docker compose up -d --build`  
W ten sposób nasza aplikacja zostanie zrestartowana i zmiany zostaną wgrane.

### Ręczna instalacja (niezalecana)
Poniższy poradnik został zrealizowany na ubuntu 20.04.
#### Instalacja node.js oraz npm
Jeżeli nie mamy zainstalowanego node.js lub npm na serwerze to musimy zainstalować. Najpierw wpisujemy polecenie
`apt-get update`, a następnie pobieramy node oraz npm poprzez polecenia:

`curl -sL https://deb.nodesource.com/setup_14.x | sudo bash -`  
`sudo apt -y install nodejs`  
`sudo apt install npm`

#### Wgrywanie szablonu
Szablon wgrywamy poprzez S-FTP/FTP na serwer, gdzie będzie on utrzymywany. Następnie używając SSH przechodzimy do 
jego lokalizacji (`cd /twoja/lokalizacja/szablonu`). Wykonujemy `npm install`, a po zakończeniu uruchamiamy `npm run build`, następnie `screen` i `npm run start`, by wyjść z sesji screena użyjemy następującego skrótu `CTRL + A + D`.
Nasz szablon działa teraz lokalnie na porcie 3000, pora udostępnić go światu!

#### Konfiguracja nginx
Jeżeli nie posiadamy zainstalowanego nginx to instalujemy go następującym poleceniem `apt-get install nginx`. Przechodzimy teraz do folderu, gdzie
będzie znajdowała się nasza konfiguracja nginx używając polecenia `cd /etc/nginx/sites-enabled`. Wpisujemy teraz `sudo nano vishop`
i wklejamy następującą konfigurację:
```
map $sent_http_content_type $expires {
    "text/html"                 epoch;
    "text/html; charset=utf-8"  epoch;
    default                     off;
}

server {
    listen          80;
    server_name     _;    # tutaj wpisz swoja domene na ktorej masz rekord A

    gzip            on;
    gzip_types      text/plain application/xml text/css application/javascript;
    gzip_min_length 1000;

    location / {
        expires $expires;

        proxy_redirect                      off;
        proxy_set_header Host               $host;
        proxy_set_header X-Real-IP          $remote_addr;
        proxy_set_header X-Forwarded-For    $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto  $scheme;
        proxy_read_timeout                  1m;
        proxy_connect_timeout               1m;
        proxy_pass                          http://127.0.0.1:3000;
    }
}
```
Zapisujemy i wychodzimy (ctrl+s, a później ctrl+x). 
Uruchamiamy nasz serwer nginx za pomocą polecenia - `sudo systemctl start nginx` / bądź restartujemy jeżeli takowy serwer już działa - `sudo systemctl restart nginx`

## Uruchomienie lokalnie jako dev
Wymagana jest wersja **node.js 12 - 14**. Jeżeli mamy już node w takiej wersji to wystarczy pobrać szablon, wejść do niego
i wpisać `npm install`, a następnie `npm run dev`. Teraz nasz szablon jest uruchomiony w trybie dev i mamy hot reload, można
teraz z łatwością edytować stronę mając podgląd na żywo.

Po zakończeniu edycji szablon instalujemy tak jak normalnie (patrz wyżej).
