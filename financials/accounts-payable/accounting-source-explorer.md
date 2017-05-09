---
title: "Eksplorator źródeł księgowania"
description: "Ten artykuł zawiera informacje o Eksplorator źródeł księgowania, którego można używać do szczegółowej analizy informacji źródłowych stojących za wpisami księgowymi w księgi głównej."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 8913e61285d5d180883471991b659ddcb260afe3
ms.lasthandoff: 03/31/2017


---

# <a name="accounting-source-explorer"></a>Eksplorator źródeł księgowania

[!include[banner](../includes/banner.md)]


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




