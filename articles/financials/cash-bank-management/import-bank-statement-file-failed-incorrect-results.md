---
title: "Rozwiązywanie problemów z importowaniem pliku wyciągu bankowego"
description: "Ważne jest, aby plik wyciągu bankowego z banku pasował do układu obsługiwanego przez program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Ze względu na ścisłe normy dotyczące wyciągów bankowych większość integracji będzie działać poprawnie. Jednak czasami pliku wyciągu nie można zaimportować lub ma on nieprawidłowe wyniki. Zazwyczaj te problemy są powodowane przez małe różnice w pliku wyciągu bankowego. W tym artykule wyjaśniono, jak skorygować te różnice i rozwiązać problemy."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 33b7a499caf9292e44c155a0e1bd6a8929558be5
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017

---

# <a name="bank-statement-file-import-troubleshooting"></a>Rozwiązywanie problemów z importowaniem pliku wyciągu bankowego

[!include[banner](../includes/banner.md)]


Ważne jest, aby plik wyciągu bankowego z banku pasował do układu obsługiwanego przez program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Ze względu na ścisłe normy dotyczące wyciągów bankowych większość integracji będzie działać poprawnie. Jednak czasami pliku wyciągu nie można zaimportować lub ma on nieprawidłowe wyniki. Zazwyczaj te problemy są powodowane przez małe różnice w pliku wyciągu bankowego. W tym artykule wyjaśniono, jak skorygować te różnice i rozwiązać problemy.

<a name="what-is-the-error"></a>Na czym polega błąd?
------------------

Po próbie zaimportowania pliku wyciągu bankowego przejdź do historii zadania zarządzania danymi i szczegółów wykonania operacji, aby znaleźć błąd. Błąd może pomóc poprzez wskazane wyciągu, salda lub wiersza wyciągu. Jednak prawdopodobnie dostarczy za mało informacji, aby pomóc w zidentyfikowaniu pola lub elementu, który jest przyczyną problemu.

## <a name="what-are-the-differences"></a>Jakie są różnice?
Porównaj definicję układu pliku bankowego z definicją importu w programie Finance and Operations i zapisz wszelkie różnice w polach i elementach. Porównaj plik wyciągu bankowego z powiązanym przykładowym plikiem programu Finance and Operations. W plikach ISO20022 wszelkie różnice powinny być dobrze widoczne.

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

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  Skopiuj zawartość pliku wyciągu bankowego i wkleić ją do pliku XML, tak aby zastąpiła fragment **TUWKLEJPLIKINSTRUKCJI**.

### <a name="debug-the-xslt"></a>Debugowanie przekształcenia XSLT

Aby uzyskać więcej informacji, zobacz <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.

1.  Uruchom program Microsoft Visual Studio.
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

Skoryguj przekształcenie, aby uzyskać odpowiednie pole lub element w pliku wyciągu bankowego. Następnie zamapuj to pole lub element do odpowiedniego elementu programu Finance and Operations.

### <a name="debitcredit-indicator"></a>Wskaźnik debetu/kredytu

Czasami pozycje debetowe mogą być importowane jako kredytowe, i odwrotnie. Aby rozwiązać ten problem, należy zmienić odpowiednie przekształcenie XSLT. Jeśli wyciągi bankowe pochodzą z wielu banków, upewnij się, że używają takich samych zasad ustalania strony debetowej/kredytowej, albo utwórz oddzielne przekształcenia.

-   Szablon GetAmountCreditDebitIndicator BAI2XML-to-Reconciliation.xlst
-   Szablon GetCreditDebit ISO20022XML-to-Reconcilation.xslt
-   Szablon operacji GetCreditDebitIndicator MT940XML-to-Reconcilation.xslt

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Przykłady formatów i układów technicznych i wyciągów bankowych
W tabeli poniżej przedstawiono przykłady definicji układów technicznych plików importu zaawansowanego uzgadniania konta bankowego i trzy powiązane przykładowe pliki wyciągów bankowych. Przykładowe pliki i układy techniczne można pobrać stąd: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  


| Definicja układu technicznego                             | Przykładowy plik wyciągu bankowego          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |






