---
title: Rozwiązywanie problemów z importowaniem pliku wyciągu bankowego
description: Ważne jest, aby plik wyciągu bankowego z banku pracował do układu obsługiwanego przez Microsoft Dynamics 365 Finance. Ze względu na ścisłe normy dotyczące wyciągów bankowych większość integracji będzie działać poprawnie. Jednak czasami pliku wyciągu nie można zaimportować lub ma on nieprawidłowe wyniki. Zazwyczaj te problemy są powodowane przez małe różnice w pliku wyciągu bankowego. W tym artykule wyjaśniono, jak skorygować te różnice i rozwiązać problemy.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc5b9cf3449b48767a27891a019f8fe8df2a900559898e3cb1849d25bec7c987
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757128"
---
# <a name="bank-statement-file-import-troubleshooting"></a>Rozwiązywanie problemów z importowaniem pliku wyciągu bankowego

[!include [banner](../includes/banner.md)]

Ważne jest, aby plik wyciągu bankowego z banku pracował do układu obsługiwanego przez Microsoft Dynamics 365 Finance. Ze względu na ścisłe normy dotyczące wyciągów bankowych większość integracji będzie działać poprawnie. Jednak czasami pliku wyciągu nie można zaimportować lub ma on nieprawidłowe wyniki. Zazwyczaj te problemy są powodowane przez małe różnice w pliku wyciągu bankowego. W tym artykule wyjaśniono, jak skorygować te różnice i rozwiązać problemy.

## <a name="what-is-the-error"></a>Na czym polega błąd?

Po próbie zaimportowania pliku wyciągu bankowego przejdź do historii zadania zarządzania danymi i szczegółów wykonania operacji, aby znaleźć błąd. Błąd może pomóc poprzez wskazane wyciągu, salda lub wiersza wyciągu. Jednak prawdopodobnie dostarczy za mało informacji, aby pomóc w zidentyfikowaniu pola lub elementu, który jest przyczyną problemu.

> [!NOTE]
> Importowane wyciągi bankowe mogą się nakładać tylko dla pojedynczego punktu w czasie.  Na przykład, jeśli zestawienie kończy się 1 stycznia 2021 o godzinie 24:00, to datą rozpoczęcia następnego zestawienia może być 12:00 w dniu 1 stycznia 2021 24:00.

## <a name="what-are-the-differences"></a>Jakie są różnice?
Porównaj definicję układu pliku bankowego z definicją importu w programie Finance i zapisz wszelkie różnice w polach i elementach. Porównaj plik wyciągu bankowego z powiązanym przykładowym plikiem programu Finance. W plikach ISO20022 wszelkie różnice powinny być dobrze widoczne.

## <a name="time-zone-differences-on-imported-bank-statements"></a>Różnice stref czasowych dla zaimportowanych wyciągów bankowych
Wartości daty i godziny w pliku importu mogą się różnić od wartości daty i godziny wyświetlanej w Finance and Operations. Aby uniknąć tej rozbieżności, należy wprowadzić preferencję dotyczącą strefy czasowej na stronie **Konfigurowanie źródeł danych**. Aby uzyskać więcej informacji, zapoznaj się z tematem [Konfigurowanie zaawansowanego procesu importu uzgodnień bankowych](set-up-advanced-bank-reconciliation-import-process.md).

## <a name="transformations"></a>Przekształcenia
Zazwyczaj zmiany należy dokonać w jednym z trzech przekształceń. Każde przekształcenie jest zapisywane dla określonego standardu.

| Nazwa zasobu                                         | Nazwa pliku                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>Debugowanie przekształceń
### <a name="adjust-the-bai2-and-mt940-files"></a>Korygowanie plików BAI2 i MT940

Pliki BAI2 i MT940 są plikami tekstowymi i wymagają skorygowania, aby umożliwić debugowanie przekształceń Extensible Stylesheet Language Transformation (XSLT). Program dokonuje tej korekty podczas importowania pliku.

1.  Utwórz plik XML i skopiuj do niego następujący tekst:

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  Skopiuj zawartość pliku wyciągu bankowego i wkleić ją do pliku XML, tak aby zastąpiła fragment **TUWKLEJPLIKINSTRUKCJI**.

### <a name="debug-the-xslt"></a>Debugowanie przekształcenia XSLT

Aby uzyskać więcej informacji, zobacz <https://msdn.microsoft.com/library/ms255605.aspx>.

1.  Uruchom Microsoft Visual Studio.
2.  Utwórz aplikację konsoli.
3.  Otwórz odpowiednie przekształcenie XSLT.
4.  Kliknij przekształcenie XLST i jego stronę właściwości.
5.  Jako źródło danych wejściowych ustaw lokalizację pliku wyciągu bankowego.
6.  Określ lokalizację i nazwę dla danych wyjściowych.
7.  Ustaw wymagane punkty przerwania.
8.  W menu kliknij kolejno opcje **XML** &gt; **Rozpocznij debugowanie XSLT**.

### <a name="format-the-xslt-output"></a>Formatowanie danych wyjściowych XSLT

Podczas wykonywania przekształcenia jest tworzony plik wyjściowy, który można wyświetlić w programie Visual Studio. Za pomocą kombinacji klawiszy Ctrl+K, Ctrl+D i Ctrl+K można szybko sformatować plik wyjściowy.

### <a name="adjust-the-transformation"></a>Korygowanie przekształcenia

Skoryguj przekształcenie, aby uzyskać odpowiednie pole lub element w pliku wyciągu bankowego. Następnie zamapuj to pole lub element do odpowiedniego elementu programu Finance.

### <a name="debitcredit-indicator"></a>Wskaźnik debetu/kredytu

Czasami pozycje debetowe mogą być importowane jako kredytowe, i odwrotnie. Aby rozwiązać ten problem, należy zmienić odpowiednie przekształcenie XSLT. Jeśli wyciągi bankowe pochodzą z wielu banków, upewnij się, że używają takich samych zasad ustalania strony debetowej/kredytowej, albo utwórz oddzielne przekształcenia.

-   Szablon GetAmountCreditDebitIndicator BAI2XML-to-Reconciliation.xlst
-   Szablon GetCreditDebit ISO20022XML-to-Reconcilation.xslt
-   Szablon operacji GetCreditDebitIndicator MT940XML-to-Reconcilation.xslt

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Przykłady formatów i układów technicznych i wyciągów bankowych
W tabeli poniżej przedstawiono przykłady definicji układów technicznych plików importu zaawansowanego uzgadniania konta bankowego i trzy powiązane przykładowe pliki wyciągów bankowych. Przykładowe pliki i układy techniczne można pobrać stąd: [Importownaie plików przykładowych](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Definicja układu technicznego                             | Przykładowy plik wyciągu bankowego          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
