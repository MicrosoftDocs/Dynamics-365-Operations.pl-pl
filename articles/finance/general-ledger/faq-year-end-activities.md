---
title: Działania na koniec roku — często zadawane pytania
description: W tym artykule można znaleźć pytania, które mogą powstać podczas zamknięcia roku, oraz odpowiedzi, które mogą pomóc w działaniach związanych z zamknięciem roku.
author: moaamer
ms.date: 12/01/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2e33c1dcbfa4da74f2e8acc6e29f04fda3abd185
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853049"
---
# <a name="year-end-activities-faq"></a>Działania na koniec roku — często zadawane pytania 

[!include [banner](../includes/banner.md)]

W tym artykule można znaleźć pytania, które mogą powstać podczas zamknięcia roku, oraz odpowiedzi, które mogą pomóc w działaniach związanych z zamknięciem roku. Informacje zawarte w tym artykule skupiają się głównie wokół pytań dotyczących działań związanych z zamknięciem roku w obszarach Księga główna i Rozrachunki z dostawcami.

## <a name="general-ledger-year-end-enhancements"></a>Ulepszenia na koniec roku w księdze głównej

Rozwiązanie Microsoft Dynamics 365 Finance w wersji 10.0.20 wprowadziło rozszerzenie zamknięcia roku. To rozszerzenie jest domyślnie włączone w wersji 10.0.25 i obowiązkowe od wersji 10.0.29. Jeśli w organizacji jest używana wersja wcześniejsza niż 10.0.25, zaleca się włączenie tej funkcji przed rozpoczęciem procesu zamknięcia na koniec roku. Aby używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego **Zarządzanie funkcjami**, aby sprawdzić stan funkcji i ją włączyć, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** Księga główna
- **Nazwa funkcji:** Ulepszenia na koniec roku w księdze głównej

Konfiguracja szablonów zamknięcia roku została przeniesiona na nową stronę ustawień: **Konfiguracja szablonu zamknięcia roku**. Istniejąca strona zamknięcia roku upodobni się do strony **Przeszacowanie w walucie obcej dla księgi głównej**, gdzie lista jest wyświetlana za każdym razem, gdy zamknięcie roku zostanie uruchomione lub wycofane. Na stronie nie będą wyświetlane informacje historyczne o zamknięciach roku, które zostały wykonane przed włączeniem tej funkcji. Kierownik ds. księgowości może inicjować zamknięcie roku z nowej strony.

Aby wycofać zamknięcie roku, wybierz ostatni rok obrachunkowy dla odpowiedniej osoby prawnej, a następnie wybierz przycisk **Wycofaj zamknięcie roku**. Wycofanie spowoduje usunięcie wpisów księgowych dla poprzedniego zamknięcia roku i nie spowoduje automatycznego ponownego uruchomienia zamknięcia roku. Jeśli funkcja **Ulepszenia na koniec roku w księdze głównej** zostanie włączona po zakończeniu operacji zamknięcia roku i użytkownik chce wycofać historyczne wyniki na koniec roku, należy ponownie uruchomić historyczne zamknięcie roku po włączeniu parametru księgi głównej **Usuń istniejące wpisy zamknięcia roku po ponownym zamknięciu roku**.

Zamknięcie roku można uruchomić ponownie, uruchamiając proces po raz kolejny dla roku obrachunkowego i osoby prawnej. Proces będzie nadal korzystać z ustawienia parametru Księga główna, aby ustalić, czy ponowne zamknięcie roku będzie rozliczać tylko nowe lub zmienione transakcje, czy też przetworzy ponowne uruchomienie dla wszystkich transakcji i całkowicie wycofa poprzednie zamknięcie.

## <a name="general-ledger-the-general-ledger-year-end-enhancements-feature-is-enabled-why-cant-i-view-my-previous-year-closings-in-the-history-section-of-the-year-end-close-page"></a>Księga główna: funkcja Ulepszenia na koniec roku w księdze głównej jest włączona. Dlaczego nie można wyświetlić moich poprzednich zamknięć roku w sekcji Historia strony Zamknięcie roku?

