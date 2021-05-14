---
title: ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML (listopad 2016)
description: W tym temacie opisano sposób utworzenia nowej konfiguracji raportowania elektronicznego zawierającej szablon do generowania dokumentów elektronicznych w formacie OPENXML.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f23748f6f1d2c3045b1dc69d8e46821f67da593
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944275"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML (listopad 2016)

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację raportowania elektronicznego (ER) zawierającą szablon generowania dokumentów elektronicznych w formacie OPENXML. Ta konfiguracja będzie używana do przetwarzania płatności dla dostawcy.

W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. Kroki można wykonać na danych firmy GBSI.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”. Musi także istnieć plik programu Excel, który zostanie zaimportowany podczas tworzenia szablonu. Do pliku można przejść z [szablonu raportu o płatnościach](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx).


## <a name="upload-the-payments-data-model-configuration"></a>Przekazywanie konfiguracji modelu danych płatności
1. W okienku nawigacji przejdź do **Moduły > Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne**.
2. Na liście wybierz dostawcę konfiguracji przykładowej firmy Litware, Inc. Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę opisaną w [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md).
3. Wybierz **Aktywuj**.
4. Wybierz **Repozytoria**. Wybierz repozytorium typu zasobów operacyjnych, jeśli jest dostępne. Jeśli jej dostępne, pomiń poniższe kroki tworzenia nowego repozytorium.  
5. Wybierz przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.
6. W polu **Typ repozytorium konfiguracji** wpisz `Operations resourcesdd`.
7. Kliknij opcję **Utwórz repozytorium**.
8. Kliknij przycisk **OK**.
9. Kliknij przycisk **Otwórz**.
10. W drzewie zaznacz element **Model płatności**.
11. Wybierz opcję **Importuj**. Zaimportuj ten model danych. Będzie on służył jako źródło danych w nowej konfiguracji formatu. Jeśli ta konfiguracja została już zaimportowana, pomiń ten krok.  
12. Wybierz opcję **Tak**.
13. Zamknij strony, dopóki nie powrócisz na stronę Raportowanie elektroniczne.

## <a name="create-a-new-format-configuration"></a>Utwórz nową konfigurację formatu.
1. Wybierz **Raportowanie konfiguracji**.
2. W drzewie zaznacz element **Model płatności**.
3. Wybierz przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe.
4. W polu **Nowe** wprowadź wartość `Format based on data model PaymentModel`. Tworzenie formatu opartego na modelu danych PaymentModel
5. W polu **Nazwa** wpisz `Sample worksheet report`. Przykładowy raport arkusza  
6. Wprowadź **Opis** wpisz `Sample worksheet report for vendors' payments`. Przykładowy raport arkusza o płatnościach dostawców.  
7. W polu **Definicja modelu danych** wprowadź lub wybierz wartość. Zaznacz definicję **CustomerCreditTransferInitiation**.  
8. Wybierz **Utwórz konfigurację**.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Projektowanie nowego dokumentu w formacie arkusza OPENXML
1. W drzewie zaznacz węzeł **Payment model\Sample worksheet report**.
2. Wybierz opcję **Konstruktor**.
3. W okienku akcji wybierz pozycję **Importuj**.
4. Wybierz **Importuj z programu Excel**.
5. Wybierz **Załączniki**. Dołącz istniejący dokument programu Excel jako szablon.  
6. Wybierz pozycję **Nowy**.
7. Wybierz **Plik**. Wskaż istniejący plik programu Excel.  
8. Zamknij stronę.
9. W polu **Szablon** wprowadź lub wybierz wartość. Zaznacz załączony plik programu Excel, który ma być używany jako szablon.  
10. Kliknij przycisk **OK**. Należy zwrócić uwagę, że składniki formatu raportowania elektronicznego zostały utworzone w formacie projektowania opartym na strukturze źródłowego dokument programu MS Excel (nazwanych zakresów).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Tworzenie nowego źródła danych do obliczania sum według kodów walut
1. Kliknij kartę **Mapowanie**.
2. Kliknij przycisk **Dodaj źródło**, aby otworzyć rozwijane okno dialogowe.
3. W drzewie zaznacz element **Funkcje\Grupuj wg**.
4. W polu **Nazwa** wpisz `PaymentByCurrency`.
5. Kliknij opcję **Edytuj grupę według**.
6. Rozwiń pozycję **model** w drzewie, a następnie wybierz **model\Płatności**.
7. Wybierz **Dodaj pole do**.
8. Wybierz **Jakie elementy do grupowania**.
9. Rozwiń pozycję **model\Płatności**, a następnie wybierz **model\Płatności\Waluta**.
10. Wybierz **Dodaj pole do**.
11. Wybierz **Zgrupowane pola**.
12. W drzewie zaznacz element **model\Płatności\Wskazana kwota(InstructedAmount)**.
13. Wybierz **Dodaj pole do**, a następnie wybierz **pola agregacji**.
14. W polu **Metoda** wybierz opcję. Wybierz funkcję **agregacji SUMA**.  
15. W polu **Nazwa** wpisz `TotalInstructuredAmount`.
16. Wybierz opcję **Zapisz**.
17. Zamknij stronę.
18. Kliknij przycisk **OK**.

