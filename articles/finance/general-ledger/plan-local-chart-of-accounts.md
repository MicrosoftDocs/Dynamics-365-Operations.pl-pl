---
title: Planowanie lokalnego planu kont
description: Ten artykuł zawiera informacje, które pomogą zaplanować plan kont, gdy są spełnione ustawowe/lokalne wymagania dotyczące organizacji.
author: VeselinaE
ms.date: 10/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount, DimensionDetails, MainAccountDetails
ROBOTS: ''
audience: Application User
ms.devlang: ''
ms.reviewer: twheeloc
ms.tgt_pltfrm: ''
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.search.industry: ''
ms.author: veneva
ms.search.validFrom: 10/07/2021
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78379fd51cf24985fce83e2b6aa9a475af7df363
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946253"
---
# <a name="plan-your-local-chart-of-accounts"></a>Planowanie lokalnego planu kont

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje, które pomogą zaplanować plan kont, gdy organizacja obejmuje firmy, które muszą spełniać wymagania określone w określonych lokalizacjach, w których prowadzą działalność. W tym artykule przedstawiono następujące terminy opisujące plan kont:

- **Globalny** — plan kont, który jest używany globalnie przez organizację. W większości przypadków skonsolidujesz z tym planem kont.
- **Lokalny** — plan kont, którego używają firmy w konkretnym kraju lub regionie.
- **Udostępniony** — plan kont używany przez ponad jedną firmę. Można udostępniać zarówno globalny, jak i lokalny plan kont.

Istnieje możliwość tworzenia i udostępniania wielu planów kont. Udostępniony plan kont może być używany przez więcej niż jedną firmę, ale tylko jeden plan kont może być przypisany do każdej firmy. Plan kont używany przez firmę definiuje się na stronie **Księga**.

Podczas projektowania planu kont wiele organizacji stara się utworzyć globalny plan kont. Możliwość udostępniania planu kont umożliwia tworzenie globalnego planu kont. Tworzenie i używanie pojedynczego planu kont ma swoje korzyści. Na przykład ład i kontrola, konserwacja i raportowanie są łatwiejsze.

Większość organizacji preferuje globalny plan kont i jest to najprostszy typ do zaimplementowania. Mimo tego niektóre firmy wymagają lokalnego planu kont z następujących przyczyn:

- Lokalne wymagania ustawowe
- Wymagania lokalnych standardów księgowania
- Wymagania branżowe
- Specyficzne dla firmy wymagania dotyczące raportowania i analizy

Jeśli organizacja wymaga, aby firma używała lokalnego planu kont, do implementacji są dostępne dwie opcje:

- Przypisz globalny plan kont i zdefiniuj inne sposoby spełniania wymagań lokalnych.
- Przypisz lokalny plan kont do firmy i zdefiniuj relacje z globalnym planem kont.

Od używanej opcji zależy struktura organizacji i struktura raportowania.

[![Diagram pokazujący sposób, w jaki struktura organizacji określa, czy używać globalnego, czy lokalnego planu kont](./media/local-chart-of-accounts-diagram.png)](./media/local-chart-of-accounts-diagram.png)

Jeśli globalny plan kont jest przypisany do firmy, są dostępne następujące opcje spełniania wymagań w zakresie lokalnego raportowania:

- Przeprowadź konsolidację lokalną.
- Użyj wymiaru finansowego do śledzenia lokalnego planu kont.
- Utwórz lokalne konta główne w globalnym planie kont.
- Wykonaj mapowanie zewnętrzne na lokalny plan kont.

Jeśli lokalny plan kont jest przypisany do firmy, jedyną obecnie dostępną opcją do spełnienia globalnych wymagań raportowania jest konsolidacja globalna.

## <a name="global-chart-of-accounts-assigned-to-a-legal-entity"></a>Globalny plan kont przypisany do firmy