Przed włączeniem funkcji **Ulepszenia na koniec roku w księdze głównej** jest śledzona data i godzina ostatniego przetworzenia zamknięcia roku. Historia nie była śledzona za każdym razem, gdy wykonano zamknięcie roku. W związku z tym szczegóły każdego uruchomienia zamknięcia roku nie są dostępne do wyświetlenia. Po włączeniu tej funkcji są zachowywane informacje dotyczące kolejnych procesów zamknięcia roku. Załączniki ze wszystkich procesów zamknięcia roku, nawet tych uruchomionych przed włączeniem funkcji, można wyświetlić na stronie **Transakcje załącznika**. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-cant-be-run-because-one-or-more-ledger-transactions-posted-into-the-fiscal-year-that-you-are-closing-were-settled-to-a-ledger-transaction-in-a-different-fiscal-year-what-does-this-error-mean"></a>Księga główna: proces zamknięcia roku zakończył się niepowodzeniem z powodu następującego błędu: „Nie można uruchomić zamknięcia roku, ponieważ co najmniej jedna transakcja księgi zaksięgowana w zamykanym roku obrachunkowym została rozliczona w transakcji księgi w innym roku obrachunkowym.” Co ten błąd oznacza?

Ponieważ włączona jest funkcja **Relacja między rozliczeniem księgi a zamknięciem roku**, tylko rozliczone transakcje księgi z zamykanego roku obrachunkowego są wykluczone z salda otwarcia. Takie zachowanie powoduje, że uznania i obciążenia nie są zbilansowane. Aby uzyskać więcej informacji, zobacz temat [Relacja między rozliczeniem księgi a zamknięciem roku](awareness-between-ledger-settlement-year-end-close.md).

## <a name="general-ledger-reversal-of-the-year-end-close-process-is-failing-because-of-the-following-error-the-year-end-close-for-112022-cant-be-reversed-because-beginning-balance-transaction-have-been-ledger-settled-in-fiscal-year-112023-what-does-this-error-mean"></a>Księga główna: wycofanie procesu zamknięcia roku zakończyło się niepowodzeniem z powodu następującego błędu: „Nie można wycofać zamknięcia roku dla dnia 2022-01-01, ponieważ transakcja salda początkowego została rozliczona w roku obrachunkowym 2023-01-01.” Co ten błąd oznacza?

Ponieważ jest włączona funkcja **Relacja między rozliczeniem księgi a zamknięciem roku**, nie są dozwolone wycofania przetwarzania zamknięcia roku, jeśli otwierające transakcje zostały rozliczone w nowym roku obrachunkowym. Przed wycofaniem zamknięcia roku dla dnia 1 stycznia 2022 roku należy wycofać rozliczenia księgi w nowym roku obrachunkowym 2023. Można także ponownie zamknąć rok dla dnia 1 stycznia 2022 roku, ale tylko dla nowych wpisów korekt. Aby ponownie zamknąć rok tylko dla korekt, wyłącz parametr księgi głównej **Usuń istniejące wpisy na koniec roku podczas ponownego zamknięcia roku**.

## <a name="general-ledger-why-isnt-the-ledger-settlement-automation-processing-decembers-ledger-settlement-transactions"></a>Księga główna: dlaczego automatyzacja rozliczenia księgi nie przetwarza transakcji rozliczenia księgi z grudnia?

Funkcja **Automatyzowanie rozliczeń księgi** po uruchomieniu wystąpienia spowoduje uruchomienie automatyzacji dla transakcji z datą od pierwszego dnia roku obrachunkowego do daty bieżącej. W latach obrachunkowych, które zakończą się 31 grudnia, można zmienić datę wykonania wystąpienia, aby zagwarantować, że będzie ono uruchamiane w grudniu. Na przykład automatyzacja jest ustawiona tak, aby była uruchamiana pierwszego dnia każdego miesiąca. Automatyzacja ta zostanie uruchomiona 1 grudnia 2022 roku i jest zaplanowana do uruchomienia 1 stycznia 2023 roku. Zaleca się zmianę wystąpienia 1 stycznia 2023 roku na datę 31 grudnia 2022 roku. Ta zmiana zapewni, że transakcje z datami od 2 grudnia do 31 grudnia będą brane pod uwagę do automatycznego rozliczenia.