## <a name="map-format-components-to-data-sources"></a>Mapowanie składników formatu do źródeł danych
1. W drzewie zaznacz węzeł **model\Payments\Initiating Party(InitiatingParty)\Name** i **Excel\ReportHeader\CompanyName**.
2. Wybierz **Powiąż**.
3. W drzewie wybierz **model\Payments\Creditor\Identification\Source ID(SourceID)** i **Excel\PaymLines\VendAccountName**.
4. Wybierz **Powiąż**.
5. W drzewie wybierz **model\Payments\Creditor\Name** i **Excel\PaymLines\VendName**.
6. Wybierz **Powiąż**.
7. W drzewie wybierz **model\Payments\Creditor Agent(CreditorAgent)\Name** i **Excel\PaymLines\Bank**.
8. Wybierz **Powiąż**.
9. W drzewie wybierz **model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)** i **Excel\PaymLines\RoutingNumber**.
10. Wybierz **Powiąż**.
11. W drzewie wybierz **model\Payments\Creditor Account(CreditorAccount)\Identification\Number** i **Excel\PaymLines\AccountNumber**.
12. Wybierz **Powiąż**.
13. W drzewie wybierz **model\Payments\Instructed Amount(InstructedAmount)** i **Excel\PaymLines\Debit**.
14. Wybierz **Powiąż**.
15. W drzewie wybierz **model\Payments\Currency** i **Excel\PaymLines\Currency**.
16. Wybierz **Powiąż**.
17. W drzewie wybierz **PaymentByCurrency\grouped\Currency** i **Excel\SummaryLines\SummaryCurrency**.
18. Wybierz **Powiąż**.
19. W drzewie wybierz **PaymentByCurrency\aggregated\TotalInstructuredAmount** i **Excel\SummaryLines\SummaryAmount**.
20. Wybierz **Powiąż**.
21. W drzewie wybierz **PaymentByCurrency** i **Excel\SummaryLines**.
22. Wybierz **Powiąż**.
23. W drzewie wybierz **model\Payments** i **Excel\PaymLines**.
24. Wybierz **Powiąż**.
25. Wybierz przycisk **Zapisz**, a następnie zamknij stronę.

## <a name="use-the-created-configuration-for-payments-processing"></a>Używanie utworzonej konfiguracji do przetwarzania płatności
1. Wybierz opcję **Zmień stan**.
2. Wybierz opcję **Zakończone**.
3. Kliknij przycisk **OK**.
4. W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Ustawienia płatności > Metody płatności**.
5. Użyj szybkiego filtru, aby wyfiltrować pole **Metoda płatności** według wartości **Elektroniczne**.
6. Wybierz opcję **Edycja**.
7. Rozwiń sekcję **Formaty plików**.
8. W polu **Ogólne raportowanie elektroniczne** wybierz opcję **Tak**.
9. W polu **Konfiguracja formatu eksportu** wpisz lub wybierz wartość. Zaznacz konfigurację **Przykładowy raport arkusza**.  
10. Wybierz opcję **Zapisz**.
11. Zamknij stronę.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Używanie utworzonej konfiguracji w celu testowania przetwarzania arkuszy płatności
1. W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Płatności > Arkusz płatności**.
2. Wybierz pozycję **Nowy**, aby utworzyć arkusz płatności.
3. W polu **Nazwa** wpisz **VendPay**.
4. Wybierz **Linie**.
5. W polu **Konto** podaj wartości `GB_SI_000001`.
6. W polu **Debet** wpisz wartość `1000`.
7. Wybierz pozycję **Nowy**.
8. W polu **Konto** podaj wartości `GB_SI_000005`.
9. W polu **Debet** wpisz wartość `2000`.
10. W polu **Waluta** wpisz wartość `EUR`.
11. W polu **Konto przeciwstawne** wpisz wartość `GBSI OPER`.
12. W polu **Metoda płatności** wpisz `Electronic`.
13. Wybierz opcję **Zapisz**.
14. Wybierz **Generuj płatności**.
15. W polu **Metoda płatności** wpisz `Electronic`.
16. W polu **Nazwa pliku** wpisz `Payments`.
17. W polu **Konto bankowe** wpisz `GBSI OPER`.
18. Zaznacz element **OK** i kliknij przycisk **OK** ponownie. Przejrzyj utworzony arkusz, łącznie ze szczegółami wierszy płatności oraz sumami dla każdego kodu waluty użytego w tym komunikacie płatności.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
