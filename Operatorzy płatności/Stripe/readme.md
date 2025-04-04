---
icon: repo
---
# Konfiguracja Stripe

Pierwszym krokiem jest oczywiście założenie konta na platformie Stripe. Po rejestracji przechodzimy do panelu stripe (dashboard.stripe.com), a następnie
po wybraniu naszego sklepu w menu po lewej na dole klikamy zakładkę developers. 

### Sekret
Przechodzimy następnie do API keys i kopiujemy secret key. W panelu VIshop w formularzu operatora Stripe jest to sekret, tam
też wklejamy nasz secret key.

### Webhook
Przechodzimy w panelu Stripe teraz do webhooks, klikamy przycisk add endpoint i uzupełniamy formularz. W polu endpoint url
wklejamy URL notyfikacji z panelu VIshop, który jest pokazany przy dodawaniu/edytowaniu operatora Stripe. Teraz w Stripe
klikamy select events, a następnie select all events i zatwierdzamy formularz poprzez przycisk add endpoint.


Po utworzeniu webhooka w Stripe przechodzimy do niego (w panelu Stripe) i pod signing secret klikamy reveal. Pokaże nam się
nasze hasło notyfikacji, które kopiujemy i wklejamy w polu hasło notyfikacji w panelu VIshop.