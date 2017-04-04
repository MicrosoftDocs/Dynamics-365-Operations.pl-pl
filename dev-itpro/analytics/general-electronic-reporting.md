---
title: "Raportowanie elektroniczne — omówienie"
description: "Ten artykuł zawiera omówienie narzędzia Raportowanie elektroniczne (RE). Przedstawiono w nim informacje dotyczące najważniejszych koncepcji, scenariusze obsługiwane przez narzędzie Raportowanie elektroniczne oraz listę formatów zaprojektowanych i udostępnionych w ramach rozwiązania."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: b3e8174d07c9b9fd4210486c369c640fe07c49eb
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-overview"></a>Raportowanie elektroniczne — omówienie

Ten artykuł zawiera omówienie narzędzia Raportowanie elektroniczne (RE). Przedstawiono w nim informacje dotyczące najważniejszych koncepcji, scenariusze obsługiwane przez narzędzie Raportowanie elektroniczne oraz listę formatów zaprojektowanych i udostępnionych w ramach rozwiązania.

Raportowanie elektroniczne (ER) jest narzędziem, które służy do konfigurowania formatów dokumentów elektronicznych zgodnie z wymogami prawnymi różnych krajów/regionów. ER pozwala zarządzać tymi formatami podczas ich całego cyklu życia. Na przykład można wdrożyć nowe wymogi prawne, a następnie generować dokumenty biznesowe w wymaganym formacie w celu elektronicznej wymiany informacji z organami rządowymi, bankami i innymi stronami. Aparat ER jest adresowany do użytkowników biznesowych, a nie programistów. Ponieważ konfiguruje się formaty, a nie kod, procesy tworzenia i dostosowywania formatów dokumentów elektronicznych są szybsze i łatwiejsze. ER obecnie obsługuje arkusze w formatach tekstowym, XML i OPENXML. Jednak interfejs rozszerzeń zapewnia obsługę większej liczby formatów.

## <a name="capabilities"></a>Możliwości
Aparat GER ma następujące cechy:

-   Reprezentuje pojedynczy wspólne narzędzie do raportowania elektronicznego w różnych domenach i zastępuje więcej niż 20 różnych aparatów, które masz jakiś rodzaj raportowania elektronicznego Microsoft Dynamics 365 dla operacji.
-   To sprawia, że format raportu izolowane od bieżącego 365 Dynamics do wykonania operacji. (Innymi słowy, format ma zastosowanie dla różnych wersji systemu Dynamics 365 dla operacji.)
-   Obsługuje tworzenie niestandardowego formatu opartego na oryginalnym formacie. Zawiera funkcje automatycznego uaktualniania dostosowanego formatu po dokonaniu zmian w oryginalnym formacie spowodowanych nową koniecznością przetłumaczenia/dostosowania.
-   Staje się podstawowym standardowym narzędziem do obsługi wymagań tłumaczeniowych w raportach elektronicznych — dla oprogramowania zarówno firmy Microsoft, jak i jej partnerów.
-   Obsługuje możliwość dystrybucji formatów do partnerów i odbiorców za pomocą portalu Microsoft Dynamics Lifecycle Services (LCS).

## <a name="concepts"></a>Koncepcje
### <a name="components"></a>Składniki

ER obsługuje dwa typy składników: **Model danych** i **Format**.

#### <a name="data-model-components"></a>Składniki typu Model danych

Składnik typu Model danych jest abstrakcyjnym przedstawieniem struktury danych służącym do opisu konkretnego obszaru domeny biznesowej w sposób na tyle szczegółowy, by spełnić wymagania raportowania w tej domenie. Składnik będący modelem danych zawiera następujące elementy:

-   Model danych jako zestaw jednostek biznesowych określonej domeny oraz hierarchiczna definicja relacji między tymi jednostkami.
-   Przepływ danych modelu mapowania, która łączy wybrane Dynamics 365 dla źródeł danych operacji do poszczególnych elementów modelu danych, który określa, w czasie wykonywania i regulamin populacji danych biznesowych do danych modelu składnika.

