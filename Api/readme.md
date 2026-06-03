---
icon: book
order: -2
---

# API VIshop
API VIshop jest w pełni publiczne i dostępne dla wszystkich. Do stworzenia pełnoprawnej strony działającej na API VIshop 
wymagane jest premium, część endpointów (od pozyskania listy serwerów i bezpośredniego generowania płatności) go wymaga.
Również oficjalne szablony VIshop wykorzystują API i można je w pełni przerabiać i brać z nich kod działający na API.

Oficjalnej dokumentacji API nie ma, natomiast istnieje kilka prostych sposób na rozwiązanie tego problemu. Pierwszym z nich
są wspomniane już wcześniej oficjalne szablony VIshop. Działają one w pełni na API VIshop i tak naprawdę nie trzeba nawet pisać
strony od nowa, a wystarczy przerobić front-end szablonu. Można też sprawdzić w ich kodzie jak działa API, jakie są endpointy,
parametry itd.

Drugim sposobem jest uruchomienie zbadaj element -> networking i wykonywanie różnych akcji na sklepach VIshop - wszystkie
wykonane requesty do API wraz z wysłanymi danymi będą w networking w kategorii Fetch/XHR. Zalecamy robienie tego na sklepach
SaaS, nie szablonach ze względu na to, że w szablonach część endpointów jest wywoływana po stronie serwera więc nie widać
tego w zbadaj element.

Trzecim sposobem jest skorzystanie z tego - https://pastebin.com/BGbqbZQc, jest to prowizoryczna dokumentacja API wykonana
na podstawie szablonu.

Warto też pamiętać o [VIshop Pay](/pay/), znacząco to ułatwia sprawę - dzięki temu nie musimy zajmować się generowaniem zakupu,
kodami rabatowymi i generalnie tymi najcięższymi rzeczami. Wystarczy tylko pobierać listę serwerów, produktów i je wyświetlać
co jest banalne i pozwala na szybkie stworzenie własnej strony działającego na VIshop.