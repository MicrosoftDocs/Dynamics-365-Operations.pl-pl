---
title: "Obszar roboczy zarządzania rachunkami bankowymi"
description: "Ten temat zawiera informacje o obszarze roboczym Zarządzanie rachunkami bankowymi. Ten obszar roboczy pokazuje informacje dotyczące firmowych kont bankowych. Zawiera widok Podsumowanie i stronę Analizy. Widok Podsumowanie zawiera kafelki podsumowań, informacje o rachunkach bankowych, wykres salda i pokrewne informacje. Strona Analizy wykorzystuje funkcje programu Microsoft Power BI, aby pokazywać wizualizacje dotyczące sald na rachunkach bankowych."
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b5d9f9aab56441a7ecd2407b5571de77ece2ab3f
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---
# <a name="bank-management-workspace"></a>Obszar roboczy zarządzania rachunkami bankowymi

[!include[banner](../includes/banner.md)]

Obszar roboczy **Zarządzanie rachunkami bankowymi** zawiera informacje dotyczące firmowych kont bankowych. Ten obszar roboczy zawiera widok **Podsumowanie** i stronę **Analizy**. Widok **Podsumowanie** zawiera kafelki podsumowań, informacje o rachunkach bankowych, wykres salda i pokrewne informacje. Strona **Analizy** wykorzystuje funkcje programu Microsoft Power BI, aby pokazywać wizualizacje dotyczące sald na rachunkach bankowych.

## <a name="summary-view"></a>Widok Podsumowanie

### <a name="summary"></a>Sumarycznie

Kafelki w sekcji **Podsumowanie** prezentują przegląd firmowych kont bankowych i umożliwiają szybki dostęp do najczęściej używanych stron. Informacje o uzgodnieniach kont bankowych są specyficzne dla funkcjonalności Zaawansowane uzgadnianie konta bankowego. Informacje są podawane tylko dla tych kont bankowych, które na stronie **Konto bankowe** w opcji **Zaawansowane uzgadnianie konta bankowego** mają ustawioną opcję **Tak**. Z sekcji **Podsumowanie** można importować elektroniczne pliki bankowe dla rachunków bankowych ze wszystkich firm.

### <a name="bank-accounts"></a>Konta bankowe

Każde konto bankowe w firmie jest reprezentowana przez kartę w sekcji **Konta bankowe**. Jest wyświetlane bieżące saldo i możesz przejść do szczegółów transakcji, które składają się na sumaryczną wartość salda. Również z pola kwoty **Transakcje pomostowe** można przechodzić do szczegółów transakcji składających się na łączną kwotę. Transakcjami pomostowymi są wszelkie transakcje oczekujące, które zostały zaksięgowane w za pomocą funkcji transakcji pomostowej, ale nie zostały jeszcze rozliczone. Kwota **Saldo oczekujące** jest bieżącym saldem pomniejszonym o kwoty z transakcji pomostowych (oczekujących).

Karta pokazuje także, kiedy konto bankowe było po raz ostatni uzgadniane. Te informacje są wyświetlane tylko wtedy, gdy dla rachunku bankowego włączono opcję Zaawansowane uzgadnianie konta bankowego.

### <a name="balance"></a>Bilansowe

Wykres **Saldo** przedstawia historyczne informacje o saldzie dla konta bankowego wybranego w sekcji **Konta bankowe** lub podsumowanie historycznych informacji o saldach dla wszystkich kont bankowych w firmie. Informacje te są dostępne dla różnych okresów: bieżącego tygodnia, bieżącego miesiąca, bieżącego roku, ostatnich pięciu lat i dla wszystkich okresów (pełna historia konta bankowego). 

Jeśli wyświetlasz wykres **Saldo** dla pojedynczego konta bankowego, salda historyczne są pokazywane w walucie konta bankowego. Jeśli wyświetlasz wykres dla wszystkich rachunków bankowych w firmie, salda historyczne są pokazywane w walucie rozliczeniowej.

Informacje o dacie ostatniej aktualizacji danych są wyświetlane w górnej części wykresu. W razie potrzeby można aktualizować dane.

### <a name="related-information"></a>Informacje pokrewne

Z sekcji **Informacje pokrewne** można otworzyć stronę **Arkusz finansowy**, aby wykonać przelewy bankowe. Można także szybko otworzyć strony **Transakcje bankowe** i **Transakcje pomostowe**.

## <a name="analytics-view"></a>Widok Analizy

Strona **Analizy** zawiera ważne wskaźniki dotyczące kont bankowych w bieżącej firmie. Na stronie są dostępne następujące wizualizacje:

-   Łączne saldo rachunków bankowych w walucie systemowej
-   Saldo wg firmy
-   Dzisiejsze saldo rzeczywiste w porównaniu z prognozowanym w walucie konta bankowego
-   Saldo wg konta bankowego
-   Saldo wg waluty

Analizy rachunków bankowych ze wszystkich firm można przeglądać w obszarze roboczym **Przegląd środków pieniężnych — wszystkie firmy**.

