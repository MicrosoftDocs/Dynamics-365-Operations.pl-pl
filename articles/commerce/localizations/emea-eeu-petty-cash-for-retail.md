---
title: Zarządzanie gotówką podręczną w aplikacji Commerce dla Europy Wschodniej
description: W tym temacie opisano sposób konfigurowania i używania funkcji zarządzania środkami pieniężnymi w aplikacji Commerce dla Europy Wschodniej.
author: epopov
manager: annbe
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Retail, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: b7c7c63083dceebe73bfa04169a0b2da3228c8b1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004716"
---
# <a name="petty-cash-management-for-commerce-for-eastern-europe"></a>Zarządzanie gotówką podręczną w aplikacji Commerce dla Europy Wschodniej

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje dotyczące lokalizacji dla Europy Wschodniej i specyficznej dla branży handlowej.

Zgodnie z wymaganiami dotyczącymi księgowania w krajach Europy Wschodniej operacje kont kasowych można skonfigurować do automatycznego przetwarzania paragonów, dokumentów kasowych i raportów kasowych. Aby uzyskać więcej informacji, zobacz [(EEUR) Konfigurowanie parametrów zarządzania gotówką](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/eeur-set-up-parameters-for-cash-management).

Sprzadawcy detaliczni mogą akceptować różne typy płatności w zamian za produkty i usługi, które sprzedają. Jakkolwiek środki pieniężne to najczęściej używana forma płatności, sprzedawcy detaliczni mogą również pobierać płatności w formie czeków, kart lub załączników. W punkcie sprzedaży detalicznej, kasa przetwarza gotówkę, paragony z kart kredytowych i inne płatności.

Przy użyciu zarządzania środkami pieniężnymi w aplikacji Commerce można wykonać następujące czynności:

- Utwórz konto środków pieniężnych dla metody płatności wybranej dla każdego sklepu.
- Umożliwia korzystanie z arkuszy kasowych w celu księgowania transakcji kasowych i płatności odbiorcy , które są przyjmowane w punkcie sprzedaży detalicznej.
- Agregowanie transakcji w wierszu zestawienia podczas księgowania zestawienia. Można agregować przekazywanie pieniędzy do sejfu i banku, transakcje na załącznikach, transakcje usunięcia środków płatniczych, transakcje deklaracji przyjęcia do kasy, transakcje przychodów, transakcje wydatków, płatności odbiorcy, transakcje sprzedaży i transakcji zwrotu.

