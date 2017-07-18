---
title: "Zamknięcie na koniec roku"
description: "W tym temacie opisano wymaganą konfigurację i kroki wykonywania procesu zamknięcia roku w księdze głównej."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 50a6a23febc725eb05d30d5db4f97ca699607461
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="year-end-close"></a>Zamknięcie na koniec roku

[!include[banner](../includes/banner.md)]


W tym temacie opisano wymaganą konfigurację i kroki wykonywania procesu zamknięcia roku w księdze głównej. 

Na koniec roku obrachunkowego trzeba uruchomić proces zamknięcia roku, aby przenieść salda otwarcia do nowego roku. Większość organizacji wykonuje proces zamknięcia roku wiele razy. Po raz pierwszy ma to na celu przeniesienie sald do nowego roku obrachunkowego. Następnie można ponownie uruchomić zamknięcie roku dowolną potrzebą liczbę razy, aby przenosić salda z zapisów korygujących do nowego roku obrachunkowego. 

W trakcie procesu zamknięcia roku mogą być tworzone dwa typy transakcji. Transakcja otwarcia jest generowana zawsze i służy do tworzenia sald otwarcia w nowym roku obrachunkowym. Transakcja otwarcia pokazuje salda kont księgowych bilansu w nowym roku obrachunkowym oraz salda z kont księgowych rachunku wyników na koncie księgowym zysków zatrzymanych w nowym roku obrachunkowym. Transakcja otwarcia jest opcjonalnie tworzona w celu sprowadzenia sald kont wynikowych do zera w zamykanym roku obrachunkowym.

## <a name="prepare-to-run-the-year-end-close"></a>Przygotowanie do wykonania zamknięcia roku
Przed uruchomieniem procesu zamknięcia roku należy sprawdzić poprawność następujących ustawień: 

Na stronie **Konto główne**:

-   Sprawdź poprawność ustawienia **Typ konta głównego** dla każdego konta głównego. Atrybut Typ konta głównego jest używany do określenia, czy saldo konta głównego będzie przekazywane do przyszłego okresu jako saldo otwarcia, czy też zamykane do zysków zatrzymanych w transakcji otwarcia.
-   Pole **Konto otwarcia** może służyć do przenoszenia salda konta głównego do nowego konta głównego podczas zamknięcia roku. Nowe konto główne jest wprowadzane w polu **Konto otwarcia**. Zazwyczaj tej opcji używa się do kont głównych bilansu, gdy istniejące konto główne jest dezaktywowane, a dla nowego roku obrachunkowego stosuje się nowe konto główne.

Na stronie **Parametry księgi głównej** w obszarze **Zamknięcie roku obrachunkowego**:

-   Opcja **Usuwanie transakcji zamknięcia roku** służy do określania, czy transakcje otwarcia wygenerowane przez system z poprzedniego zamknięcia roku powinny zostać usunięte podczas ponownego wykonywania procesu zamknięcia roku. Jeśli ta opcja jest ustawiona na **Tak**, poprzednia transakcja otwarcia jest usuwana oraz jest tworzona nowa transakcja otwarcia na podstawie bieżących sald. Jeśli ta opcja jest ustawiona na **Nie**, poprzednia transakcja otwarcia pozostaje oraz jest tworzona dodatkowa transakcja otwarcia w celu przeniesienia sald do następnego okresu z transakcji korygujących zaksięgowanych po poprzednim zamknięciu na roku.
-   Opcja **Tworzenie transakcji zamknięcia w trakcie przeniesienia** służy do tworzenia transakcji zamknięcia w zamykanym roku obrachunkowym w celu wyzerowania sald kont wynikowych. Jeśli ta opcja jest ustawiona na **Tak**, są tworzone transakcje otwarcia i zamknięcia. Jeśli ta opcja jest ustawiona na **Nie**, jest tworzona tylko transakcja otwarcia w następnym roku obrachunkowym w celu przeniesienia sald. Salda kont wynikowych (rachunku wyników) pozostają na koniec roku obrachunkowego.
-   Opcja **Ustaw stan roku obrachunkowego na trwale zamknięty** służy do ustawiania rokowi obrachunkowemu stanu trwałego zamknięcia. Tego ustawienia należy używać ostrożnie, ponieważ okresów o stanie trwałego zamknięta nie można otworzyć ponownie, co uniemożliwia księgowanie korekt w roku obrachunkowym. Najlepszym rozwiązaniem jest ustawić wartość **Nie**.
-   Opcja **Należy podać numer załącznika** jest używana do definiowania, czy numer załącznika jest wymagany podczas wykonywania procesu zamknięcia roku. Najlepszym rozwiązaniem jest wymaganie numeru załącznika, aby łatwo identyfikować transakcję otwarcia.

