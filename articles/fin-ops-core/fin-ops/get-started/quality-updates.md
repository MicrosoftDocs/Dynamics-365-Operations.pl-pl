---
title: Aktywne aktualizacje jakości
description: Ten artykuł zawiera informacje dotyczące aktywnego dostarczania aktualizacji jakości.
author: rashmansur
ms.date: 09/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 25306a8ccebb5cd01debc90cf497d4a942840ef4
ms.sourcegitcommit: 43a0fb019bc67c00c39c2778343ba89924c3322c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671433"
---
# <a name="proactive-quality-updates"></a>Aktywne aktualizacje jakości

[!include[banner](../includes/banner.md)]

W ciągu ostatnich kilku lat firma Microsoft dokonała ciągłych postępów, które nazywamy [One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md). Przesłanie One Version jest proste: im bliżej tego, że możemy mieć wszystkich odbiorców w tej samej wersji oprogramowania, tym wyższa jakość, którą możemy dostarczyć. Znajdujemy i rozwiązujemy problemy jeden raz, a potem szybko dostarczmy te rozwiązania klientom.

To założenie jest potwierdzone przez wyniki: mniejsza liczba problemów w naszych produktach. Jeśli odbiorcy nie używają tej samej wersji, ciągle widzimy, że napotykają na problemy, na które dostępne jest już rozwiązanie. Już poczyniliśmy duże postępy w zakresie Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations i Dynamics 365 Commerce, dzięki najnowszym postępom technicznym, teraz można przejść do następnego kroku. Poniższe informacje informują, co zamierzamy zrobić, co zostało już wykonane, aby ustawić ten etap oraz w jaki sposób i w jakim czasie wprowadzamy nowe możliwości bez przerw.

## <a name="focus-on-quality-updates"></a>Skupienie się na aktualizacjach jakości

Obecnie dostarczamy siedem [aktualizacji usług](public-preview-releases.md) rocznie. Na przykład wersja 10.0.29 jest aktualizacją usługi. Do tego czasu było osiem aktualizacji rocznie. Jednak jedna aktualizacja została porzucona w odpowiedzi na opinię klienta, która ujawniła żądanie, aby uniknąć zmian pod koniec roku kalendarzowego.

Nie będzie można zmieniać kadencji aktualizacji usługi. Zamiast tego, następny krok w przód w ramach procesu One Version będzie dotyczył *aktualizacji jakości*. Aktualizacje jakości to zbiorcze kompilacje poprawek. Nie zawierają nowych funkcji. W dowolnym czasie cała nasza społeczność odbiorców jest rozłożona na trzy lub cztery ostatnie aktualizacje usług. Jednak w przypadku dowolnej aktualizacji usługi w grupie można używać kilkadziesiąt różnych wersji aktualizacji jakości, w zależności od dat wdrażania. W następnym kroku aktywnie rozsyłamy aktualizacje jakości. Już korzystamy z tego modelu w przypadku aplikacji opartych na naszych systemach Dataverse i widzimy oczekiwane wyniki poprawy jakości i zmniejszenia zdarzeń pomocy technicznej.

Zmniejszenie wad może oczywiście zmniejszyć lub całkowicie wyeliminować aktualizacje jakości. W uaktualnianych standardach systemu istnieje wiele inicjatyw mających na celu ograniczenie wad wymagających aktualizacji jakości. Nawet jeśli w ramach aktualizacji jakości zostaną zredukowane obciążenia, spójność bazy klientów poprawi obsługę, szybciej uzyskają usprawnienia i zmniejszy się częstotliwość napotykania na problemy przez klientów, dla których istnieją już rozwiązania.

## <a name="making-proactive-distribution-possible"></a>Tworzenie aktywnej dystrybucji

Wdrożono już wiele postępów umożliwiających prewencyjne dostarczanie aktualizacji jakości:

