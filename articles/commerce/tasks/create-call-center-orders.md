---
title: Tworzenie zamówień dla biur obsługi
description: Ta procedura zawiera instruktaż wyszukiwania odbiorcy, tworzenia nowego zamówienia, wyszukiwania produktu i inkasowania płatności od odbiorcy.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4ec10e0f79e4eca7f51ba48c679dcf6fe745eb29
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141437"
---
# <a name="create-call-center-orders"></a>Tworzenie zamówień dla biur obsługi

[!include [banner](../includes/banner.md)]

Ta procedura zawiera instruktaż wyszukiwania odbiorcy, tworzenia nowego zamówienia, wyszukiwania produktu i inkasowania płatności od odbiorcy. Procedura wykorzystuje dane firmy demonstracyjnej USRT i jest przeznaczona dla pracownika ds. zamówień sprzedaży. Warunki wstępne: Użytkownik wykonujący tę procedurę musi być skonfigurowany jako użytkownik biura obsługi, a półroczny katalog firmy Fabrikam musi być opublikowany i zawierać co najmniej jeden kod źródłowy.

1. Wybierz kolejno opcje Handel detaliczny i inny > Odbiorcy > Obsługa klienta.
2. W polu SearchText wprowadź kryteria wyszukiwania, aby znaleźć odbiorcę.
    * W tej przykładowej procedurze wpisz „karen”, a następnie naciśnij klawisz tab.  
3. Kliknij przycisk Wyszukaj.
    * Ponieważ w danych demonstracyjnych jest tylko jeden odbiorca o nazwie Karen, zostanie on automatycznie zaznaczony.  
4. Kliknij opcję Nowe zamówienie sprzedaży.
5. Rozwiń lub zwiń sekcję Nagłówek zamówienia sprzedaży.
6. Wybierz kod źródłowy dla katalogu.
    * Jeśli nie ma żadnych aktywnych kodów źródłowych, można zamknąć pole Źródło i pominąć ten krok.  
7. Kliknij przycisk Dodaj wiersz.
8. W polu Numer towaru wpisz wyszukiwany termin, przy użyciu którego chcesz znaleźć towar.
    * W tej przykładowej procedurze wprowadź część numeru towaru „8111”, a następnie naciśnij klawisz tab. Pojawi się wyskakujące okno wyszukiwania towaru.  
9. Wybierz produkt, który chcesz dodać do zamówienia sprzedaży.
10. Wprowadź ilość sprzedaży.
11. Kliknij Utwórz.
12. Kliknij przycisk Gotowe, aby zarejestrować informacje o płatności od odbiorcy.
13. Kliknij przycisk Dodaj.
    * Łącze Dodaj znajduje się na karcie Płatności. Jeśli karta Płatności jest zwinięta, rozwiń ją.  
14. Wybierz metodę płatności.
    * W tej procedurze wybierz płatność gotówką.  
15. Zamknij stronę.
16. Wpisz kwotę.
    * W tej procedurze wprowadź kwotę równą saldu zamówienia, które widać na stronie Podsumowanie zamówienia sprzedaży na lewo od pola kwoty. Dzięki temu będzie można sfinalizować zamówienie jako w pełni opłacone.  
17. Kliknij przycisk OK.
18. Kliknij przycisk Prześlij.

