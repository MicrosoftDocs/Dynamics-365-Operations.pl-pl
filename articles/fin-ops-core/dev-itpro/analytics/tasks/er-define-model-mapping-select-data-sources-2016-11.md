---
title: Definiowanie mapowań modeli raportowanie elektronicznego i wybieranie dla nich źródeł danych
description: W tym temacie wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może wybrać źródła danych modelu danych raportowania elektronicznego.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7b5f291372bc459bc1979dca4a95cfafb39e2ad9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567301"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a>Definiowanie mapowań modeli raportowanie elektronicznego i wybieranie dla nich źródeł danych

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może wybrać źródła danych modelu danych raportowania elektronicznego (ER). Źródła danych będą kojarzone z poszczególnymi składnikami wybranego modelu danych podczas projektowania oraz wypełnią model danych danymi biznesowymi w czasie wykonywania. W tym przykładzie wybierzesz źródła danych dla istniejącego modelu danych, który został utworzony dla przykładowej firmy Litware, Inc. Aby wykonać te kroki, należy najpierw wykonać procedurę „Tworzenie nowego modelu danych”.


## <a name="open-the-electronic-reporting-configurations-tree"></a>Otwieranie drzewa konfiguracji raportowania elektronicznego
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Konfiguracje raportowania.

## <a name="insert-a-new-model-mapping"></a>Wstaw nowe mapowanie modelu.
1. W drzewie zaznacz element „Płatności (model uproszczony)”.
2. Kliknij przycisk Konstruktor.
3. Kliknij opcję Mapuj model na źródło danych.
4. Kliknij przycisk Nowy.
    * Spowoduje to utworzenie nowego rekordu, który przyporządkuje model danych do źródła danych. W tym przykładzie modelu danych zostanie zmapowany do źródeł danych dla żądanego typu płatności: polecenia przelewu.     Istnieje możliwość zaprojektowania więcej niż jednego mapowania dla określonego modelu danych. Na przykład można utworzyć mapowanie dla różnych typów płatności, na przykład dla poleceń zapłaty i poleceń przelewu. W tym przykładzie utworzysz mapowanie dla poleceń przelewu.  
5. W polu Nazwa wpisz „Mapowanie polecenia przelewu”.
    * Mapowanie polecenia przelewu  
6. W polu Opis wpisz „Mapowanie polecenia przelewu w modelu płatności”.
    * Mapowanie polecenia przelewu w modelu płatności  
7. W polu Definicja wpisz „CustomerCreditTransferInitiation”.
    * CustomerCreditTransferInitiation  
8. Rozstrzygnij zmiany w definicji.
9. Kliknij przycisk Zapisz.

## <a name="define-required-data-sources-for-the-current-model-mapping"></a>Definiowanie wymaganych źródeł danych dla mapowania bieżącego modelu
1. Kliknij przycisk Konstruktor.
2. W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.
3. Kliknij opcję Dodaj element główny.
    * Wprowadź to źródło danych, aby uzyskać dostęp do transakcji płatności.  
4. W polu Nazwa wpisz „Transakcje”.
    * Transakcje  
5. W polu Etykieta wpisz „Transakcje”.
    * Transakcje  
6. W polu Pomoc wpisz „Wiersze arkusza księgi”.
    * Wiersze arkusza księgi  
7. W polu Monituj o zapytanie wybierz opcję Tak.
    * Wybierz opcję Tak.  
8. W polu Tabela wpisz „LedgerJournalTrans”.
    * LedgerJournalTrans  
9. Kliknij przycisk OK.
    * Wybierz tabelę LedgerJournalTrans jako źródło danych dla bieżącego modelu danych.  
10. W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.
11. Kliknij przycisk Dodaj.
    * Kliknij przycisk Dodaj, aby dodać nowe pole obliczeniowe.  
12. W polu Nazwa wpisz „$EndToEndID”.
    * $EndToEndID  
13. Kliknij opcję Edytuj formułę.
14. W drzewie zaznacz element „Ciąg\ZŁĄCZ”.
15. Kliknij opcję Dodaj funkcję.
16. W drzewie rozwiń węzeł „Transakcje”.
17. W drzewie zaznacz element „Transakcje\Załącznik”.
18. Kliknij opcję Dodaj źródło danych.
19. W polu Formuła wpisz „CONCATENATE(Transakcje.Załącznik, "-", ”.
    * Na końcu formuły wpisz [ , "-", ].  
20. W drzewie zaznacz element „Ciąg\TEKST”.
21. Kliknij opcję Dodaj funkcję.
22. W drzewie zaznacz element „Transakcje\Identyfikator rekordu(RecId)”.
23. Kliknij opcję Dodaj źródło danych.
24. W polu Formuła wpisz „CONCATENATE(Transakcje.Załącznik, "-", TEKST(Transakcje.RecId))”.
    * Na końcu formuły wpisz [))].  
