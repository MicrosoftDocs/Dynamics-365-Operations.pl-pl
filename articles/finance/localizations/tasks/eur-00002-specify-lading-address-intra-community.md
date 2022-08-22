---
title: EUR-00002 Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej
description: Ta procedura pokazuje, jak określić adres załadunku dla transakcji handlu wewnątrzwspólnotowego.
author: AdamTrukawka
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form:
- PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, TransportationDocument, LogisticsPostalAddress, SysLookupMultiSelectGrid
- VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog, Intrastat, SysQueryForm
ms.openlocfilehash: 2094d24f256647ee3193f7e069e33bf4d99c1b70
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280606"
---
# <a name="eur-00002-specifying-a-lading-address-for-an-intra-community-transaction"></a>EUR-00002 Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak określić adres załadunku dla transakcji handlu wewnątrzwspólnotowego. Na przykład niemiecka firma zamawia towary od dostawcy z adresem służbowym w Niemczech. Ten dostawca ma magazyn we Włoszech i wysyła towary stamtąd. Tę dostawę należy zgłosić w systemie Intrastat. To samo zachowanie obowiązuje w przypadku zwrotów od odbiorców.
Ta procedura dotyczy wszystkich krajów/regionów Europy. Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech. Zanim będzie można wykonać tę procedurę, trzeba skonfigurować funkcję raportowania Intrastat. Procedura jest przeznaczona dla księgowych. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.

1. Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. Wprowadź lub wybierz wartość.
    * Na przykład zaznacz DE-001. Ten dostawca ma adres służbowy w Niemczech.  
4. Kliknij przycisk OK.
5. Na liście oznacz wybrany wiersz.
6. W polu Numer towaru wprowadź lub wybierz wartość D0001.
7. Kliknij przycisk Zapisz.
8. W okienku akcji kliknij pozycję Zakup.
9. Kliknij opcję Szczegóły transportu.
10. W polu Data i godzina ładowania wprowadź datę i godzinę.
11. Kliknij opcję Dodaj adres.
12. Kliknij przycisk Nowy i utwórz nowy adres z celem Załadunek.
13. W polu Nazwa lub opis wpisz wartość „Włoski”.
14. Jako wartość wybierz Załadunek.
    * Należy zwrócić uwagę, że celem adresu musi być Załadunek.  
15. W polu Kraj/region wprowadź lub wybierz wartość ITA.
16. Kliknij przycisk Zapisz.
17. Zamknij stronę.
18. Kliknij przycisk Zapisz.
    * Sprawdź poprawność adresu załadunku.  
19. Zamknij stronę.
20. W okienku akcji kliknij pozycję Zakup.
21. Kliknij przycisk Potwierdź.
22. W okienku akcji kliknij pozycję Faktura.
23. Kliknij opcję Faktura.
24. W polu Numer wpisz wartość.
25. Wprowadź datę w polu Data faktury.
26. Na liście Domyślnie z zaznacz opcję Ilość z dokumentu przyjęcia produktów, aby otworzyć rozwijane okno dialogowe.
27. W polu Domyślna ilość dla wierszy zaznacz wartość „Ilość zamówiona”.
28. Kliknij przycisk OK.
29. Kliknij opcję Szczegóły transportu.
    * Sprawdź, czy towary zostały wysłane z Włoch. W razie potrzeby można edytować szczegóły załadunku.  
30. Zamknij stronę.
31. Kliknij przycisk Księguj.
32. Zamknij stronę.
33. Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.
34. Kliknij przycisk Przeniesienie.
35. W polu Faktura dostawcy zaznacz opcję Tak.
36. Kliknij przycisk OK.
37. Kliknij kartę Ogólne.
    * Znajdź nowo utworzony wiersz i upewnij się, że nadawca wysłał towary z Włoch.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