- **Aktualizowanie blisko zerowego przestoju** — aby wypychać częściej środowiska, konieczne jest zmniejszenie wpływu na dostępność środowiska w celu zachowania umów dotyczących poziomu usług (SLA) usługi Dynamics 365. Aktualizacja blisko zerowego przestoju pierwotnie została wprowadzona, aby pomóc ulepszyć miesięczne poprawianie systemu operacyjnego poprzez zastosowanie trybu failover klastra w celu uaktywnienia zaktualizowanego obrazu z minimalnym przerwaniem. Mechanizm stosowania aktualizacji jest ulepszony, dzięki czemu jeszcze mniej destruktywny i obejmuje zarówno poprawianie systemu operacyjnego, jak i wdrażanie aktualizacji jakości.

    W przypadku interakcyjnych użytkowników aktywna sesja może zostać przerwana, a ponowienie próby zostanie ponowione w środowisku, które zostało teraz zaktualizowane. Dzięki wprowadzeniu [planowania partii opartego na priorytecie](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), które jest obecnie dostępne od razu po aktualizacji, planowanie i przetwarzanie wsadowe odzyska i wznowi działanie natychmiast po aktualizacji. Planowanie wsadowe oparte na priorytecie zostanie oparte na priorytetach, zanim odbiorcy zaczną uczestniczyć w prewencyjnej dystrybucji aktualizacji jakości w swoich środowiskach produkcyjnych.

- **Godziny bezczynności** — są zdefiniowane godziny bezczynności dla każdego regionu Azure, a w trakcie tej godziny występują blisko zerowe aktualizacje przestojów.

## <a name="the-proactive-update-process"></a>Proces aktywnej aktualizacji

Wdrażanie aktywnej aktualizacji jakości będzie zgodne z procesem wdrażania w bezpieczny sposób (SDP). Szczegółowe informacje kodu SDP będą się rozwijać, ale aktualizacje jakości zostaną początkowo wdrożone w środowiskach piaskownicy. Proces rozpocznie się od środowisk, które decydują się na wcześniejsze wdrożenie. Wraz ze wzrostem procentu pomyślnie wdrożonej piaskownicy rozpoczyna się wdrażanie w środowiskach produkcyjnych. Przypominamy, proces rozpocznie się od środowisk, które decydują się na wcześniejsze wdrożenie. W systemach nasłuchiwania system będzie monitorować telemetrię systemu i zdarzenia w aktywnych witrynach, a w przypadku wykrycia jakiegokolwiek zdarzenia spowoduje to zatrzymanie rozsyłania określonej wersji. Odbiorcy nadal będą mogli ściągać aktualizacje jakości przed prewencyjnym wdrożeniem, jeśli będą potrzebne.

Z aktualnych danych zarządzania wydaniami wynika, że w aktualizacjach jakości jest wprowadzonych mniej niż 3% cofnięć. Większy nacisk na eliminację zmian oraz rozszerzony protokół SDP spowoduje, że potencjalny wpływ cofnięć będzie znacznie niższy niż wzrost jakości osiągnięty dzięki większej możliwości szybkiego wdrażania poprawek dla odbiorców.

## <a name="process-changes"></a>Przetwórz zmiany

Zestaw zmian procesów jest implementowany przed aktywacją wdrożenia aktywnej aktualizacji jakości:

