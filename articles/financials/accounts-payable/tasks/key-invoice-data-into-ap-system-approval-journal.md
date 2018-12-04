--- 
title: "Wpisywanie danych faktury w systemie AP za pomocą arkusza zatwierdzania"
description: "W tym przewodniku po zadaniach pokazano sposób używania rejestru faktur do tworzenia faktur, a następnie używania arkusza zatwierdzania do aktualizowania kont wydatków."
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 048eda77064b6aa3f666e998a8e551d2f7adc385
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="key-invoice-data-into-ap-system-using-approval-journal"></a>Wpisywanie danych faktury w systemie AP za pomocą arkusza zatwierdzania

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach pokazano sposób używania rejestru faktur do tworzenia faktur, a następnie używania arkusza zatwierdzania do aktualizowania kont wydatków.


## <a name="create-and-post-and-invoice"></a>Tworzenie i księgowanie faktury
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Faktury > Rejestr faktur.
2. Kliknij przycisk Nowy.
3. Wybierz nazwę rejestru faktur, którego chcesz używać.
4. Na liście kliknij łącze w wybranym wierszu.
5. Kliknij przycisk Wiersze, aby otworzyć rejestr i wprowadzić wiersze wydatków.
6. Wybierz dostawcę. Na przykład wprowadź lub wybierz dostawcę US-104.
7. W polu Faktura wpisz wartość.
8. W polu Opis wpisz wartość.
9. W polu Kredyt wpisz liczbę.
10. W polu Zatwierdzone przez kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. Zaznacz osobę zatwierdzającą i kliknij przycisk Wybierz, aby ją wybrać.
12. Kliknij przycisk Księguj.
13. Zamknij stronę.
14. Zamknij stronę.

## <a name="approve-an-invoice"></a>Zatwierdzanie faktury
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Faktury > Zatwierdzenie faktury.
2. Kliknij przycisk Nowy.
3. Wybierz nazwę arkusza zatwierdzania faktur, którego chcesz używać.
4. Na liście kliknij łącze w wybranym wierszu.
5. Kliknij przycisk Wiersze, a zostanie wyświetlona strona, gdzie będzie można wybrać faktury do zatwierdzenia.
6. Kliknij przycisk Znajdź załączniki, aby wyświetlić wszystkie faktury gotowe do zatwierdzenia.
7. Oznacz utworzoną przez siebie fakturę.
8. Kliknij opcję Wybierz.
    * Załączniki wybrane powyżej zostaną po zaznaczeniu przeniesione do tej listy.  
9. Kliknij przycisk OK.
10. Kliknij pole Numer konta, aby dodać konto wydatków do faktury.
11. Wprowadź numer konta i opuść to pole. Na przykład wpisz 600120.
12. Kliknij przycisk Księguj.
13. Kliknij opcję Załącznik, aby wyświetlić zapisy, które zostały zaksięgowane.
    * Konto faktur oczekujących na zatwierdzenie zostanie wycofane i zastąpione kontem wydatków rzeczywistych.  


