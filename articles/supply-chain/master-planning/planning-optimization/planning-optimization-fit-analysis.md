---
title: Analiza dopasowań optymalizacji planowania
description: W tym artykule wyjaśniono, jak sprawdzić bieżącą konfigurację i dane, porównując je z możliwościami funkcji optymalizacji planowania.
author: t-benebo
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsFitAnalysis, MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 633daba553b1544c2caa788f4cec1da4c1da6960
ms.sourcegitcommit: 7af116c60f3a94671a7a80c04097d70180754930
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2022
ms.locfileid: "9347297"
---
# <a name="planning-optimization-fit-analysis"></a>Analiza dopasowań optymalizacji planowania

[!include [banner](../../includes/banner.md)]

Wynik z analizy dopasowania optymalizacji planowania należy analizować w ramach procesu migracji. Należy pamiętać, że zakres optymalizacji planowania nie jest równy bieżącej wbudowanej funkcji planowania głównego. Zalecamy współpracę z partnerem i zapoznanie się z dokumentacją w celu przygotowania się do migracji. 

Analiza dopasowania optymalizacji planowania pomaga określić miejsce, w którym wynik może się różnić między wbudowanym aparatem planowania głównego i optymalizacją planowania. Analiza jest przeprowadzana na podstawie bieżących ustawień i danych. 

Aby wyświetlić wyniki analizy dotyczącej optymalizacji planowania, przejdź do okna **Planowanie główne** \> **Konfiguracja** \> **Analiza dopasowań optymalizacji planowania**, a następnie wybierz opcję **Uruchom analizę**. Jeśli analiza wykryje niespójności, zostaną one wyświetlone na tej samej stronie. (Analiza może potrwać kilka minut.)

> [!NOTE]
>
> - Niektóre niespójności nie są wykrywane w trakcie analizy dopasowań optymalizacji planowania. Więcej informacji można znaleźć w temacie [Różnice między klasycznym planowaniem głównym a optymalizacją planowania](planning-optimization-differences-with-built-in.md).
>
> - W przypadku znalezienia niespójności nadal można skorzystać z optymalizacji planowania. Wyniki analizy dopasowania pokazują tylko miejsca, w których usługa planowania nie będzie przestrzegać bieżących ustawień. Innymi słowy pokazują one miejsca, w których niektóre procesy mogą być ignorowane lub mogą być nieobsługiwane.

## <a name="analysis-results-example-1"></a>Wyniki analizy: przykład 1

- **Funkcja:** Produkcyjne
- **Problem** : towary z listą składową BOM większą niż zero: 56
- **Wyjaśnienie:** odnaleziona analiza dopasowania odnalazła 56 towarów, które mają konfigurację BOM produkcji. Ponieważ bieżąca wersja funkcji optymalizacji planowania nie obsługuje produkcji, optymalizacja planowania spowoduje generowanie planowanych zamówień zakupu zamiast planowanych zleceń produkcyjnych. Wyświetlone zostanie także ostrzeżenie, w którym znajdują się odnośne towary.

## <a name="analysis-results-example-2"></a>Wyniki analizy: przykład 2

- **Funkcja:** akcje
- **Problem:** Grupy zapotrzebowania z włączoną opcją obliczania akcji: 6
- **Wyjaśnienie:** znaleziono analizę dopasowania z sześcioma grupami zapotrzebowania, w których jest włączone Obliczanie akcji. Ponieważ bieżąca wersja funkcji optymalizacji planowania nie obsługuje akcji, podczas planowania głównego nie zostaną wygenerowane żadne akcje.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Przegląd możliwych wyników z analizy dopasowania