Jeśli trzeba przypisać globalny plan kont do firmy, jak opisano wcześniej, będą dostępne cztery opcje konfigurowania systemu. W przypadku wszystkich czterech opcji jeden plan kont jest konfigurowany i połączony z każdą firmą na stronie **Księga**. Każda z opcji korzysta z innego podejścia w celu spełnienia wymagań dotyczących lokalizacji. W poniższych sekcjach przedstawiono kroki wysokiego poziomu niezbędne do skonfigurowania systemu pod potrzeby lokalizacji. Opisano w nich także korzyści i wady poszczególnych opcji.

### <a name="do-local-consolidation"></a>Przeprowadzenie konsolidacji lokalnej

Konsolidacja lokalna jest zalecanym podejściem do spełniania wymagań lokalnego planu kont i korzystania z zaprojektowanych do tego celu funkcji systemu.

#### <a name="set-up-consolidation-for-a-local-chart-of-accounts"></a>Konfigurowanie konsolidacji dla lokalnego planu kont

1. Utwórz pojedynczy globalny plan kont, który zawiera wszystkie wymagane konta główne.
2. W każdej firmie przypisz globalny plan kont na stronie **Księga**.
3. Utwórz firmę konsolidacji dla każdej wymaganej lokalizacji.
4. Wykonaj jeden z następujących kroków:

    - Jeśli wymagana jest tylko jedna lokalizacja, należy skonfigurować konto konsolidacyjne na stronie **Konto główne** lub użyć stron **Grupy konsolidacji** i **Dodatkowe konta konsolidacji**.
    - Jeśli wymagana jest więcej niż jedna lokalizacja lub zarówno numer konta, jak i nazwa konta wymagają tłumaczenia, użyj stron **Grupy konsolidacji** i **Dodatkowe konta konsolidacji** w celu reprezentacji wymagań dotyczących lokalizacji.

5. Uruchom proces konsolidacji, aby przekształcić wartość ze źródłowej firmy, która używa globalnego planu kont do konsolidowanej firmy, która używa lokalnego planu kont.

#### <a name="advantages"></a>Zalety

- To podejście zapewnia spójny sposób pracy w całej organizacji.
- Tłumaczenie stanowiska lokalnego jest zakończone.
- Ta metoda obsługuje tłumaczenie zarówno identyfikatora konta głównego, jak i nazwy każdego konta głównego.
- Obsługuje wiele lokalizacji.

#### <a name="disadvantages"></a>Wady

- Zostanie utworzona dodatkowa firma konsolidacyjna.
- Został zakończony proces dodatkowej konsolidacji.
- To podejście może raportować w lokalnym planie dopiero po zakończeniu procesu konsolidacji.

### <a name="use-a-financial-dimension-to-track-the-local-chart-of-accounts"></a>Używanie wymiaru finansowego do śledzenia lokalnego planu kont

W tym podejściu jest używany wymiar finansowy, w którym wartości wymiarów finansowych reprezentują lokalne konta główne wymagane do lokalizacji. Działa dobrze, jeśli wymagana jest tylko jedna lokalizacja. Jednak będzie to mniej użyteczne w przypadku dodawania kolejnych lokalizacji i wymiarów finansowych.

#### <a name="set-up-a-financial-dimension-for-a-local-chart-of-accounts"></a>Ustawianie wymiaru finansowego dla lokalnego planu kont

1. Utwórz pojedynczy globalny plan kont, który zawiera wszystkie wymagane konta główne.
2. W każdej firmie przypisz globalny plan kont na stronie **Księga**.
3. Utwórz wymiar finansowy, które reprezentuje lokalny plan kont.
4. Utwórz wartości wymiaru finansowego, które reprezentują konta główne i lokalnym planie kont.
5. Zaktualizuj strukturę konta, tak aby zawierała wymiar finansowy „plan kont”.
6. Upewnij się, że wymiar finansowy „lokalny plan kont” zawsze miał wartość i że nie zezwala na pozostawienie wartości pustej. Rozważ użycie wymiarów pochodnych lub stałych.
7. Utwórz zestaw wymiarów finansowych, w którym wymiar finansowy „lokalny plan kont” jest pierwszym wybranym wymiarem finansowym. Zestaw wymiarów finansowych może być używany podczas generowania bilansu próbnego.

#### <a name="advantages"></a>Zalety

