--- 
title: Tworzenie konfiguracji formatu na potrzeby raportowania elektronicznego (ER)
description: "W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć konfiguracji formatu dla raportowania elektronicznego (ER)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: c46b222cb12d0432609c47f89afc522e02c41ab6
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-format-configuration-for-electronic-reporting-er"></a>Tworzenie konfiguracji formatu na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć konfiguracji formatu dla raportowania elektronicznego (ER). Ta konfiguracja formatu określi format dokumentów elektronicznych, które będą używane do przetwarzania płatności. W tym przykładzie utworzysz konfigurację formatu dla przykładowej firmy Litware, Inc. W celu wykonania tych kroków należy najpierw wykonać procedurę „Mapowanie modelu na wybrane źródła danych”.


## <a name="create-a-new-format-configuration"></a>Utwórz nową konfigurację formatu.
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Konfiguracje raportowania.
3. W drzewie zaznacz element „Płatności (model uproszczony)”.
4. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
5. W polu Nowy wpisz „Format oparty na modelu danych PaymentModel”.
6. W polu Nazwa wpisz „BACS (fikcyjny brytyjski)”.
    * BACS (fikcyjny brytyjski)  
7. W polu Opis wpisz „Format płatności dla dostawcy BACS (fikcyjny brytyjski)”.
    * Format płatności dla dostawcy BACS (fikcyjny brytyjski)  
    * Aktywny dostawca konfiguracji jest automatycznie umieszczany w tym miejscu. Ten dostawca będzie mógł obsługiwać tę konfigurację. Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.  
    * Można zdefiniować określony format dokumentu elektronicznego. Pozostaw to pole puste, aby wybrać format w czasie wykonywania.  
8. W polu Definicja modelu danych wprowadź lub wybierz wartość.
9. Kliknij przycisk Utwórz konfigurację.
    * Utworzono nową konfigurację. Wersja robocza może służyć do przechowywania formatu projektu w celu zarządzania dokumentami elektronicznymi.  

## <a name="design-format-of-electronic-document"></a>Zaprojektuj format dokumentu elektronicznego.
1. Kliknij przycisk Konstruktor.
2. Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.
3. W drzewie zaznacz element „Wspólne\Plik”.
4. W polu Nazwa wpisz „Xml”.
    * XML  
5. W polu Kodowanie wpisz „UTF-8”.
    * UTF-8  
6. Kliknij przycisk OK.
7. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
8. W drzewie zaznacz element „XML\Element”.
9. W polu Nazwa wpisz „Komunikat”.
    * Wiadomość  
10. Kliknij przycisk OK.
11. W drzewie zaznacz element „Xml\Komunikat”.
12. Kliknij opcję Dodaj element.
13. W polu Nazwa wpisz „ProcessingDate”.
    * ProcessingDate  
14. Kliknij przycisk OK.
15. Kliknij opcję Dodaj element.
16. W polu Nazwa wpisz „MessageId”.
    * MessageId  
17. Kliknij przycisk OK.
18. Kliknij opcję Dodaj element.
19. W polu Nazwa wpisz „Płatności”.
    * Płatności  
20. Kliknij przycisk OK.
21. W drzewie zaznacz element „Xml\Komunikat\Płatności”.
22. Kliknij opcję Dodaj element.
23. W polu Nazwa wpisz „Towar”.
    * Element  
24. Kliknij przycisk OK.
25. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar”.
26. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
27. W drzewie zaznacz element „XML\Atrybut”.
28. W polu Nazwa wpisz „Identyfikator”.
    * Identyfikator  
29. Kliknij przycisk OK.
30. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
31. W drzewie zaznacz element „XML\Element”.
32. W polu Nazwa wpisz „Dostawca”.
    * Dostawca  
33. Kliknij przycisk OK.
34. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca”.
35. Kliknij opcję Dodaj element.
36. W polu Nazwa wpisz „Nazwa”.
    * Nazwisko  
37. Kliknij przycisk OK.
38. Kliknij opcję Dodaj element.
39. W polu Nazwa wpisz „Bank”.
    * Bank  
40. Kliknij przycisk OK.
41. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank”.
42. Kliknij opcję Dodaj element.
43. W polu Nazwa wpisz „RoutingNumber”.
    * RoutingNumber  
44. Kliknij przycisk OK.
45. Kliknij opcję Dodaj element.
46. W polu Nazwa wpisz „AccountNumber”.
    * AccountNumber  
47. Kliknij przycisk OK.
48. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca”.
49. Kliknij opcję Kopiuj.
50. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar”.
51. Kliknij opcję Wklej.
52. W polu Nazwa wpisz „Płatnik”.
    * Płatnik  
53. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar”.
54. Kliknij opcję Dodaj element.
55. W polu Nazwa wpisz „Waluta”.
    * Waluta  
56. Kliknij przycisk OK.
57. Kliknij opcję Dodaj element.
58. W polu Nazwa wpisz „Opis”.
    * opis  
59. Kliknij przycisk OK.
60. Kliknij opcję Dodaj element.
61. W polu Nazwa wpisz „TransDate”.
    * TransDate  
62. Kliknij przycisk OK.
63. Kliknij opcję Dodaj element.
64. W polu Nazwa wpisz „Kwota”.
    * Ilość  
65. Kliknij przycisk OK.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Przygotuj składniki formatu w celu zmapowania na elementy modelu danych.
1. W drzewie zaznacz element „Xml\Komunikat\ProcessingDate”.
2. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
3. W drzewie zaznacz element „Tekst\DateTime”.
4. W polu Format wpisz „rrrr-MM-dd”.
    * rrrr-MM-dd  
5. Kliknij przycisk OK.
6. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\TransDate”.
7. Kliknij opcję Dodaj datę/godzinę.
8. W polu Format wpisz „rrrr-MM-dd”.
    * rrrr-MM-dd  
9. W polu Typ daty/godziny wybierz opcję „Data”.
10. Kliknij przycisk OK.
11. W drzewie zaznacz element „Xml\Komunikat\MessageId”.
12. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
13. W drzewie zaznacz element „Tekst\Ciąg”.
14. Kliknij przycisk OK.
15. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa”.
16. Kliknij opcję Dodaj ciąg.
17. Kliknij przycisk OK.
18. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\RoutingNumber”.
19. Kliknij opcję Dodaj ciąg.
20. Kliknij przycisk OK.
21. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\AccountNumber”.
22. Kliknij opcję Dodaj ciąg.
23. Kliknij przycisk OK.
24. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Nazwa”.
25. Kliknij opcję Dodaj ciąg.
26. Kliknij przycisk OK.
27. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Bank\RoutingNumber”.
28. Kliknij opcję Dodaj ciąg.
29. Kliknij przycisk OK.
30. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Bank\AccountNumber”.
31. Kliknij opcję Dodaj ciąg.
32. Kliknij przycisk OK.
33. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Waluta”.
34. Kliknij opcję Dodaj ciąg.
35. Kliknij przycisk OK.
36. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Opis”.
37. Kliknij opcję Dodaj ciąg.
38. Kliknij przycisk OK.
39. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Kwota”.
40. Kliknij opcję Dodaj ciąg.
41. Kliknij przycisk OK.
42. Kliknij przycisk Zapisz.
43. Zamknij stronę.