## <a name="general-ledger-whats-the-difference-between-the-reverse-year-end-close-action-and-the-delete-existing-year-end-entries-when-reclosing-parameter-for-year-end-close"></a>Księga główna: jaka jest różnica między akcją wycofania zamknięcia roku a parametrem Usuń istniejące wpisy na koniec roku podczas ponownego zamknięcia dla zamknięcia roku?

Może nie być jasna różnica między akcją **Wycofaj zamknięcie roku** a parametrem **Usuń istniejące wpisy na koniec roku podczas ponownego zamknięcia** w księdze głównej (**Księga główna \> Ustawienia księgi \> Parametry księgi głównej**).

Wybierz akcję **Wycofaj zamknięcie roku** podczas uruchamiania procesu zamknięcia roku, aby usunąć wszystkie wpisy salda zamknięcia i salda otwarcia, tak jakby zamknięcie roku nigdy nie zostało uruchomione. W takim przypadku załączniki zostaną usunięte. Zamknięcie roku nie zostanie ponownie automatycznie uruchomione. Aby uruchomić zamknięcie roku, wybierz akcję **Uruchom zamknięcie roku**.

Parametr **Usuń istniejące wpisy na koniec roku podczas ponownego zamknięcia roku** w księdze głównej jest używany tylko wtedy, gdy jest uruchomione (nie wycofywane) zamknięcie roku. Jeśli parametr ma wartość **Tak**, wszystkie wpisy salda zamknięcia i salda otwarcia zostaną usunięte, a zamknięcie na koniec roku zostanie ponownie uruchomione. Ta opcja ma zastosowanie, gdy organizacja chce, aby wszystkie transakcje, w tym korekty od ostatniego zamknięcia roku, zostały zaksięgowane w jednym wpisie księgowania dla wpisów salda zamknięcia i salda otwarcia. Jeśli ten parametr ma wartość ustawioną na **Nie**, wszystkie wpisy salda zamknięcia i salda otwarcia zostaną pozostawione. Nie zostaną one usunięte. Zamiast tego zostanie utworzony nowy wpis salda zamknięcia i salda otwarcia jedynie dla różnicy albo dla nowych transakcji zaksięgowanych od ostatniego zamknięcia roku mającego miejsce w danym roku obrachunkowym.

> [!NOTE]
> Wpis salda zamknięcia jest tworzony w zamykanym roku. Dzieje się tak tylko wtedy, gdy parametr **Tworzenie transakcji zamknięcia podczas transferu** w księdze głównej ma wartość **Tak**. Wpis salda otwarcia jest tworzony zawsze, ponieważ jest to saldo początkowe dla następnego roku.

## <a name="general-ledger-what-is-the-difference-between-close-all-and-close-single-options-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process"></a>Księga główna: jaka jest różnica między opcjami „Zamknij wszystko” i „Zamknij jeden” w sekcji wymiaru przeniesienia zysków i strat procesu zamknięcia roku?

**Zamknij wszystko** zachowuje oryginalne wartości wymiarów finansowych z zaksięgowanych transakcji i używa ich do tworzenia sald otwarcia dla konta zysków zatrzymanych. Oddzielne salda początkowe wstrzymanych dochodów będą tworzone dla każdej unikatowej kombinacji wartości wymiarów finansowych. Jeśli jest zaznaczona opcja **Zamknij jeden**, wszystkie zaksięgowane transakcje, które mają ten wymiar finansowy, zostaną podsumowane w saldzie początkowym wstrzymanych dochodów dla wartości wymiaru wprowadzonej w polu wyświetlanym po opcji **Zamknij jeden**. 

