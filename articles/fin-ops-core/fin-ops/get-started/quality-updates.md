---
title: Aktywne aktualizacje jakości
description: Ten artykuł zawiera informacje dotyczące aktywnego dostarczania aktualizacji jakości.
author: rashmansur
ms.date: 11/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 7d8de017c54a13a9935d74d33a57813922c9f823
ms.sourcegitcommit: 8aee31d6dffabe13969dd5b9de4e0bf95f53e67e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887138"
---
# <a name="proactive-quality-updates"></a>Aktywne aktualizacje jakości

[!include[banner](../includes/banner.md)]

W ciągu ostatnich kilku lat firma Microsoft dokonała ciągłych postępów, które nazywamy [One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md). Przesłanie One Version jest proste: im bliżej tego, że możemy mieć wszystkich odbiorców w tej samej wersji oprogramowania, tym wyższa jakość, którą możemy dostarczyć. Znajdujemy i rozwiązujemy problemy jeden raz, a potem szybko dostarczmy te rozwiązania klientom.

To założenie jest potwierdzone przez wyniki: mniejsza liczba problemów w naszych produktach. Jeśli odbiorcy nie używają tej samej wersji, ciągle widzimy, że napotykają na problemy, na które dostępne jest już rozwiązanie. Już poczyniliśmy duże postępy w zakresie Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations i Dynamics 365 Commerce, dzięki najnowszym postępom technicznym, teraz można przejść do następnego kroku. Poniższe informacje informują, co zamierzamy zrobić, co zostało już wykonane, aby ustawić ten etap oraz w jaki sposób i w jakim czasie wprowadzamy nowe możliwości bez przerw.

## <a name="what-you-need-to-know"></a>Czego potrzeba wiedzieć

