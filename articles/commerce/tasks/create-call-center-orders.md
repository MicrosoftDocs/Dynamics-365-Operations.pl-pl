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
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 08a806514a92a99a9f0b18b36817f49a09516ab8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964852"
---
# <a name="create-call-center-orders"></a>Tworzenie zamówień dla biur obsługi

[!include [banner](../includes/banner.md)]

Ta procedura zawiera instruktaż wyszukiwania odbiorcy, tworzenia nowego zamówienia, wyszukiwania produktu i inkasowania płatności od odbiorcy. Procedura wykorzystuje dane firmy demonstracyjnej USRT i jest przeznaczona dla pracownika ds. zamówień sprzedaży. Warunki wstępne: Użytkownik wykonujący tę procedurę musi być skonfigurowany jako użytkownik biura obsługi, a półroczny katalog firmy Fabrikam musi być opublikowany i zawierać co najmniej jeden kod źródłowy.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Odbiorcy \> Obsługa klienta**.
2. W polu **SearchText** wprowadź kryteria wyszukiwania, aby znaleźć odbiorcę.
    * W tej przykładowej procedurze wpisz „Karen”, a następnie naciśnij klawisz **Tab**.  
3. Wybierz opcję Wyszukaj.
    * Ponieważ w danych demonstracyjnych jest tylko jeden klient o imieniu „Karen”, wynik zostanie wybrany automatycznie.  
4. Wybierz opcję **Nowe zamówienie sprzedaży**.
5. Rozwiń lub zwiń sekcję nagłówek **Zamówienia sprzedaży**.
6. Wybierz kod źródłowy dla katalogu.
    * Jeśli nie ma żadnych aktywnych kodów źródłowych, można pominąć ten krok.  
7. Wybierz **Dodaj wiersz**.
8. W polu **Numer towaru** wpisz wyszukiwany termin, przy użyciu którego chcesz znaleźć towar.
    * W tej przykładowej procedurze wprowadź częściowy numer pozycji „8111” i naciśnij klawisz tab. Ta czynność spowoduje wyświetlenie okna wyszukiwania przedmiotów.  
9. Wybierz produkt, który chcesz dodać do zamówienia sprzedaży.
10. Wprowadź ilość sprzedaży.
11. Wybierz opcję **Utwórz**.
12. Wybierz **Gotowe**, aby zarejestrować informacje o płatności od odbiorcy.
13. Wybierz opcję **Dodaj**.
    * Łącze Dodaj znajduje się na karcie Płatności. Jeśli karta Płatności jest zwinięta, rozwiń ją.  
14. Wybierz metodę płatności.
    * W tej procedurze wybierz płatność gotówką.  
15. Zamknij stronę.
16. Wpisz kwotę.
    * W tej procedurze wprowadź kwotę równą saldu zamówienia, które widać na stronie Podsumowanie zamówienia sprzedaży na lewo od pola kwoty. Ta czynność pozwoli Ci zrealizować zamówienie jako w pełni opłacone.  
17. Kliknij przycisk **OK**.
18. Wybierz opcję **Prześlij**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dostosowywanie wiadomości e-mail dotyczących transakcji według metod dostawy](../customize-email-delivery-mode.md)

[Zmienianie metody dostawy w punkcie sprzedaży](../pos-change-delivery-mode.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]