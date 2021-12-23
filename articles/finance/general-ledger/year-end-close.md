---
title: Zamknięcie na koniec roku
description: W tym temacie opisano wymaganą konfigurację i kroki wykonywania procesu zamknięcia roku w księdze głównej.
author: kweekley
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04eeb8886d74fa8c633d2ac4e9e47aa28a12ee30
ms.sourcegitcommit: e06b7d4de6d5ee7ae491d437d6c0365608a5380b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/06/2021
ms.locfileid: "7892484"
---
# <a name="year-end-close"></a>Zamknięcie na koniec roku

[!include [banner](../includes/banner.md)]

W tym temacie opisano wymaganą konfigurację i kroki wykonywania procesu zamknięcia roku w księdze głównej.

Na koniec roku obrachunkowego trzeba uruchomić proces zamknięcia roku, aby przenieść salda otwarcia do nowego roku. Większość organizacji wykonuje proces zamknięcia roku wiele razy. Pierwsze uruchomienie powoduje przeniesienie sald do nowego roku obrachunkowego. Proces można następnie powtarzać tyle razy, ile jest to konieczne, aby przenieść salda z wpisów korygujących do nowego roku obrachunkowego.

W trakcie procesu zamknięcia roku mogą być tworzone dwa typy transakcji. Transakcja otwarcia jest generowana zawsze i służy do tworzenia sald otwarcia w nowym roku obrachunkowym. Transakcja otwarcia pokazuje salda kont księgowych bilansu w nowym roku obrachunkowym oraz salda z kont księgowych rachunku wyników na koncie księgowym zysków zatrzymanych w nowym roku obrachunkowym. Transakcja otwarcia jest opcjonalnie tworzona w celu sprowadzenia sald kont wynikowych do zera w zamykanym roku obrachunkowym.

## <a name="prepare-to-run-the-year-end-close"></a>Przygotowanie do wykonania zamknięcia roku

Przed uruchomieniem procesu zamknięcia roku należy sprawdzić poprawność następujących ustawień:

Na stronie **Konto główne**:

- Sprawdź, czy pole **Typ konta głównego** jest poprawnie ustawione dla każdego konta głównego. Typ konta głównego określa, czy saldo konta głównego zostanie przesunięte jako saldo otwarcia, czy zamknięte w zyskach zatrzymanych w transakcji otwarcia.
- Saldo konta głównego można przenieść na nowe konto główne podczas zamknięcia na koniec roku. Nowe konto główne jest wprowadzane w polu **Konto otwarcia**. Zazwyczaj tej opcji używa się do kont głównych bilansu, gdy istniejące konto główne jest dezaktywowane, a dla nowego roku obrachunkowego stosuje się nowe konto główne.

Na stronie **Parametry księgi głównej** w obszarze **Zamknięcie roku obrachunkowego**:

- Opcja **Usuń istniejące wpisy na koniec roku przy ponownym zamknięciu roku** służy do określenia, czy wygenerowana przez system transakcja otwarcia z poprzedniego zamknięcia na koniec roku powinna zostać usunięta po ponownym uruchomieniu zamknięcia na koniec roku. Jeśli ta opcja jest ustawiona na **Tak**, poprzednie transakcje otwarcia i opcjonalnego zamknięcia są usuwane, a nowa transakcja otwarcia lub zamknięcia jest tworzona na podstawie bieżących sald. Jeśli ta opcja jest ustawiona na **Nie**, poprzednie transakcje otwarcia i opcjonalne zamknięcia pozostają, a dodatkowa transakcja otwarcia lub zamknięcia jest tworzona w celu przeniesienia sald do przodu z transakcji korygujących, które zostały zaksięgowane po zamknięciu poprzedniego roku na koniec roku.
- Opcja **Tworzenie transakcji zamknięcia w trakcie przeniesienia** służy do tworzenia transakcji zamykających w zamykanym roku obrotowym, w celu doprowadzenia wszystkich kont głównych do wartości 0 (zero). Jeśli ta opcja jest ustawiona na **Tak**, tworzona jest zarówno transakcja otwierająca, jak i zamykająca. Jeśli ta opcja jest ustawiona na **Nie**, jest tworzona tylko transakcja otwarcia w następnym roku obrachunkowym w celu przeniesienia sald. Salda kont głównych pozostają na koniec roku obrachunkowego.
- Opcja **Ustaw stan roku obrachunkowego na trwale zamknięty** służy do ustawiania rokowi obrachunkowemu stanu trwałego zamknięcia. Korzystaj z tej opcji ostrożnie, ponieważ okresy, które mają status zamknięty na stałe, nie mogą być ponownie otwierane. W związku z tym korekt nie można zaksięgować w roku obrachunkowym. Najlepszym rozwiązaniem jest ustawienie tej opcji na **Nie**.
- Opcja **Numer załącznika należy wypełnić** została usunięta. Załącznik jest teraz wymagany, gdy uruchamiany jest proces zamknięcia na koniec roku. W tym czasie numer załącznika jest wprowadzany ręcznie.