25. Kliknij przycisk Zapisz.
    * Upewnij się, że w utworzonej formule nie zostały wykryte żadne błędy. Zobacz kartę BŁĘDY pod formantem edytora formuły.  
26. Zamknij stronę.
27. Kliknij przycisk OK.
    * Dodaj pole obliczeniowe do tego źródła danych.  
28. Kliknij przycisk Dodaj.
    * Kliknij przycisk Dodaj, aby dodać nowe pole obliczeniowe.  
29. W polu Nazwa wpisz „$Amount”.
    * $Amount  
30. Kliknij opcję Edytuj formułę.
31. W drzewie rozwiń węzeł „Transakcje”.
32. W drzewie zaznacz element „Transakcje\Debet(AmountCurDebit)”.
33. Kliknij opcję Dodaj źródło danych.
34. W polu Formuła wpisz „Transakcje.AmountCurDebit - ”.
    * Na końcu formuły wpisz [ - ].  
35. W drzewie zaznacz element „Transakcje\Kredyt(AmountCurCredit)”.
36. Kliknij opcję Dodaj źródło danych.
37. Kliknij przycisk Zapisz.
38. Zamknij stronę.
39. Kliknij przycisk OK.
    * To spowoduje dodanie pola obliczeniowego $Amount do wybranego źródła danych dla bieżącego modelu danych.  
40. W drzewie zaznacz element „Transakcje\$Amount”.
41. W drzewie rozwiń węzeł „Transakcje”.
42. W drzewie rozwiń lub zwiń węzeł „Transakcje\$Amount”.
43. W drzewie rozwiń lub zwiń węzeł „Transakcje”.
44. W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.
45. Kliknij opcję Dodaj element główny.
    * Wprowadź to źródło danych, aby uzyskać dostęp do szczegółów konta bankowego firmy.  
46. W polu nazwa wpisz „BankAccount”.
    * BankAccount  
47. W polu Etykieta wpisz „Konto bankowe”.
    * Konto bankowe  
48. W polu Pomoc wpisz „Konto bankowe”.
    * Konto bankowe  
49. W polu Monituj o zapytanie wybierz opcję Tak.
    * Wybierz opcję Tak.  
50. W polu Tabela wpisz „BankAccountTable”.
    * BankAccountTable  
51. Kliknij przycisk OK.
    * Wybierz tabelę BankAccountTable jako źródło danych dla bieżącego modelu danych.  
52. Kliknij opcję Dodaj element główny.
    * Wprowadź to źródło danych, aby uzyskać dostęp do wymagań firmy.  
53. W polu Nazwa wpisz „Firma”.
    * Firma  
54. W polu Etykieta wpisz wartość.
    * Informacje o firmie  
55. W polu Pomoc wpisz „Informacje o firmie”.
    * Informacje o firmie  
56. W polu Monituj o zapytanie wybierz opcję Tak.
    * Wybierz opcję Tak.  
57. W polu Tabela wpisz „CompanyInfo”.
    * CompanyInfo  
58. Kliknij przycisk OK.
    * Wybierz tabelę CompanyInfo jako źródło danych dla bieżącego modelu danych.  
59. W drzewie zaznacz element „Funkcje\Pole obliczeniowe”.
60. Kliknij opcję Dodaj element główny.
    * Wstaw pole obliczeniowe jako nowe źródło danych.  
61. W polu Nazwa wpisz „ProcessingDateTime”.
    * ProcessingDateTime  
62. W polu Etykieta wpisz „Data i godzina przetwarzania”.
    * Data i godzina przetwarzania  
63. Kliknij opcję Edytuj formułę.
64. W drzewie zaznacz element „Data/godzina\SESSIONNOW”.
65. Kliknij opcję Dodaj funkcję.
66. Kliknij przycisk Zapisz.
67. Zamknij stronę.
68. Kliknij przycisk OK.
    * Dodaj pole obliczeniowe ProcessingDateTime jako źródło danych dla bieżącego modelu danych.  
69. Kliknij przycisk Zapisz.
70. Zamknij stronę.
71. Zamknij stronę.
72. Zamknij stronę.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]