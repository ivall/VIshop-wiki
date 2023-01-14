---
icon: book
---

# Podpinanie domeny

## Konfiguracja domeny w panelu VIshop
W celu podpięcia domeny udaj się do ustawień sklepu, gdzie znajdziesz pole podpisane jako "Własna domena" i wpisz tam swoją
domenę, po czym klinkij przycisk "zapisz".  
![](https://i.imgur.com/3uT01E3.png)
## Tworzenie rekordu CNAME
Następnie wejdź na panel swojego dostawcy domeny (w naszym przypadku jest to Cloudflare), wybierz swoją domenę i przejdź do sekcji DNS. 
Utwórz nowy rekord typu CNAME i ustaw go na vishop.pl, nazwa rekordu powinna być taka jest w panelu VIshop.
Na przykład, gdy w panelu VIshop wpiszemy sklep.vishop.pl to nazwą rekordu CNAME jest sklep.
![](https://i.imgur.com/9BkBjEg.png)
## Tworzenie rekordu TXT
!!!success Rekordy TXT w przypadku Cloudflare
Jeżeli korzystasz z Cloudflare to na tym etapie możesz zakończyć konfigurację domeny. Rekordy TXT nie są wymagane w 
przypadku korzystania z Cloudflare.
!!!
Po dodaniu rekordu CNAME należy stworzyć rekord typu TXT. W tym celu przechodzimy ponownie do panelu VIshop, do zakładki ustawienia.
Klikamy "sprawdź rekordy txt". Naszym oczom ukaże się nazwa rekordu TXT oraz jego wartość.  

Przechodzimy ponownie do panelu operatora domeny i tworzymy nowy rekord DNS z typem TXT.
![](https://i.imgur.com/pNB4jgG.png)  
Jeżeli poprawnie wykonałeś wszystkie kroki to domena zacznie działać w ciągu maksymalnie kilkunastu godzin.