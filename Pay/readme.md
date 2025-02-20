---
icon: credit-card
order: -1
---
# VIshop Pay
## Czym jest VIshop Pay?
VIshop Pay to nowoczesny i prosty sposób na łatwe zaimplementowanie płatności na swojej stronie. Wystarczy umieścić skrypt
VIshop na stronie i użyć funkcji od płatności podając ID sklepu i produktu. Można również wykorzystać VIshop Pay jako zewnętrzną
stronę na którą można przekierować użytkownika w celu dokonania przez niego zakupu. Funkcja VIshop Pay jest dostępna tylko w **premium**.

## Jak tego użyć?
Wystarczy na swoją stronę dodać następujący skrypt:
```
<script src="https://vishop.pl/pay.js" defer></script>
```
Można teraz używać płatności wykorzystując funkcję:
```
vishopPay(idSklepu, idProduktu)
```
ID produktu możesz uzyskać z API 
VIshop - https://dev123.vishop.pl/panel/shops/ID_SKLEPU/products.

Istnieje również możliwość użycia VIshop Pay jako strony, na którą użytkownik zostanie przekierowany. Poprawny link
dla każdego produktu to https://pay.vishop.pl/ID_SKLEPU/ID_PRODUKTU.