Wszystkie transakcje, które miały miejsce w module punktu sprzedaży detalicznej POS, są księgowane w arkuszu księgi. Arkusze płatności gotówkowych, arkusze płatności odbiorcy i arkusze finansowe służą do tworzenia i księgowania zestawień. Aby uzyskać więcej informacji, zobacz [Tworzenie, obliczanie i księgowanie zestawień dla sklepu sieci sprzedaży](https://docs.microsoft.com/dynamics365/unified-operations/retail/tasks/create-calculate-post-statement-retail-store).

Na stronie **Zaksięgowane zestawienia** w okienku akcji można wykonać następujące czynności:

- Wybierz kolejno opcje **Informacje \> Arkusz płatności gotówką**, aby uzyskać dostęp do arkuszy płatności gotówkowych powiązanych z zestawieniem.
- Wybierz kolejno opcje **Informacje \> Arkusz finansowy** , aby uzyskać dostęp do arkuszy księgi związanych z zestawieniami innych niż płatności odbiorcy i płatności gotówką.

## <a name="set-up-for-cash-management-for-pos"></a>Konfiguracja zarządzania gotówką dla programu POS

Przed użyciem zarządzania gotówką, należy wykonać poniższą procedurę konfiguracji:

- Na stronie **Metody płatności** skonfiguruj metody płatności dla każdego typu płatności akceptowanego przez sprzedawcę detalicznego. Można używać różnych metod płatności do księgowania transakcji w POS. Aby uzyskać więcej informacji o metodach płatności, zobacz [Metody płatności](https://docs.microsoft.com/dynamics365/unified-operations/retail/payment-methods).
- Skonfiguruj parametry dla operacji gotówkowych.
- Ustaw metodę płatności dla płatności gotówką w sklepie.

### <a name="set-up-parameters-for-cash-operations"></a>Skonfiguruj parametry dla operacji gotówkowych

Można skonfigurować parametry, aby utworzyć i zaksięgować transakcje gotówkowe w Commerce. Można użyć arkuszy płatności gotówkowych, arkuszy płatności odbiorcy lub arkuszy finansowych do księgowania transakcji sprzedaży i płatności w POS. Można zagregować transakcje, które mają te same właściwości, podczas księgowania zestawienia.

1. Wybierz kolejno opcje **Commerce \> Ustawienia central \> Parametry \> Parametry Commerce**. W lewym okienku kliknij opcję **Księgowanie**.
2. W obszarze **Księgowanie** na skróconej karcie **Agregacja** w opcji **Usunięcie/zmiana środków płatniczych** ustaw wartość **Tak**, aby agregować transakcje usunięcia lub przyjęcia środków płatniczych, które są skojarzone z wierszem zestawienia podczas księgowania zestawienia. Transakcja usunięcia środków płatniczych jest tworzona podczas wypłaty gotówki z szuflady kasowej w punkcie sprzedaży. Transakcja przyjęcia środków płatniczych jest tworzona podczas wpłaty gotówki do szuflady kasowej w punkcie sprzedaży.
3. Aktywuj poszczególne parametry wymienione poniżej, aby agregować transakcje, które są skojarzone z wierszem zestawienia podczas księgowania zestawienia:

    - **Przekazanie pieniędzy do banku** — Agregowanie transakcji bankowych.
    - **Przekazanie do sejfu** — Agregowanie transakcji przekazania do sejfu.
    - **Transakcje przychodów/wydatków** — Agregowanie transakcji wpływu/wpłaty lub wypływu/wypłaty.
    - **Transakcje na załączniku** — Agregowanie transakcji w załączniku.
    - **Płatności odbiorcy** — Agregowanie płatności od odbiorców.
    - **Sprzedaż i zwroty** — Agregowanie transakcji sprzedaży i zwrotu.

4. Na skróconej karcie **Płatności** wybierz domyślną nazwę arkusza dla następujących opcji:

    - **Arkusz płatności odbiorcy** — Ten arkusz jest używany do księgowania płatności od odbiorców.
    - **Arkusz płatności gotówką** — Ten arkusz jest używany do księgowania płatności gotówką.
    - **Arkusz finansowy** — Ten arkusz jest używany do księgowania transakcji innych niż płatności gotówkowe i płatności od odbiorców.

### <a name="set-up-a-payment-method-for-cash-payments-in-a-store"></a>Ustaw metodę płatności dla płatności gotówką w sklepie

Poniższa procedura umożliwia konfigurowanie metody płatności dla płatności gotówką w sklepie.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Kanały \> Sklepy \> Wszystkie sklepy**.
2. Na stronie listy **Wszystkie sklepy** wybierz sklep, dla którego chcesz skonfigurować metodę płatności.
3. W okienku akcji na karcie **Konfiguracja** w grupie **Konfiguracja** kliknij opcję **Metody płatności**.
4. Na stronie **Metody płatności** utwórz lub wybierz metodę płatności.
5. Na skróconej karcie **Księgowanie** w grupie pól **Konto** w polu **Typ konta** zaznacz opcję **Konto kasowe**.

    > [!NOTE]
    > Opcję **Konto kasowe** w polu **Typ konta** można wybrać tylko po zaznaczeniu opcji **Normalnie** lub **Usunięcie/zmiana środków płatniczych** w polu **Funkcja**.

6. W polu **Numer konta** wybierz numer konta kasowego dla metody płatności.
7. W grupie pól **Usunięcie/zmiana środków płatniczych** w polu **Konto przeciwstawne** wybierz konto przeciwstawne do księgowania transakcji usunięcia lub deklaracji przyjęcia dla metody płatności.

> [!NOTE]
> Konta przeciwstawne należy skonfigurować dla obu metod płatności używanych w sklepie — wpłacania gotówki oraz usunięcia lub przyjęcia środków płatniczych. Spowoduje to utworzenie zbilansowanych zapisów księgi głównej dla transakcji usunięcia lub przyjęcia środków płatniczych.