Jednostka biznesowa modelu danych jest przedstawiona jako kontener (rekord). Właściwości jednostki biznesowej są przedstawione jako składniki danych (pola). Każdy element danych ma niepowtarzalną nazwę, etykietę, opis i wartość. Wartość każdego elementu danych może być zaprojektowane tak, aby była rozpoznawana jako ciąg tekstowy, liczba całkowita, liczba rzeczywista, data, typ stałotekstowy, wartość logiczna itd. Ponadto może to być inny rekord lub lista rekordów. Pojedynczy składnik typu Model danych może zawierać kilka hierarchii jednostek biznesowych właściwych dla danej domeny, a także mapowania modelu obsługujące przepływ danych właściwy dla konkretnego raportu w czasie wykonywania. Hierarchie są rozróżniane przez pojedynczy rekord, który został wybrany jako główny dla mapowania modelu. Na przykład model danych obszaru domeny płatności może obsługiwać następujące mapowania:

-   Firma -&gt; dostawcy -&gt; transakcji płatności domeny AP
-   Odbiorca —&gt; Company -&gt; transakcji płatności rozrachunków z Odbiorcami domeny

Zauważ, że jednostki biznesowe (np. Firma i Transakcje płatności) są projektowane tylko jeden raz. Następnie różne mapowania używają ich wielokrotnie. Mapowanie modelu ma następujące cechy:

-   Dla typów danych operacji może używać różnych 365 Dynamics jako źródła danych dla modelu danych. Na przykład może używać tabel, jednostek danych, metod lub tekstów stałych.
-   Obsługuje parametry wejściowe użytkownika, które można zdefiniować jako źródła danych modelu danych, gdy część danych musi być określona w czasie wykonywania.
-   Obsługuje transformacji Dynamics 365 dla danych operacji do wymaganych grup, filtrowanie, sortowanie i sumowanie danych, a także dołączanie przy użyciu logicznych pól, zaprojektowanych za pomocą programu Microsoft Excel, takich jak formuł obliczeniowych (Aby uzyskać więcej szczegółowych informacji, zobacz [Projektant formuł w raportach elektronicznych](general-electronic-reporting-formula-designer.md)).

[![Edytor formuł programu Excel jak](./media/pic-formula-1024x615.png)](./media/pic-formula.png) składnik modelu danych jest przeznaczony dla każdej domeny business która powinna służyć jako źródło danych ujednolicony za zgłoszenie izoluje raportów z fizycznego wykonania usługi Dynamics 365 dla źródeł danych operacji, która reprezentuje specyficznego dla domeny firmy pojęć i funkcji w formie, która sprawia, że wstępnego projektu raportowania formatu i późniejszego utrzymania bardziej efektywne.

#### <a name="format-components"></a>Składniki typu Format

Składnik typu Format określa schemat danych wyjściowych raportowania, które będą generowane w czasie wykonywania. Schemat składa się z następujących elementów:

-   Format definiujący strukturę i zawartość dokumentu raportowania elektronicznego generowanego podczas wykonywania.
-   Źródła danych jako zestaw parametrów wejściowych użytkownika i modelu danych właściwego dla domeny, który wykorzystuje wybrany model mapowania.
-   Mapowanie formatu jako zestaw powiązań źródeł danych formatu zawierających poszczególne elementy formatu, które podczas wykonywania określają przepływ danych i reguły generowania danych wyjściowych w tym formacie.
-   Weryfikacja formatu jako zbiór konfigurowalne reguł, które kontrolują generowanie raportu w czasie wykonywania w zależności od kontekstu uruchomienia (na przykład reguła może zatrzymywać generowanie danych wyjściowych płatności dla dostawcy i zgłaszać wyjątek, gdy brakuje określonych atrybutów wybranego dostawcy, takich jak numer konta bankowego).

Składnik typu Format obsługuje następujące funkcje:

-   Tworzenie danych wyjściowych raportowania jako pojedynczych plików w różnych formatach: tekst, XML lub arkusz.
-   Tworzenie wielu plików oddzielnie, a także hermetyzacja tych plików do plików zip.

Składnik typu Formatu oferuje funkcję załączania określonych plików, które mogą być używane w wynikach raportowania:

-   Skoroszyty programu Excel zawierające arkusze, których można używać jako szablonów danych wyjściowych w formacie arkusza OPENXML.
-   Inne pliki, które mogą zostać włączone w dane wyjściowe formatu jako pliki wstępnie zdefiniowane.

#### <a name="component-versioning"></a>Przechowywanie wersji składnika

Dla składników ER jest obsługiwane przechowywanie wersji. Poniższy przepływ pracy służy do zarządzania zmianami w składnikach ER:

