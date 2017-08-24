--- 
title: "Generowanie dokumentów elektronicznych dla płatności przy użyciu konfiguracji formatu na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może używać nowej konfiguracji formatu raportowania elektronicznego (ER) do generowania dokumentów elektronicznych w celu przetwarzania płatności."
author: NickSelin
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 95da806cc2844dc946e809f1afecef25a7b520e5
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="generate-electronic-documents-for-payments-using-a-format-configuration-for-electronic-reporting-er"></a>Generowanie dokumentów elektronicznych dla płatności przy użyciu konfiguracji formatu na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może używać nowej konfiguracji formatu raportowania elektronicznego (ER) do generowania dokumentów elektronicznych w celu przetwarzania płatności. Kroki można wykonać na danych przykładowej firmy GBSI.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie konfiguracji z formatem dokumentu płatności”.


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>Zmiana konfiguracji metody płatności elektronicznych
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Metody płatności.
2. W razie potrzeby przełącz sekcję Format pliku, aby ją rozwinąć.
3. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Metoda płatności z wartością „Elektroniczne”.
4. Kliknij przycisk Edytuj.
5. W polu Ogólne raportowanie elektroniczne wybierz opcję Tak.
    * Wybierz opcję Tak, aby używać wzorca ogólnego raportowania elektronicznego do generowania plików płatności.  
6. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Wybierz konfigurację formatu BACS (fikcyjny brytyjski).
8. Kliknij przycisk Zapisz.
9. Zamknij stronę.

## <a name="test-the-format-of-generated-payment-files"></a>Testowanie formatu wygenerowanych plików płatności
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.
2. Kliknij przycisk Nowy.
3. Na liście oznacz wybrany wiersz.
4. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz opcję VendPay.  
6. Kliknij przycisk Zapisz.
7. Kliknij przycisk Wiersze.
8. W polu Firma wpisz wartość „DEMF”.
    * DEMF  
9. W polu Konto podaj wartości „DE-01001”.
    * DE - 01001  
10. W polu Opis wpisz „Płatność”.
    * Płatność  
11. W polu Debet wpisz liczbę.
    * 1000  
12. Kliknij kartę Płatność.
13. W polu Metoda płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
14. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz wartość Elektroniczne.  
15. Na liście kliknij łącze w wybranym wierszu.
16. Kliknij przycisk Zapisz.
17. Kliknij opcję Generuj płatności.
18. W polu Metoda płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
19. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz wartość Elektroniczne.  
20. Na liście kliknij łącze w wybranym wierszu.
    * Zaznacz wartość Elektroniczne.  
21. W polu Nazwa pliku wpisz wartość.
    * Na przykład wpisz „płatności”.  
22. W polu Konto bankowe kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
23. Na liście kliknij łącze w wybranym wierszu.
    * Zaznacz wartość GBSI OPER.  
24. Kliknij przycisk OK.
25. Kliknij przycisk OK.
    * Przeanalizuj utworzony plik płatności w formacie XML. Porównaj go z zaprojektowanym układem dokumentu i zdefiniowanymi atrybutami transakcji płatności.  


