---
title: "Zamknięcie na koniec roku"
description: "W tym temacie opisano wymagane instalacji i kroków umożliwiających uruchomienie procesu zamknięcia na koniec roku księgi głównej."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 926ee087a0e0c4743f29315b1d82c7d37e95be28
ms.openlocfilehash: 22233cfa1df79076c8ea42f75ea309bac990d574
ms.lasthandoff: 03/31/2017


---

# <a name="year-end-close"></a>Zamknięcie na koniec roku

W tym temacie opisano wymagane instalacji i kroków umożliwiających uruchomienie procesu zamknięcia na koniec roku księgi głównej. 

Na koniec roku obrachunkowego należy uruchomić proces Zamknij na koniec roku do przenoszenia sald otwarcia do nowego roku. Większość organizacji będzie uruchamiać wiele razy proces zamknięcia na koniec roku. Po raz pierwszy byłoby uzyskać sald przeniesione do nowego roku obrachunkowego. Zamknięcia na koniec roku można następnie uruchomić ponownie, jak wiele razy są wymagane do przenoszenia sald z dostosowania wpisów do nowego roku obrachunkowego. 

Proces zamykania podczas koniec roku, istnieją dwa typy możliwe transakcje utworzone. Transakcja otwarcia zawsze jest generowany i jest używany do tworzenia sald otwarcia w nowym roku obrachunkowym. Transakcja otwarcia Pokazuje salda kont księgi bilansu w nowym roku obrachunkowym i sald z sald konta księgowe zysków i strat na koncie księgowym niepodzielonego zysku lat ubiegłych w nowym roku obrachunkowym. Opcjonalnie tworzenia transakcji zamknięcia przynieść sald kont wynikowych do zera w roku obrachunkowym, są zamknięte.

## <a name="prepare-to-run-the-year-end-close"></a>Przygotowanie do uruchomienia zamknięcie na koniec roku
Przed uruchomieniem procesu zamknięcia na koniec roku należy sprawdzić poprawność ustawień dla następujących elementów: 

Na stronie **Konto główne**:

-   Sprawdź poprawność **typu konta głównego** jest poprawnie zdefiniowany dla każdego konta głównego. Typ konta głównego jest używany do określenia, czy saldo konta głównego zostaną doprowadzone do przodu jako salda otwarcia lub zamkniętych do zysków zatrzymanych w transakcji otwarcia.
-   **Konto otwarcia** pola mogą być używane do przenoszenia salda konta głównego do nowego konta głównego podczas zamknięcia na koniec roku. Nowe konto główne jest wprowadzana w **konto otwarcia** pole. Zazwyczaj to posłuży dla kont bilansu głównego podczas inaktywowany konta głównego i nowe konto główne jest używany dla nowego roku obrachunkowego.

Na **parametrów księgi głównej** strony pod **zamknięcie roku obrachunkowego**:

-   **Usuń zamknięcia transakcji roku** opcja służy do określania, czy transakcja otwarcia generowanych przez system z poprzedniego zamknięcia na koniec roku powinny zostać usunięte, po ponownym uruchomieniu zamknięcia na koniec roku. Jeśli ta opcja jest ustawiona na **tak**, usunąć poprzednich transakcji otwarcia i nowych transakcji otwarcia jest tworzony na podstawie bieżącego salda. Jeśli ta opcja jest ustawiona na **nr**, pozostaje poprzednich transakcji otwarcia i tworzenia dodatkowych transakcji otwarcia do przenoszenia sald do przodu od regulowania transakcje zaksięgowane po Zamknij koniec poprzedniego roku.
-   **Tworzenie transakcji zamknięcia w trakcie przeniesienia** opcja służy do tworzenia transakcji zamknięcia roku obrachunkowego zamykane w celu doprowadzenia do sald kont wynikowych zero. Jeśli ta opcja jest ustawiona na **tak**, transakcja otwarcia i zamknięcia transakcji jest tworzony. Jeśli ta opcja jest ustawiona na **nr**, tylko transakcja otwarcia jest tworzony w następnym roku obrachunkowego do przeniesienia sald. Pozostają sald kont zysków i strat na koniec roku obrachunkowego.
-   **Ustaw stan roku obrachunkowego na stale zamknięta** opcja jest używana do ustawiania roku obrachunkowego do stanu zamkniętego trwale. Tego ustawienia należy używać ostrożnie, ponieważ wszystkie okresy w stanie stale zamknięta nie można otworzyć ponownie, zapobieganie korekt z są księgowane do roku obrachunkowego. Jest najlepszym rozwiązaniem, ustaw tę wartość na **nr**.
-   **Należy podać numer załącznika** opcja jest używana do definiowania czy numer załącznika jest wymagana podczas uruchamiania procesu zamknięcia na koniec roku. Jest najlepszym rozwiązaniem jest wymagają numeru załącznika, aby łatwo zidentyfikować transakcji otwarcia.