- Prewencyjne aktualizacje jakości (PQU) są stosowane co miesiąc.
- Wyjątki dotyczące proaktywnych aktualizacji jakości będą dozwolone w przypadku klientów podlegających regulacjom Amerykańskiej Agencji ds. Żywności i Leków (FDA).
- Proaktywne aktualizacje jakości nigdy nie spowodują obniżenia jakości środowiska lub automatycznego przejścia z jednej wersji aktualizacji do drugiej. 
- Firma Microsoft ustala, jak prewencyjne aktualizacje jakości będą zarządzane w środowiskach regulowanych oraz w przypadku odbiorców w chmurze i w chmurze rządowej.
- Powiadomienia dotyczące proaktywnych aktualizacji jakości są umieszczane w [Centrum wiadomości Microsoft 365](https://admin.microsoft.com/AdminPortal/).
- Pięć dni przed zastosowaniem proaktywnej aktualizacji jakości w środowisku klienci są powiadamiani, że nastąpi aktualizacja.
- Odbiorcy nie mogą anulować ani opóźnić prewencyjnych aktualizacji jakości.
- Prewencyjne aktualizacje jakości są instalowane w oknie konserwacji specyficznej dla [regionu](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).
- Aktualizacje jakości są tak opracowane, aby mieć niskie ryzyko wystąpienia problemów lub przemów, i są one obsługiwane przez dane firmy Microsoft.
- Firma Microsoft zaleca testowanie na poziomie docelowym w przypadku określonych problemów lub określonych poprawek związanych z prewencyjną aktualizacją jakości.
- WSZYSTKIE środowiska piaskownicy, z wyjątkiem tych, które mają ograniczony czasowo wyjątek ze względu na przepisy, zostaną włączone do 7 stycznia 2023 roku.
- Wprowadzanie do produkcji aktualizacji proaktywnej jakości rozpocznie się 21 stycznia 2023 roku. 
- Włączenie produkcyjne rozpocznie się tylko w przypadku projektów Lifecycle Services, które mają włączoną piaskownicę (piaskownice) i do tej pory regularnie otrzymują proaktywne aktualizacje jakości dla wszystkich wspieranych wersji aktualizacji usług. Dotyczy to tylko środowisk klientów, którym nie zapewniono żadnych wyjątków ze względu na przepisy lub inne przyczyny prawne.
- Pełny harmonogram proaktywnych aktualizacji jakości dla środowisk piaskownicowych i produkcyjnych w ciągu 2023 roku znajduje się poniżej.
- Przy każdej aktualizacji serwisu trwa lub ma się rozpocząć co najmniej jedna wersja do wydania PQU. Kiedy twoje środowiska zostaną włączone do procesu PQU, możesz otrzymać zaplanowaną wcześniej proaktywną aktualizację jakości dla wszystkich z nich, kiedy przejdziesz na nowszą wersję aktualizacji usługi. Jeśli planujesz aktualizację do nowszej wersji, sprawdź harmonogram, aby ustalić, kiedy jest zaplanowany PQU dla aktualizacji serwisowej. 

> [!Note]
> Standardowy test wydajności (tier4), test wydajności Premium (tier5) sandboxy i środowiska produkcyjne będą otrzymywać PQUs w weekendy. 

## <a name="focus-on-quality-updates"></a>Skupienie się na aktualizacjach jakości

Obecnie dostarczamy siedem [aktualizacji usług](public-preview-releases.md) rocznie. Na przykład wersja 10.0.29 jest aktualizacją usługi. Do tego czasu było osiem aktualizacji rocznie. Jednak jedna aktualizacja została porzucona w odpowiedzi na opinię klienta, która ujawniła żądanie, aby uniknąć zmian pod koniec roku kalendarzowego.

Nie będzie można zmieniać kadencji aktualizacji usługi. Zamiast tego, następny krok w przód w ramach procesu One Version będzie dotyczył *aktualizacji jakości*. Aktualizacje jakości to zbiorcze kompilacje poprawek. Nie zawierają nowych funkcji. W dowolnym czasie cała nasza społeczność odbiorców jest rozłożona na trzy lub cztery ostatnie aktualizacje usług. Jednak w przypadku dowolnej aktualizacji usługi w grupie można używać kilkadziesiąt różnych wersji aktualizacji jakości, w zależności od dat wdrażania. W następnym kroku aktywnie rozsyłamy aktualizacje jakości. Już korzystamy z tego modelu w przypadku aplikacji opartych na naszych systemach Dataverse i widzimy oczekiwane wyniki poprawy jakości i zmniejszenia zdarzeń pomocy technicznej.

Zmniejszenie wad może oczywiście zmniejszyć lub całkowicie wyeliminować aktualizacje jakości. W uaktualnianych standardach systemu istnieje wiele inicjatyw mających na celu ograniczenie wad wymagających aktualizacji jakości. Nawet jeśli w ramach aktualizacji jakości zostaną zredukowane obciążenia, spójność bazy klientów poprawi obsługę, szybciej uzyskają usprawnienia i zmniejszy się częstotliwość napotykania na problemy przez klientów, dla których istnieją już rozwiązania.

## <a name="making-proactive-distribution-possible"></a>Tworzenie aktywnej dystrybucji

Wdrożono już wiele postępów umożliwiających prewencyjne dostarczanie aktualizacji jakości:

- **Aktualizowanie blisko zerowego przestoju** — aby wypychać częściej środowiska, konieczne jest zmniejszenie wpływu na dostępność środowiska w celu zachowania umów dotyczących poziomu usług (SLA) usługi Dynamics 365. Aktualizacja blisko zerowego przestoju pierwotnie została wprowadzona, aby pomóc ulepszyć miesięczne poprawianie systemu operacyjnego poprzez zastosowanie trybu failover klastra w celu uaktywnienia zaktualizowanego obrazu z minimalnym przerwaniem. Mechanizm stosowania aktualizacji jest ulepszony, dzięki czemu jeszcze mniej destruktywny i obejmuje zarówno poprawianie systemu operacyjnego, jak i wdrażanie aktualizacji jakości.

    W przypadku interakcyjnych użytkowników aktywna sesja może zostać przerwana, a ponowienie próby zostanie ponowione w środowisku, które zostało teraz zaktualizowane. Dzięki wprowadzeniu [planowania partii opartego na priorytecie](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md) planowanie i przetwarzanie wsadowe odzyska i wznowi działanie natychmiast po aktualizacji. Planowanie wsadowe oparte na priorytecie zostanie oparte na priorytetach, zanim odbiorcy zaczną uczestniczyć w prewencyjnej dystrybucji aktualizacji jakości w swoich środowiskach produkcyjnych.

- **Godziny bezczynności** — są zdefiniowane godziny bezczynności dla każdego regionu Azure, a w trakcie tej godziny występują blisko zerowe aktualizacje przestojów.

## <a name="the-proactive-update-process"></a>Proces aktywnej aktualizacji

Wdrażanie aktywnej aktualizacji jakości będzie zgodne z procesem wdrażania w bezpieczny sposób (SDP). Szczegółowe informacje kodu SDP będą się rozwijać, ale aktualizacje jakości zostaną początkowo wdrożone w środowiskach piaskownicy. Wraz ze wzrostem procentu pomyślnie wdrożonej piaskownicy rozpoczyna się wdrażanie w środowiskach produkcyjnych. W systemach nasłuchiwania system będzie monitorować telemetrię systemu i zdarzenia w aktywnych witrynach, a w przypadku wykrycia jakiegokolwiek zdarzenia spowoduje to zatrzymanie rozsyłania określonej wersji. Odbiorcy nadal będą mogli ściągać aktualizacje jakości przed prewencyjnym wdrożeniem, jeśli będą potrzebne.

Z aktualnych danych zarządzania wydaniami wynika, że w aktualizacjach jakości jest wprowadzonych mniej niż 3% cofnięć. Większy nacisk na eliminację zmian oraz rozszerzony protokół SDP spowoduje, że potencjalny wpływ cofnięć będzie znacznie niższy niż wzrost jakości osiągnięty dzięki większej możliwości szybkiego wdrażania poprawek dla odbiorców.

## <a name="process-changes"></a>Przetwórz zmiany

Zestaw zmian procesów jest implementowany przed aktywacją wdrożenia aktywnej aktualizacji jakości:

- **Schemat** — narzędzie zapewnia, że kompilacje aktualizacji jakości obejmują tylko zmiany schematów, które można zastosować w trybie online usługi. To podejście pomoże zachować możliwość stosowania aktualizacji przy użyciu przestoju najbliższego zera.
- **Zwiększona obserwacja zmian** — obecnie istnieje już dodatkowy krok procesu zatwierdzania zmian uwzględnianych w aktualizacji jakości. Ograniczenie w dodatkowym kroku zostanie zwiększone, aby zmniejszyć ryzyko cofnięć. Zmiany powodujące niezgodność nie są dozwolone w aktualizacjach jakości, a zwiększona obserwacja zmian pomaga zapewnić, że osiągamy ten cel.
- **Widoczność** — powiadomienia są wysyłane przez centrum administracyjne, Lifecycle Services i inne dostępne kanały dotyczące nadchodzących proaktywnych aktualizacji jakości. Ponadto zespoły pomocy technicznej i informacje dotyczące zdarzeń mają wgląd w możliwości aktywnego wdrażania aktualizacji jakości.

    > [!NOTE]
    > Zespół ds. komunikacji Microsoft bada postępującą degradację narzędzi poczty e-mail, która uniemożliwia dostarczanie powiadomień e-mail. Kontynuuj monitorowanie Centrum wiadomości Microsoft 365 pod kątem wiadomości powiązanych z dołączaniem i powiadomieniami.

- **Zabezpieczenie awarii za pomocą dystrybucji testowej** – Funkcja obowiązuje w celu zmiany kodu w razie zastosowania w poprawce aktualizacji jakości lub do użycia istniejących dystrybucji testowych funkcji właściwych dla tej poprawki. Jeśli po proaktywnym wdrożeniu wymagane jest wycofanie lub wyłączenie zmiany, można to zrobić za pośrednictwem systemu lotów, aby uniknąć dalszych awarii.
- **Oznaczenie synchronizacji w piaskownicy** – Rozłozona w czasie aktualizacja do wyizolowanej piaskownicy do wyboru wraz z produkcją nie jest obecnie obsługiwana. W projekcie Lifecycle Services wszystkie piaskownice warstwy 2 i 3 będą otrzymywać proaktywne aktualizacje co najmniej 7 dni przed uruchomieniem środowiska produkcyjnego. Dotyczy to tylko środowisk klientów, dla których nie przewidziano żadnych wyjątków ze względu na przepisy lub inne przyczyny prawne.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>Co to jest rozszerzenie planowania dla aktualizacji jakości?

Dystrybucja proaktywnych aktualizacji jakości dla środowisk piaskownicy rozpoczęła się we wrześniu 2022 roku dla klientów chmury publicznej Azure. Do 1 stycznia 2023 roku zakończymy włączanie 99% piaskownic do proaktywnych aktualizacji jakości.

Wyjątki w procesie aktywnej aktualizacji dystrybucji będą dozwolone tylko dla odbiorców podlegających regulacjom z FDA. Nadal pracujemy nad zarządzaniem środowiskami regulowanymi oraz ich odbiorców w chmurze rządowej. 

Ponieważ odbiorcy będą regularnie obierać mniejsze obciążenia, oczekujemy, że bieżący proces będzie prostszy. Dostosujemy częstotliwość wdrażania aktualizacji, ponieważ wykazujemy możliwość uruchamiania procesu bez przerwy. Ten proces działa już efektywnie w naszej platformie Dataverse i aplikacjach oraz dostarcza przewidywanych usprawnień jakości usług. Robimy ten sam krok naprzód dla aplikacji finansowych i operacyjnych.


## <a name="when-will-quality-updates-start-for-production-environments"></a>Kiedy rozpocznie się aktualizacja jakości w środowiskach produkcyjnych?
W ciągu kilku pierwszych miesięcy 2023 roku, począwszy od 15 stycznia, rozpoczniemy włączanie środowisk produkcyjnych do aktualizacji proaktywnych i stopniowo będziemy zwiększać odsetek środowisk produkcyjnych, które otrzymują aktualizacje proaktywne. W projekcie Lifecycle Services wybierzemy tylko środowisko produkcyjne, w którym znajdują się już środowiska piaskownicowe, aby otrzymywać proaktywne aktualizacje. Przed aktualizacją klienci, których środowiska produkcyjne są włączane do systemu, zostaną o tym powiadomieni poprzez centrum wiadomości lub baner Lifecycle Services. Pełny harmonogram proaktywnych aktualizacji jakości dla środowisk piaskownicowych i produkcyjnych w ciągu 2023 roku znajduje się poniżej.

## <a name="what-is-the-schedule-for-sandbox-proactive-quality-updates"></a>Co to jest harmonogram dla aktywnych aktualizacji jakości piaskownicy?
Aby uzyskać informacje dotyczące godzin bezczynności w poszczególnych regionach, zobacz [Czym są okna planowanej konserwacji według regionów?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).

### <a name="proactive-quality-update-release-10029"></a><a name="schedule"></a> Aktywna aktualizacja jakości, wydanie: 10.0.29
**Wersja aplikacji: 10.0.1326.70**  
**Odpowiedni najnowszy artykuł z bazy wiedzy: 750332**

| Stacja | Regiony | Zakończony harmonogram | Nadchodzący harmonogram piaskownicy|
|---|---|---|---|
| Stacja 1 | Kanada Środkowa, Kanada Wschodnia, Francja Środkowa, Indie Środkowe, Norwegia Wschodnia, Szwajcaria Zachodnia | 14–17 października 2022 r., 2–5 listopada 2022 r., 13–16 listopada 2022 r., 5–8 grudnia 2022 r. | 2–5 stycznia 2023 r. |
| Stacja 2 | Francja Południowa, Indie Południowe, Norwegia Zachodnia, Szwajcaria Północna, Północna Republika Południowej Afryki, Australia Wschodnia, Wschodnie Zjednoczone Królestwo, Północne Zjednoczone Emiraty Arabskie, Japonia Wschodnia, Australia Południowo-Wschodnia, Azja Południowo-Wschodnia | 15–18 października 2022 r., 2–5 listopada 2022 r., 13–16 listopada 2022 r., 5–8 grudnia 2022 r. | 2–5 stycznia 2023 r. |
| Stacja 3 | Azja Wschodnia,Zachodnie Zjednoczone Królestwo, Japonia Zachodnia, Brazylia Południowa, Europa Zachodnia, Wschodnie Stany Zjednoczone, Północne Zjednoczone Emiraty Arabskie | 16–19 października 2022 r., 2–5 listopada 2022 r., 13–16 listopada 2022 r., 5–8 grudnia 2022 r. | 2–5 stycznia 2023 r. |
| Stacja 4 | Europa Północna, Środkowe Stany Zjednoczone, Zachodnie Stany Zjednoczone | 17–20 października 2022 r., 2–5 listopada 2022 r., 15–18 listopada 2022 r., 5–8 grudnia 2022 r. | 2–5 stycznia 2023 r. |
| Stacja 5 | DoD, Government Community Cloud, Chiny | Niezaplanowane | Niezaplanowane |

### <a name="proactive-quality-update-release-10030"></a><a name="schedule"></a> Aktywna aktualizacja jakości, wydanie: 10.0.30
**Wersja aplikacji: 10.0.1362.77**
**Odpowiedni najnowszy artykuł z bazy wiedzy: 767597**

| Stacja | Regiony | Zakończony harmonogram | Nadchodzący harmonogram piaskownicy |
|---|---|---|---|
| Stacja 1 | Kanada Środkowa, Kanada Wschodnia, Francja Środkowa, Indie Środkowe, Norwegia Wschodnia, Szwajcaria Zachodnia | Od 1 grudnia do 4 grudnia 2022 |  Od 13 grudnia do 16 grudnia 2022 | 
| Stacja 2 | Francja Południowa, Indie Południowe, Norwegia Zachodnia, Szwajcaria Północna, Północna Republika Południowej Afryki, Australia Wschodnia, Wschodnie Zjednoczone Królestwo, Północne Zjednoczone Emiraty Arabskie, Japonia Wschodnia, Australia Południowo-Wschodnia, Azja Południowo-Wschodnia | Od 2 grudnia do 5 grudnia 2022 |  Od 13 grudnia do 16 grudnia 2022 | 
| Stacja 3 | Azja Wschodnia,Zachodnie Zjednoczone Królestwo, Japonia Zachodnia, Brazylia Południowa, Europa Północna, Wschodnie Stany Zjednoczone, Północne Zjednoczone Emiraty Arabskie | Od 3 grudnia do 6 grudnia 2022 |  Od 13 grudnia do 16 grudnia 2022 | 
| Stacja 4 | Europa Zachodnia, Środkowe Stany Zjednoczone, Zachodnie Stany Zjednoczone | Od 4 grudnia do 7 grudnia 2022 |  Od 13 grudnia do 16 grudnia 2022 | 
| Stacja 5 | DoD, Government Community Cloud, Chiny | Niezaplanowane | Niezaplanowane |

### <a name="proactive-quality-update-calendar-year-2023-schedule"></a><a name="schedule"></a> Proaktywna aktualizacja jakości – Harmonogram na rok kalendarzowy 2023

#### <a name="stations-to-region-mapping"></a><a name="Stations-Regions"></a> Mapowanie stacji na region

| Stacje | Regiony |
|---|---|
| Stacja 1 | Do wykonania |
| Stacja 2 | Kanada Środkowa, Kanada Wschodnia, Francja Środkowa, Indie Środkowe, Norwegia Wschodnia, Szwajcaria Zachodnia |
| Stacja 3 | Francja Południowa, Indie Południowe, Norwegia Zachodnia, Szwajcaria Północna, Północna Republika Południowej Afryki, Australia Wschodnia, Wschodnie Zjednoczone Królestwo, Północne Zjednoczone Emiraty Arabskie, Japonia Wschodnia, Australia Południowo-Wschodnia, Azja Południowo-Wschodnia |
| Stacja 4 | Azja Wschodnia,Zachodnie Zjednoczone Królestwo, Japonia Zachodnia, Brazylia Południowa, Europa Północna, Wschodnie Stany Zjednoczone, Północne Zjednoczone Emiraty Arabskie |
| Stacja 5 | Europa Zachodnia, Środkowe Stany Zjednoczone, Zachodnie Stany Zjednoczone |
| Stacja 6 | DoD, Government Community Cloud, Chiny |


> [!IMPORTANT]
> Jest to ogólny harmonogram na rok 2023. Bardziej konkretny harmonogram znajdziesz w poniższym przykładzie dla styczniowego 2 wydania wersji aplikacji 10.0.30. Dokładny harmonogram i wersja aplikacji zostaną zaktualizowane na 7 dni przed rozpoczęciem pociągu do aktualizacji jakości.

> [!Note]
> Tylko środowiska produkcyjne znajdujące się na pokładzie otrzymają aktualizację do 2 wydania wersji 10.0.30, środowiska znajdujące się na pokładzie otrzymają wyraźny komunikat.

| Aktualizacja jakości – wdrożenie | Wersja | Czas trwania wdrożenia |
|---|---|---|
| 2 wydanie 10.0.30 | 16 grudnia 2022 r. | 2–29 stycznia 2023 r. |
| 3 wydanie wersji 10.0.30 | 13 stycznia 2023 r. | 30 stycznia do 25 lutego 2023 r. |
| 4 wydanie 10.0.30 | 24 lutego 2023 | 6 marca do 8 kwietnia 2023 r. |
| 1 wydanie wersji 10.0.31 | 3 lutego 2023 | 13 lutego 2023 r. do 18 marca 2023 r.|
| 2 wydanie wersji 10.0.31 | 3 marca 2023 | 13 marca 2023 r. do 15 kwietnia 2023 r.|
| 3 wydanie wersji 10.0.31 | 14 kwietnia 2023 r. | 24 kwietnia 2023 r. do 27 maja 2023 r.|
| 1 wydanie wersji 10.0.32 | 31 marca 2023 | 10 kwietnia 2023 r. do 13 maja 2023 r.|
| 2 wydanie wersji 10.0.32 | 28 kwietnia 2023 r. | 8 maja 2023 r. do 10 czerwca 2023 r.|
| 3 wydanie wersji 10.0.32 | 26 maja 2023 r. | 5 czerwca 2023 r. do 8 lipca 2023 r.|
| 1 wydanie wersji 10.0.33 | 28 kwietnia 2023 r. | 8 maja 2023 r. do 10 czerwca 2023 r.|
| 2 wydanie wersji 10.0.33 | 26 maja 2023 r. | 5 czerwca 2023 r. do 8 lipca 2023 r.|
| 3 wydanie wersji 10.0.33 | 14 lipca 2023 r. | 24 lipca 2023 r. do 26 sierpnia 2023 r.|
| 1 wydanie wersji 10.0.34 | 23 czerwca 2023 r. | 3 lipca 2023 r. do 5 sierpnia 2023 r.|
| 2 wydanie wersji 10.0.34 | 21 lipca 2023 r. | 31 lipca 2023 r. do 2 września 2023 r.|
| 3 wydanie wersji 10.0.34 | 1 września 2023 r. | 11 września 2023 r. do 14 października 2023 r.|
| 1 wydanie wersji 10.0.35 | 28 lipca 2023 r. | 7 sierpnia 2023 r. do 9 września 2023 r.|
| 2 wydanie wersji 10.0.35 | 25 sierpnia 2023 r. | 4 września 2023 r. do 7 października 2023 r.|
| 3 wydanie wersji 10.0.35 | 20 października 2023 r. | 30 października 2023 r. do 16 grudnia 2023 r.|
| 1 wydanie wersji 10.0.36 | 29 września 2023 r. | 9 października 2023 r. do 11 listopada 2023 r.|
| 2 wydanie wersji 10.0.36 | 27 października 2023 r. | 6 listopada 2023 r. do 16 grudnia 2023 r.|
| 3 wydanie wersji 10.0.36 | 12 stycznia 2024 | 22 stycznia 2023 r. do 24 lutego 2024 r.|
| 1 wydanie wersji 10.0.37 | 3 listopada 2023 r. | 13 listopada 2023 r. do 6 stycznia 2024 r.|
| 2 wydanie wersji 10.0.37 | 30 grudnia 2023 r. | 8 stycznia 2024 r. do 10 lutego 2024 r.|
| 3 wydanie wersji 10.0.37 | 27 stycznia 2024 | 5 lutego 2024 r. do 9 marca 2024 r.|
| 4 wydanie wersji 10.0.37 | 23 lutego 2024 | 4 marca 2024 r. do 6 kwietnia 2024 r.|

### <a name="proactive-quality-update-upcoming-10030-release-2-train-schedule"></a><a name="schedule"></a> Proaktywna aktualizacja jakości – nadchodzący harmonogram wydań 2 wersji 10.0.30
**Wersja aplikacji: 10.0.1362.99**

| Stacje | Nadchodzący harmonogram piaskownicy | Najbliższy harmonogram produkcji |
|---|---|---|
| Stacja 1 | ND | ND |
| Stacja 2 | 2–5 stycznia 2023 r. | 21–22 stycznia 2023 r. |
| Stacja 3 | 3–6 stycznia 2023 r. | 28–29 stycznia 2023 r. |
| Stacja 4 | 9–12 stycznia 2023 r. | ND |
| Stacja 5 | 16–19 stycznia 2023 r. | ND |
| Stacja 6 | ND | ND |

> [!IMPORTANT] 
> Pięć dni wcześniej firma Microsoft zaktualizuje poprzedni harmonogram i wysyła powiadomienia do zestawu środowisk, które mają otrzymać te aktualizacje jakości. Poprzedni harmonogram ma zastosowanie tylko do środowisk, które zostały powiadomione o nadchodzącej aktualizacji. Aby uzyskać informacje dotyczące godzin bezczynności w poszczególnych regionach, zobacz [Czym są okna planowanej konserwacji według regionów?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).
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
Aby zidentyfikować listę zmian, które zostaną wprowadzone w ładunku aktualizacji jakości, należy wykonać poniższe kroki. 

Użyj pociągu aktualizacji jakości 10.0.28 i powiązanej wersji aplikacji 10.0.1265.89.

1. W Lifecycle Services i otwórz stronę **Szczegóły środowiska** dla piaskownicy. 
2. W sekcji **Dostępne aktualizacje** wybierz pozycję **Wyświetl aktualizację** dla najnowszej kompilacji aktualizacji jakości. 
3. Wyeksportuj kompilację do formatu CSV lub pliku Microsoft Excel.
4. W eksportowanych plikach przefiltruj i wybierz **Wersję kompilacji** o numerze kompilacji mniejszym lub równym 10.0.1265.89. Powinieneś być teraz w stanie zobaczyć ładunek delta.
 
> [!NOTE]
> Eksport do pliku CSV lub Excel musi nastąpić przed zaktualizowaniem środowiska. W przeciwnym razie możesz użyć środowiska o podobnej konfiguracji, w którym nie zainstalowano aktualizacji, i wykonać kroki powyżej.

[![Przykład środowiska z aktualizacją jakości.](./media/how-to-get-kb-list-pqu.png)](./media/how-to-get-kb-list-pqu.png)

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>Co dzieje się w przypadku, gdy po aktualizacji jakości zostanie znaleziony problem krytyczny?
Problem krytyczny lub wycofanie to co najmniej jedno ze zdarzeń, które zwykle powodują, że wielu odbiorców doświadcza zdegradowanego doświadczenia w jednej lub większej liczbie usług. Te problemy mogą powodować nieplanowany przestój, w tym brak dostępności, obniżenie wydajności i problemy związane z zarządzaniem usługą. Jeśli takie problemy mają poważny wpływ na klienta, do czasu omówienia i rozwiązania problemu zostanie zatrzymane wprowadzanie aktualizacji jakości. Zazwyczaj następna aktualizacja jakości będzie wymagała poprawki, aby wznowić wprowadzanie.

Jeśli dotyczy tylko jednego środowiska klienta, skontaktuj się z pomocą techniczną firmy Microsoft, aby utworzyć bilet. Na podstawie uzasadnienia zatrzymamy wprowadzanie aktualizacji jakości dla wszystkich innych środowisk w tym projekcie do czasu usunięcia problemu.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lifecycle-services"></a>Czy odbiorcy mogą nadal ręcznie stosować aktualizacje poprawek z usługi Lifecycle Services?
Tak. Aby zapewnić trwającą parzystość z tym, jak poprawki działają, nadal można stosować aktualizacje poprawek do środowisk klientów w usługach Lifecycle Services. Jednak przed wdrożeniem aktualizacji ważne jest, aby pamiętać, że poprawki wdrożone w ramach aktualizacji jakości przejść przez standardową aktualizację SDP. Zmniejsza to ryzyko związane z dostępem do materiałów o większej jakości. Zaleca się wybranie aktualizacji jakości poprzez ręczne stosowanie poprawek w celu zwiększenia niezawodności.

## <a name="can-customers-proactively-install-a-quality-update-build-ahead-of-the-schedule"></a>Czy klienci mogą wcześniej instalować kompilację aktualizacji jakości?
Tak. Aktualizację jakości można zainstalować proaktywnie. Firma Microsoft pominie aktualizację, jeśli bieżąca wersja kompilacji środowiska jest równa lub wyższa od bieżącej aktualizacji jakości.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Jeśli w środowisku w ciągu tygodnia zaplanowana jest planowana miesięczna aktualizacja usługi, czy nadal otrzyma ono aktualizacje jakości?
- Aktualizacje jakości nie są stosowane w środowiskach produkcyjnych, jeśli w ciągu tygodnia zaplanowano aktualizację usługi, która ma zostać zaplanowana.
- Jeśli środowisko piaskownicy ma taką samą lub nowszą wersję kompilacji niż zbliżającą się aktualizacja jakości, zostanie pominięta.
- Jeśli środowisko produkcyjne ma taką samą lub nowszą wersję kompilacji niż zbliżającą się aktualizacja jakości, zostanie pominięta.
- Jeśli piaskownica ma tę samą lub nowszą wersję kompilacji z powodu aktualizacji jakości lub ręcznej aktualizacji do produkcji, produkcja nadal będzie tworzyć zaplanowaną wersję miesięcznej aktualizacji usługi. Jeśli nie chcesz, aby zaplanowane środowisko produkcyjne było aktualizowane do wersji aktualizacji usługi, możesz wstrzymać aktualizację usługi z poziomu usługi Lifecycle Services. 
- Zaleca się korzystanie z najnowszej kompilacji aktualizacji jakości w celu przetestowania zmian nachodzącej aktualizacji usługi w celu lepszej stabilności i wyników.

## <a name="if-an-environment-has-an-upcoming-scheduled-action-and-a-scheduled-quality-update-in-the-same-maintenance-window-will-it-still-receive-the-quality-update"></a>Czy środowisko ma zaplanowaną akcję zbliżającą się i zaplanowaną aktualizację jakości w tym samym oknie konserwacji, czy nadal będzie otrzymywać aktualizację jakości?
Jeśli istnieje konflikt ze wstępnie zaplanowaną akcją, na przykład przywrócenie punktu w czasie (PITR), aktualizacja jakości zostanie ponownie zaplanowana do następnego dostępnego czterodniowego okna konserwacji. Aby uzyskać więcej informacji dotyczących harmonogramu, zobacz [Co to jest harmonogram aktywnych aktualizacji jakości?](#schedule). 

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>Czy środowisko może zostać przywrócone do poprzedniego stanu, jeśli po zastosowaniu aktualizacji jakości wystąpią problemy?
Po zastosowaniu aktualizacji jakości nie ma możliwości wycofywania w żadnych okolicznościach. Dostępne są tylko opcje poprawiania, aby zminimalizować problemy.

## <a name="what-about-fda-regulation-and-gxp"></a>Co to są przepisy FDA i GxP?
Plan dla odbiorców podlegających weryfikacji i przepisom FDA jest nadal rozwijany. Należy oczekiwać wkrótce większej liczby aktualizacji w tym miejscu. Na razie wszyscy tego typu odbiorcy są zwolnieni z aktualizacji jakości. Aby zapewnić, że odbiorca podlega przepisom ustawy FDA, odwiedź [Ofertę Microsoft Azure GxP](/azure/compliance/offerings/offering-gxp).

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>Które wersje aktualizacji usług są obsługiwane w przypadku tych aktualizacji jakości?
Klienci wszystkich obsługiwanych wersji usługi kwalifikują się do aktualizacji jakości. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retail-sdk"></a>Wdrożenia aplikacji finansowych i operacyjnych ze składnikami Retail z reguły wymagają dodatkowej pracy oprócz ponownego rozmieszczenia wdrożenia MPOS. Jak te aktualizacje jakości będą miały wpływ na Retail SDK? 
Ponieważ charakter poprawki nie zmienia się w ładunku aktualizacji jakości, więc nie przewidujemy w tej chwili żadnego dodatkowego wpływu, w szczególności związanego ze składnikami Retail.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che"></a>Czy ma wpływ na środowiska hostowane w chmurze (CHE)? 
Środowiska CHE spoza zakresu aktualizacji jakości, ponieważ są poza zakresem rozwiązania Microsoft.

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>Czy występują problemy z integracją z programem Microsoft Dataverse? 
Brak znanych problemów z integracją związanych z aktualizacjami jakości za pomocą Dataverse.

