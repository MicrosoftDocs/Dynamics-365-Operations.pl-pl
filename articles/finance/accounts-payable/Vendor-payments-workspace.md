---
title: Obszar roboczy płatności dla dostawców
description: Ten temat zawiera informacje o komórkowym obszarze roboczym Płatności dla dostawców. Obszar roboczy Płatności dla dostawców zawiera informacje związane z przetwarzaniem płatności dla dostawców.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymentWorkspace
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 34f4e22f571569a6276f8a801d33c6afef8480dc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979570"
---
# <a name="vendor-payments-workspace"></a>Obszar roboczy płatności dla dostawców

[!include [banner](../includes/banner.md)]

Obszar roboczy **Płatności dla dostawców** zawiera informacje związane z przetwarzaniem płatności dla dostawców. Ten obszar roboczy zawiera widok **Moja praca** i stronę **Analizy**. Widok **Moja praca** zawiera kafelki podsumowań, siatki transakcji z dostawcami i informacje o odnośnych dostawcach. Strona **Analizy** wykorzystuje funkcje programu Microsoft Power BI, aby pokazywać wizualizacje dotyczące płatności dla dostawców.

## <a name="setup-needed-to-view-power-bi-content"></a>Konfiguracja potrzebna do wyświetlenia zawartości Power BI.

Aby dane były wyświetlane w elementach wizualnych **Płatność dostawców** Power BI, należy wykonać następujące czynności konfiguracyjne.
1. Otwórz **Administracja Systemu > Konfiguracja > Parametry Systemu** i ustaw **Walutę systemu** oraz **Kurs wymiany systemu**.
2. Umożliwia przejście do **Księga główna > Kalendarze > Kalendarze obrachunkowe** w celu weryfikacji dat kalendarza obrachunkowego przypisanych do aktywnego okresu.
3. Przejdź do ustawień **Księga główna > Ustawienie > Księga** aby określić **Waluta rozliczeniowa** i **Typ kursu wymiany**. 
4. Zdefiniuj kursy wymiany między walutami transakcji a walutą księgową, walutą księgową a walutą systemu. Żeby to zrobić, otwórz **Księga Ogólna > Waluty > Kursy wymiany walut**.
5. Przejdź do **Administracja systemu > Ustawienie > Magazynu jednostki**, aby odświeżyć **VendPaymentBIMeasureV2** miarę agregacji.

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


|            Strona raportu            |                                                                                                                                                                                Wizualizacja                                                                                                                                                                                |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Przegląd płatności dla dostawcy      | <ul><li>Zaległe faktury</li><li>Faktury należne dzisiaj</li><li>Rabaty otrzymane do rabatów utraconych</li><li>Faktury należne w przyszłości wg daty rabatu gotówkowego</li><li>Faktury należne w przyszłości wg terminu zapłaty</li><li>Faktury zapłacone z opóźnieniem do faktur zapłaconych na czas</li><li>Przypisanie przepływu pracy płatności</li><li>Saldo dostawcy do salda odbiorcy</li><li>Otwarte faktury z wstrzymaniem płatności</li></ul> |
|         Zaległe faktury         |                                                                                             <ul><li>Zaległe faktury</li><li>Szczegóły zaległych faktur</li><li>Otwarte faktury razem</li><li>Zaległe faktury wg grup dostawców</li><li>Zaległe faktury wg firm</li></ul>                                                                                              |
|        Faktury należne dzisiaj         |                                                                                                         <ul><li>Faktury należne dzisiaj</li><li>Szczegóły faktur należnych dzisiaj</li><li>Faktury należne dzisiaj wg firm</li><li>Faktury należne dzisiaj wg grup dostawców</li></ul>                                                                                                          |
| Rabaty otrzymane do rabatów utraconych |                                                                             <ul><li>Rabaty otrzymane do rabatów utraconych</li><li>Szczegóły rabatów otrzymanych do rabatów utraconych</li><li>Rabaty otrzymane do rabatów utraconych wg firm</li><li>Rabaty otrzymane do rabatów utraconych wg grup dostawców</li></ul>                                                                              |
|      Faktury należne w przyszłości       |                                                 <ul><li>Faktury należne w przyszłości</li><li>Szczegóły faktur należnych w przyszłości</li><li>Faktury należne w przyszłości wg firm</li><li>Faktury należne w przyszłości wg grup dostawców</li><li>Faktury należne w przyszłości wg daty rabatu gotówkowego</li><li>Faktury należne w przyszłości wg terminu zapłaty</li></ul>                                                  |
|        Faktury zapłacone z opóźnieniem         |                                                         <ul><li>Faktury zapłacone po terminie zapłaty</li><li>Szczegóły faktur zapłaconych po terminie zapłaty</li><li>Faktury zapłacone po terminie zapłaty wg firm</li><li>Faktury zapłacone po terminie zapłaty wg grup dostawców</li><li>Faktury zapłacone z opóźnieniem do faktur zapłaconych na czas</li></ul>                                                          |
|         Przepływ pracy płatności          |                                                                                <ul><li>Wystąpienia przepływu pracy płatności dostawcom</li><li>Wystąpienia przepływu pracy płatności dostawcom wg osób zatwierdzających</li><li>Wystąpienia przepływu pracy płatności dostawcom wg firm</li><li>Średnia liczba dni w przepływie pracy wg osób zatwierdzających</li></ul>                                                                                |
|    Saldo dostawcy do salda odbiorcy     |                                                                                                                   <ul><li>Saldo dostawcy do salda odbiorcy</li><li>Saldo dostawcy do salda odbiorcy wg firm</li><li>Szczegóły salda dostawcy do salda odbiorcy</li></ul>                                                                                                                    |
|    Faktury z wstrzymaniem płatności     |                                                                                         <ul><li>Faktury z wstrzymaniem płatności</li><li>Szczegóły faktur z wstrzymaniem płatności</li><li>Faktury z wstrzymaniem płatności wg firm</li><li>Faktury z wstrzymaniem płatności wg grup dostawców</li></ul>                                                                                          |