- Na poziomie transakcji istnieją konta główne zarówno globalne, jak i lokalne. Konto główne jest kontem globalnym, a wartość wymiaru finansowego lokalna.
- Dzięki temu podejściu dostępne jest raportowanie w czasie rzeczywistym i widoki zarówno globalnego stanowiska finansowego, jak i lokalnego.

#### <a name="disadvantages"></a>Wady

- Jeśli w parametrach księgi głównej w polu **Wartości używane dla konta podsumowującego** jest ustawiona wartość **Zasady podziału księgowości**, wymiary finansowe reprezentujące konto główne wydatków/składników majątku/przychodów będą niepoprawnie używane na koncie podsumowującym rozrachunków z odbiorcami i rozrachunków z dostawcami. Zamiast tego zaleca się ustawienie w tym polu dokumentu źródłowego, aby upewnić się, że będą używane poprawne wartości wymiarów finansowych.
- Jeśli jest wymaganych wiele lokalnych planów kont, a dla każdego z nich jest używany jeden wymiar finansowy, lista użytych wartości wymiarów finansowych może być długa i trudno będzie z nią pracować.
- Jeśli jest wymaganych wiele lokalnych planów kont, a do ich przedstawienia jest używany oddzielny wymiar finansowy, dodanie wymiarów finansowych i zestawów wymiarów finansowych może mieć wpływ na użyteczność i wydajność systemu.
- Zaleca się uważne rozważenie liczby wymaganych wymiarów finansowych, liczby wartości w każdym z nich oraz liczby zestawów wymiarów finansowych, ponieważ wszystkie te czynniki mogą wpływać na wydajność systemu.

### <a name="create-local-main-accounts-in-the-global-chart-of-accounts"></a>Tworzenie lokalnego konta głównego w globalnym planie kont

*O co prosił redaktor:* W tym podejściu lokalne konta główne w globalnym planie kont zawierają konta główne w lokalnym planie kont w globalnym planie kont.

*Wersja oryginalna:* Lokalne konta główne w ramach globalnego certyfikatu analizy oznacza, że lokalne konta główne certyfikatu analizy są zawarte w globalnym certyfikacie analizy.

*Co powinno być powiedziane:* W tym podejściu lokalne konta główne w lokalnym planie kont są uwzględniane w globalnym planie kont.


#### <a name="set-up-local-main-accounts-in-the-global-chart-of-accounts"></a>Ustawianie lokalnego konta głównego w globalnym planie kont

1. Utwórz pojedynczy plan kont, który zawiera konta główne zarówno dla globalnego, jak i lokalnego planu kont.
2. W każdej firmie przypisz plan kont na stronie **Księga**.
3. Utwórz konta sum w planie kont, aby zsumować konta główne reprezentujące ten sam cel.
4. Utwórz zastąpienia firmy dla poszczególnych kont lokalnych, aby zapobiec transakcjom z innych firm, dla których konto lokalne nie zostało zaprojektowane.
5. Utwórz zastąpienia firmy dla każdego konta globalnego, aby zapobiec transakcjom z firm lokalizacji.

#### <a name="advantages"></a>Zalety

- Widok w czasie rzeczywistym zarówno globalnej, jak i lokalnej pozycji finansowej jest dostępny w określonych raportach i w określonych widokach w systemie, na przykład w raporcie bilansu finansowego. Jest on również dostępny za pomocą przycisku **Okres** na koncie sum.
- Nie masz dodatkowego segmentu na koncie księgi.

#### <a name="disadvantages"></a>Wady

- Całkowite użycie konta i widoczność są ograniczone. Na przykład konta sum nie są widoczne na stronie listy **Bilans próbny**.
- Konserwacja wymaga dodatkowego nakładu pracy.
- Tworzenie raportów finansowych wymaga ręcznego nakładu pracy.

### <a name="do-external-mapping-to-the-local-chart-of-accounts"></a>Wykonywanie mapowania zewnętrznego na lokalny plan kont