-   Wersja tworzona pierwotnie jest oznaczona jako **WERSJA ROBOCZA**. Ta wersja może być edytowana i jest dostępna do testów.
-   Wersję **WERSJA ROBOCZA** można przekonwertować na wersję **UKOŃCZONA**. Ta wersja może być używana w lokalnych procesach raportowania.
-   **ZAKOŃCZONE** wersji mogą być konwertowane na **SHARED** wersji. Ta wersja została opublikowana na LCS i mogą być używane w sprawozdawczości procesów globalnych.
-   Wersję **UDOSTĘPNIONA** można przekonwertować na wersję **WYCOFANA**. Tę wersję można następnie usunąć.

Wersje, które mają albo ** ukończone ** lub **SHARED** stanu są dostępne dla innych wymiany danych. Na składniku mającym te stany można wykonywać następujące operacje:

-   Może być serializowany w formacie XML i wywożonych z 365 Dynamics dla operacji jako plik w formacie XML.
-   Może być reserialized z pliku XML i przywożone do 365 Dynamics dla operacji jako nową wersję składnika encja-Relacja.

#### <a name="component-date-effectivity"></a>Daty obowiązywania składnika

Wersje składników ER mają daty obowiązywania. Datę **Obowiązuje od** można zdefiniować dla składnika ER, aby określić datę, od której ten składnik zaczyna działać dla procesów raportowania. 365 Dynamics dla operacji Data sesji jest używana do definiowania, czy składnik jest prawidłowa do wykonania. Gdy dla danej daty jest dostępnych kilka wersji, najnowsza wersja jest używana w procesach raportowania.

#### <a name="component-access"></a>Dostęp do składnika

Dostęp do składników formatu aplikacji ER zależy od ustawienia kodu ISO kraju/regionu. Gdy to ustawienie jest puste dla wybranej wersji konfiguracji formatu, składnik format jest możliwy z dowolnego 365 Dynamics dla operacji firmy w czasie wykonywania. Gdy to ustawienie zawiera kody kraju/regionu ISO, składnik format jest dostępna tylko z 365 Dynamics dla firm operacje, które mają podstawowy adres, który jest zdefiniowany dla jednego z kodów kraju/regionu ISO składnik format. Różne wersje składnika formatu danych mogą mieć różne ustawienia kodów ISO kraju/regionu.

#### <a name="configuration"></a>Konfiguracja

Konfiguracja narzędzia ER jest otoką konkretnego składnika ER: **Model danych** lub **Format**. Konfiguracja może zawierać różne wersje konkretnego składnika ER. Każda konfiguracja jest oznaczona jako należąca do określonego dostawcy konfiguracji. **Projekt** wersja składnika konfiguracji można edytować, gdy właściciel konfiguracji zostało wybrane jako aktywnego dostawcy w ustawieniach ER w 365 Dynamics dla operacji. Każda konfiguracja modelu zawiera składnik **Model danych**. Nowa konfiguracja formatu może zostać wygenerowana na podstawie (pochodzić od) określonej konfiguracji modelu danych. Utworzona konfiguracja formatu będzie przedstawiana w drzewie konfiguracji jako element podrzędny oryginalnej konfiguracji modelu danych. Tworzona konfiguracja formatu zawiera składnik **Format**. Składnik **Model danych ** oryginalnej konfiguracji modelu jest automatycznie wstawiany do składnika **Format** podrzędnej konfiguracji formatu jako domyślne źródło danych. Konfiguracja ER jest udostępniony do Dynamics 365 dla firm operacji.

#### <a name="provider"></a>Dostawca

Dostawca ER określa stronę (podmiotu) używaną do wskazania autora (właściciela) konfiguracji ER. Aplikacja ER pozwala zarządzać listą dostawców konfiguracji. Format konfiguracji, które są dopuszczone do dokumentów elektronicznych w ramach usługi Dynamics 365 dla rozwiązania operacje są oznaczone jako posiadanych przez **Microsoft** dostawcy konfiguracji.

#### <a name="repository"></a>Repozytorium

Konfiguracje ER są przechowywane w repozytorium ER. Obecnie obsługiwane są następujące typy repozytoriów ER: **zasobów operacyjnych** i **projektu LCS**. ** Operacji zasobów ** repozytorium zapewnia dostęp do listy konfiguracje, wydane w ramach usługi Dynamics 365 dla operacji rozwiązania przez firmę Microsoft jako dostawca konfiguracji ER. Te konfiguracje mogą importowane do bieżącej 365 Dynamics dla wystąpienia operacji i używanych do raportowania elektronicznego. Można je również wykorzystywać dla dodatkowych tłumaczeń/dostosowań. Repozytorium **Projekt usługi LCS** zapewnia dostęp do listy konfiguracji określonego projektu LCS (biblioteki zasobów projektu usługi LCS) wybranego na etapie rejestracji repozytorium. Encja-Relacja pozwala przesyłać udostępnionego konfiguracje z bieżącym 365 Dynamics dla wystąpienia operacji do określonego **projektu LCS** repozytorium. Można także importować konfiguracje z określonego **projektu LCS** repozytorium do bieżącego 365 Dynamics dla wystąpienia operacji. Wymagane **projektu LCS** repozytoriów można rejestrować indywidualnie dla każdego dostawcy konfiguracji bieżącej usługi Dynamics 365 dla wystąpienia operacji. Każde repozytorium może być dedykowane określonemu dostawcy konfiguracji.

