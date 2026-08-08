---
icon: copilot
label: Vibecoding szablonu
order: -3
---
# Vibecoding - stwórz własny szablon z AI

!!!warning Premium
Szablony wymagają aktywnego **premium** - dotyczy to również własnych szablonów tworzonych z AI.
!!!

Nie musisz umieć programować, żeby mieć własny, unikalny szablon. Przygotowaliśmy dokument, który
zawiera wszystko, co AI (Claude Code, Codex, Cursor, Copilot, Windsurf itp.) musi wiedzieć,
żeby zbudować od zera stronę itemshopu działającą na VIshop - pełny opis API, oba sposoby płatności
i sprawdzone konwencje z oficjalnych szablonów.

Dokument jest dostępny pod adresem: https://wiki.vishop.pl/szablony-ai.txt

## Jak zacząć

1. Znajdź ID swojego sklepu w panelu VIshop.
2. Otwórz swoje narzędzie AI (najlepiej takie z dostępem do internetu i plików, np. Claude Code lub Cursor).
3. Wklej poniższy prompt, podmieniając ID sklepu:

```
Przeczytaj https://wiki.vishop.pl/szablony-ai.txt i stwórz mi szablon itemshopu VIshop
dla sklepu o ID 123. Zanim zaczniesz pisać kod, zadaj mi pytania o sposób płatności,
technologię, funkcje i wygląd strony.
```

4. Odpowiedz na pytania AI (płatności przez VIshop Pay czy własny formularz, kolory, funkcje itd.) i iteruj - opisuj zmiany, które chcesz zobaczyć, aż strona będzie Ci się podobać.

Sposób wdrożenia gotowej strony zależy od wybranej technologii. Jeżeli AI stworzy czystą
stronę HTML (lub stronę generowaną statycznie), wystarczy dowolny hosting WWW - np. GitHub Pages,
Cloudflare Pages albo zwykły hosting z FTP. Jeżeli wybierzesz node.js (Nuxt itp.), stronę wdrożysz
tak samo jak oficjalne szablony:

[!ref Instalacja szablonu](/szablony/)

W razie wątpliwości po prostu zapytaj AI, jak wdrożyć stworzoną stronę.
