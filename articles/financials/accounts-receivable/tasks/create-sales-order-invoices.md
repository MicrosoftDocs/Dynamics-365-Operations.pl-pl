--- 
title: "Tworzenie faktur zamówienia sprzedaży"
description: "W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b72d5b283f9401d358ee68f4650c486ebb2fd7d
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-sales-order-invoices"></a>Tworzenie faktur zamówienia sprzedaży

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach opisano fakturowanie zamówienia sprzedaży, łącznie ze scalaniem faktur i przetwarzaniem wsadowym. Ta procedura wykorzystuje firmę demonstracyjną USMF.


## <a name="create-an-invoice-from-a-sales-order"></a>Tworzenie faktury na podstawie zamówienia sprzedaży
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Niezafakturowane zamówienia sprzedaży o stanie Wysłano.
2. Zaznacz zamówienie sprzedaży na liście. 
3. W okienku akcji kliknij pozycję Faktura.
4. Kliknij opcję Faktura.
    * Należy zauważyć, że z tym zamówieniem sprzedaży jest skojarzonych wiele dokumentów dostawy. Zamiast numeru dokumentu dostawy będzie wyświetlane tylko słowo <multiple>.  
5. Rozwiń sekcję Parametry.
    * W celu zaksięgowania faktury w ustawieniu Księgowanie musi być ustawiona wartość Tak. Można także wyłączyć księgowania i tylko wydrukować fakturę. Jednak ten sam efekt można osiągnąć przez utworzenie faktury pro forma zamiast regularnej faktury.  
    * Ta opcja jest używana do zadań wsadowych. Kwerenda jest uruchamiana po uruchomieniu zadania wsadowego.    
6. W polu Drukuj wybierz opcję „Po”.
7. W obszarze Drukuj fakturę zaznacz opcję Tak.
    * Funkcja Zarządzanie drukowaniem może wydrukować wiele kopii faktury i również wysłać ją pocztą e-mail jako plik PDF.  
8. W polu Drukuj opłaty zaznacz opcję „Podsumowanie”.
9. W polu Sprawdzanie limitu kredytu zaznacz opcję „Saldo”.
10. Kliknij przycisk Anuluj.

## <a name="combine-orders-into-a-single-invoice"></a>Łączenie zamówień w jedną fakturę
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.
2. Odszukaj odbiorcę, który ma otwartych wiele faktur.
3. Wybierz otwarte zamówienie sprzedaży.
4. Zaznacz inne otwarte zamówienie sprzedaży tego samego odbiorcy.
5. W okienku akcji kliknij pozycję Faktura.
6. Kliknij opcję Faktura.
7. Rozwiń sekcję Parametry.
8. W polu Ilość zaznacz opcję Wszystko.
    * Należy zwrócić uwagę, że w sekcji Przegląd widać dwie faktury. Scalmy je teraz w jedną fakturę.  
9. W pola Aktualizacja zbiorcza dla zaznacz opcję „Konto płatnika”.
10. Kliknij przycisk Rozmieść, aby scalić zamówienia sprzedaży w jedną fakturę.
    * Dwa zamówienia sprzedaży są teraz scalone w jedną fakturę.   
11. Kliknij przycisk Anuluj.
12. Kliknij przycisk Tak.

## <a name="post-invoices-in-a-batch"></a>Zbiorcze księgowanie faktur
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Fakturowanie zbiorcze > Faktura.
2. Kliknij opcję Wybierz.
3. Kliknij przycisk OK.
4. Kliknij przycisk Zadanie wsadowe.
5. Kliknij przycisk Tak, aby włączyć przetwarzanie wsadowe.
6. Kliknij przycisk Cykl.
7. Wybierz dni
8. Kliknij przycisk OK.
9. Kliknij przycisk OK.
10. Kliknij przycisk Anuluj.
11. Kliknij przycisk Tak.