- **Schemat** — narzędzie zapewnia, że kompilacje aktualizacji jakości obejmują tylko zmiany schematów, które można zastosować w trybie online usługi. To podejście pomoże zachować możliwość stosowania aktualizacji przy użyciu przestoju najbliższego zera.
- **Zwiększona obserwacja zmian** — obecnie istnieje już dodatkowy krok procesu zatwierdzania zmian uwzględnianych w aktualizacji jakości. Ograniczenie w dodatkowym kroku zostanie zwiększone, aby zmniejszyć ryzyko cofnięć. Zmiany powodujące niezgodność nie są dozwolone w aktualizacjach jakości, a zwiększona obserwacja zmian pomaga zapewnić, że osiągamy ten cel.
- **Widoczność** — powiadomimy za pośrednictwem poczty e-mail i usługi Lifecycle Services (LCS) o zbliżających się aktywnych aktualizacjach jakości. Ponadto zespoły pomocy technicznej i informacje dotyczące zdarzeń mają wgląd w możliwości aktywnego wdrażania aktualizacji jakości.
- **Zabezpieczenie awarii za pomocą dystrybucji testowej** – Funkcja obowiązuje w celu zmiany kodu w razie zastosowania w poprawce aktualizacji jakości lub do użycia istniejących dystrybucji testowych funkcji właściwych dla tej poprawki. Jeśli po proaktywnym wdrożeniu wymagane jest wycofanie lub wyłączenie zmiany, można to zrobić za pośrednictwem systemu lotów, aby uniknąć dalszych awarii.
- **Wyznaczenie synchronizacji piaskownicy** — poniżej 20% odbiorców ma obecnie wiele piaskownic i jedna piaskownica jest wdrożona tam, gdzie wersja odpowiada wersji produkcyjnej, co pomaga w rozwiązywaniu problemów. Jeśli klient używa piaskownicy do testowania nowszej wersji niż w wersji produkcyjnej, ta piaskownica będzie otrzymywać aktualizacje jakości w nowszej wersji.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>Co to jest rozszerzenie planowania dla aktualizacji jakości?

Dystrybucję aktywnych aktualizacji jakości dla środowisk piaskownicy można rozpocząć pod koniec września lub października 2022 dla odbiorców w chmurze publicznej Azure. Środowiska w wersji próbnej również rozpoczną otrzymywanie wdrożenia aktywnej aktualizacji w tym czasie. We wrześniu do każdego klienta zostanie wysłane powiadomienie, aby poinformować go o oczekiwanym harmonogramie dla swojego środowiska. Wyjątki w procesie aktywnej aktualizacji dystrybucji będą dozwolone tylko dla odbiorców podlegających regulacjom z FDA. Nadal pracujemy nad zarządzaniem środowiskami regulowanymi oraz ich odbiorców w chmurze rządowej.

W ciągu następnych sześciu miesięcy będziemy stopniowo zwiększać wartość procentową środowisk piaskownicy, które otrzymują aktywne aktualizacje, dopóki nie zostaną uwzględnione wszystkie wskazane środowiska i nie rozpoczniemy aktualizowania środowisk produkcyjnych. Przez cały okres będziemy monitorować, aby zagwarantować, że proces wdrażania będzie bezproblemowy i że możemy ponownie osiągnąć cel, który nie przerwie obciążeń.

Ponieważ odbiorcy będą regularnie obierać mniejsze obciążenia, oczekujemy, że bieżący proces będzie prostszy. Dostosujemy częstotliwość wdrażania aktualizacji, ponieważ wykazujemy możliwość uruchamiania procesu bez przerwy. Ten proces działa już efektywnie w naszej platformie Dataverse i aplikacjach oraz dostarcza przewidywanych usprawnień jakości usług. Planujemy podjęcie tego samego kroku w przypadku aplikacji finansowych i operacyjnych.

## <a name="when-will-quality-updates-start-for-production-environments"></a>Kiedy rozpocznie się aktualizacja jakości w środowiskach produkcyjnych?
W tej chwili aktualizacje jakości są przeznaczone tylko do środowisk piaskownicy. Zaktualizujemy tę przestrzeń o datę rozpoczęcia dla środowisk produkcyjnych, gdy będziemy mieć bardziej konkretne dane i metryki, od proaktywnych aktualizacji dla piaskownic po ocenę gotowości do produkcji.

## <a name="what-is-the-schedule-for-sandbox-proactive-quality-updates"></a>Co to jest harmonogram dla aktywnych aktualizacji jakości piaskownicy?
Aby uzyskać informacje dotyczące godzin bezczynności w poszczególnych regionach, zobacz [Czym są okna planowanej konserwacji według regionów?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).

### <a name="proactive-quality-update-release-10028"></a>Aktywna aktualizacja jakości, wydanie: 10.0.28
**Wersja aplikacji: 10.0.1265.89**
**Odpowiedni najnowszy artykuł z bazy wiedzy: 745340**

