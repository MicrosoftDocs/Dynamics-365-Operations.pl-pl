---
title: Tworzenie i edytowanie ofert sprzedaży
description: Ta procedura przedstawia sposób tworzenia i aktualizowania oferty sprzedaży.
author: omulvad
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable, CustQuotationConfirmationJournal, CustQuotationJournal, CustSalesLines, SalesQuotationCopying, SalesQuotationDeleteQuotations, SalesQuotationListPagePreviewPane, SalesQuotationTypeGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb9c0b3cfa34fc61bb568b7d2677647cef495d81c7bfc9521dba0fd5e43482e5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738874"
---
# <a name="create-and-edit-sales-quotations"></a>Tworzenie i edytowanie ofert sprzedaży

[!include [banner](../../includes/banner.md)]

Ta procedura przedstawia sposób tworzenia i aktualizowania oferty sprzedaży. Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF.


## <a name="create-a-sales-quotation"></a>Tworzenie oferty sprzedaży
1. Przejdź do **Okienko nawigacyji > Moduły > Sprzedaż i marketing > Oferty sprzedaży >Wszystkie oferty**.
2. Kliknij przycisk **Nowy**.
3. W polu **Typ konta** wybierz opcję „Prospekt”.
4. W polu **Prospekt** wprowadź lub wybierz wartość.
5. Rozwiń sekcję **Ogólne**. Ponieważ wybrano opcję utworzenia oferty sprzedaży z poziomu obszaru Sprzedaż i marketing, typ jest automatycznie ustawiany na „Oferta sprzedaży”. Aby utworzyć ofertę dla projektu, trzeba przejść do niego z modułu **Zarządzanie projektami i ich księgowanie**.
6. Kliknij przycisk **OK**. Pola i akcje w wierszach oferty są bardzo podobne do używanych w wierszach zamówienia sprzedaży.   Tak jak zamówienia sprzedaży, oferty można tworzyć dla określonego towaru, a gdy towar jest nieznany lub nie istnieje w momencie utworzenia oferty, można je tworzyć dla kategorii sprzedaży.     
7. W polu **Towar** wprowadź lub wybierz wartość.
8. W polu **Oddział** wpisz wartość.
9. W polu **Ilość** wpisz liczbę. Jeśli istnieją ważne umowy handlowe na towar wybrany w wierszu, odnośna cena i rabaty zostaną automatycznie skopiowane do wiersza oferty. Upewnij się, że pole Cena jednostkowa zawiera wartość. Jeśli chcesz, można również wprowadzić wartości rabatów. 
10. Kliknij przycisk **Zapisz**.
11. W **okienku akcji** kliknij opcję **Oferta sprzedaży**.
12. Kliknij przycisk **Suma**.
13. Kliknij przycisk **OK**.
14. Zaznacz wybrany wiersz oferty sprzedaży.
15. W **okienku akcji** kliknij pozycję **Oferta**.
16. Kliknij **Symulacja ceny**.
    - Na stronie **Uruchom symulację ceny** można wypróbować korygowanie spodziewanych przychodów lub rentowności wynikającej z oferty na podstawie żądanej ceny jednostkowej, kwoty rabatu, procentu rabatu, łącznej kwoty, marży lub współczynnika marży. Po uzyskaniu zadowalających docelowych wartości zastosuj sugestię do wiersza oferty, a jego pola związane z ceną zostaną odpowiednio zaktualizowane.  
    - Można utworzyć tyle symulacji cen, ile potrzeba. Po kliknięciu przycisku **Nowy** warunki cenowe z bieżącego wiersza oferty są kopiowane do strony. Następnie można zmodyfikować wartości w polach dotyczących ceny na docelowe. Zmiana w jednym z pól spowoduje uruchomienie ponownego obliczania we wszystkich pozostałych polach. Aby system obliczał marżę sprzedaży i współczynnik marży, musi być znany koszt jednostkowy produktu. Karta Symulowane ceny zawiera szczegółowy widok oryginalnych cen, proponowanych zmian oraz ich wpływu na sumy w ofercie. Co do zasady zastosowanie do wiersza oferty symulacji ustawiającej nową kwotę powoduje, że system wykuje ponowne obliczenie i wprowadza nową wartość w polu Cena jednostkowa. Jeśli symulacja opiera się na nowej marży lub nowym współczynniku marży, jest aktualizowane tylko pole Kwota netto, a pole Cena jednostkowa pozostaje puste. W obu przypadkach wszelkie rabaty, które istniały w wierszu oferty przed symulacją, zostaną usunięte.
17. W **okienku akcji** kliknij pozycję **Oferta**.
18. Kliknij przycisk **Wyślij ofertę**.
19. W polu **Drukowanie** oferty zaznacz opcję „Tak”.
20. Kliknij przycisk **OK**. Generowanie raportu może nieco potrwać. Przez ten czas nie zamykaj strony.

## <a name="update-a-sales-quotation"></a>Aktualizowanie oferty sprzedaży
1. Przejdź do **Okienko nawigacyji > Moduły > Sprzedaż i marketing > Oferty sprzedaży >Wszystkie oferty**.
2. W **okienku akcji** kliknij pozycję **Monituj**.
3. Kliknij opcję **Konwertuj na odbiorcę**.
4. W polu **Konto odbiorcy** wpisz wartość.
5. Kliknij przycisk **Sprawdź**. Upewnij się, że zostanie wyświetlony komunikat, iż wpisany numer konta jest wolny i można go użyć.  
6. Kliknij przycisk **OK**. System utworzył nowe konto odbiorcy dla potencjalnego klienta w ofercie.  
7. Zamknij stronę.
8. W **okienku akcji** kliknij pozycję **Monituj**.
9. Kliknij przycisk **Potwierdź**.
10. W polu **Przyczyna** wprowadź lub wybierz wartość.
11. Kliknij przycisk **OK**.
12. W **okienku akcji** kliknij pozycję **Ogólne**.
13. Kliknij opcję **Zamówienia sprzedaży**.
14. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]