Na stronie **Kalendarz obrachunkowy**:

-   Przed uruchomieniem procesu zamknięcia roku kolejny rok obrachunkowy musi już istnieć. Następny rok obrachunkowy jest konieczny w celu utworzenia sald początkowych w okresie otwarcia.

Na stronie **Kalendarz księgi**:

-   Opcjonalnie: Każdemu okresowi obrachunkowemu w zamykanym roku obrachunkowym można ustawić status **Wstrzymane**, aby uniemożliwić wprowadzanie nowych transakcji. Gdy zostaną zidentyfikowane zapisy korygujące, okresy wstrzymane można otworzyć ponownie w celu zaksięgowania tych zapisów, nawet jeśli proces zamknięcia roku został już wykonany.

## <a name="define-year-end-close-templates"></a>Definiowanie szablonów zamknięcia roku
Po skonfigurowaniu systemu można uruchomić proces zamknięcia roku. Na stronie **Zamknięcie na koniec roku** można zdefiniować szablon dla grupy firm, dla których będzie wykonywany proces zamknięcia roku. Szablon będzie używany dla każdego wystąpienia procesu zamknięcia roku, ale można go zmodyfikować w razie pojawienia się zmian w organizacji. 

Najpierw należy zdefiniować ustawienie **Nazwa grupy** dla szablonu i wybrać kalendarz obrachunkowy. Nazwa grupy powinna identyfikować grupę firm, do których ma być stosowany szablon.  Na przykład szablony można skonfigurować na podstawie lokalizacji geograficznej, z oddzielnym grupami dla firm w Ameryce Północnej, regionie EMEA i Azji Południowo-Wschodniej. 

Następnie firmy można dodać do szablonu. Firmy mogą być dodawane poprzez wybieranie hierarchii organizacyjnej lub wybieranie firm. Jeśli wybrano hierarchię organizacyjną, do szablonu zostaną dodane tylko firmy w hierarchii używające wybranego kalendarza obrachunkowego. Jeśli do szablonu dodajesz bezpośrednio firmy, można dodawać tylko firmy mające ten sam kalendarz obrachunkowy. Ten sam kalendarz obrachunkowy jest wymagany, ponieważ zamknięcie roku jest wykonywane poprzez wybranie roku obrachunkowego, który może się różnić między kalendarzami. 

Po dodaniu firm należy zdefiniować konta główne zysków zatrzymanych dla każdej firmy. Pole **Data ostatniego zamknięcia na koniec roku** będzie aktualizowane po każdym uruchomieniu zamknięcia roku dla firmy. 

Karta **Wymiar finansowy** jest używana do określania, które wymiary finansowe będą używane w transakcji otwarcia. Należy zauważyć, że definiowane ustawienia dotyczą tylko firmy wybranej w siatce **Firmy**. Tę konfigurację należy powtórzyć dla każdej firmy w siatce. 

Opcja **Przenieś wymiary bilansu** służy do określenia, czy wymiary finansowe w transakcjach zaksięgowanych na kontach bilansowych powinny być zachowane w transakcji otwarcia. Najlepszym rozwiązaniem jest ustawić w tej opcji wartość **Tak**. Opcja **Przenieś wymiary zysków i strat** jest używana do określenia, które wymiary finansowe w transakcjach zaksięgowanych na koncie wynikowym zostaną przeniesione do konta głównego zysków zatrzymanych. Najpierw należy zidentyfikować wymiary finansowe mające zastosowanie do wybranej firmy. Będą to wszystkie wymiary finansowe, względem których księgowano w ciągu roku, nawet jeśli wymiar finansowy nie jest częścią aktywnej struktury konta. Następnie należy zdefiniować każdy wymiar jako **Zamknij jeden** lub **Zamknij wszystko**.  Wartością domyślną jest **Zamknij wszystko**, co powoduje zachowanie oryginalnych wartości wymiarów finansowych z zaksięgowanych transakcji oraz wykorzystywanie ich do tworzenia sald otwarcia na koncie zysków zatrzymanych. Oddzielne salda początkowe zysków zatrzymanych będą tworzone dla każdej unikatowej kombinacji wartości wymiarów finansowych. Jeśli jest zaznaczona opcja **Zamknij jeden**, wszystkie transakcje zaksięgowane z tym wymiarem finansowym zostaną zsumowane do salda początkowego zysków zatrzymanych dla wartości wymiaru wprowadzonej w polu **Zamknij jeden**. Na przykład załóżmy, że wszystkie transakcje w roku obrachunkowym zostały zaksięgowane ze strukturą konta Konto główne — Dział. W szablonie w wymiarze finansowym Dział jest zaznaczona opcja **Zamknij jeden** i wprowadzono wartość 100. Jeśli całkowity dochód ze wszystkich transakcji zaksięgowanych w działach 200, 300 i 400 wynosi 100 000 USD, zostanie utworzone jedno saldo otwarcia dla zysków zatrzymanych — 100. Jeśli wybierzesz opcję **Zamknij jeden** i pozostawisz pustą wartość wymiaru finansowego, wszystkie transakcje zostaną zaksięgowane do zysków zatrzymanych z pustą tą wartością wymiaru. 