W poniższej tabeli przedstawiono różne wyniki, które mogą być widoczne po analizie dopasowania. Znaki numerów (*\#*) zostaną zastąpione liczbą określającą liczbę rekordów z wyświetlonym problemem.

> [!IMPORTANT]
> W przypadku funkcji, które nie są jeszcze obsługiwane, w poniższej tabeli przedstawiono oczekiwane informacje o dostępności, które są szacowane na podstawie bieżącego ustawienia. Te oszacowania mogą ulec zmianie bez powiadomienia.

| Funkcja | Wymieniony problem | Wyjaśnienie | Oczekiwana dostępność |
| --- | --- | --- | --- |
| Akcje | Grupy zapotrzebowania z włączoną opcją obliczania akcji: *\#* | Ta funkcja jest teraz obsługiwana. | Obsługiwana |
| Kalendarze podstawowe | Kalendarze używające kalendarza podstawowego: *\#* | Ta funkcja jest teraz obsługiwana. | Obsługiwana | 
| Kody dyspozycji partii | Wzorce dyspozycji partii z towarami nie do dyspozycji: *\#* | Ta funkcja jest oczekiwana. Obecnie po włączeniu Optymalizacji planowania kody dyspozycji partii są ignorowane. | 2022 Zwolnij grupę czynności 2 |
| Możliwe do zrealizowania (CTP) | Domyślne ustawienia zamówienia z kontrolą daty dostawy ustawioną na CTP: *\#* | W Supply Chain Management 10.0.28 i nowszych proces o nazwie *CTP dla Planning Optimization* udostępnia potwierdzone daty wysyłki i odbioru po uruchomieniu planu dynamicznego. W starszych wersjach Supply Chain Management ustawienie CTP jest ignorowane, gdy włączona jest optymalizacja planowania. | Obsługiwana |
| Kopiuj plan statyczny do dynamicznego | Funkcja Kopiuj plan statyczny do dynamicznego jest włączona w parametrach planowania głównego. | Optymalizacja planowania nie kopiuje planu statycznego do planu dynamicznego, niezależnie od tego ustawienia. Zazwyczaj pojęcie to jest mniej istotne ze względu na szybkość i pełną regenerację, którą zapewnia Optymalizacja planowania. Jeśli użyto dwóch lub więcej planów, planowanie główne powinno być wyzwalane dla każdego planu. | N/D |
| Akceptacja | Grupy zapotrzebowania z ustawionym horyzontem czasowym automatycznej akceptacji: *\#* | W wersji 10.0.7 i nowszych akceptacja jest obsługiwana jako osobne zadanie wsadowe w ramach planowania głównego ( pod warunkiem, że włączono funkcję *Automatyczna akceptacja Optymalizacji planowania* w module [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Należy pamiętać, że Automatyczna akceptacja optymalizacji planowania jest oparta na dacie zamówienia (data rozpoczęcia), a nie na dacie zapotrzebowania (data zakończenia). To zachowanie gwarantuje, że akceptacja zamówień odbywa się w odpowiednim czasie, bez konieczności uwzględniania czasu realizacji w horyzoncie czasowym akceptacji. | Obsługiwana |
| Akceptacja | Rekordy zapotrzebowania na towary z ustawioną automatyczną akceptacją: *\#* | W wersji 10.0.7 i nowszych automatyczna akceptacja jest obsługiwana jako osobne zadanie wsadowe w ramach planowania głównego ( pod warunkiem, że włączono funkcję *Automatyczna akceptacja Optymalizacji planowania* w module [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Należy pamiętać, że Automatyczna akceptacja optymalizacji planowania jest oparta na dacie zamówienia (data rozpoczęcia), a nie na dacie zapotrzebowania (data zakończenia). To zachowanie gwarantuje, że akceptacja zamówień odbywa się w odpowiednim czasie, bez konieczności uwzględniania czasu realizacji w horyzoncie czasowym akceptacji. | Obsługiwana |
| Akceptacja | Plany główne z ustawioną automatyczną akceptacją: *\#* | W wersji 10.0.7 i nowszych automatyczna akceptacja jest obsługiwana jako osobne zadanie wsadowe w ramach planowania głównego ( pod warunkiem, że włączono funkcję *Automatyczna akceptacja Optymalizacji planowania* w module [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Należy pamiętać, że Automatyczna akceptacja optymalizacji planowania jest oparta na dacie zamówienia (data rozpoczęcia), a nie na dacie zapotrzebowania (data zakończenia). To zachowanie gwarantuje, że akceptacja zamówień odbywa się w odpowiednim czasie, bez konieczności uwzględniania czasu realizacji w horyzoncie czasowym akceptacji. | Obsługiwana |
| FitAnalysisPlanningItems | Pozycje planowania: *\#* | Ta funkcja jest oczekiwana. Obecnie elementy planowania są traktowane jak zwykłe pozycje, gdy jest włączona Optymalizacja planowania. | 2022 wydanie grupy czynności 2 lub nowszej |
| Prognozy | Grupy zapotrzebowania z włączonymi opcjami „Uwzględnij zamówienia międzyfirmowe”:*\#* | Ta funkcja jest teraz obsługiwana. Aby uzyskać dodatkowe informacje, zobacz temat [Planowanie międzyfirmowe](Intercompany-planning.md) | Obsługiwana |
| Prognozy | Grupy zapotrzebowania z opcją „Zmniejsz prognozę o” ustawioną na wartość inną niż „Zamówienia”: *\#* | Ta funkcja jest teraz obsługiwana. Aby uzyskać więcej informacji, zobacz [Planowanie główne z uwzględnieniem prognoz popytu](demand-forecast.md) | Obsługiwana |
| Prognozy | Modele prognozy z podmodelami: *\#* |  Ta funkcja jest teraz obsługiwana. Aby uzyskać więcej informacji, zobacz [Planowanie główne z uwzględnieniem prognoz popytu](demand-forecast.md) | Obsługiwana |
| Prognozy | Plany główne z włączoną opcją „Uwzględnij prognozę dostaw”: *\#* | Ta funkcja jest oczekiwana. Obecnie prognozy dostaw nie są obsługiwane, jeśli Optymalizacja planowania jest włączona. Zostaną one zignorowane niezależnie od tego ustawienia. | 2022 wydanie grupy czynności 2 lub nowszej |
| Horyzont czasowy zamrożenia | Grupy zapotrzebowania z ustawionym horyzontem czasowym zamrożenia: *\#* | Ta funkcja jest oczekiwana. Obecnie podczas włączania optymalizacji planowania konfiguracja horyzontu czasowego zamrożenia nie jest brany pod uwagę, niezależnie od tego ustawienia. | 2022 Zwolnij grupę czynności 2 |
| Horyzont czasowy zamrożenia | Rekordy zapotrzebowania na towary z ustawionym horyzontem czasowym zamrożenia: *\#* | Ta funkcja jest oczekiwana. Obecnie podczas włączania optymalizacji planowania konfiguracja horyzontu czasowego zamrożenia nie jest brany pod uwagę, niezależnie od tego ustawienia. | 2022 Zwolnij grupę czynności 2 |
| Horyzont czasowy zamrożenia | Plany główne z ustawionym horyzontem czasowym zamrożenia: *\#* | Ta funkcja jest oczekiwana. Obecnie podczas włączania optymalizacji planowania konfiguracja horyzontu czasowego zamrożenia nie jest brany pod uwagę, niezależnie od tego ustawienia. | 2022 Zwolnij grupę czynności 2 |
| Międzyfirmowe | Plany główne uwzględniające planowany popyt od dostawcy do odbiorcy: *\#* | Ta funkcja jest teraz obsługiwana. Aby uzyskać dodatkowe informacje, zobacz temat [Planowanie międzyfirmowe](Intercompany-planning.md) | Obsługiwana |
| Kanban | Rekordy zapotrzebowania na towary z planowanym typem zamówienia Kanban: *\#* | Ta funkcja jest oczekiwana. Obecnie zapotrzebowanie na towary, dla którego ustawiono wartość Kanban, będzie ignorowane, gdy jest włączona Optymalizacja planowania. Typ zamówienia planowanego Kanban utworzy ostrzeżenie podczas planowania głównego, a planowane zamówienia zakupu zostaną utworzone w celu pokrycia pokrewnego popytu. | Przyszłe grupy czynności |
| Kanban | Towary z domyślnym typem zamówienia Kanban: *\#* | Obecnie domyślny typ zamówienia, dla którego ustawiono wartość Kanban, będzie ignorowane, gdy jest włączona Optymalizacja planowania. Typ zamówienia domyślnego Kanban utworzy ostrzeżenie podczas planowania głównego, a planowane zamówienia zakupu zostaną utworzone w celu pokrycia pokrewnego popytu. | Przyszłe grupy czynności |
| Stan cyklu życia produktu | Stany cyklu życia produktu nieaktywne dla planowania: *\#* | Ta funkcja jest teraz obsługiwana. Aby uzyskać dodatkowe informacje, zobacz temat [Wykluczanie produktów z określonymi stanami cyklu życia produktu](product-lifecycle-state.md) | Obsługiwana |
| Produkcyjne | Wiersze BOM z zaokrągleniem lub wieloma wariantami konfiguracji: *\#* | Ta funkcja jest oczekiwana. Obecnie zaokrąglanie i wielokrotność konfiguracji są ignorowane w wierszach BOM, gdy jest włączona Optymalizacja planowania, niezależnie od tego ustawienia. | Przyszłe grupy czynności|
| Produkcyjne | Wiersze BOM/wiersze formuł z miarą formuły: *\#* | Ta funkcja jest oczekiwana. Obecnie formuła z miarą jest ignorowana w wierszach BOM i formuły, gdy jest włączona Optymalizacja planowania, niezależnie od tego ustawienia. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Wiersze BOM/wiersze formuł z podstawianiem pozycji (grupy planowania): *\#* | Ta funkcja jest oczekiwana. Obecnie podstawianie pozycji (grupy planowania) jest ignorowana w wierszach BOM i formuły, gdy jest włączona Optymalizacja planowania, niezależnie od tego ustawienia. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Wiersze BOM/wiersze formuł z ilością ujemną: *\#* | Ta funkcja jest oczekiwana. Wiersze BOM i formuły, które mają ilość ujemną, zostaną uwzględnione z ilością 0 (zero), a w przypadku włączenia Optymalizacji planowania zostanie wygenerowane ostrzeżenie. Zaktualizuj dane podstawowe, aby uniknąć ostrzeżeń. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Wiersze BOM/wiersze formuł ze zużyciem zasobu: *\#* | Ta funkcja jest oczekiwana. Obecnie podczas włączania Optymalizacji planowania ignorowane są wiersze BOM i formuły, w których zużycie zasobów jest włączone. Gdy ta funkcja jest obsługiwana, wymaganie materiałowe zostanie ustawione na datę rozpoczęcia produkcji. Dopóki ta funkcja nie będzie obsługiwana, wymagania nie będą generowane dla materiałów oznaczonych flagą zużycia zasobów. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Wiersze BOM/wiersze formuł ze zużyciem etapowym: *\#* | Ta funkcja jest oczekiwana. Ignorowane jest zużycie etapowe w wierszach BOM i formuły, w których włączona jest Optymalizacja planowania. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Listy BOM ze zdefiniowanymi stałymi odpadkami lub odpadkami zmiennymi: *\#* | Ta funkcja jest oczekiwana. Obecnie stałe odpadki i zmienne odpadki, które są zdefiniowane w BOM, są ignorowane, gdy jest włączona Optymalizacja planowania. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Listy BOM z podwykonawstwem: *\#* | Ta funkcja jest teraz obsługiwana. | Obsługiwana |
| Produkcyjne | Listy BOM bez oddziału: *\#* | Ta funkcja jest teraz obsługiwana. Aby uzyskać dodatkowe informacje, zobacz temat [Planowanie produkcji](production-planning.md) | Obsługiwana |
| Produkcyjne | Popyt ze zdefiniowanymi konkretnymi wymaganiami dotyczącymi list BOM lub marszruty: *\#* | Ta funkcja jest oczekiwana. Obecnie określone wymagania dotyczące BOM lub marszruty zdefiniowane na zapotrzebowaniu (takie jak BOM podrzędny lub Podmarszruta w zamówieniu sprzedaży) są ignorowane, gdy jest włączona Optymalizacja planowania. Zostanie użyta standardowa wersja BOM lub marszruta, niezależnie od tego ustawienia. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Wersje formuły zawierające produkty towarzyszące/uboczne: *\#* | Ta funkcja jest oczekiwana. Obecnie produkty towarzyszące i uboczne skojarzone z wersją formuły są ignorowane, gdy jest włączona Optymalizacja planowania. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Wersje formuły z uzyskiem: *\#* | Ta funkcja jest oczekiwana. Obecnie uzysk skojarzony z wersją formuły jest ignorowany, gdy jest włączona Optymalizacja planowania. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Plany uwzględniające sekwencjonowanie: *\#* | Ta funkcja jest oczekiwana. Obecnie gdy jest włączona Optymalizacja planowania, harmonogram nie jest brany pod uwagę, niezależnie od tego ustawienia. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Zwolnione, nierozpoczęte zlecenia produkcyjne, których rozpoczęcie jest planowane na dzisiaj: *\#* | Ta funkcja jest oczekiwana. Obecnie, jeśli zlecenie produkcyjne jest opóźnione, planowanie główne zakłada, że zostanie zakończone dzisiaj. Ma to zastosowanie w przypadku zwolnionych zleceń produkcyjnych, w przypadku których data dostawy przypada w przeszłości, ale nie została jeszcze zakończona. | Przyszłe grupy czynności |
| Produkcyjne | Zaplanowane zasoby z ograniczonymi zdolnościami produkcyjnymi: *\#* | Ta funkcja jest oczekiwana. Obecnie są ignorowane zasoby zaplanowane z ograniczonymi zdolnościami produkcyjnymi, gdy jest włączona Optymalizacja planowania. Planowanie jest wykonywane na podstawie domyślnego czasu realizacji produktu. | 2022 Zwolnij grupę czynności 2 |
| Produkcyjne | Marszruty używane podczas planowania: *\#* | Ta funkcja jest obsługiwana. | Obsługiwana |
| Produkcyjne | Rezerwacja wiersza sprzedaży z użyciem rozłożenia: *\#* | Rezerwacja wiersza sprzedaży wykorzystująca rozłożenie nie jest obsługiwana, jeśli jest włączona Optymalizacja planowania. | Przyszłe grupy czynności |
| Produkcyjne | Planowanie z rozłożeniem zleceń produkcyjnych: *\#* | Planowanie wykorzystujące rozłożenie zleceń produkcyjnych nie jest obsługiwane, jeśli jest włączona Optymalizacja planowania. Zlecenia produkcyjne można planować pojedynczo. | Przyszłe grupy czynności |
| Zapytania ofertowe | Plany główne z włączoną opcją zapytań ofertowych: *\#* | Ta funkcja jest oczekiwana. Obecnie zapytania ofertowe (ZO) nie są traktowane jako popyt, gdy jest włączona Optymalizacja planowania. Zostaną one zignorowane niezależnie od tego ustawienia. | 2022 Zwolnij grupę czynności 2 |
| Zapotrzebowania | Plany główne z włączoną opcją zapotrzebowań: *\#* | Ta funkcja jest teraz obsługiwana. Aby dowiedzieć się więcej, zobacz temat [Zapotrzebowania na zakup](purchase-requisitions.md) | Obsługiwana |
| Marginesy bezpieczeństwa | Grupy zapotrzebowania z marginesem bezpieczeństwa: *\#* | Ta funkcja jest teraz obsługiwana. Aby uzyskać dodatkowe informacje, zobacz temat [Marginesy bezpieczeństwa](safety-margins.md) | Obsługiwana |
| Marginesy bezpieczeństwa | Plany główne z marginesem bezpieczeństwa: *\#* | Ta funkcja jest teraz obsługiwana. Aby uzyskać dodatkowe informacje, zobacz temat [Marginesy bezpieczeństwa](safety-margins.md) |  Obsługiwana |
| Realizacja zapasu bezpieczeństwa | Rekordy zapotrzebowania na towary z wartością „Uzupełnij stany minimalne” niższą niż wartość „Data dzisiejsza + czas zaopatrzenia”: *\#* | Optymalizacja planowania zawsze używa *Daty dzisiejszej + czasu zaopatrzenia*. Ta zmiana będzie wprowadzona w przyszłości w celu przygotowania uproszczonej konfiguracji planowania i zapewnienia wyniku akcji. Jeśli czas zaopatrzenia nie jest uwzględniony w zapasach bezpieczeństwa, zamówienia planowane utworzone dla bieżącego niskiego stanu zapasów będą zawsze opóźnione z powodu czasu realizacji. To zachowanie może spowodować powstanie istotnych zakłóceń i niechcianych zamówień planowanych. Najlepszym rozwiązaniem jest zmiana tego ustawienia, tak aby była używana *Data dzisiejsza + czas zaopatrzenia*. Zaktualizuj dane podstawowe, aby uniknąć ostrzeżeń. | ND |
| Oferty sprzedaży | Plany główne z włączoną opcją ofert sprzedaży: *\#* | Ta funkcja jest oczekiwana. Obecnie po włączeniu Optymalizacji planowania oferty są ignorowane. Zostaną one zignorowane niezależnie od tego ustawienia. | 2022 wydanie grupy czynności 2 lub nowszej |
| Okres trwałości | Plany główne z włączoną opcją okresu trwałości: *\#* | Ta funkcja jest oczekiwana. Obecnie podczas włączania optymalizacji planowania okres trwałości nie jest brany pod uwagę, niezależnie od tego ustawienia. | Obsługiwana |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie optymalizacji planowania](planning-optimization-overview.md)

[Rozpoczęcie optymalizacji planowania](get-started.md)

[Różnice między klasycznym planowaniem głównym a optymalizacją planowania](planning-optimization-differences-with-built-in.md)

[Parametry nieużywane przez optymalizację planowania](not-used-parameters.md)

[Wyświetlanie historii planu i dzienników planowania](plan-history-logs.md)

[Stosowanie filtrów do planu](plan-filters.md)

[Anuluj planowanie pracy](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