Na przykład załóżmy, że wszystkie transakcje w roku obrachunkowym zostały zaksięgowane ze strukturą konta Konto główne — Dział. W szablonie w wymiarze finansowym Dział jest zaznaczona opcja **Zamknij jeden** i wprowadzono wartość 100 jako wymiar finansowy. Jeśli całkowity dochód ze wszystkich transakcji zaksięgowanych w działach 200, 300 i 400 wynosi 100 000 USD, zostanie utworzone jedno saldo otwarcia dla wstrzymanych dochodów — 100. Jeśli wybierzesz opcję **Zamknij jeden**, ale pozostawisz wartość wymiaru finansowego pustą, wszystkie transakcje zostaną zaksięgowane we wstrzymanych dochodach, a wartość wymiaru pozostanie pusta.

## <a name="general-ledger-when-i-select-close-single-option-on-the-transfer-profit-and-loss-dimension-section-of-the-year-end-close-process-will-my-detailed-transactional-information-be-lost"></a>Księga główna: czy po wybraniu opcji „Zamknij jeden” w sekcji wymiarów wynikowych przeniesienia procesu zamknięcia na koniec roku informacje szczegółowe dotyczące moich transakcji zostaną utracone?

Opcje **Zamknij wszystko** i **Zamknij jeden** służą do określania, które wymiary finansowe w transakcjach zaksięgowanych na kontach zysków i strat zostaną przeniesione na konto główne wstrzymanych dochodów. Nie ma to wpływu na historyczne, szczegółowe księgowanie na kontach zysków i strat i pozostanie szczegółem. Ta opcja wpływa na poziom szczegółów przeniesionych na konta wstrzymanych dochodów jako saldo otwarcia w nowym roku. 

## <a name="general-ledger-the-year-end-close-process-is-failing-because-the-reporting-currency-for-the-year-does-not-balance-what-does-this-mean"></a>Księga główna: proces zamknięcia roku zakończy się niepowodzeniem, ponieważ waluta raportowania dla roku się nie bilansuje. Co to oznacza?

Ten błąd może wystąpić po włączeniu funkcji **Relacja między rozliczeniem księgi a zamknięciem roku** (funkcja relacji). Jeśli ta funkcja jest włączona, transakcje księgi, które zostały rozliczone, nie będą dłużej uwzględniane w saldzie otwarcia następnego roku obrachunkowego podczas zamknięcia roku księgi głównej. Nieuwzględnienie rozliczonych transakcji księgi może stanowić dla klientów problem podczas zamknięcia roku, jeśli księga jest zdefiniowana w walucie raportowania.   
Rozliczenie księgi jest wykonywane tylko dla waluty rozliczeniowej.  Podczas rozliczania transakcji księgi sprawdzanie poprawności zapewnia tylko zgodność uznań w walucie rozliczeniowej z obciążeniami w walucie rozliczeniowej. Kwoty w walucie raportowania dla tych transakcji księgi nie są sprawdzane pod względem poprawności i uznania mogą nie równać się obciążeniom.  Ponadto rozliczenie księgi nie umożliwia automatycznego obliczania i księgowania zysków/strat w walucie raportowania.  Ze względu na te ograniczenia podczas rozliczania księgi transakcja zysków/strat musi istnieć w walucie raportowania.  Jeśli w rozliczeniu księgi nie uwzględniono zysków/strat, podczas próby zamknięcia roku pojawi się komunikat informujący o braku zbilansowania.  Aby uzyskać więcej informacji, zobacz [Funkcja relacji między rozliczeniem księgi a walutą raportowania nie jest zbilansowana](reporting-currency-yec.md).

## <a name="general-ledger-what-can-be-changed-to-help-enhance-the-performance-of-year-end-processing"></a>Księga główna: co można zmienić, aby pomóc w zwiększeniu wydajności przetwarzania na koniec roku?

