---
title: ER Mapowanie składników utworzonego formatu na elementy modelu danych (listopad 2016)
description: W poniższej procedurze pokazano, jak użytkownik posiadający rolę Administrator systemu lub Deweloper raportowania elektronicznego może mapować elementy modelu danych na składniki utworzonej konfiguracji raportowania elektronicznego (ER), która definiuje format dokumentu elektronicznego dla domeny biznesowej płatności.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a24ef0e091379f14a163a6385be988143a1ec608
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544341"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a>ER Mapowanie składników utworzonego formatu na elementy modelu danych (listopad 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższej procedurze pokazano, jak użytkownik posiadający rolę Administrator systemu lub Deweloper raportowania elektronicznego może mapować elementy modelu danych na składniki utworzonej konfiguracji raportowania elektronicznego (ER), która definiuje format dokumentu elektronicznego dla domeny biznesowej płatności. Ten format będzie używany później do generowania dokumentów elektronicznych przeznaczonych do przetwarzania płatności. W tym przykładzie utworzysz konfigurację formatu dla przykładowej firmy „Litware, Inc.”. Podane kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy. Aby wykonać te kroki, należy najpierw wykonać kroki przewodnika po zadaniu „Tworzenie konfiguracji formatu”.


## <a name="select-a-format-configuration"></a>Wybieranie konfiguracji formatu
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Konfiguracje raportowania.
3. W drzewie rozwiń węzeł „Płatności (model uproszczony)”.
4. W drzewie zaznacz element „Płatności (model uproszczony)\BACS (fikcyjny brytyjski)”.
5. Kliknij przycisk Konstruktor.

## <a name="map-format-components-to-data-model-elements"></a>Zmapuj składniki formatu na elementy modelu danych.
1. Kliknij przycisk Rozwiń/zwiń.
2. Kliknij kartę Mapowanie.
3. W drzewie rozwiń model„”
4. W drzewie zaznacz element „Xml\Komunikat\ProcessingDate\DateTime”.
5. W drzewie zaznacz element „model\ProcessingDateTime”.
6. Kliknij opcję Powiąż.
7. W drzewie zaznacz element „Xml\Komunikat\MessageId\Ciąg”.
8. W drzewie zaznacz element „model\MessageIdentification”.
9. Kliknij opcję Powiąż.
10. W drzewie rozwiń węzeł „model\Płatności”.
11. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Kwota\Ciąg”.
12. W drzewie zaznacz element „model\Płatności\InstructedAmount”.
13. Kliknij opcję Powiąż.
14. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\TransDate\DateTime”.
15. W drzewie zaznacz element „model\Płatności\TransactionDate”.
16. Kliknij opcję Powiąż.
17. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Opis\Ciąg”.
18. W drzewie zaznacz element „model\Płatności\Opis”.
19. Kliknij opcję Powiąż.
20. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Waluta\Ciąg”.
21. W drzewie zaznacz element „model\Płatności\Waluta”.
22. Kliknij opcję Powiąż.
23. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Identyfikator”.
24. W drzewie zaznacz element „model\Płatności\End2EndID”.
25. Kliknij opcję Powiąż.
26. W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.
27. W drzewie rozwiń „model\Płatności\Konto wierzyciela".
28. W drzewie rozwiń „model\Płatności\Wierzyciel\Agent".
29. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Nazwa\Ciąg”.
30. W drzewie zaznacz element „model\Płatności\Wierzyciel\Nazwa”.
31. Kliknij opcję Powiąż.
32. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\RoutingNumber\Ciąg”.
33. W drzewie zaznacz element „model\Płatności\Wierzyciel\Agent\RoutingNumber”.
34. Kliknij opcję Powiąż.
35. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Dostawca\Bank\AccountNumber\Ciąg”.
36. W drzewie zaznacz element „model\Płatności\Wierzyciel\Konto\Numer”.
37. Kliknij opcję Powiąż.
38. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Nazwa\Ciąg”.
39. W drzewie rozwiń węzeł „model\Płatności\Dłużnik”.
40. W drzewie rozwiń „model\Płatności\Dłużnik\Konto".
41. W drzewie rozwiń „model\Płatności\Dłużnik\Agent".
42. W drzewie zaznacz element „model\Płatności\Dłużnik\Nazwa”.
43. Kliknij opcję Powiąż.
44. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Bank\RoutingNumber\Ciąg”.
45. W drzewie zaznacz element „model\Płatności\Dłużnik\Agent\RoutingNumber”.
46. Kliknij opcję Powiąż.
47. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar\Płatnik\Bank\AccountNumber\Ciąg”.
48. W drzewie zaznacz element „model\Płatności\Dłużnik\Konto\Numer”.
49. Kliknij opcję Powiąż.
50. W drzewie zaznacz element „Xml\Komunikat\Płatności\Towar”.
51. W drzewie zaznacz element „model\Płatności”.
52. Kliknij opcję Powiąż.
53. Kliknij przycisk Zapisz.

## <a name="validate-format-mapping"></a>Sprawdzanie poprawności mapowania formatu.
1. Kliknij przycisk Sprawdź poprawność.
    * Sprawdź poprawność nowego mapowania, aby się upewnić, że wszystkie powiązania są w porządku.  
2. Zamknij stronę.

## <a name="change-status-of-the-current-version-of-format-configuration"></a>Zmień stan bieżącej wersji konfiguracji formatu.
    * W następnych krokach zmienisz stan konfiguracji formatu z Wersja robocza na Zakończony, aby udostępnić go dla operacji generowania dokumentu płatniczego.  
1. Kliknij przycisk Zmień stan.
2. Kliknij przycisk Wykonaj.
3. Wypełnij pole Opis.
    * Na przykład „wersja 1”.  
4. Kliknij przycisk OK.
5. Wybierz ukończoną wersję bieżącej konfiguracji.
    * Należy zauważyć, że konfiguracja została zapisana jako ukończona wersja 1.1. To jest wersja 1 formatu, który jest oparty na wersji 1 modelu danych.  

## <a name="define-effective-date-for-completed-version-of-format"></a>Określ datę wejścia w życie ukończonej wersji formatu.
    * Każdą wersję formatu można skonfigurować jako dostępną do użycia począwszy od określonej daty. Kiedy więcej niż jedna wersja formatu jest aktywna w określonym dniu, do użycia zostanie wybrany najnowszy forma (na podstawie numeru wersji). Do wyboru odpowiedniej wersji jest używana wartość daty sesji.  

## <a name="restrict-access-to-created-format-from-companies"></a>Ograniczanie dostępu do utworzonego formatu z firm
1. Rozwiń sekcję Kody ISO krajów/regionów.
    * Można ograniczyć dostęp do każdego formatu, identyfikując określone kraje/regiony, w których format się stosuje. Gdy lista krajów/regionów dla określonego formatu jest pusta, tego formatu można używać dla dowolnej firmy. Jeśli do listy krajów/regionów zostaną wstawione jakieś kody ISO krajów/regionów, formatu można używać tylko w firmach, których adres podstawowy mieści się w danym kraju/regionie.  