| Stacja | Regiony | Zakończony harmonogram| Nadchodzący harmonogram piaskownicy
|---|---|---|---|
| Stacja 1 | Kanada Środkowa, Kanada Wschodnia, Francja Środkowa, Indie Środkowe, Norwegia Wschodnia, Szwajcaria Zachodnia | Od 15 września do 18 września 2022, a od 19 września do 22 września 2022 | Od 7 października do 10 października 2022 |
| Stacja 2 | Francja Południowa, Indie Południowe, Norwegia Zachodnia, Szwajcaria Północna, Północna Republika Południowej Afryki, Australia Wschodnia, Wschodnie Zjednoczone Królestwo, Północne Zjednoczone Emiraty Arabskie, Japonia Wschodnia, Australia Południowo-Wschodnia, Azja Południowo-Wschodnia | Od 25 września do 28 września 2022 | Od 7 października do 10 października 2022 |
| Stacja 3 | Azja Wschodnia,Zachodnie Zjednoczone Królestwo, Japonia Zachodnia, Brazylia Południowa, Europa Zachodnia, Wschodnie Stany Zjednoczone, Północne Zjednoczone Emiraty Arabskie | Od 26 września do 29 września 2022 | Od 7 października do 10 października 2022 |
| Stacja 4 | Europa Północna, Środkowe Stany Zjednoczone, Zachodnie Stany Zjednoczone | Od 28 września do 1 października 2022 | Od 7 października do 10 października 2022 |
| Stacja 5 | DoD, Government Community Cloud, Chiny | Niezaplanowane | Niezaplanowane |

### <a name="proactive-quality-update-release-10029"></a><a name="schedule"></a> Aktywna aktualizacja jakości, wydanie: 10.0.29
**Wersja aplikacji: 10.0.1326.70**
**Odpowiedni najnowszy artykuł z bazy wiedzy: 748926**

| Stacja | Regiony | Nadchodzący harmonogram piaskownicy
|---|---|---|
| Stacja 1 | Kanada Środkowa, Kanada Wschodnia, Francja Środkowa, Indie Środkowe, Norwegia Wschodnia, Szwajcaria Zachodnia | Od 14 października do 17 października 2022 |
| Stacja 2 | Francja Południowa, Indie Południowe, Norwegia Zachodnia, Szwajcaria Północna, Północna Republika Południowej Afryki, Australia Wschodnia, Wschodnie Zjednoczone Królestwo, Północne Zjednoczone Emiraty Arabskie, Japonia Wschodnia, Australia Południowo-Wschodnia, Azja Południowo-Wschodnia | Od 15 października do 18 października 2022 |
| Stacja 3 | Azja Wschodnia,Zachodnie Zjednoczone Królestwo, Japonia Zachodnia, Brazylia Południowa, Europa Zachodnia, Wschodnie Stany Zjednoczone, Północne Zjednoczone Emiraty Arabskie | Od 16 października do 19 października 2022 |
| Stacja 4 | Europa Północna, Środkowe Stany Zjednoczone, Zachodnie Stany Zjednoczone | Od 17 października do 20 października 2022 |
| Stacja 5 | DoD, Government Community Cloud, Chiny | Niezaplanowane |

> [!IMPORTANT] 
> Pięć dni wcześniej firma Microsoft zaktualizuje poprzedni harmonogram i wysyła powiadomienia pocztą e-mail do zestawu środowisk, które mają otrzymać te aktualizacje jakości. Poprzedni harmonogram ma zastosowanie tylko do środowisk, które zostały powiadomione o nadchodzącej aktualizacji. Aby uzyskać informacje dotyczące godzin bezczynności w poszczególnych regionach, zobacz [Czym są okna planowanej konserwacji według regionów?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).
>
> Dla każdej grupy regionów lub *stacji*, dla której zaplanowano aktualizację jakości, która ma zostać wydana, plan pokazuje zakres czterech dni. Aktualizacje jakości rozpoczną się tylko w środowiskach piaskownicy. Następnie wraz ze wzrostem procentu pomyślnie wdrożonej piaskownicy rozpoczyna się wdrażanie w środowiskach produkcyjnych po uprzednim powiadomieniu klientów.
> 
> Aktualizacje jakości zawsze będą się powtarzać, co pozwala nam określić zestaw środowisk zgodnie z planem i zakończyć wszystkie zestawy do końca czwartego dnia dla stacji. Nie oznacza to jednak, że aktualizacja środowiska potrwa cztery dni. Oznacza to, że nie można wstępnie określić, który zestaw środowisk zostanie zaktualizowany danego dnia w przedziale czterech dni. Wszystkie aktualizacje zostaną wykonane w godzinach nocnych, prawie nie powodując przestoju. Aktualizacje będą ostatecznie kończyć się w nocnym oknie danego regionu.