W celu poprawy wydajności zamknięcia na koniec roku można wprowadzić kilka zmian. Zalecamy rozważenie sugerowanych zmian w celu podjęcia decyzji w kwestii tego, czy są one odpowiednie dla organizacji.

### <a name="optimize-year-end-close-service"></a>Optymalizacja usługi zamknięcia roku

Usługa **Optymalizacja zamknięcia roku** umożliwia klientom rozwiązania Microsoft Dynamics 365 Finance przyspieszenie zamknięcia roku, przenosząc pracochłonne przetwarzania na koniec roku do mikrousługi. Czas zaoszczędzony dzięki efektywnemu zamknięciu roku daje każdemu zespołowi rozwiązania Finance szansę na szybką reakcję na wymagane korekty, w wyniku której generowane są raporty finansowe. Dzięki przetwarzaniu zamknięcia roku w mikrousłudze zwalniane są cenne zasoby. Poprawienie przetwarzania minimalizuje obciążenie serwera SQL Server i daje klientom możliwość przyspieszenia przetwarzania zamknięcia roku.

Usługa **Optymalizacja zamknięcia roku** jest dostępna w wersji 10.0.31, dzięki czemu klienci mogą używać nowej usługi dla końca 2022 roku. Ponadto usługa została zaimportowana wstecz do wersji 10.0.30 i 10.0.29. Aby uzyskać więcej informacji, zobacz [Optymalizacja zamknięcia roku](optimize-year-end-close.md).

### <a name="dimension-sets"></a>Zestawy wymiarów

Po uruchomieniu zamknięcia roku poszczególne salda zestawu wymiarów są przebudowywane. To zachowanie ma bezpośredni wpływ na wydajność. Niektóre organizacje tworzą zestawy wymiarów niepotrzebnie, tylko dlatego, że były one używane w przeszłości lub mogły zostać kiedyś użyte. Ponieważ te niepotrzebne zestawy wymiarów są dalej przebudowywane podczas realizacji procesu zamknięcia roku, wydłuża się czas jego trwania. Poświęć nieco czasu na ocenę zestawów wymiarów i usuń te z nich, które nie są potrzebne.

Zbędne zestawy wymiarów wpływają również na przebieg zadania wsadowego **BudgetDimensionFocusInitializeBalance** (**Księga główna \> Plan kont \> Wymiary \> Zestawy wymiarów finansowych**).

[![Zestawy wymiarów finansowych.](./media/faq-2020-yr-end-04.png)](./media/faq-2020-yr-end-04.png)

### <a name="year-end-close-template-configuration"></a>Konfiguracja szablonu zamknięcia na koniec roku

Szablon zamknięcia na koniec roku pozwala organizacjom wybrać poziom wymiaru finansowego do obsługi podczas przenoszenia sald kont wynikowych do wstrzymanych dochodów. Ustawienia umożliwiają organizacji obsługę szczegółowych wymiarów finansowych (**Zamknij wszystko**) podczas przenoszenia sald do wstrzymanych dochodów lub podjęcie decyzji o podsumowaniu kwot w ramach wartości jednego wymiaru (**Zamknij jeden**). Możliwe jest jego zdefiniowanie dla każdego wymiaru finansowego. Aby uzyskać więcej informacji dotyczących tych ustawień, zobacz artykuł [Zamknięcie na koniec roku](year-end-close.md).

Zalecamy ocenę wymagań organizacji i, jeśli to możliwe, zamknięcie możliwie wielu wymiarów za pomocą opcji **Zamknij jeden** dotyczącej końca roku, aby poprawić wydajność. Po zamknięciu wartości (która może być także wartością pustą) jednego wymiaru system określa mniej szczegółów podczas ustalania sald dla zapisów na koncie wstrzymanych dochodów.

### <a name="degenerate-dimensions"></a>Zdegeneruj wymiary

