---
icon: book
---

# Podpinanie domeny

## Konfiguracja domeny w panelu VIshop
W celu podpięcia domeny udaj się do ustawień sklepu, gdzie znajdziesz pole podpisane jako "Własna domena" i wpisz tam swoją
domenę, po czym kliknij przycisk "zapisz". 
!!!warning Uwaga!
Tylko Cloudflare umożliwia podpięcie domeny w postaci domena.pl. Inni operatorzy domen wymagają podania subdomeny
np. sklep.domena.pl. Przeniesienie domeny na Cloudflare jest darmowe, proste i szybkie ale nie jest wymagane.
!!!
![](https://i.imgur.com/3uT01E3.png)
## Konfiguracja domeny na Cloudflare
Następnie wejdź na panel Cloudflare, wybierz swoją domenę i przejdź do sekcji DNS. 
Utwórz nowy rekord typu CNAME i ustaw target na `vishop.pl`, nazwa rekordu powinna być taka jest w panelu VIshop.
Na przykład, gdy w panelu VIshop wpiszemy `domena.pl` to nazwą rekordu CNAME jest `domena.pl`.
![](https://i.imgur.com/9BkBjEg.png)
:tada: Jeżeli poprawnie wykonałeś wszystkie kroki to domena zacznie działać w ciągu kilku minut.
## Konfiguracja domeny na OVH i innych stronach
### Tworzenie rekordu CNAME
Przejdź do panelu operatora (w tym przypadku OVH), u którego posiadasz domenę i wybierz swoją domenę. Następnie przejdź
do zakładki DNS (Strefa DNS). Dodaj nowy rekord typu CNAME, jego nazwa musi być taka sama jak domena podana w panelu VIshop.
W tym przypadku będzie to `sklep.ivsystems.pl`. Jako adres docelowy (czasami zwany też celem) ustaw vishop.pl.
![](https://i.imgur.com/aYkafxG.png)
### Tworzenie rekordu TXT
Po utworzeniu rekordu CNAME przejdź do panelu VIshop, do zakładki ustawienia i kliknij `pokaż rekordy txt`. Teraz wróć do
panelu operatora i utwórz nowy rekord typu TXT o nazwie otrzymanej w panelu (zwróć uwagę czy domena nie zduplikuje się).
Wartość rekordu ustaw również na tą z panelu, którą otrzymałeś po kliknięciu przycisku.
![](https://i.imgur.com/km0zJQB.png)
:tada: Jeżeli poprawnie wykonałeś wszystkie kroki to domena zacznie działać w ciągu maksymalnie godziny.
