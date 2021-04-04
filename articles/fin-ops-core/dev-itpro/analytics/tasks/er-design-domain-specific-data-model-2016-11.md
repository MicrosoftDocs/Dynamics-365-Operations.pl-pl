---
title: ER Projektowanie modelu danych dla konkretnej domeny
description: W tym temacie opisano sposób utworzenia nowej konfiguracji raportowania elektronicznego (ER) zawierającej model danych na potrzeby dokumentów elektronicznych płatności.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 284fad8b6646c35217789cc9936cbe9fe75a03d0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567816"
---
# <a name="er-design-domain-specific-data-model"></a>ER Projektowanie modelu danych dla konkretnej domeny

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą dane dokumentów płatności elektronicznych. Ten model danych będzie później używany jako źródło danych podczas tworzenia formatu dokumentów płatności.

W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy. Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.

    Wybierz dostawcę konfiguracji przykładowej firmy „Litware, Inc.”. Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.  
    
2. Kliknij opcję Konfiguracje raportowania.

    Utworzysz konfigurację, która zawiera model danych dla dokumentów płatności elektronicznych. Ten model danych będzie później używany jako źródło danych podczas tworzenia formatu dokumentów płatności.  

## <a name="create-a-new-data-model-configuration"></a>Tworzenie nowej konfiguracji modelu danych
1. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
2. W polu Nazwa wpisz „Płatności (model uproszczony)”.
3. W polu Opis wpisz „Konfiguracja modelu płatności”.

    Aktywny dostawca konfiguracji jest automatycznie umieszczany w tym miejscu. Ten dostawca będzie mógł obsługiwać tę konfigurację. Inni dostawcy mogą używać tej konfiguracji, ale nie będą mogli nią zarządzać.  

4. Kliknij przycisk „Utwórz konfigurację”, aby dokończyć zadanie tworzenia konfiguracji.

## <a name="create-a-data-model"></a>Tworzenie modelu danych
Tworzysz nowy model danych dla wybranej konfiguracji. Ta wersja konfiguracji będzie miała stan Wersja robocza.  
1. Kliknij przycisk Konstruktor.

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a>Definiowanie struktury strony uczestniczącej w procesie płatności
1. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
2. W polu Nazwa wpisz „Strona”.
3. Kliknij przycisk Dodaj.
4. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
5. W polu Nazwa wpisz „Nazwa”.
6. W polu Typ elementu wybierz opcję „Ciąg”.
7. Kliknij przycisk Dodaj.
8. W polu Znajdź wpisz „Strona”.
9. Kliknij opcję Znajdź poprzednie.

## <a name="define-the-bank-structure-for-this-model"></a>Definiowanie struktury banku dla tego modelu
1. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
2. W polu Nazwa wpisz „Agent”.
3. W polu Typ elementu wybierz opcję „Rekord”.
4. Kliknij przycisk Dodaj.
5. W polu Opis wpisz „Instytucja finansowa (np. bank) obsługująca konto strony (dłużnika/wierzyciela).”.

    Instytucja finansowa (np. bank) obsługująca konto strony (dłużnika/wierzyciela).  

6. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
7. W polu Nazwa wpisz „Nazwa”. 
8. W polu Typ elementu wybierz opcję „Ciąg”.
9. Kliknij przycisk Dodaj.
10. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
11. W polu Nazwa wpisz „SWIFT”.
12. Kliknij przycisk Dodaj.
13. W polu Opis wpisz „Kod identyfikacyjny banku”. 
14. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
15. W polu Nazwa wpisz „RoutingNumber”.
16. Kliknij przycisk Dodaj.
17. W polu Opis wpisz „Kod banku”.
18. Kliknij opcję Znajdź poprzednie.

## <a name="define-the-bank-account-structure-for-this-model"></a>Definiowanie struktury konta banku dla tego modelu
1. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
2. W polu Nazwa wpisz „Konto”. 
3. W polu Typ elementu wybierz opcję „Rekord”.
4. Kliknij przycisk Dodaj.
5. W polu Opis wpisz „Identyfikator konta strony w instytucji finansowej (na przykład w banku).”.

    Identyfikator konta strony w instytucji finansowej (na przykład w banku).  

6. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
7. W polu Nazwa wpisz „Waluta”. 
8. W polu Typ elementu wybierz opcję „Ciąg”.
9. Kliknij przycisk Dodaj.
10. W polu Opis wpisz „Kod waluty”.
11. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
12. W polu Nazwa wpisz „Numer”. 
13. Kliknij przycisk Dodaj.
14. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
15. W polu Nazwa wpisz „IBAN”. 
16. Kliknij przycisk Dodaj.
17. W polu Opis wpisz „Międzynarodowy numer konta bankowego”.

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a>Definiowanie struktury komunikatu płatności dla płatności poleceniem przelewu
1. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
2. W polu Nowy węzeł jako wpisz „Element główny modelu”.
3. W polu Nazwa wpisz „CustomerCreditTransferInitiation”.
4. Kliknij przycisk Dodaj.
5. W polu Znajdź wpisz „CustomerCreditTransferInitiation”. 
6. Kliknij opcję Znajdź poprzednie.
7. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
8. W polu Nazwa wpisz „MessageIdentification”. 
9. Kliknij przycisk Dodaj.
10. W polu Opis wpisz „Odwołanie bezpośrednie przypisane przez stronę zlecającą (i wysłane do następnej strony) w celu identyfikacji komunikatu.”.

    Odwołanie bezpośrednie przypisane przez stronę zlecającą (i wysłane do następnej strony) w celu identyfikacji komunikatu.  

11. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
12. W polu Nazwa wpisz „ProcessingDateTime”.
13. W polu Typ elementu wybierz opcję „DateTime”.
14. Kliknij przycisk Dodaj.
15. W polu Opis wpisz „Data i godzina utworzenia komunikatu płatności.”. 
16. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.

    Definiowanie struktury transakcji płatności dla tego modelu.  

17. W polu Nazwa wpisz „Płatności”.
18. W polu Typ elementu wybierz opcję „Lista rekordów”.
19. Kliknij przycisk Dodaj.
20. W polu Opis wpisz „Wiersze płatności w bieżącym komunikacie”.
21. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
22. W polu Nazwa wpisz „Wierzyciel”. 
23. W polu Typ elementu wybierz opcję „Rekord”.
24. Kliknij przycisk Dodaj.
25. W polu Opis wpisz „Strona, do której należy przesłać kwotę pieniężną.”. 
26. Kliknij opcję Przełącz odwołanie do elementu.
27. W polu Znajdź wpisz „Strona”.
28. Kliknij przycisk Znajdź następny.
29. Kliknij przycisk OK.
30. W polu Znajdź wpisz „Płatności”.
31. Kliknij przycisk Znajdź następny.
32. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
33. W polu Nazwa wpisz „Dłużnik”. 
34. Kliknij przycisk Dodaj.
35. W polu Opis wpisz „Strona będąca dłużna kwotę pieniężną (ostatecznemu) wierzycielowi.”.
36. Kliknij opcję Przełącz odwołanie do elementu.
37. W polu Znajdź wpisz „Strona”.
38. Kliknij przycisk Znajdź następny.
39. Kliknij przycisk OK.
40. Kliknij przycisk Znajdź następny.
41. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
42. W polu Nazwa wpisz „Opis”.
43. W polu Typ elementu wybierz opcję „Ciąg”.
44. Kliknij przycisk Dodaj.
45. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
46. W polu Nazwa wpisz „Waluta”.
47. Kliknij przycisk Dodaj.
48. W polu Opis wpisz „Kod waluty”.
49. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
50. W polu Nazwa wpisz „TransactionDate”. 
51. W polu Typ elementu wybierz opcję „Data”.
52. Kliknij przycisk Dodaj.
53. W polu Opis wpisz „Data transakcji”. 
54. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
55. W polu Nazwa wpisz „InstructedAmount”.  
56. W polu Typ elementu wybierz opcję „Liczba rzeczywista”.
57. Kliknij przycisk Dodaj.
58. W polu Opis wpisz „Kwota pieniężna do przekazania między dłużnikiem a wierzycielem przed potrąceniem opłat. Kwota powinna być wyrażona w walucie podanej przez stronę inicjującą.”.

    Kwota pieniężna do przekazania między dłużnikiem a wierzycielem przed potrąceniem opłat. Kwota powinna być wyrażona w walucie podanej przez stronę inicjującą.  

59. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
60. W polu Nazwa wpisz „End2EndID”. 
61. W polu Typ elementu wybierz opcję „Ciąg”.
62. Kliknij przycisk Dodaj.
63. W polu Opis wpisz „Unikatowy identyfikator przypisywany przez stronę inicjującą. Identyfikator jest przekazywany bez zmian w całym łańcuchu operacji.”. 
64. W polu Nazwa wpisz „PaymentModel”.

    Nazwa PaymentModel jest dopasowana do wstępnie zdefiniowanych interfejsów formularzy płatności.  

65. Kliknij przycisk Zapisz.
66. Zamknij stronę.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]