---
title: "Eksplorator źródeł księgowania"
description: "Ten artykuł zawiera informacje o Eksplorator źródeł księgowania, którego można używać do szczegółowej analizy informacji źródłowych stojących za wpisami księgowymi w księgi głównej."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cb5a674472936a52b624c548fd37079d57eb6cb7
ms.openlocfilehash: d21f214ef8a29c19f0af1d4a2bdfc3264987f0b8
ms.contentlocale: pl-pl
ms.lasthandoff: 12/14/2017

---

# <a name="accounting-source-explorer"></a>Eksplorator źródeł księgowania

[!INCLUDE [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o Eksplorator źródeł księgowania, którego można używać do szczegółowej analizy informacji źródłowych stojących za wpisami księgowymi w księgi głównej.

Eksplorator źródeł księgowania to nowa strona, która pokazuje informacje o źródle. Może służyć albo jako autonomiczne narzędzie, albo do analizy szczegółów zapisów księgowych w księdze głównej. Można na przykład uzyskać najbardziej szczegółowe informacje o źródle dla salda bilansu próbnego lub dla transakcji na załączniku. Następnie za pomocą funkcji eksportu do MS Excel można dalej dzielić informacje w programie Microsoft Excel (na przykład w tabeli przestawnej lub raporcie tabeli przestawnej).

Eksplorator źródeł księgowania zawsze pokazuje tę samą sumę według konta księgowego co Księga główna (np. w bilansie próbnym). W bilansie próbnym można wyświetlić segmenty w osobnych kolumnach. Wystarczy zaznaczyć odpowiedni zestaw wymiarów finansowych. 

Za pomocą parametrów można zdefiniować interwał dat dla analizy. Ta funkcja przypomina też funkcję bilansu próbnego.

Dla wszystkich dokumentów, które używają struktury dokumentów źródłowych, Eksplorator źródeł księgowania zawiera dodatkowe informacje oparte o zasady podziału księgowań i (jeśli dotyczy) o zasady podziału księgowań dla projektu. Te informacje obejmują typ kwoty pieniężnej, projekt, działanie, kategorię i właściwość wiersza. Oto kilka przykładów dostępnych analiz:

-   Odchylenia między zamówieniami zakupu i fakturami od dostawcy, ponieważ każde odchylenie jest reprezentowane przez typ kwoty pieniężnej, np. odchylenie opłaty
-   Rozliczane i nierozliczane godziny i wydatki według projektu, jednostki biznesowej i konta głównego

Dla dokumentów źródłowych, które używają koncepcji tożsamości odwołania do dokumentu Eksplorator źródeł księgowań pokazuje jeszcze więcej szczegółów, takich jak odbiorcy, dostawcy, pracownik, produkt, ilość, tekst jednostki i opisy. Oto kilka przykładów dostępnych analiz:

-   Wydatki na hotele na jednostkę biznesową i markę hotelu dla okresu obrachunkowego w oparciu o raporty z wydatków
-   Rabaty na dostawcę, produkt, dział

W przypadku tych dokumentów Eksplorator źródeł księgowania pozwala też przejść do rzeczywistych dokumentów źródłowych.




