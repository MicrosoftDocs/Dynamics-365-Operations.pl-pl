---
title: ER Mapowanie modelu danych na wybrane źródła danych
description: W tym temacie opisano sposób mapowania modelu danych raportowania elektronicznego (ER) na wybrane źródła danych Microsoft Dynamics 365 Finance.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e2ba94c9ec3ecc33f0c697d9f18f763749e4ba1
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093755"
---
# <a name="er-map-data-model-to-selected-data-sources"></a>ER Mapowanie modelu danych na wybrane źródła danych

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może mapować model danych raportowania elektronicznego (ER) na wybrane źródła danych. To mapowanie modelu będzie później używane jako źródło danych w konfiguracji formatu używanej do zarządzania dokumentami płatności elektronicznych. W tym przykładzie zmapujesz model danych przykładowej firmy Litware, Inc. na źródła danych. W celu wykonania tych kroków należy najpierw wykonać kroki w procedurze „Wybór źródeł danych do mapowania modelu”.


## <a name="open-er-configurations-tree"></a>Otwórz drzewo konfiguracje raportowania w przedsiębiorstwie.
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Konfiguracje.

## <a name="select-created-model-mapping"></a>Wybór utworzonego mapowania modelu
1. W drzewie zaznacz element „Płatności (model uproszczony)”.
    * Upewnij się, że wcześniej utworzono konfigurację modelu „Płatności (model uproszczony)”. W przeciwnym razie teraz przerwij, wykonaj przewodnik po zadaniu „Tworzenie nowej konfiguracji z modelem danych wybranej domeny” i wróć do tego miejsca.  
2. Kliknij opcję Projektant modeli.
3. Kliknij opcję Mapuj model na źródło danych.
4. Wybierz rekord „Mapowanie polecenia przelewu”.
    * Mapowanie polecenia przelewu  

## <a name="bind-created-data-sources-to-data-model-elements"></a>Tworzenie powiązania między źródłami danych a elementami modelu danych
1. Kliknij przycisk Konstruktor.
2. W drzewie zaznacz element „Data i godzina przetwarzania(ProcessingDateTime)”.
3. W drzewie zaznacz element „Data przetwarzania(ProcessingDateTime)”.
4. Kliknij opcję Powiąż.
5. W drzewie zaznacz element „Identyfikator komunikatu płatności(MessageIdentification)”.
6. W drzewie rozwiń węzeł „Transakcje”.
7. W drzewie zaznacz element „Transakcje\Arkusz z numerem partii(JournalNum)”.
8. Kliknij opcję Powiąż.
9. W drzewie zaznacz element „Płatności”.
10. W drzewie zaznacz element „Transakcje”.
11. Kliknij opcję Powiąż.
12. W drzewie rozwiń węzeł „Płatności=Transakcje”.
13. W drzewie rozwiń węzeł „Płatności=Transakcje\Wierzyciel”.
14. W drzewie rozwiń węzeł „Płatności=Transakcje\Wierzyciel\Konto”.
15. W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Konto\Kod waluty(Currency)”.
16. W drzewie rozwiń węzeł „Transakcje\vendBankAccountInTransactionCompany()”.
17. W drzewie zaznacz element „Płatności=Transakcje\vendBankAccountInTransactionCompany()\Waluta(CurrencyCode)”.
18. Kliknij opcję Powiąż.
19. W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Konto\Kod IBAN(IBAN)”.
20. W drzewie zaznacz element „Transakcje\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)”.
21. Kliknij opcję Powiąż.
22. W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Konto\Numer”.
23. W drzewie zaznacz element „Płatności=Transakcje\vendBankAccountInTransactionCompany()\Numer konta bankowego(AccountNum)”.
24. Kliknij opcję Powiąż.
25. W drzewie rozwiń węzeł „Płatności=Transakcje\Wierzyciel\Agent”.
26. W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Agent\Nazwa”.
27. W drzewie zaznacz element „Transakcje\vendBankAccountInTransactionCompany()\Nazwa”.
28. Kliknij opcję Powiąż.
29. W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Agent\Numer rozliczeniowy(RoutingNumber)”.
30. W drzewie zaznacz element „Płatności=Transakcje\vendBankAccountInTransactionCompany()\Numer rozliczeniowy(RegistrationNum)”.
31. Kliknij opcję Powiąż.
32. W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Agent\Kod SWIFT(SWIFT)”.
33. W drzewie zaznacz element „Płatności=Transakcje\vendBankAccountInTransactionCompany()\Kod SWIFT(SWIFTNo)”.
34. Kliknij opcję Powiąż.
35. W drzewie zaznacz element „Płatności=Transakcje\Wierzyciel\Nazwa”.
36. W drzewie rozwiń węzeł „Transakcje\findVendTable()”.
37. W drzewie zaznacz element „Transactions\findVendTable()\name()”.
38. Kliknij opcję Powiąż.
39. W drzewie zaznacz element „Płatności=Transakcje\Kod waluty(Currency)”.
40. W drzewie rozwiń węzeł „Transakcje\>Relacje”.
41. W drzewie rozwiń węzeł „Transakcje\>Relacje\Tabela walut(Currency)”.
42. W drzewie zaznacz element „Transakcje\>Relacje\Tabela walut(Currency)\Kod waluty(CurrencyCodeISO)”.
43. Kliknij opcję Powiąż.
44. W drzewie rozwiń węzeł „Płatności=Transakcje\Dłużnik”.
45. W drzewie rozwiń węzeł „Płatności=Transakcje\Dłużnik\Konto”.
46. W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Konto\Kod waluty(Currency)”.
47. W drzewie zaznacz element „Konto bankowe(BankAccount)”.
48. W drzewie rozwiń węzeł „Konto bankowe(BankAccount)”.
49. W drzewie zaznacz element „Konto bankowe(BankAccount)\Waluta(CurrencyCode)”.
50. Kliknij opcję Powiąż.
51. W drzewie zaznacz element „Konto bankowe(BankAccount)\IBAN”.
52. W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Konto\Kod IBAN(IBAN)”.
53. Kliknij opcję Powiąż.
54. W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Konto\Numer”.
55. W drzewie zaznacz element „Konto bankowe(BankAccount)\Numer konta bankowego(AccountNum)”.
56. Kliknij opcję Powiąż.
57. W drzewie rozwiń węzeł „Płatności=Transakcje\Dłużnik\Agent”.
58. W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Agent\Nazwa”.
59. W drzewie zaznacz element „Konto bankowe(BankAccount)\Nazwa”.
60. Kliknij opcję Powiąż.
61. W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Agent\Numer rozliczeniowy(RoutingNumber)”.
62. W drzewie zaznacz element „Konto bankowe(BankAccount)\Numer rozliczeniowy(RegistrationNum)”.
63. Kliknij opcję Powiąż.
64. W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Agent\Kod SWIFT(SWIFT)”.
65. W drzewie zaznacz element „Konto bankowe(BankAccount)\Kod SWIFT(SWIFTNo)”.
66. Kliknij opcję Powiąż.
67. W drzewie zaznacz element „Płatności=Transakcje\Dłużnik\Nazwa”.
68. W drzewie zaznacz element „Informacje o firmie(Company)”.
69. W drzewie rozwiń węzeł „Informacje o firmie(Company)”.
70. W drzewie zaznacz element „Informacje o firmie(Company)\Nazwa”.
71. Kliknij opcję Powiąż.
72. W drzewie zaznacz element „Płatności=Transakcje\Opis”.
73. W drzewie zaznacz element „Transakcje\Opis(Txt)”.
74. Kliknij opcję Powiąż.
75. W drzewie zaznacz element „Płatności=Transakcje\Kod kompleksowej identyfikacji(End2EndID)”.
76. W drzewie zaznacz element „Transakcje\$EndToEndID”.
77. Kliknij opcję Powiąż.
78. W drzewie zaznacz element „Płatności=Transakcje\Wskazana kwota(InstructedAmount)”.
79. W drzewie zaznacz element „Transakcje\$Amount”.
80. Kliknij opcję Powiąż.
81. W drzewie zaznacz element „Płatności=Transakcje\Data transakcji(TransactionDate)”.
82. W drzewie zaznacz element „Transakcje\Data(TransDate)”.
83. Kliknij opcję Powiąż.

## <a name="validate-created-mapping"></a>Sprawdzanie poprawności utworzonego mapowania
1. Kliknij przycisk Sprawdź poprawność.
    * Sprawdź poprawność nowego mapowania, aby się upewnić, że wszystkie powiązania są w porządku.  
2. Kliknij strzałkę, aby rozwinąć lub zwinąć sekcję Lista błędów.
3. Kliknij przycisk Zapisz.
4. Zamknij stronę.
5. Zamknij stronę.
6. Zamknij stronę.

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a>Zmiana stanu bieżącej wersji konfiguracji modelu
1. Kliknij przycisk Zmień stan.
    * Zmień stan żądanej konfiguracji modelu — z Wersja robocza na Zakończono, aby ją udostępnić na potrzeby projektu formatu płatności.  
2. Kliknij przycisk Wykonaj.
    * Wybierz opcję Zakończone.  
3. Wypełnij pole Opis.
    * Na przykład „wersja 1”.  
4. Kliknij przycisk OK.
5. Wybierz ukończoną wersję bieżącej konfiguracji.
    * Należy zauważyć, że utworzona konfiguracja została zapisana jako ukończona wersja 1.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]