Na stronie **Kalendarz obrachunkowy**:

- Następny rok obrachunkowy musi istnieć przed uruchomieniem zamknięcia na koniec roku. W przeciwnym razie salda początkowe nie mogą zostać utworzone w okresie otwarcia.

Na stronie **Kalendarz księgi**:

- Opcjonalnie: Każdemu okresowi obrachunkowemu w zamykanym roku obrachunkowym można ustawić status **Wstrzymane**, aby uniemożliwić wprowadzanie nowych transakcji. Gdy zostaną zidentyfikowane zapisy korygujące, okresy wstrzymane można otworzyć ponownie w celu zaksięgowania tych zapisów, nawet jeśli proces zamknięcia roku został już wykonany.

Na stronie **Konfiguracja szablonu zamknięcia na koniec roku**:

- Po włączeniu funkcji **Ulepszenia końca roku księgi głównej** proces konfigurowania szablonu zamknięcia na koniec roku jest oddzielony od procesu uruchamiania zamknięcia na koniec roku. Szablon można zdefiniować na stronie **Konfiguracja szablonu zamknięcia na koniec roku** (**Księga główna \> Konfiguracja księgi \> Konfiguracja szablonu zamknięcia na koniec roku**) lub można uzyskać do niego dostęp z proces zamknięcia na koniec roku.

## <a name="define-year-end-close-templates"></a>Definiowanie szablonów zamknięcia roku

Po skonfigurowaniu systemu można uruchomić proces zamknięcia roku. Na stronie **Konfiguracja szablonu zamknięcia na koniec roku** można zdefiniować szablon dla grupy firm, dla których będzie wykonywany proces zamknięcia roku. Szablon będzie używany dla każdego wystąpienia procesu zamknięcia roku, ale można go zmodyfikować w razie pojawienia się zmian w organizacji.

Najpierw należy zdefiniować pole **Nazwa grupy** dla szablonu i wybrać kalendarz obrachunkowy. Nazwa grupy powinna identyfikować grupę firm, do których ma być stosowany szablon. Podczas określania grup podmiotów prawnych pamiętaj, że podmioty prawne można uwzględnić w tej samej grupie tylko wtedy, gdy wybrano dla nich ten sam kalendarz obrachunkowy. Na przykład szablony można konfigurować na podstawie lokalizacji geograficznej i można tworzyć oddzielne grupy dla podmiotów prawnych z Ameryki Północnej, podmiotów prawnych z Europy, Bliskiego Wschodu i Afryki (EMEA) oraz podmiotów prawnych Azji i Pacyfiku (APAC).

Następnie firmy można dodać do szablonu. Firmy mogą być dodawane poprzez wybieranie hierarchii organizacyjnej lub wybieranie firm. Jeśli wybrano hierarchię organizacyjną, do szablonu zostaną dodane tylko firmy w hierarchii używające wybranego kalendarza obrachunkowego. Jeśli do szablonu dodajesz bezpośrednio firmy, można dodawać tylko firmy mające ten sam kalendarz obrachunkowy. Ten sam kalendarz obrachunkowy jest wymagany, ponieważ zamknięcie roku jest wykonywane poprzez wybranie roku obrachunkowego, który może się różnić między kalendarzami.

Po dodaniu firm należy zdefiniować konta główne zysków zatrzymanych dla każdej firmy.

Karta **Wymiar finansowy** jest używana do określania, które wymiary finansowe będą używane w transakcji otwarcia. Pamiętaj, że konfiguracja na tej karcie dotyczy tylko firmy wybranej w siatce **Firmy**. Tę konfigurację należy powtórzyć dla każdej firmy w siatce.