Przyjęcie globalnego planu kont zakłada, że użytkownik zarządza mapowaniem i lokalizacjami poza systemem. W tym przypadku wystarczy utworzyć jeden globalny plan kont w rozwiązaniu Microsoft Dynamics 365 Finance i spełnić wymagania spoza systemu.

#### <a name="set-up-external-mapping-to-a-local-chart-of-accounts"></a>Ustawianie mapowania zewnętrznego na lokalny plan kont

1. Utwórz pojedynczy globalny plan kont, który zawiera wszystkie wymagane konta główne.
2. W każdej firmie przypisz globalny plan kont na stronie **Księga**.
3. Wykonywanie mapowania na lokalny plan kont poza rozwiązaniem Finance.

#### <a name="advantages"></a>Zalety

- To podejście zapewnia ujednolicone sposoby pracy w całej organizacji.

#### <a name="disadvantages"></a>Wady

- Brak dostępnych raportów lokalnych z systemu.
- Podczas tworzenia raportów finansowych ta metoda może być błędna.

## <a name="local-chart-of-accounts-assigned-to-legal-entity"></a>Lokalny plan kont przypisany do firmy

Jeśli organizacja zdecyduje się nie używać globalnego planu kont dla wszystkich firm, dla każdego lokalnego planu kont tworzony jest oddzielny plan kont. Następnie każda firma jest łączona z odpowiednim planem kont na stronie **Księga**.

### <a name="do-global-consolidation"></a>Przeprowadzenie konsolidacji globalnej

W tym podejściu konsolidowana firma jest używana do zwijania i łączenia sald poszczególnych źródłowych firm lokalnych w połączony globalny plan kont w firmie konsolidacyjnej. W tym celu należy zarządzać mapowaniem poszczególnych lokalnych planów kont na globalny plan kont w firmie konsolidacyjnej.

#### <a name="set-up-global-consolidation"></a>Ustawianie konsolidacji globalnej

1. Utwórz osobny plan kont dla każdej firmy, która ma inny lokalny plan kont. Jeśli dowolna firma ma ten sam lokalny plan kont, wymagany jest tylko jeden lokalny plan kont i można go udostępniać.
2. W każdej firmie przypisz odpowiedni plan kont na stronie **Księga**.
3. Opcjonalnie: utwórz plan kont dla globalnego planu kont każdej firmy konsolidacyjnej, która ma inny globalny plan kont.
4. Utwórz firmę konsolidacyjną dla każdego wymaganego poziomu konsolidacji i przypisz odpowiedni plan kont na stronie **Księga**.
5. Wykonaj jeden z następujących kroków:

    - Jeśli wymagana jest tylko jedna konsolidacja, skonfiguruj konto konsolidacyjne na stronie **Konto główne**.
    - Jeśli wymagana jest więcej niż jedna konsolidacja lub zarówno numer konta, jak i nazwa konta wymagają tłumaczenia, użyj stron **Grupy konsolidacji** i **Dodatkowe konta konsolidacji** w celu reprezentacji wymagań dotyczących globalnego planu kont.

6. Uruchom proces konsolidacji, aby przenieść salda z firm lokalnych do firmy skonsolidowanej. Ta firma skonsolidowana używa kont konsolidacyjnych określonych w kroku 5.

#### <a name="advantages"></a>Zalety

- Lokalny format standardów księgowania jest stosowany w macierzyście.
- Dzięki temu lokalnemu zespołowi finansowemu będzie łatwiej pracować.

#### <a name="disadvantages"></a>Wady

- Brak dostępnego widoku globalnego stanowiska w czasie rzeczywistym.
- Proces konsolidacji może być częściej uruchamiany.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Planowanie planu kont](plan-chart-of-accounts.md)
- [Konfigurowanie ksiąg](configure-ledger.md)
- [Wymiary finansowe i księgowanie](Default-dimensions.md#balancing-dimension)
- [Zestawy wymiarów finansowych](financial-dimension-sets.md)
- [Omówienie konsolidacji i eliminacji](../budgeting/consolidation-elimination-overview.md)
- [Grupy kont konsolidacyjnych i dodatkowe konta konsolidacyjne](../budgeting/consolidation-account-groups-consolidation-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