## <a name="supported-scenarios"></a>Obsługiwane scenariusze
### <a name="building-a-data-model"></a>Budowanie modelu danych

Aplikacja ER zawiera projektanta modeli, który może służyć do budowania modeli danych dla konkretnych domen biznesowych. Wszystkie jednostki biznesowe właściwe dla domeny oraz relacje między nimi można przedstawić w modelu danych jako strukturę hierarchiczną. Ilustracja poniżej zawiera przykład tego rodzaju modelu danych (modelu danych dla domeny płatności). [![Przykład modelu danych](./media/pic-data-model-1024x550.png)](./media/pic-data-model.png) do zapoznania się ze szczegółami dotyczącymi tego scenariusza, grać **ER modelu określonych danych domeny** przewodnik zadania (część **7.5.4.3 składników rozwiązania/usługi IT Acquire/programowania (10677)** proces biznesowy).

### <a name="translating-data-model-content"></a>Tłumaczenie zawartości modelu danych

Zawartość modelu danych (etykiet i opisów) może zostać przetłumaczony na inne języki, które obsługuje usługi Dynamics 365 dla operacji. Powody tłumaczenia zawartości modelu danych mogą być następujące:

-   Podczas projektowania — w celu poprawy czytelności zawartości dla projektantów formatów mówiących w obcym języku, którzy używają modelu danych do mapowania danych składników formatu.
-   W czasie, aby zawartość bardziej użytkownika przyjazne poprzez przedstawienie monity i pomoc dla parametrów wykonywania wykonywania i również skonfigurować komunikaty sprawdzania poprawności (błędy i ostrzeżenia), w języku, który preferuje aktualnie zalogowanego Dynamics 365 dla działań użytkownika

Poniższa ilustracja zawiera przykład tłumaczenia zawartości modelu danych z języka angielskiego na japoński. [![Zawartość w języku angielskim modelu danych](./media/pic-translate-en-1024x495.png)](./media/pic-translate-en.png)[![danych modelu zawartości przetłumaczone na język japoński](./media/pic-translate-ja-1024x495.png)](./media/pic-translate-ja.png)

### <a name="configuring-data-model-mappings"></a>Konfigurowanie mapowania modelu danych

ER zapewnia projektanta mapowania model, który pozwala użytkownikom na mapę modeli danych, które mają one przeznaczone na konkretne 365 Dynamics dla źródeł danych operacji. Na ilustracji poniżej widać przykład takiego mapowania modelu danych (mapowanie modelu danych **Polecenie przelewu SEPA** związanego z domeną płatności). [![Przykład mapowania modelu danych ](./media/pic-model-mapping-1024x551.png)](./media/pic-model-mapping.png)do zapoznania się ze szczegółami dotyczącymi tego scenariusza, grać **ER zdefiniować wzór źródła danych mapowania i wybierz** i **modelu encja-Relacja mapę danych do wybrane źródła danych** zadań linie pomocnicze (część **7.5.4.3 składników rozwiązania/usługi IT Acquire/programowania (10677)** proces biznesowy).

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Przechowywanie zaprojektowanego składnika modelu jako konfiguracji modelu

ER można przechowywać zaprojektowanym modelu wraz z mapowania danych powiązanych jako Konfiguracja modelu bieżącej usługi Dynamics 365 dla wystąpienia operacji. Ilustracja poniżej zawiera przykład tego rodzaju konfiguracji modelu danych (konfiguracji modelu płatności). [![Przykład konfiguracji modelu danych ](./media/pic-model-configuration-1024x585.png)](./media/pic-model-configuration.png)do zapoznania się ze szczegółami dotyczącymi tego scenariusza, grać **modelu encja-Relacja mapę danych do wybrane źródła danych** przewodnik zadania (część **7.5.4.3 składników rozwiązania/usługi IT Acquire/programowania (10677)** proces biznesowy).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Budowanie formatu na podstawie modelu danych