Na **kalendarza obrachunkowego** stronę:

-   Kolejnego roku obrachunkowego musi istnieć przed uruchomieniem zamknięcie na koniec roku. Kolejnego roku obrachunkowego jest wymagany w celu utworzenia sald początkowych w okresie otwarcia.

Na **kalendarz księgi** stronę:

-   Opcjonalnie: Każdy okres obrachunkowy dla zamykania roku obrachunkowego można ustawić **wstrzymane** zapobiec wprowadzane nowe transakcje. Gdy wpisy korygujące są identyfikowane, okresy wstrzymania On można otworzyć ponownie do księgowania zapisów regulacji, nawet jeśli proces zamknięcia na koniec roku zostało już uruchomione.

## <a name="define-year-end-close-templates"></a>Definiowanie szablonów zamknięcia na koniec roku
Po skonfigurowaniu systemu można uruchomić proces zamknięcia na koniec roku. Na **zamknięcie na koniec roku** stronie szablonu można zdefiniować dla grupy osób prawnych, dla których proces zamykania koniec roku zostaną uruchomione. Szablon zostanie ponownie na koniec każdego roku blisko, ale mogą być modyfikowane, jeśli ze zmianami w organizacji. 

Najpierw należy zdefiniować **Nazwa grupy** dla szablonu i wybierz kalendarz obrachunkowy. Nazwa grupy należy zidentyfikować grupy podmiotów prawnych, które są włączone.  Na przykład szablony mogą ustawiona na podstawie Geografia, z oddzielnym grupy utworzone dla Ameryki Północnej osób prawnych, osoby prawne EMEA i osoby prawne Azja i PACYFIK. 

Następnie osoby prawne można dodać do szablonu. Osoby prawne mogą być dodawane przez wybranie hierarchii organizacyjnej lub wybierając wymienione osoby prawne. Jeśli wybrano hierarchii organizacyjnej, tylko osoby prawne w ramach hierarchii używających wybranego kalendarza obrachunkowego zostaną dodane do szablonu. Jeśli używasz osoby prawne do dodania do szablonu mogą być dodawane tylko osoby prawne ten sam kalendarz obrachunkowy. Ten sam kalendarz obrachunkowy jest wymagane, ponieważ zamknięcia na koniec roku jest prowadzony przez wybranie roku obrachunkowego, który może się różnić od kalendarza do kalendarza. 

Po dodaniu osoby prawne, należy zdefiniować konta zysków zatrzymanych główne dla każdej firmy. **Data zakończenia ostatniego roku zamknąć** pole będzie aktualizowane za każdym razem uruchomić Zamknij koniec roku firma. 

**Wymiaru finansowego** karta jest używana do definiowania wymiarów finansowych, które będą używane w odniesieniu do transakcji otwarcia. Należy zauważyć, że ustawienia są definiowane są istotne dla tylko wybranej firmy w **osoby prawne** siatki. Instalator będzie powtarzany dla każdej firmy w siatce. 

**Transferu wymiary bilans** służy do określenia, czy wymiary finansowe dotyczące transakcji zaksięgowanych na kontach bilansu powinny być utrzymane w odniesieniu do transakcji otwarcia. Jest najlepszym rozwiązaniem, aby ustawić tę opcję na **tak**. **Transferu zysków i strat wymiary** jest używana do definiowania, które wymiary finansowe na transakcje zaksięgowane dla zysków i strat zostanie przeniesiona na konto główne niepodzielonego zysku lat ubiegłych. Najpierw należy zidentyfikować wymiarów finansowych istotne dla wybranej firmy. Obejmowałoby to wymiary finansowe zaksięgowane w roku, nawet jeśli wymiar finansowy nie jest częścią struktury konta aktywne. Następnie należy zdefiniować każdego wymiaru jako **Zamknij pojedynczy** lub **Zamknij wszystkie**.  Wartością domyślną jest **Zamknij wszystkie**, zapewniający zachowanie oryginalnego wymiaru finansowego wartości z zaksięgowanych transakcji, które są wykorzystywane do tworzenia otwarcie salda na koncie zysków zatrzymanych. Oddzielne niepodzielonego zysku lat ubiegłych salda początkowe zostanie utworzony dla każdej unikatowej kombinacji wartości wymiaru finansowego. Jeśli **Zamknij pojedynczy** jest zaznaczona, wszystkie transakcje zaksięgowane z tego wymiaru finansowego zostaną podsumowane w zysków zatrzymanych, począwszy od salda dla wartości wymiaru wprowadzony w polu po **Zamknij pojedynczy**. Na przykład załóżmy, że wszystkie transakcje dla roku obrachunkowego zostały umieszczone ze struktury konta konta główne — dział. W wymiarze Dział finansowy na tym szablonie **Zamknij pojedynczy** jest zaznaczone, 100 oznacza wartość wprowadzona. Jeśli całkowity dochód wszystkie transakcje zaksięgowane do działów, 200, 300 i 400 jest $100,000, jeden saldo otwarcia zostaną utworzone dla niepodzielony zysk - 100. Jeśli wybierzesz **Zamknij pojedynczy** i pozostaw pustą wartość wymiaru finansowego, wszystkie transakcje będą publikowane w niepodzielonego zysku lat ubiegłych z tą wartością wymiaru jest pusta. 