Wymiar zdegenerowany zapewnia brak możliwości ponownego użycia jest samego i w połączeniu z innymi wymiarami. Istnieją dwa typy wymiarów zdegenerowanych. Pierwszy typ to wymiar, który jest indywidualnie degenerowany. Zazwyczaj ten typ wymiaru degenerowanego pojawia się tylko w jednej transakcji lub w małych zestawach transakcji. Drugi typ jest wymiarem, który staje się degenerowany w połączeniu z jednym lub większą liczbą dodatkowych wymiarów wykazujących te same możliwości na podstawie dostępnych permutacji, które można generować. Wymiar zdegenerowany może mieć znaczący wpływ na wydajność procesu zamknięcia na koniec roku. Aby zminimalizować problemy z wydajnością, w konfiguracji zamknięcia na koniec roku zdefiniuj wszystkie wymiary zdegenerowane jako **Zamknij jeden**, tak jak opisano w poprzedniej sekcji.

## <a name="accounts-payable-what-changes-have-been-made-to-support-1099-year-end-reporting-for-2022"></a>Rozrachunki z dostawcami: jakie zmiany zostały wprowadzone w celu zapewnienia obsługi raportów 1099 dotyczących końca roku dla roku 2022?

#### <a name="update-to-all-1099-forms"></a>Aktualizacja wszystkich formularzy 1099

We wszystkich formularzach 1099 dla roku podatkowego 2022 zostały wprowadzone następujące zmiany:

- W 2021 r. rok w formularzach 1099 był stały. Od 2022 r. jest on wypełniany przez raport.

#### <a name="1099-misc"></a>1099-MISC

W formularzu 1099-MISC dla roku podatkowego 2022 zostały wprowadzone następujące aktualizacje:

- Pole 13: teraz wskazuje wymaganie złożenia deklaracji zgodnej z ustawą o ujawnianiu informacji o rachunkach zagranicznych dla celów podatkowych (FATCA).
- Pole 14: używane teraz do raportowania nadmiarowych płatności odpraw.
- Pole 15: używane teraz do raportowania płatności w ramach planów niekwalifikowanego odroczonego wynagrodzenia (NQDC).
- Pole 16: używane teraz do raportowania potrącanych podatków stanowych.
- Pole 17: używane teraz do raportowania stanowego numeru płatnika.
- Pole 18: używane teraz do raportowania dochodu stanowego.

## <a name="accounts-payable-1099--how-do-i-change-the-1099-box-and-values-for-a-vendor-that-wasnt-tracking-1099-information-throughout-the-year"></a>Rozrachunki z dostawcami: 1099 — w jaki sposób zmienić pole i wartości dla dostawcy w formularzu 1099, który nie śledził informacji dotyczących podatku 1099 przez cały rok?

Użyj funkcji **Aktualizacja formularza 1099**, aby przejść przez poprzednio zapłacone transakcje faktur i ponownie prawidłowo przypisać dane 1099 zgodnie z ustawieniami na karcie **Podatek 1099** na stronie **Dostawca**. Aby użyć funkcji **Aktualizacja formularza 1099**, przejdź do **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy**, wybierz dostawcę, a następnie w okienku akcji na karcie **Dostawca** wybierz **Aktualizacja formularza 1099**.

## <a name="can-i-run-the-update-1099-functionality-for-all-my-vendors-at-once"></a>Czy można uruchomić funkcję Aktualizacja formularza 1099 dla wszystkich dostawców jednocześnie?

Strony **Aktualizacja informacji 1099 dla wielu dostawców** można użyć do zaktualizowania pola formularza 1099 w rekordzie dostawcy i aktualizowania transakcji przy użyciu informacji z pola 1099. Aby otworzyć tę stronę, przejdź do **Rozrachunki z dostawcami \> Zadanie okresowe \> Podatek 1099**. Aby uzyskać dostęp do tej strony, należy mieć przypisane uprawnienia zabezpieczeń **Aktualizuj pole i transakcje 1099 dla wielu dostawców**.