Aplikacja ER zawiera projektanta formatów umożliwiającego tworzenie formatów konkretnych dokumentów elektronicznych dla wybranej domeny biznesowej poprzez wybranie składnika modelu jako bazy. Ten sam projektant formatów pozwala zmapować utworzony format na mapowanie modelu danych wybranej domeny jako źródło danych. Na ilustracji poniżej widać przykład tego rodzaju formatu (konfiguracji formatu obsługującej format płatności **BACS** dla Wielkiej Brytanii). [![Przykład formatu, który ma model danych jako podstawy](./media/pic-format-1024x690.png)](./media/pic-format.png) Aby zapoznać się ze szczegółami dotyczącymi tego scenariusza, grać **ER projektu domeny określony format** przewodnik zadania (część **7.5.4.3 składników rozwiązania/usługi IT Acquire/programowania (10677)** proces biznesowy).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Tworzenie konfiguracji do generowania dokumentów elektronicznych w formacie arkusza OPENXML

Projektant formatów w aplikacji ER może służyć do redagowania określonego dokumentu elektronicznego w formacie arkusza OPENXML. Poniżej przedstawiono przykład tego rodzaju format (format konfiguracji do generowania arkusza FORMACIE szczegółowe informacje o wybranym arkuszu płatności):[![Pic-ER-format-Excel](./media/pic-er-format-excel.jpg)](./media/pic-er-format-excel.jpg) do zapoznania się ze szczegółami dotyczącymi tego scenariusza, grać **ER utworzyć konfigurację dla raportów w formacie OPENXML** przewodnik zadania (część **7.5.4.3 składników rozwiązania/usługi IT Acquire/programowania (10677)** proces biznesowy). Umożliwia określonych poniżej plik programu Excel jako szablon w formacie projektowanie ER wykonaj krok Importuj szablon format tego podręcznika zadań: [szablonu raportu płatności (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Przechowywanie zaprojektowanego składnika formatu w konfiguracji formatu

ER można przechowywać zaprojektowany format razem z mapowań danych skonfigurowanych jako Konfiguracja format bieżącej 365 Dynamics dla wystąpienia operacji. Poprzednia ilustracja zawiera przykład tego typu konfiguracji formatu (**BACS (Wielka Brytania)**, która jest obiektem podrzędnym konfiguracji **Model płatności**). Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Projektowanie formatu dla konkretnej domeny** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="configuring-dynamics-365-for-operations-to-start-to-use-a-created-format-internally"></a>Konfigurowanie systemu Dynamics 365 dla operacji zacząć używać formatu utworzone wewnętrznie

Aby rozpocząć korzystanie z formatu utworzone do generowania raportów elektronicznych można skonfigurować Dynamics 365 dla operacji. Odwołanie do utworzonej konfiguracji formatu powinno być zdefiniowane w ustawieniach konkretnej domeny. Na przykład aby zacząć używać konfiguracji formatu ER dla płatności elektronicznych dostawcy w formacie BACS, konfiguracji formatu powinny się odwoływać w szczególnych metod płatności, jak przedstawiono na poniższych ilustracjach: 

[![Konfiguracja formatu BACS (Wielka Brytania)](media/ger-bacs-uk-format-configuration.png) 

[![Odwoływanie się do formatu BACS (Wielka Brytania) w formę płatności](media/ger-bacs-uk-format-method.png) 

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Używanie formatu do generowania dokumentów elektronicznych dla płatności** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

## <a name="handling-er-components"></a>Obsługa składników raportowania elektronicznego
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publikowanie składnika ER w portalu LCS w celu zaoferowania go na zewnątrz (tłumaczenie)

Właściciel utworzonego składnika (modelu lub formatu) może użyć aplikacji ER do opublikowania ukończonej wersji składnika w usłudze LCS. Potrzebne jest do tego repozytorium typu **Projekt usługi LCS** dla bieżącego dostawcy konfiguracji ER. Gdy stan ukończonej wersji składnika zmieni się z **UKOŃCZONA** na **UDOSTĘPNIONA**, ta wersja jest opublikowana w portalu LCS. Po opublikowaniu składnika w usłudze LCS jego właściciel staje się dostawcą usługi obsługującej ten składnik. Jeśli na przykład zadaniem składnika formatu jest generowanie dokumentów elektronicznych wymaganych prawem (np. zgodnie ze scenariuszem tłumaczenia), zakłada się, że format będzie na bieżąco aktualizowany o zmiany legislacyjne, a dostawca będzie publikował nowe wersje składnika w reakcji na każdy nowy wymóg prawny. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Przekazywanie konfiguracji do usługi Lifecycle Services** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importowanie składnika ER z usługi LCS na potrzeby użytku wewnętrznego

ER pozwala importować składniki ER z LCS do bieżącej usługi Dynamics 365 dla wystąpienia operacji. Potrzebne jest do tego repozytorium typu **Projekt usługi LCS**. Składnik ER został zaimportowany z LCS do bieżącej usługi Dynamics 365 dla wystąpienia operacji, właściciel tego wystąpienia staje się konsumenta usługi, która jest dostarczana przez właściciela (autor) przywożonych składnika. Na przykład jeśli składnik formatu służy do generowania określonego dokumentu elektronicznego z 365 Dynamics dla operacji w formacie specyficzne dla kraju/regionu (scenariusz lokalizacji), zakłada się, że odbiorca usługi będą mogli uzyskać wszelkie aktualizacje, które zostały wprowadzone do wielkości tego formatu, aby zachować zgodne z obowiązującymi przepisami. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Importowanie konfiguracji z usługi Lifecycle Services** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Budowanie formatu na podstawie innego formatu (dostosowywanie)

Aplikacja ER pozwala utworzyć (pochodny) nowy składnik z bieżącej (bazowej) wersji składnika, którą zaimportowano z usługi LCS. Na przykład użytkownik chce utworzyć nowy format pochodny w celu zaimplementowania pewnych szczególnych wymagań dotyczących dokumentu elektronicznego (na przykład dodatkowe pole lub rozszerzony opis) dla scenariusza personalizacji. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Uaktualnianie formatu przez przyjęcie jej nowej wersji bazowej** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Uaktualnianie formatu przez przyjęcie jej nowej wersji bazowej (zmiana bazy)

Narzędzie ER pozwala automatyczne powielać zmiany z najnowszej wersji składnika bazowego do aktualnej wersji roboczej składnika pochodnego. Ten proces jest nazywany *zmianą bazy*. Na przykład nowa zmiana przepisów, którą wprowadzono w najnowszej wersji składnika formatu zaimportowanego z usługi LCS, może być automatycznie scalana do dostosowanej wersji tego formatu dokumentu elektronicznego. Wszelkie zmiany, których nie można scalić automatycznie, są uznawane za konflikty. Te konflikty są wyświetlane do rozstrzygnięcia ręcznego w projektancie odpowiedniego składnika. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Uaktualnianie formatu przez przyjęcie jej nowej wersji bazowej** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

## <a name="list-of-er-configurations-that-are-delivered-in-the-dynamics-365-for-operations-solution"></a>Wykaz ER konfiguracji, które są dostarczane w usłudze Dynamics 365 dla operacji rozwiązania
| Konfiguracje modeli danych specyficzne dla domen: Tytuł | Domena                | Konfiguracje formatów zależne od modeli danych: Tytuł | Opis                                                        |
|--------------------------------------------------|-----------------------|---------------------------------------------------|--------------------------------------------------------------------|
| Model plik audytu                                 | Audyt finansowy       |                                                   |                                                                    |
|                                                  |                       | Plik audytu (Holandia)                                   | Format pliku audytu dla Holandii                                  |
| Model BAS                                        | Sprawozdawczość podatkowa         |                                                   |                                                                    |
|                                                  |                       | BAS (Australia)                                          | Format BAS dla Australii                                           |
| Model dla Construction Industry Scheme               | Sprawozdawczość podatkowa         |                                                   |                                                                    |
|                                                  |                       | Miesięczna deklaracja CIS (Wielka Brytania)                           | Format miesięcznej deklaracji CIS dla Wielkiej Brytanii                   |
| Model ponaglenia                          | Faktury elektroniczne  |                                                   |                                                                    |
|                                                  |                       | Ponaglenie OIOUBL (Dania)                     | Format ponaglenia dla Danii                        |
| Model księgowania w księdze elektronicznej (Meksyk)          | Sprawozdawczość podatkowa         |                                                   |                                                                    |
|                                                  |                       | Księga pomocnicza XML (Meksyk)                         | Format raportu transakcji księgi pomocniczej z podziałem na konta dla Meksyku |
|                                                  |                       | Plan kont XML (MX)                         | Format raportu o planie kont dla Meksyku                          |
|                                                  |                       | Arkusze XML (Meksyk)                                 | Format raportu o transakcjach arkusza dla Meksyku                      |
|                                                  |                       | Bilans próbny XML (Meksyk)                            | Format raportu o bilansie próbnym dla Meksyku                             |
| Model Elster                                     | Sprawozdawczość podatkowa         |                                                   |                                                                    |
|                                                  |                       | Elster (Niemcy)                                       | Format Elster dla Niemiec                                          |
| Model listy sprzedaży do UE                              | Sprawozdawczość o handlu       |                                                   |                                                                    |
|                                                  |                       | Lista sprzedaży do UE (Niemcy)                                | Format tekstowy listy sprzedaży do krajów UE dla Niemiec                               |
|                                                  |                       | Lista sprzedaży do UE (Dania)                                | Format tekstowy listy sprzedaży do krajów UE dla Danii                               |
|                                                  |                       | Lista sprzedaży do UE (Francja)                                | Format XML listy sprzedaży do krajów UE dla Francji                                |
|                                                  |                       | Lista sprzedaży do UE (Holandia)                                | Format XML listy sprzedaży do krajów UE dla Holandii                           |
|                                                  |                       | Tekstowa lista sprzedaży do UE (Wielka Brytania)                            | Format tekstowy listy sprzedaży do krajów UE dla Wielkiej Brytanii                    |
|                                                  |                       | Lista sprzedaży XML do UE (Wielka Brytania)                            | Format XML listy sprzedaży do krajów UE dla Wielkiej Brytanii                    |
|                                                  |                       | Raport kolumnowy z listą sprzedaży do UE                   | Raport kolumnowy z listą sprzedaży do UE                                    |
|                                                  |                       | Raport wierszowy z listą sprzedaży do UE                      | Raport wierszowy z listą sprzedaży do UE                                       |
| Model księgowania FEC (Francja)                        | Sprawozdawczość podatkowa         |                                                   |                                                                    |
|                                                  |                       | Dane księgowe FEC XML (Francja)                      | Format XML eksportu danych księgowych FEC dla Francji                   |
| Niemiecki plik audytu                                | Audyt finansowy       |                                                   |                                                                    |
|                                                  |                       | Wyjściowy niemiecki plik audytu                          | Wyjściowy plik audytu dla Niemiec i Austrii                          |
| Model Intrastat                                  | Sprawozdawczość o handlu       |                                                   |                                                                    |
|                                                  |                       | Intrastat (Niemcy)                                    | Format Intrastat dla Niemiec                                       |
|                                                  |                       | Intrastat (Dania)                                    | Format Intrastat dla Danii                                       |
|                                                  |                       | Intrastat INTRACOM (Francja)                           | Format Intrastat INTRACOM dla Francji                               |
|                                                  |                       | Intrastat SAISUNIC (Francja)                           | Format Intrastat SAISUNIC dla Francji                               |
|                                                  |                       | Intrastat (Holandia)                                    | Format Intrastat dla Holandii                               |
|                                                  |                       | Intrastat (Wielka Brytania)                                    | Format Intrastat dla Wielkiej Brytanii                            |
|                                                  |                       | Raport Intrastat                                  | Raport kontrolny Intrastat w formacie Excel                                     |
| Model faktur sprzedaży                           | Faktury elektroniczne  |                                                   |                                                                    |
|                                                  |                       | Faktura korygująca za projekt OIOUBL (Dania)                   | Format faktury korygującej za projekt OIOUBL dla Danii                      |
|                                                  |                       | Faktura za projekt OIOUBL (Dania)                       | Format faktury za projekt OIOUBL dla Danii                          |
|                                                  |                       | OIOUBL Faktura korygująca za sprzedaż (Dania)                     | Format faktury korygującej za sprzedaż OIOUBL dla Danii                        |
|                                                  |                       | Faktura za sprzedaż OIOUBL (Dania)                         | Format faktury za sprzedaż OIOUBL dla Danii                            |
| Model deklaracji OB                             | Sprawozdawczość podatkowa         |                                                   |                                                                    |
|                                                  |                       | Deklaracja OB (Holandia)                               | Format deklaracji OB dla Holandii                          |
| Model płatności                                    | Płatności              |                                                   |                                                                    |
|                                                  |                       | Betalingsservice (Dania)                             | Format płatności Betalingsservice dla Danii                        |
|                                                  |                       | Realizacja weksla (Francja)                  | Format realizacji weksla dla Francji                      |
|                                                  |                       | BTL91 (Holandia)                                        | Format płatności dla dostawcy BTL91 dla Holandii                    |
|                                                  |                       | CFONB Prelevements (Francja)                           | Format płatności poleceniem zapłaty CFONB dla Francji                       |
|                                                  |                       | CFONB Virements (FR)                              | Format płatności dostawcy krajowemu CFONB dla Francji                    |
|                                                  |                       | Nordea Płatności dla dostawców (Dania)                                | Format płatności dla dostawców w Nordea Corporate Netbank dla Danii         |
|                                                  |                       | Usługi płatności bezpośredniej przez ANZ (Australia)                    | Format usługi płatności bezpośredniej przez ANZ dla Australii                 |
|                                                  |                       | Usługi płatności bezpośredniej przez CBA (Australia)                    | Format usługi płatności bezpośredniej przez CBA dla Australii                 |
|                                                  |                       | Usługi płatności bezpośredniej przez NAB (Australia)                    | Format usługi płatności bezpośredniej przez NAB dla Australii                 |
|                                                  |                       | Usługi płatności bezpośredniej przez STG (Australia)                    | Format usługi płatności bezpośredniej przez STG dla Australii                 |
|                                                  |                       | Usługi płatności bezpośredniej przez WBC (Australia)                      | Format usługi płatności bezpośredniej przez WBC dla Australii                   |
|                                                  |                       | DirectLink (Nowa Zelandia)                                   | Format płatności DirectLink dla Nowej Zelandii                              |
|                                                  |                       | Plik płatności JBA (Japonia)                             | Format płatności JBA dla Japonii                                       |
|                                                  |                       | Polecenie przelewu ISO20022                          | Format polecenia przelewu SEPA dla Europy                             |
|                                                  |                       | Polecenie przelewu ISO20022 (Francja)                     | Format polecenia przelewu SEPA dla Francji                             |
|                                                  |                       | Polecenie przelewu ISO20022 (Niemcy)                     | Format polecenia przelewu SEPA dla Niemiec                            |
|                                                  |                       | Polecenie przelewu ISO20022 (Holandia)                     | Format polecenia przelewu SEPA dla Holandii                    |
|                                                  |                       | Polecenie zapłaty ISO20022                             | Format polecenia zapłaty SEPA dla Europy                                |
|                                                  |                       | Polecenie zapłaty ISO20022 (Francja)                        | Format polecenia zapłaty SEPA dla Francji                                |
|                                                  |                       | Polecenie zapłaty ISO20022 (Niemcy)                        | Format polecenia zapłaty SEPA dla Niemiec                               |
|                                                  |                       | Polecenie zapłaty ISO20022 (Holandia)                        | Format polecenia zapłaty SEPA dla Holandii                       |
|                                                  |                       | BACS (Wielka Brytania)                                         | Format BACS płatności dla dostawców dla Wielkiej Brytanii                  |
| Opłata zwrotna                                   | Sprawozdawczość podatkowa         |                                                   |                                                                    |
|                                                  |                       | Lista sprzedaży z opłatą zwrotną                         | Format listy sprzedaży z opłatą zwrotną                                   |
| Holenderski model integracji XBRL                     | Raportowanie podatku XBRL        |                                                   |                                                                    |
|                                                  |                       | Semansys XBRL (Holandia)                                | Format eksportu Semansys XBRL dla Holandii                    |
| Model GAF (Malezja)                                   | Audyt finansowy       |                                                   |                                                                    |
|                                                  |                       | Plik GAF (Malezja)                                     | Format GAF dla Malezji                                         |
| Raport o wiekowaniu dla dostawców (Chiny)                         | Analiza danych dla dostawców |                                                   |                                                                    |
|                                                  |                       | Format raportu o wiekowaniu dla dostawców (Chiny)                   | Format raportu o wiekowaniu dla dostawców dla Chin                               |
| Model deklaracji na fakturze od dostawcy                 | Analiza danych dla dostawców |                                                   |                                                                    |
|                                                  |                       | Deklaracja na fakturze od dostawcy (Islandia)                   | Format deklaracji na fakturze od dostawcy dla Islandii                      |
|                                                  |                       | Raport o deklaracji na fakturze od dostawcy (Islandia)            | Raport o deklaracji na fakturze od dostawcy dla Islandii                      |



<a name="see-also"></a>Informacje dodatkowe
--------

[Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego](electronic-reporting-configuration.md)

[Zarządzanie cyklem życia konfiguracji raportowania elektronicznego](general-electronic-reporting-manage-configuration-lifecycle.md)


