--- 
title: "ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML (listopad 2016)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą szablon generowania dokumentów elektronicznych w formacie OPENXML."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 3e6b6b16f202af051ccff02051eb438ea49ff6da
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML (listopad 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą szablon generowania dokumentów elektronicznych w formacie OPENXML. Ta konfiguracja będzie używana do przetwarzania płatności dla dostawcy.



W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Kroki można wykonać na danych firmy GBSI.



Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”. Musi także istnieć plik programu Excel, który zostanie zaimportowany podczas tworzenia szablonu. Do pliku można przejść z [szablonu raportu o płatnościach](https://go.microsoft.com/fwlink/?linkid=862266).


## <a name="upload-the-payments-data-model-configuration"></a>Przekazywanie konfiguracji modelu danych płatności
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Na liście oznacz wybrany wiersz.
    * Wybierz dostawcę konfiguracji przykładowej firmy Litware, Inc. Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.  
3. Kliknij opcję Ustaw jako aktywny.
4. Kliknij Repozytoria.
    * Wybierz repozytorium typu zasobów operacyjnych, jeśli jest dostępne. Jeśli jej dostępne, pomiń poniższe kroki tworzenia nowego repozytorium.  
5. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
6. W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.
7. Kliknij opcję Utwórz repozytorium.
8. Kliknij przycisk OK.
9. Kliknij przycisk Otwórz.
10. W drzewie zaznacz element „Model płatności”.
11. Kliknij przycisk Importuj.
    * Zaimportuj ten model danych. Będzie on służył jako źródło danych w nowej konfiguracji formatu. Jeśli ta konfiguracja została już zaimportowana, pomiń ten krok.  
12. Kliknij przycisk Tak.
13. Zamknij stronę.
14. Zamknij stronę.

## <a name="create-a-new-format-configuration"></a>Utwórz nową konfigurację formatu.
1. Kliknij opcję Konfiguracje raportowania.
2. W drzewie zaznacz element „Model płatności”.
3. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
4. W polu Nowy wpisz „Format oparty na modelu danych PaymentModel”.
    * Tworzenie formatu opartego na modelu danych PaymentModel  
5. W polu Nazwa wpisz „Przykładowy raport arkusza”.
    * Przykładowy raport arkusza  
6. W polu Opis wpisz „Przykładowy raport arkusza o płatnościach dla dostawców”.
    * Przykładowy raport arkusza o płatnościach dla dostawców.  
7. W polu Definicja modelu danych wprowadź lub wybierz wartość.
    * Zaznacz definicję „CustomerCreditTransferInitiation”.  
8. Kliknij przycisk Utwórz konfigurację.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Projektowanie nowego dokumentu w formacie arkusza OPENXML
1. W drzewie zaznacz węzeł „Model płatności\Przykładowy raport arkusza”.
2. Kliknij przycisk Konstruktor.
3. W okienku akcji kliknij pozycję Importuj.
4. Kliknij opcję Importuj z programu Excel.
5. Kliknij opcję Załączniki.
    * Dołącz istniejący dokument programu Excel jako szablon.  
6. Kliknij przycisk Nowy.
7. Kliknij opcję Plik.
    * Wskaż istniejący plik programu Excel.  
8. Zamknij stronę.
9. W polu Szablon wprowadź lub wybierz wartość.
    * Zaznacz załączony plik programu Excel, który ma być używany jako szablon.  
10. Kliknij przycisk OK.
    * Należy zwrócić uwagę, że składniki formatu raportowania elektronicznego zostały utworzone w formacie projektowania opartym na strukturze źródłowego dokument programu MS Excel (nazwanych zakresów).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Tworzenie nowego źródła danych do obliczania sum według kodów walut
1. Kliknij kartę Mapowanie.
2. Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.
3. W drzewie zaznacz element „Funkcje\Grupuj wg”.
4. W polu Nazwa wpisz „PaymentByCurrency”.
    * PaymentByCurrency  
5. Kliknij opcję Edytuj grupę według.
6. W drzewie rozwiń model„”
7. W drzewie zaznacz element „model\Płatności”.
8. Kliknij opcję Dodaj pole do.
9. Kliknij opcję Jakie elementy do grupowania.
10. W drzewie rozwiń węzeł „model\Płatności”.
11. W drzewie zaznacz element „model\Płatności\Waluta”.
12. Kliknij opcję Dodaj pole do.
13. Kliknij opcję Zgrupowane pola.
14. W drzewie zaznacz element „model\Płatności\Wskazana kwota(InstructedAmount)”.
15. Kliknij opcję Dodaj pole do.
16. Kliknij opcje Pola agregacji.
17. W polu Metoda wybierz opcję.
    * Wybierz funkcję agregacji SUMA.  
18. W polu Nazwa wpisz „TotalInstructuredAmount”.
    * TotalInstructuredAmount  
19. Kliknij przycisk Zapisz.
20. Zamknij stronę.
21. Kliknij przycisk OK.

## <a name="map-format-components-to-data-sources"></a>Mapowanie składników formatu do źródeł danych
1. W drzewie rozwiń model„”
2. W drzewie rozwiń węzeł „model\Płatności”.
3. W drzewie rozwiń węzeł „model\Płatności\Strona inicjująca(InitiatingParty)”.
4. W drzewie zaznacz węzeł „model\Płatności\Strona inicjująca(InitiatingParty)\Nazwa”.
5. W drzewie rozwiń węzeł „Excel\ReportHeader”.
6. W drzewie zaznacz element „Excel\ReportHeader\CompanyName”.
7. Kliknij opcję Powiąż.
8. W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.
9. W drzewie rozwiń węzeł „model\Płatności\Konto wierzyciela\Identyfikacja”.
10. W drzewie rozwiń węzeł „model\Płatności\Wierzyciel\Identyfikacja\Identyfikator źródła(SourceID)”.
11. W drzewie rozwiń węzeł „Excel\PaymLines”.
12. W drzewie zaznacz element „Excel\PaymLines\VendAccountName”.
13. Kliknij opcję Powiąż.
14. W drzewie zaznacz element „model\Płatności\Wierzyciel\Nazwa”.
15. W drzewie zaznacz element „Excel\PaymLines\VendName”.
16. Kliknij opcję Powiąż.
17. W drzewie rozwiń węzeł „model\Płatności\Agent wierzyciela(CreditorAgent)”.
18. W drzewie zaznacz element „model\Płatności\Agent wierzyciela(CreditorAgent)\Nazwa”.
19. W drzewie zaznacz element „Excel\PaymLines\Bank”.
20. Kliknij opcję Powiąż.
21. W drzewie zaznacz element „model\Płatności\Agent wierzyciela(CreditorAgent)\Kod banku(RoutingNumber)”.
22. W drzewie zaznacz element „Excel\PaymLines\RoutingNumber”.
23. Kliknij opcję Powiąż.
24. W drzewie rozwiń „model\Płatności\Konto wierzyciela(KontoWierzyciela)".
25. W drzewie rozwiń „model\Płatności\Konto wierzyciela(KontoWierzyciela)".
26. W drzewie wybierz „model\Płatności\Konto wierzyciela(CreditorAccount\Identyfikacja\Numer”.
27. W drzewie zaznacz element „Excel\PaymLines\AccountNumber”.
28. Kliknij opcję Powiąż.
29. W drzewie zaznacz element „model\Płatności\Wskazana kwota(InstructedAmount)”.
30. W drzewie zaznacz element „Excel\PaymLines\Debet”.
31. Kliknij opcję Powiąż.
32. W drzewie rozwiń węzeł „model\Płatności\Wierzyciel”.
33. W drzewie rozwiń „model\Płatności\Konto wierzyciela(KontoWierzyciela)".
34. W drzewie rozwiń węzeł „model\Płatności\Agent wierzyciela(CreditorAgent)”.
35. W drzewie zaznacz element „model\Płatności\Waluta”.
36. W drzewie zaznacz element „Excel\PaymLines\Waluta”.
37. Kliknij opcję Powiąż.
38. W drzewie rozwiń węzeł „PaymentByCurrency”.
39. W drzewie rozwiń węzeł „PaymentByCurrency\zgrupowane”.
40. W drzewie zaznacz element „PaymentByCurrency\zgrupowane\Waluta”.
41. W drzewie rozwiń węzeł „Excel\SummaryLines”.
42. W drzewie zaznacz element „Excel\SummaryLines\SummaryCurrency”.
43. Kliknij opcję Powiąż.
44. W drzewie rozwiń węzeł „PaymentByCurrency\zagregowane”.
45. W drzewie zaznacz element „PaymentByCurrency\zagregowane\TotalInstructuredAmount”.
46. W drzewie zaznacz element „Excel\SummaryLines\SummaryAmount”.
47. Kliknij opcję Powiąż.
48. W drzewie zaznacz element „PaymentByCurrency”.
49. W drzewie zaznacz element „Excel\SummaryLines”.
50. Kliknij opcję Powiąż.
51. W drzewie zaznacz element „model\Płatności”.
52. W drzewie zaznacz element „Excel\PaymLines”.
53. Kliknij opcję Powiąż.
54. Kliknij przycisk Zapisz.
55. Zamknij stronę.

## <a name="use-the-created-configuration-for-payments-processing"></a>Używanie utworzonej konfiguracji do przetwarzania płatności
1. Kliknij przycisk Zmień stan.
2. Kliknij przycisk Wykonaj.
3. Kliknij przycisk OK.
4. Zamknij stronę.
5. Zamknij stronę.
6. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Metody płatności.
7. Użyj szybkiego filtru, aby wyfiltrować pole Metoda płatności według wartości „Elektroniczne”.
    * Elektroniczne  
8. Kliknij przycisk Edytuj.
9. Rozwiń sekcję Formaty plików.
10. W polu Ogólne raportowanie elektroniczne wybierz opcję Tak.
11. W polu Konfiguracja formatu eksportu wpisz lub wybierz wartość.
    * Zaznacz konfigurację „Przykładowy raport arkusza”.  
12. Kliknij przycisk Zapisz.
13. Zamknij stronę.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Używanie utworzonej konfiguracji w celu testowania przetwarzania arkuszy płatności
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.
2. Kliknij przycisk Nowy.
    * Utwórz nowy arkusz płatności.  
3. W polu Nazwa wpisz „VendPay”.
    * VendPay  
4. Kliknij przycisk Wiersze.
5. W polu Konto wpisz wartość „GB_SI_000001”.
    * GB_SI_000001  
6. W polu Debet wpisz wartość „1000”.
7. Kliknij przycisk Nowy.
8. W polu Konto wpisz wartość „GB_SI_000005”.
    * GB_SI_000005  
9. W polu Debet wpisz wartość „2000”.
10. W polu Waluta wpisz wartość „EUR”.
    * EUR  
11. W polu Konto przeciwstawne wpisz wartość „GBSI OPER”.
    * GBSI OPER  
12. W polu Metoda płatności wpisz wartość „Elektroniczne”.
    * Elektroniczne  
13. Kliknij przycisk Zapisz.
14. Kliknij opcję Generuj płatności.
15. W polu Metoda płatności wpisz wartość „Elektroniczne”.
    * Elektroniczne  
16. W polu Nazwa pliku wpisz „Płatności”.
    * Na przykład wpisz Płatności.  
17. W polu Konto bankowe wpisz „GBSI OPER”.
    * GBSI OPER  
18. Kliknij przycisk OK.
19. Kliknij przycisk OK.
    * Przejrzyj utworzony arkusz, łącznie ze szczegółami wierszy płatności oraz sumami dla każdego kodu waluty użytego w tym komunikacie płatności.  