## <a name="how-are-the-dark-hours-handled-for-customers-that-have-one-finance-and-operations-apps-instance-but-are-active-in-multiple-time-zones"></a>W jaki sposób godziny bezczynności są obsługiwane dla odbiorców, którzy mają jedno wystąpienie aplikacji finansowych i operacyjnych, ale są aktywni w różnych strefach czasowych? 
Poza godzinami bezczynności nie ma żadnych specjalnych harmonogramów, w których istnieje wystąpienie aplikacji finansowych i operacyjnych, ponieważ planujemy wydać aktualizacje jakości w sposób minimalnie wpływający na działalność za pomocą [nZDT](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## <a name="what-is-the-current-rollout-cadence-for-proactive-quality-updates"></a>Czym jest bieżąca częstotliwość wydań dla aktywnych aktualizacji jakości?
Prewencyjne aktualizacje jakości (PQU) są obecnie wysyłane raz w miesiącu dla każdej obsługiwanej wersji aktualizacji usługi. Tylko jedna aktualizacja na miesiąc jest wypychana dla wybranego środowiska piaskownicy, chyba że odbiorcy przeniosą się do nowej wersji aktualizacji usługi. W takim przypadku mogą uzyskać zaplanowany wcześniej PQU jako część istniejącego szkolenia w ramach nowej aktualizacji usługi. W 2023 roku po zakończeniu rozsyłania na całym świecie częstotliwość tych aktualizacji będzie się zwiększać. Zawsze jest odbierane co najmniej jedno miesięczne powiadomienie, ilekroć istnieje zmiana czasu wysyłki.

## <a name="how-will-microsoft-ensure-the-quality-of-these-updates"></a>W jaki sposób firma Microsoft zapewni jakość tych aktualizacji?
Firma Microsoft stara się, by proces zwalniania potoku był wystarczająco wydajny, aby dostarczać małe ładunki, aby zachować niski koszt walidacji. Każda poprawka w aktualizacji jakości jest przetwarzana zgodnie z surowym i bezpiecznym procesem wdrażania, który pomaga poprawić jakość i niezawodność, zmniejszając w ten sposób wpływ na klientów. Wdrażanie będzie się odbywało w etapach najpierw w środowiskach piaskownicy, a następnie w produkcji. Wdrożenia etapowe umożliwiają odpowiednie monitorowanie, aby ustalić, czy dalsze wdrożenie jest bezpieczne. Zatrzymamy wdrażanie w przypadku wykrycia problemów z każdą grupą wdrożonych klientów i zapewnimy, że każdy etap wprowadzania będzie miał wystarczający czas na rozwiązanie problemów. W przypadku każdej nadchodzącej aktualizacji jakości zapewnimy wzgląd w harmonogram poprzez aktualizacje dokumentacji publicznej i wiadomości e-mail, dzięki czemu klienci mogą planować z wyprzedzeniem.

## <a name="can-customers-delay-reschedule-or-pause-a-quality-update"></a>Czy odbiorcy mogą opóźniać, ponownie zaplanować lub wstrzymać aktualizację jakości?
Nie. Głównym celem aktualizacji jakości jest zapewnienie podstawowych zabezpieczeń, prywatności, niezawodności, dostępności i wydajności oraz ciągle usprawnianie dla naszych klientów. Opóźnienie lub wstrzymanie aktualizacji, zabezpieczeń, dostępności i niezawodności będzie stanowiło zagrożenie.

## <a name="how-do-i-know-what-set-of-changes-went-into-a-quality-update-payload"></a>W jaki sposób mogę się dowiedzieć, jaki zestaw zmian wszedł w ładunek aktualizacji jakości?
Poniższe kroki są tymczasowym rozwiązaniem, w związku z tym, że nadal pracujemy nad rozwiązaniem lepiej dostępnym, aby zidentyfikować listę zmian, które zostaną wprowadzone w ładunku aktualizacji jakości. 

Użyj artykułu z bazy wiedzy 745340 dla szkolenia aktualizacji jakości 10.0.28 i powiązanej wersji 10.0.1265.89.

1. W usłudze LCS i otwórz stronę **Szczegóły środowiska** dla piaskownicy. 
2. W sekcji **Dostępne aktualizacje** wybierz pozycję **Wyświetl aktualizację** dla najnowszej kompilacji aktualizacji jakości. 
3. Wyeksportuj kompilację do formatu CSV lub pliku Microsoft Excel.
4. W eksportowanym pliku sortuj informacje na podstawie czasu (poczynając od najstarszego), a następnie wyszukaj numer artykułu z bazy wiedzy numer 745340 w kolumnie **Identyfikator aktualizacji**. Powinna teraz istnieć możliwość wybaczenia listy delta bazy wiedzy.
 
 > [!NOTE]
 > Eksport do pliku CSV lub Excel musi nastąpić przed zaktualizowaniem środowiska. W przeciwnym razie możesz użyć środowiska o podobnej konfiguracji, w którym nie zainstalowano aktualizacji, i wykonać kroki powyżej.

[![Przykład środowiska z aktualizacją jakości.](./media/how-to-get-kb-list-pqu.png)](./media/how-to-get-kb-list-pqu.png)

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>Co dzieje się w przypadku, gdy po aktualizacji jakości zostanie znaleziony problem krytyczny?
Problem krytyczny lub wycofanie to co najmniej jedno ze zdarzeń, które zwykle powodują, że wielu odbiorców doświadcza zdegradowanego doświadczenia w jednej lub większej liczbie usług. Te problemy mogą powodować nieplanowany przestój, w tym brak dostępności, obniżenie wydajności i problemy związane z zarządzaniem usługą. Jeśli takie problemy mają poważny wpływ na klienta, do czasu omówienia i rozwiązania problemu zostanie zatrzymane wprowadzanie aktualizacji jakości. Zazwyczaj następna aktualizacja jakości będzie wymagała poprawki, aby wznowić wprowadzanie.

Jeśli dotyczy tylko jednego środowiska klienta, skontaktuj się z pomocą techniczną firmy Microsoft, aby utworzyć bilet. Na podstawie uzasadnienia zatrzymamy wprowadzanie aktualizacji jakości dla wszystkich innych środowisk w tym projekcie do czasu usunięcia problemu.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lcs"></a>Czy odbiorcy mogą nadal ręcznie stosować aktualizacje poprawek z usługi LCS?
Tak. Aby zapewnić trwającą parzystość z tym, jak poprawki działają, nadal można stosować aktualizacje poprawek do środowisk klientów w usługach LCS. Jednak przed wdrożeniem aktualizacji ważne jest, aby pamiętać, że poprawki wdrożone w ramach aktualizacji jakości przejść przez standardową aktualizację SDP. Zmniejsza to ryzyko związane z dostępem do materiałów o większej jakości. Zaleca się wybranie aktualizacji jakości poprzez ręczne stosowanie poprawek w celu zwiększenia niezawodności.

## <a name="can-customers-proactively-install-a-quality-update-build-ahead-of-the-schedule"></a>Czy klienci mogą wcześniej instalować kompilację aktualizacji jakości?
Tak. Aktualizację jakości można zainstalować proaktywnie. Firma Microsoft pominie aktualizację, jeśli bieżąca wersja kompilacji środowiska jest równa lub wyższa od bieżącej aktualizacji jakości.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Jeśli w środowisku w ciągu tygodnia zaplanowana jest planowana miesięczna aktualizacja usługi, czy nadal otrzyma ono aktualizacje jakości?
- Aktualizacje jakości nie są stosowane w środowiskach produkcyjnych, jeśli w ciągu tygodnia zaplanowano aktualizację usługi, która ma zostać zaplanowana.
- Jeśli środowisko piaskownicy ma taką samą lub nowszą wersję kompilacji niż zbliżającą się aktualizacja jakości, zostanie pominięta.
- Jeśli środowisko produkcyjne ma taką samą lub nowszą wersję kompilacji niż zbliżającą się aktualizacja jakości, zostanie pominięta.
- Jeśli piaskownica ma tę samą lub nowszą wersję kompilacji z powodu aktualizacji jakości lub ręcznej aktualizacji do produkcji, produkcja nadal będzie tworzyć zaplanowaną wersję miesięcznej aktualizacji usługi. Jeśli nie chcesz, aby zaplanowane środowisko produkcyjne było aktualizowane do wersji aktualizacji usługi, możesz wstrzymać aktualizację usługi z poziomu usługi LCS. 
- Zaleca się korzystanie z najnowszej kompilacji aktualizacji jakości w celu przetestowania zmian nachodzącej aktualizacji usługi w celu lepszej stabilności i wyników.

## <a name="if-an-environment-has-an-upcoming-scheduled-action-and-a-scheduled-quality-update-in-the-same-maintenance-window-will-it-still-receive-the-quality-update"></a>Czy środowisko ma zaplanowaną akcję zbliżającą się i zaplanowaną aktualizację jakości w tym samym oknie konserwacji, czy nadal będzie otrzymywać aktualizację jakości?
Jeśli istnieje konflikt ze wstępnie zaplanowaną akcją, na przykład przywrócenie punktu w czasie (PITR), aktualizacja jakości zostanie ponownie zaplanowana do następnego dostępnego czterodniowego okna konserwacji. Aby uzyskać więcej informacji dotyczących harmonogramu, zobacz [Co to jest harmonogram aktywnych aktualizacji jakości?](#schedule). 

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>Czy środowisko może zostać przywrócone do poprzedniego stanu, jeśli po zastosowaniu aktualizacji jakości wystąpią problemy?
Po zastosowaniu aktualizacji jakości nie ma możliwości wycofywania w żadnych okolicznościach. Dostępne są tylko opcje poprawiania, aby zminimalizować problemy.

## <a name="what-about-fda-regulation-and-gpx"></a>Co to są przepisy FDA i GPX?
Plan dla odbiorców podlegających weryfikacji i przepisom FDA jest nadal rozwijany. Należy oczekiwać wkrótce większej liczby aktualizacji w tym miejscu. Na razie wszyscy tego typu odbiorcy są zwolnieni z aktualizacji jakości. Aby zapewnić, że odbiorca podlega przepisom ustawy FDA, odwiedź [Ofertę Microsoft Azure GPX](/azure/compliance/offerings/offering-gxp).

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>Które wersje aktualizacji usług są obsługiwane w przypadku tych aktualizacji jakości?
Klienci wszystkich obsługiwanych wersji usługi kwalifikują się do aktualizacji jakości. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retailsdk"></a>Wdrożenia aplikacji finansowych i operacyjnych ze składnikami Retail z reguły wymagają dodatkowej pracy oprócz ponownego rozmieszczenia wdrożenia MPOS. Jak te aktualizacje jakości będą miały wpływ na RetailSDK? 
Ponieważ charakter poprawki nie zmienia się w ładunku aktualizacji jakości, więc nie przewidujemy w tej chwili żadnego dodatkowego wpływu, w szczególności związanego ze składnikami Retail.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che"></a>Czy ma wpływ na środowiska hostowane w chmurze (CHE)? 
Środowiska CHE spoza zakresu aktualizacji jakości, ponieważ są poza zakresem rozwiązania Microsoft

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>Czy występują problemy z integracją z programem Microsoft Dataverse? 
Brak znanych problemów z integracją związanych z aktualizacjami jakości za pomocą Dataverse.