Opcja **Przenieś wymiary bilansu** służy do określenia, czy wymiary finansowe transakcji księgowanych na kontach bilansu mają być zachowywane w transakcji otwarcia. Najlepszym rozwiązaniem jest ustawienie tej opcji na **Tak**. Ustawienie wymiarów bilansu nie wpływa na istniejące salda na kontach księgowych zysków zatrzymanych. Salda te są określane przez wymiary zysków i strat, które są zdefiniowane w następnej sekcji. Na przykład rok obrachunkowy 2019 był pierwszym rokiem, który został zamknięty, a opcja **Zamknij wszystko** została użyta do wybrania wymiarów **Dział** i **Centrum kosztów** do zamknięcia. W takim przypadku dla każdej kombinacji działu i centrum kosztów utworzono oddzielne konto zysków zatrzymanych. Po zamknięciu na koniec roku w roku podatkowym 2020 zyski zatrzymane z poprzedniego roku pozostają dokładnie takie, jak zostały zaksięgowane, nawet jeśli **Wymiary bilansu przeniesienia** są ustawione na **Nie**. Salda księgowane w zyskach zatrzymanych z zamknięcia na koniec poprzedniego roku nigdy nie ulegają zmianie.

Sekcja **Przenieś wymiary zysków i strat** służy do określenia, które wymiary finansowe transakcji księgowanych na kontach zysków i strat zostaną przeniesione na konto główne zysków zatrzymanych. Najpierw należy zidentyfikować wymiary finansowe mające zastosowanie do wybranej firmy. Te wymiary finansowe obejmują wszystkie wymiary finansowe, które zostały zaksięgowane w ciągu roku, nawet jeśli wymiar finansowy nie jest częścią aktywnej struktury konta. Następnie należy zdefiniować każdy wymiar jako **Zamknij jeden** lub **Zamknij wszystko**. Opcją domyślną jest **Zamknij wszystkie**. Ta opcja zachowuje oryginalne wartości wymiarów finansowych z zaksięgowanych transakcji i używa ich do tworzenia sald otwarcia dla konta zysków zatrzymanych. Oddzielne salda początkowe zysków zatrzymanych będą tworzone dla każdej unikatowej kombinacji wartości wymiarów finansowych. Jeśli jest zaznaczona opcja **Zamknij jeden**, wszystkie zaksięgowane transakcje, które mają ten wymiar finansowy, zostaną podsumowane w saldzie początkowym zysków zatrzymanych dla wartości wymiaru wprowadzonej w polu wyświetlanym po **Zamknij jeden**. Na przykład załóżmy, że wszystkie transakcje w roku obrachunkowym zostały zaksięgowane ze strukturą konta **Konto główne — Dział**. W szablonie w wymiarze finansowym **Dział** jest zaznaczona opcja **Zamknij jeden** i wprowadzono wartość **100** jako wymiar finansowy. Jeśli całkowity dochód ze wszystkich transakcji zaksięgowanych w działach 200, 300 i 400 wynosi 100 000 USD, zostanie utworzone jedno saldo otwarcia dla **zysków zatrzymanych — 100**. Jeśli wybierzesz opcję **Zamknij jeden**, ale pozostawisz wartość wymiaru finansowego pustą, wszystkie transakcje zostaną zaksięgowane w zarobkach zatrzymanych, a wartość wymiaru pozostanie pusta.

## <a name="run-the-year-end-close-process"></a>Uruchamianie procesu zamknięcia roku

Po utworzeniu szablonów zamknięcia na koniec roku możesz zainicjować proces zamknięcia na koniec roku na stronie **Zamknięcie na koniec roku** (**Księga główna \> Zamknięcie okresu \> Zamknięcie na koniec roku**). Przed uruchomieniem zamknięcia rocznego możesz dodać nowe szablony zamknięcia rocznego lub zmodyfikować istniejące, wybierając **Konfiguracja szablonu zamknięcia rocznego**, aby otworzyć stronę konfiguracji szablonów.

Wybierz szablon zamknięcia na koniec roku, a następnie w okienku akcji wybierz opcję **Uruchom zamknięcie na koniec roku**. Wybierz wszystkie podmioty prawne lub podzbiór podmiotów prawnych z szablonu, dla którego prowadzisz zamknięcie roku na koniec roku. Jeśli przeprowadzasz zamknięcie na koniec roku po raz pierwszy w roku obrachunkowym, prawdopodobnie wybierzesz wszystkie firmy, aby utworzyć salda początkowe dla nich wszystkich. Jeśli wcześniej uruchomiono zamknięcie na koniec roku, warto uruchomić je ponownie tylko dla firm, dla których zaksięgowano wpisy dostosowujące.

Następnie wybierz rok obrachunkowy, dla którego ma zostać przeprowadzony proces zamknięcia na koniec roku. Jeśli dla ostatniego okresu obrachunkowego istnieje więcej niż jeden okres zamknięcia, pole **Nazwa okresu** staje się dostępne. Następnie można wybrać okres zamknięcia, który będzie używany do księgowania transakcji zamykającej, jeśli konfiguracja została zdefiniowana w celu utworzenia transakcji zamykającej.