Proces zamknięcia na koniec roku nie stosować się do struktury konta. To dlatego struktur kont można zmienić w ciągu całego roku obrachunkowego i nie zawsze jest możliwe ustalenie struktury konta istotne ze względu na te zmiany.  Podczas tworzenia transakcji otwarcia salda zostaną doprowadzone do przodu z wymiarów finansowych zgodnie z definicją w szablonie Zamknij koniec roku. Wpisy salda początku mogą obejmować wymiarów finansowych już w rachunku bieżącym struktury i segment kombinacje, które są już nieważne w strukturze bieżącego konta. Jeśli organizacja chce wykluczyć wymiaru finansowego dla podzielonego zarabiać saldo, początkowe ustawia wymiaru finansowego za **Zamknij pojedynczy** i pozostaw puste wartości wymiaru.

## <a name="run-the-year-end-close-process"></a>Uruchomić proces zamknięcia na koniec roku
Po utworzeniu szablony zamknięcia na koniec roku, na koniec roku Zamknij proces jest inicjowany przez wybranie **uruchomić roku obrachunkowego** w okienku akcji. Zaznacz wszystkich lub niektórych podmiotów prawnych z szablonu do uruchomienia zamknięcie na koniec roku. Po zamknięciu uruchomiona na koniec roku, po raz pierwszy w roku obrachunkowym, prawdopodobnie wybierze wszystkie podmioty prawne utworzyć salda początkowe dla wszystkich osób prawnych. Jeśli korzystasz z koniec roku blisko ponownie, istnieje możliwość uruchomienia procesu dla tylko osoby prawne dla których wpisy korygujące zostały zaksięgowane. 

Wybierz rok obrachunkowy, który chcesz uruchomić proces Zamknij koniec roku przeciwko. Jeśli istnieje okres zamknięcia więcej niż jeden dla ostatniego okresu roku obrachunkowego, **Nazwa okresu** pola staną się dostępne których okres zamknięcia do księgowania transakcji zamknięcia, można wybrać, jeśli zdefiniowana jest konfiguracja do utworzenia transakcji zamknięcia. 

Załącznik należy wprowadzić numer, który lub może nie być wymagane, w zależności od ustawień w ogóle parametrów księgi. Tego samego numeru załącznika będzie używany dla wszystkich osób prawnych wybrane do procesu Zamknij koniec roku. Numer załącznika nie jest generowany przy użyciu sekwencji numerów. Jest najlepszym rozwiązaniem, aby wprowadzić numer załącznika, nawet jeśli nie jest to wymagane. Wprowadzanie numeru załącznika ułatwia znajdowanie transakcja otwarcia w nowym roku obrachunkowym. Jeśli nie jest wprowadzony numer załącznika, załącznik będzie puste dla transakcji otwarcia. 

Jeśli chcesz odwrócić Zamknij koniec poprzedniego roku dla wybranego roku obrachunkowego, ustaw **Cofnij poprzednie zamknięcie** do **tak**. Zamknięcia na koniec roku zostanie wycofana, ale proces może zostać uruchomiony ponownie w dowolnym momencie. Jeżeli nastąpi odwrócenie kierunku zamknięcia na koniec roku, **zamknąć Data zakończenia ostatniego roku** nie będą dostępne. 

Ustawienia domyślne procesu zamknięcia na koniec roku do uruchamiania w trybie wsadowym. Jest najlepszym rozwiązaniem, aby uruchomić proces w trybie wsadowym, aby umożliwić użytkownikowi powrót do innych działań. Po zakończeniu zamknij proces zakończenia roku **zamknąć Data zakończenia ostatniego roku** zostaną zaktualizowane z datą sesji.

Aby uzyskać więcej informacji, zobacz [zamknięcie księgi głównej na koniec okresu](close-general-ledger-at-period-end.md).