## <a name="accounts-payable-1099--recalculate-existing-1099-amounts-versus-update-all-in-the-update-1099-utility"></a>Rozrachunki z dostawcami: 1099 — Oblicz ponownie istniejące kwoty podatku 1099 a Aktualizuj wszystko w narzędziu Aktualizacja formularza 1099

W przypadku jego użycia w połączeniu z polem wyboru **Aktualizuj wszystko** zaznaczenie pola wyboru **Oblicz ponownie istniejące kwoty podatku 1099** spowoduje zresetowanie kwot podatku 1099 do łącznych zapłaconych wartości.

[![Transakcje podatku 1099: przed uruchomieniem rutynowej procedury aktualizacji.](./media/faq-2020-yr-end-08.png)](./media/faq-2020-yr-end-08.png)

Pole wyboru **Oblicz ponownie istniejące kwoty podatku 1099** jest dostępne tylko wtedy, gdy faktura uwzględnia częściowe wartości podatku 1099 lub jeśli faktura została zmodyfikowana w formularzu podatku 1099. Załóżmy na przykład, że faktura jest wyceniona na 1000,00 PLN, ale użytkownik wpisuje ręcznie w formularzu 1099 kwotę 500,00 PLN dla faktury.

[![Transakcje podatku 1099: zaznaczenie zarówno opcji Aktualizuj wszystko, jak i opcji Oblicz ponownie istniejące kwoty podatku 1099.](./media/faq-2020-yr-end-07.png)](./media/faq-2020-yr-end-07.png)

Gdy ta faktura zostanie zapłacona, kwotą zapłaconą na podstawie formularza 1099 będzie 500,00 PLN. W przypadku przeprowadzania procedury ponownego obliczenia kwota w formularzu 1099 zmieni się na 1000,00 PLN, czyli łączną zapłaconą kwotę.

[![Transakcje podatku 1099: po uruchomieniu procedury 1099.](./media/faq-2020-yr-end-09.png)](./media/faq-2020-yr-end-09.png)

## <a name="accounts-payable-1099--manually-create-1099-transactions"></a>Rozrachunki z dostawcami: 1099 — ręczne tworzenie transakcji 1099

Organizacja może wymagać ręcznego utworzenia transakcji 1099, które nie są skojarzone z fakturą. Ręczne transakcje 1099 można dodać, przechodząc do sekcji **Rozrachunki z dostawcami \> Zadania okresowe \> Podatek 1099 \> Rozliczenia dostawcy dotyczące podatku 1099**. Wybierz przycisk **Ręczne transakcje podatku 1099**.

Ręcznie utworzone transakcje dotyczące podatku 1099 nie są aktualizowane przy użyciu narzędzia **Aktualizuj wszystko** ani **Ponowne obliczanie istniejące kwoty podatku 1099** w narzędziu **Aktualizacja formularza 1099**.

## <a name="accounts-payable-1099--does-dynamics-365-finance-support-the-1096-form"></a>Rozrachunki z dostawcami: 1099 — czy rozwiązanie Dynamics 365 Finance obsługuje formularz 1096?

Rozwiązanie Dynamics 365 Finance nie umożliwia wydrukowania formularza 1096 Roczne podsumowanie i przekazywanie informacji zwrotnych w USA.

## <a name="accounts-payable-1099--are-there-any-new-features-that-support-1099-reporting-for-public-sector"></a>Rozrachunki z dostawcami: 1099 — czy są dostępne nowe funkcje do obsługi raportów 1099 dla sektora publicznego?

**Aktualizacja danych formularza 1099 za pośrednictwem konta głównego** to nowa funkcja dla sektora publicznego, którą można włączyć w obszarze roboczym **Zarządzanie funkcjami**. Ta funkcja umożliwia powiązanie wartości formularza 1099 dla dostawcy za pośrednictwem konta głównego w obszarze podziału księgowań, a nie na domyślnym koncie w rekordzie dostawcy.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie dostawców dla raportowania 1099](../localizations/noam-usa-set-up-vndrs-1099-rprtg.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