Następnie wprowadź numer załącznika. Ten sam numer załącznika będzie używany dla wszystkich firm wybranych do procesu zamknięcia roku. Numer załącznika nie jest generowany z użyciem funkcji numerowania.

Proces zamknięcia roku domyślnie jest wykonywany w trybie wsadowym. Dlatego po jej zainicjowaniu możesz wrócić do innych czynności.

Ponieważ struktury kont mogą się zmieniać w ciągu roku obrachunkowego, nie zawsze można zidentyfikować odpowiednią strukturę kont. Dlatego proces zamykania na koniec roku nie jest zgodny ze strukturami kont. Podczas tworzenia transakcji otwarcia salda zostaną przeniesione na następny okres z wymiarami finansowymi określonymi w szablonie zamknięcia roku. Wpisy sald początkowych mogą obejmować wymiary finansowe, których już nie ma obecnej strukturze konta, oraz kombinacje segmentów, które już nie są prawidłowe w obecnej strukturze konta. Jeśli organizacja chce wykluczyć wymiar finansowy z salda początkowego zysków zatrzymanych, ustaw dla tego wymiaru finansowego opcję **Zamknij jeden** i pozostaw pustą wartość wymiaru.

Po zakończeniu procesu tworzony jest rekord dla każdej kombinacji firmy i roku obrachunkowego. Zobaczysz rekordy tylko dla podmiotów prawnych, do których masz dostęp. Każdy rekord zawiera datę i godzinę systemową uruchomienia procesu oraz bezpośredni link do załączników, które zostały utworzone na koniec roku.

[![Rekordy utworzone na skróconej karcie historii zamknięcia na koniec roku na stronie zamknięcia na koniec roku](./media/run-yr-end-close.png)](./media/run-yr-end-close.png)

Jeśli ponownie przeprowadzisz zamknięcie roku, zobaczysz jeden lub wiele rekordów dla każdej kombinacji podmiotu prawnego i roku obrachunkowego, w zależności od ustawienia **Usuń istniejące wpisy na koniec roku podczas ponownego zamykania roku** opcja na stronie **Parametry księgi głównej**:

- Jeśli opcja jest ustawiona na **Tak**, załącznik z poprzedniego zamknięcia na koniec roku zostanie usunięty. Rekord jest oznaczony jako **Wycofany** i jest oznaczony datą i godziną cofnięcia. Ponadto zostanie usunięte łącze do numeru załącznika. Po zamknięciu końca roku zostanie utworzony nowy rekord dla nowego tworzonego załącznika.
- Jeśli ustawiono opcję **Nie**, wraz z łączem do załącznika pozostanie rekord poprzedniego zamknięcia na koniec roku. Za każdym razem, gdy zamknięcie na koniec roku zostanie ponownie uruchomione, zostanie utworzony nowy rekord wraz z linkiem do nowych załączników.

## <a name="reverse-the-year-end-close-process"></a>Cofanie procesu zamknięcia roku

Na **stronie Zamknięcie na koniec roku** można wycofać zamknięcie na koniec roku. Wybierz rekord dla kombinacji firmy i roku obrachunkowego, który musi zostać wycofany, a następnie wybierz pozycję **Wycofaj zamknięcie na koniec roku**. Proces stornowania usuwa wszystkie załączniki otwierające i zamykające, które zostały utworzone dla roku obrachunkowego. Rekord jest oznaczony jako **Wycofany** i jest oznaczony datą i godziną cofnięcia. Ponadto zostanie usunięte łącze do numeru załącznika. Podobnie jak proces zamknięcia na koniec roku, odwrócenie działa w trybie wsadowym.

Pole wyboru **Pokaż wycofane**, które jest dostępne powyżej siatki, umożliwia ukrycie lub pokazanie rekordów dla wycofanych procesów zamknięcia na koniec roku. Po uruchomieniu procesu **Cofnięcie zamknięcia roku na koniec roku** może być konieczne zaznaczenie pola wyboru **Pokaż wycofane** w celu wyświetlenia rekordu. Możesz ustawić dodatkowe filtry, aby wyświetlić inne informacje.

[![Użycie pola wyboru Pokaż cofnięte, aby wyświetlić rekordy dla cofniętych procesów zamknięcia na koniec roku na stronie zamknięcia na koniec roku](./media/rvrs-yr-end-close.png)](./media/rvrs-yr-end-close.png)

Aby uzyskać więcej informacji, zobacz [Zamknięcie księgi głównej na koniec okresu](close-general-ledger-at-period-end.md) i [Zamykanie roku obrachunkowego](tasks/close-fiscal-year.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
