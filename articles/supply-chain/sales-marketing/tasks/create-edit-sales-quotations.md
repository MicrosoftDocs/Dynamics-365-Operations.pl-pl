---
title: Tworzenie i edytowanie ofert sprzedaży
description: Ta procedura przedstawia sposób tworzenia i aktualizowania oferty sprzedaży.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b5618a815aaff12dd366523920ed275801b3b16
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546117"
---
# <a name="create-and-edit-sales-quotations"></a>Tworzenie i edytowanie ofert sprzedaży

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura przedstawia sposób tworzenia i aktualizowania oferty sprzedaży. Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF.


## <a name="create-a-sales-quotation"></a>Tworzenie oferty sprzedaży
1. Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.
2. Kliknij przycisk Nowy.
3. W polu Typ konta wybierz opcję „Prospekt”.
4. W polu Potencjalny klient wprowadź lub wybierz wartość.
5. Rozwiń sekcję Ogólne.
    * Ponieważ wybrano opcję utworzenia oferty sprzedaży z poziomu obszaru Sprzedaż i marketing, typ jest automatycznie ustawiany na Oferta sprzedaży. Aby utworzyć ofertę dla projektu, trzeba przejść do niego z modułu Zarządzanie projektami i ich księgowanie.   
6. Kliknij przycisk OK.
    * Pola i akcje w wierszach oferty są bardzo podobne do używanych w wierszach zamówienia sprzedaży.   Tak jak zamówienia sprzedaży, oferty można tworzyć dla określonego towaru, a gdy towar jest nieznany lub nie istnieje w momencie utworzenia oferty, można je tworzyć dla kategorii sprzedaży.  
7. W polu Towar wprowadź lub wybierz wartość.
8. W polu Towar wpisz wartość.
9. Zamknij stronę.
10. Wprowadź liczbę w polu Ilość.
    * Jeśli istnieją ważne umowy handlowe na towar wybrany w wierszu, odnośna cena i rabaty zostaną automatycznie skopiowane do wiersza oferty. Upewnij się, że pole Cena jednostkowa zawiera wartość. Jeśli chcesz, można również wprowadzić wartości rabatów.  
11. Kliknij przycisk Zapisz.
12. W okienku akcji kliknij opcję Oferta sprzedaży.
13. Kliknij przycisk Sumy.
14. Kliknij przycisk OK.
15. Kliknij wiersz Oferta sprzedaży.
16. Kliknij opcję Ceny.
    * Na stronie Uruchom symulację ceny można wypróbować korygowanie spodziewanych przychodów lub rentowności wynikającej z oferty na podstawie żądanej ceny jednostkowej, kwoty rabatu, procentu rabatu, łącznej kwoty, marży lub współczynnika marży.   Po uzyskaniu zadowalających docelowych wartości zastosuj sugestię do wiersza oferty, a jego pola związane z ceną zostaną odpowiednio zaktualizowane.  
    * Można utworzyć tyle symulacji cen, ile trzeba. Po kliknięciu przycisku Nowy warunki cenowe z bieżącego wiersza oferty są kopiowane do strony. Następnie można zmodyfikować wartości w polach dotyczących ceny na docelowe. Zmiana w jednym z pól spowoduje uruchomienie ponownego obliczania we wszystkich pozostałych polach. Aby system obliczał marżę sprzedaży i współczynnik marży, musi być znany koszt jednostkowy produktu. Karta Symulowane ceny zawiera szczegółowy widok oryginalnych cen, proponowanych zmian oraz ich wpływu na sumy w ofercie.   Co do zasady zastosowanie do wiersza oferty symulacji ustawiającej nową kwotę powoduje, że system wykuje ponowne obliczenie i wprowadza nową wartość w polu Cena jednostkowa. Jeśli symulacja opiera się na nowej marży lub nowym współczynniku marży, jest aktualizowane tylko pole Kwota netto, a pole Cena jednostkowa pozostaje puste. W obu przypadkach wszelkie rabaty, które istniały w wierszu oferty przed symulacją, zostaną usunięte.  
17. Zamknij stronę.
18. W okienku akcji kliknij pozycję Oferta.
19. Kliknij przycisk Wyślij ofertę.
20. W polu Drukowanie oferty zaznacz opcję Tak.
21. Kliknij przycisk OK.
    * Generowanie raportu może nieco potrwać. Przez ten czas nie zamykaj strony.  
22. Zamknij stronę.

## <a name="update-a-sales-quotation"></a>Aktualizowanie oferty sprzedaży
1. W okienku akcji kliknij pozycję Monituj.
2. Kliknij opcję Konwertuj na odbiorcę.
3. W polu Konto odbiorcy wpisz wartość.
4. Kliknij przycisk Sprawdź.
    * Upewnij się, że zostanie wyświetlony komunikat, iż wpisany numer konta jest wolny i można go użyć.  
5. Kliknij przycisk OK.
    * System utworzył nowe konto odbiorcy dla potencjalnego klienta w ofercie.  
6. Zamknij stronę.
7. W okienku akcji kliknij pozycję Monituj.
8. Kliknij przycisk Potwierdź.
9. W polu Przyczyna wprowadź lub wybierz wartość.
10. Kliknij przycisk OK.
11. W okienku akcji kliknij pozycję Ogólne.
12. Kliknij pozycję Zamówienia sprzedaży.
13. Zamknij stronę.

