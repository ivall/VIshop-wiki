---
icon: repo
order: -2
---
# Niestandardowy

!!!warning Podstrona przeznaczona tylko dla programistów
Ta podstrona jest przeznaczona tylo dla programistów i pokazuje jak zintegrować się jako middleman pomiędzy VIshop, a
nieobsługiwanym przez VIshop operatorem płatności.
!!!

VIshop umożliwia dodanie do swojej platformy wsparcia zakupów przez VIshop. Warto wspomnieć przy tym, że VIshop na żadnym 
etapie nie obraca pieniędzmi, a jedynie udostępnia infrastrukturę techniczną do przeprowadzenia przez użytkownika zakupów. 
Każda platforma chcąca zostać niestandardowym operatorem musi zostać ręcznie zatwierdzona przez VIshop - w tym celu 
skontaktuj się mailowo lub poprzez Discorda.

Przykładowy kod w języku Python (FastAPI), który pokazuje jak działa niestandardowy operator w VIshop:

```python
import os
import requests

from typing import Optional
from fastapi import FastAPI, Form, Header, HTTPException, Request


app = FastAPI()

SECRET = "this_secret_has_to_be_unique_per_user123"

# Tylko w celach testowych - realnie ofc. wykorzystaj bazę danych
payments = {}


@app.post("/create-payment")
def create_payment(
    payment_id: str = Form(..., alias="id"),
    amount: str = Form(...),
    description: str = Form(""),
    return_link: str = Form(..., alias="returnLink"),
    webhook_url: str = Form(..., alias="webhook"),
    authorization: Optional[str] = Header(default=None),
):
    """
    Ten endpoint jest wywoływany przez VIshop i należy go ustawić w polu API URL w oknie dodawania/edycji operatora.
    """
    if authorization != f"Bearer {SECRET}":
        raise HTTPException(status_code=401, detail="Bad Authorization header")

    payments[payment_id] = {
        "webhook_url": webhook_url,
        "return_link": return_link,
    }

    # Tutaj powinieneś wygenerować płatność u realnego operatora płatności, który to powinien zwrócić redirectUrl, który przekażesz do VIshop

    return {
        "success": True,
        "redirectUrl": "https://redirect_url_from_your_provider.com/123",
    }


@app.post("/webhook")
async def webhook(request: Request):
    """
    Ten endpoint jest wywoływany przez realnego operatora płatności,
    w nim też wykonujesz request do VIshop.
    """
    data = await request.json()

    payment_id = str(data.get("order_id", ""))
    status = data.get("status")

    payment = payments.get(payment_id)

    r = requests.post(payment["webhook_url"], headers={"Authorization": f"Bearer {SECRET}"})

    if response.status_code == 200:
        return {"ok": True}

```