Proces zamknięcia roku nie przestrzega struktur kont. Dzieje się tak dlatego, że struktury kont mogą się zmieniać w trakcie roku obrachunkowego i z powodu tych zmian nie zawsze jest możliwe ustalenie aktualnej struktury konta.  Podczas tworzenia transakcji otwarcia salda zostaną przeniesione na następny okres z wymiarami finansowymi określonymi w szablonie zamknięcia roku. Wpisy sald początkowych mogą obejmować wymiary finansowe, których już nie ma obecnej strukturze konta, oraz kombinacje segmentów, które już nie są prawidłowe w obecnej strukturze konta. Jeśli organizacja chce wykluczyć wymiar finansowy z salda początkowego zysków zatrzymanych, ustaw dla tego wymiaru finansowego opcję **Zamknij jeden** i pozostaw pustą wartość wymiaru.

## <a name="run-the-year-end-close-process"></a>Uruchamianie procesu zamknięcia roku
Po utworzeniu szablonów zamknięcia roku proces zamknięcia roku inicjuje się przez wybranie opcji **Uruchom zamknięcie roku obrachunkowego** w okienku akcji. W szablonie zaznacz wszystkie lub tylko niektóre firmy, dla których ma zostać wykonane zamknięcie roku. Podczas wykonywania zamknięcia roku po raz pierwszy w roku obrachunkowym prawdopodobnie zaznaczysz wszystkie firmy, aby utworzyć dla nich salda początkowe. Jeśli ponownie wykonujesz zamknięcie roku, możesz go uruchomić tylko dla firm, u których zaksięgowano zapisy korygujące. 

Wybierz rok obrachunkowy, dla którego chcesz wykonać proces zamknięcia roku. Jeśli istnieje więcej niż jeden okres zamknięcia dla ostatniego okresu roku obrachunkowego, stanie się dostępne pole **Nazwa okresu** umożliwiające wybór okresu zamknięcia, w którym ma zostać zaksięgowana transakcja zamknięcia, o ile tylko w konfiguracji zdefiniowano tworzenie transakcji zamknięcia. 

Wprowadź numer załącznika, który jest wymagany lub nie, co zależy od ustawień w oknie Parametry księgi głównej. Ten sam numer załącznika będzie używany dla wszystkich firm wybranych do procesu zamknięcia roku. Numer załącznika nie jest generowany z użyciem funkcji numerowania. Najlepszym rozwiązaniem jest wprowadzenie numeru załącznika, nawet jeśli nie jest to wymagane. Wprowadzenie numeru załącznika ułatwi znalezienie transakcji otwarcia w nowym roku obrachunkowym. Jeśli numer załącznika nie jest wprowadzony, pole załącznika będzie puste w transakcji otwarcia. 

Jeśli chcesz wycofać poprzednie zamknięcie roku dla wybranego roku obrachunkowego, ustaw w opcji **Cofnij poprzednie zamknięcie** wartość **Tak**. Zamknięcie roku zostanie cofnięte, ale proces można ponownie uruchomić w dowolnym momencie. Jeżeli wycofasz zamknięcie roku, pole **Data ostatniego zamknięcia na koniec roku** będzie niedostępne. 

Proces zamknięcia roku domyślnie jest wykonywany w trybie wsadowym. Najlepszym rozwiązaniem jest uruchamianie procesu w trybie wsadowym, aby umożliwić użytkownikowi zajęcie się innymi zadaniami. Po zakończeniu procesu zamknięcia roku pole **Data ostatniego zamknięcia na koniec roku** zostanie zaktualizowane o datę sesji.

Aby uzyskać więcej informacji, zobacz [Zamknięcie księgi głównej na koniec okresu](close-general-ledger-at-period-end.md).




