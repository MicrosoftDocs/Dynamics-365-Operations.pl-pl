---
title: "Obszar roboczy płatności dla dostawców"
description: "Ten temat zawiera informacje o komórkowym obszarze roboczym Płatności dla dostawców. Obszar roboczy Płatności dla dostawców zawiera informacje związane z przetwarzaniem płatności dla dostawców."
author: twheeloc
manager: AnnBe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: 
ms.assetid: 
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 3abf4b151b177095b71d44e9a6c9fd8541eaa64e
ms.openlocfilehash: 4011a2383fe4556b730fa0b6353ba0b9773a4eec
ms.contentlocale: pl-pl
ms.lasthandoff: 06/14/2017

---

# <a name="vendor-payments-workspace"></a>Obszar roboczy płatności dla dostawców

[!include[banner](../includes/banner.md)]

Obszar roboczy **Płatności dla dostawców** zawiera informacje związane z przetwarzaniem płatności dla dostawców. Ten obszar roboczy zawiera widok **Moja praca** i stronę **Analizy**. Widok **Moja praca** zawiera kafelki podsumowań, siatki transakcji z dostawcami i informacje o odnośnych dostawcach. Strona **Analizy** wykorzystuje funkcje programu Microsoft Power BI, aby pokazywać wizualizacje dotyczące płatności dla dostawców.

## <a name="my-work-view"></a>Widok Moja praca

### <a name="summary-tiles"></a>Kafelki podsumowania

Kafelki w sekcji **Podsumowanie** pokazują całościowy stan informacji o płatności. Można wyświetlić arkusze płatności, które nie są jeszcze zaksięgowane, przeterminowane faktury, dane wszystkich dostawców oraz wstrzymanych dostawców. Z sekcji **Podsumowanie** można utworzyć nową sesję płatności.

Informacje zawarte w sekcji **Podsumowanie** dotyczą firmy, do której użytkownik jest aktualnie zalogowany.

### <a name="vendor-transactions-grids"></a>Siatki transakcji z dostawcami

Sekcja **Transakcje dostawcy** zawiera siatki pokazujące zaległe faktury i nierozliczone płatności. Z siatki **Zaległe faktury** można wyświetlić historię rozliczania wybranej faktury. Z siatki **Nierozliczone płatności** można wyświetlić historię rozliczania wybranej faktury i rozliczyć tę fakturę.

Pracownicy zajmujący się centralną obsługą płatności mogą za pomocą filtru wyświetlanego w górnej części każdej siatki wybrać firmę. Siatka zostanie następnie wyfiltrowana, tak aby pokazywała wyłącznie firmy zdefiniowane w hierarchii organizacyjnej centralnej obsługi płatności, do której ma wgląd pracownik zajmujący się centralną obsługą płatności.

Karta **Znajdź transakcje** w sekcji **Transakcje dostawcy** pozwala wyszukiwać transakcje z dostawcami.

### <a name="related-information"></a>Informacje pokrewne

Można wyświetlić raporty **Wiekowanie dostawców** i **Podsumowanie płatności na dzień** przy użyciu łączy w sekcji **Informacje pokrewne** w obszarze roboczym.

## <a name="analytics-page"></a>Strona Analizy

Strona **Analizy** zawiera ważne mierniki, takie jak faktury od dostawców zaległe i należne w przyszłości. Ta strona zawiera dziewięć stron raportów. Jedna strona zawiera przegląd, a pozostałe osiem stron dostarczają szczegółowych informacji o miernikach płatności w module Rozrachunki z dostawcami.

W poniższej tabeli pokazano wizualizacje dostępne na każdej stronie raportu.

| Strona raportu | Wizualizacja |
|-------------|---------------|
| Przegląd płatności dla dostawcy | <ul><li>Zaległe faktury</li><li>Faktury należne dzisiaj</li><li>Rabaty otrzymane do rabatów utraconych</li><li>Faktury należne w przyszłości wg daty rabatu gotówkowego</li><li>Faktury należne w przyszłości wg terminu zapłaty</li><li>Faktury zapłacone z opóźnieniem do faktur zapłaconych na czas</li><li>Przypisanie przepływu pracy płatności</li><li>Saldo dostawcy do salda odbiorcy</li><li>Otwarte faktury z wstrzymaniem płatności</li></ul> |
| Zaległe faktury | <ul><li>Zaległe faktury</li><li>Szczegóły zaległych faktur</li><li>Otwarte faktury razem</li><li>Zaległe faktury wg grup dostawców</li><li>Zaległe faktury wg firm</li></ul> |
| Faktury należne dzisiaj | <ul><li>Faktury należne dzisiaj</li><li>Szczegóły faktur należnych dzisiaj</li><li>Faktury należne dzisiaj wg firm</li><li>Faktury należne dzisiaj wg grup dostawców</li></ul> |
| Rabaty otrzymane do rabatów utraconych | <ul><li>Rabaty otrzymane do rabatów utraconych</li><li>Szczegóły rabatów otrzymanych do rabatów utraconych</li><li>Rabaty otrzymane do rabatów utraconych wg firm</li><li>Rabaty otrzymane do rabatów utraconych wg grup dostawców</li></ul> |
| Faktury należne w przyszłości | <ul><li>Faktury należne w przyszłości</li><li>Szczegóły faktur należnych w przyszłości</li><li>Faktury należne w przyszłości wg firm</li><li>Faktury należne w przyszłości wg grup dostawców</li><li>Faktury należne w przyszłości wg daty rabatu gotówkowego</li><li>Faktury należne w przyszłości wg terminu zapłaty</li></ul> |
| Faktury zapłacone z opóźnieniem | <ul><li>Faktury zapłacone po terminie zapłaty</li><li>Szczegóły faktur zapłaconych po terminie zapłaty</li><li>Faktury zapłacone po terminie zapłaty wg firm</li><li>Faktury zapłacone po terminie zapłaty wg grup dostawców</li><li>Faktury zapłacone z opóźnieniem do faktur zapłaconych na czas</li></ul> |
| Przepływ pracy płatności | <ul><li>Wystąpienia przepływu pracy płatności dostawcom</li><li>Wystąpienia przepływu pracy płatności dostawcom wg osób zatwierdzających</li><li>Wystąpienia przepływu pracy płatności dostawcom wg firm</li><li>Średnia liczba dni w przepływie pracy wg osób zatwierdzających</li></ul> |
| Saldo dostawcy do salda odbiorcy | <ul><li>Saldo dostawcy do salda odbiorcy</li><li>Saldo dostawcy do salda odbiorcy wg firm</li><li>Szczegóły salda dostawcy do salda odbiorcy</li></ul> |
| Faktury z wstrzymaniem płatności | <ul><li>Faktury z wstrzymaniem płatności</li><li>Szczegóły faktur z wstrzymaniem płatności</li><li>Faktury z wstrzymaniem płatności wg firm</li><li>Faktury z wstrzymaniem płatności wg grup dostawców</li></ul> |

