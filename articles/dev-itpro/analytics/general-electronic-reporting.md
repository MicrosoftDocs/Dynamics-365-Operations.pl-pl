---
title: "Raportowanie elektroniczne — omówienie"
description: "Ten artykuł zawiera omówienie narzędzia Raportowanie elektroniczne (RE). Przedstawiono w nim informacje dotyczące najważniejszych koncepcji, scenariusze obsługiwane przez narzędzie Raportowanie elektroniczne oraz listę formatów zaprojektowanych i udostępnionych w ramach rozwiązania."
author: kfend
manager: AnnBe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 704235fb1aacb7e3101d4b1feca1e36051059ade
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="electronic-reporting-overview"></a>Omówienie Raportowania elektroniczne

[!include[banner](../includes/banner.md)]


Ten temat zawiera omówienie narzędzia Raportowanie elektroniczne. Przedstawiono w nim informacje dotyczące najważniejszych koncepcji, scenariusze obsługiwane przez narzędzie Raportowanie elektroniczne oraz listę formatów zaprojektowanych i udostępnionych w ramach rozwiązania.

ER jest narzędziem, które służy do konfigurowania formatów dokumentów elektronicznych przychodzących i wychodzących zgodnie z wymogami prawnymi różnych krajów/regionów. ER pozwala zarządzać tymi formatami podczas ich całego cyklu życia. Na przykład można wdrożyć nowe wymogi prawne, a następnie generować dokumenty biznesowe w wymaganym formacie w celu elektronicznej wymiany informacji z organami rządowymi, bankami i innymi stronami.

Aparat ER jest adresowany do użytkowników biznesowych, a nie programistów. Ponieważ konfiguruje się formaty, a nie kod, procesy tworzenia i dostosowywania formatów dokumentów elektronicznych są szybsze i łatwiejsze.

ER obecnie obsługuje arkusze w formatach tekstowym, XML, dokumentów programu Microsoft Word i OPENXML. Jednak interfejs rozszerzeń zapewnia obsługę dodatkowych formatów.

## <a name="capabilities"></a>Możliwości
Aparat GER ma następujące cechy:

- Stanowi jedno współużytkowane narzędzie do raportowania elektronicznego w różnych domenach oraz zastępuje ponad 20 różnych innych aparatów obsługujących różne formy raportowania elektronicznego w programie Microsoft Dynamics 365 for Finance and Operations.
- Izoluje format raportu od bieżącej implementacji programu Finance and Operations. Innymi słowy format można stosować do różnych wersji programu Finance and Operations.
- Obsługuje tworzenie niestandardowego formatu opartego na oryginalnym formacie. Zawiera również funkcje automatycznego uaktualniania dostosowanego formatu po dokonaniu zmian w oryginalnym formacie spowodowanych koniecznością przetłumaczenia/dostosowania.
- Staje się podstawowym standardowym narzędziem do obsługi wymagań tłumaczeniowych w raportach elektronicznych — dla oprogramowania zarówno firmy Microsoft, jak i jej partnerów.
- Obsługuje możliwość dystrybucji formatów do partnerów i odbiorców za pomocą portalu Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Podstawowe pojęcia
### <a name="components"></a>Składniki

ER obsługuje dwa typy składników: **Model danych** i **Format**.

#### <a name="data-model-components"></a>Składniki typu Model danych

Składnik typu Model danych jest abstrakcyjnym przedstawieniem struktury danych. Służy do opisu konkretnego obszaru domeny biznesowej w sposób na tyle szczegółowy, by spełnić wymagania raportowania w tej domenie. Składnik będący modelem danych zawiera następujące elementy:

- Model danych jako zestaw jednostek biznesowych określonej domeny oraz hierarchiczna definicja relacji między tymi jednostkami.
- Mapowanie modelu, które łączy wybrane źródła danych programu Finance and Operations z poszczególnymi elementami tego modelu danych, które określają w czasie wykonywania przepływ danych i reguły wprowadzania danych biznesowych do składnika będącego modelem danych.

Jednostka biznesowa modelu danych jest przedstawiona jako kontener (rekord). Właściwości jednostki biznesowej są przedstawione jako składniki danych (pola). Każdy element danych ma niepowtarzalną nazwę, etykietę, opis i wartość. Wartość każdego elementu danych może być zaprojektowane tak, aby była rozpoznawana jako ciąg tekstowy, liczba całkowita, liczba rzeczywista, data, element stałotekstowy, wartość logiczna itd. Ponadto może to być inny rekord lub lista rekordów.

Pojedynczy składnik typu Model danych może zawierać kilka hierarchii jednostek biznesowych właściwych dla danej domeny. Może również zawierać mapowania modelu obsługujące przepływ danych właściwy dla raportu w czasie wykonywania. Hierarchie są rozróżniane przez pojedynczy rekord, który został wybrany jako główny dla mapowania modelu. Na przykład model danych obszaru domeny płatności może obsługiwać następujące mapowania:

- Firma > Dostawca > Transakcje płatności w przypadku domeny rozrachunków z dostawcami
- Odbiorca > Firma > Transakcje płatności w przypadku domeny rozrachunków z odbiorcami

Zauważ, że jednostki biznesowe, np. Firma i Transakcje płatności, są projektowane tylko jeden raz. Następnie różne mapowania używają ich wielokrotnie.

Mapowanie modelu obsługujące wychodzące dokumenty elektroniczne ma następujące możliwości:

- Może wykorzystywać różne typy danych programu Finance and Operations jako źródła danych dla modelu danych. Na przykład może używać tabel, jednostek danych, metod lub tekstów stałych.
- Obsługuje parametry wejściowe użytkownika, które można zdefiniować jako źródła danych modelu danych, gdy część danych musi być określona w czasie wykonywania.
- Obsługuje przekształcanie danych programu Finance and Operations w wymagane grupy. Umożliwia także filtrowanie, sortowanie i sumowanie danych, a także dołączanie logicznych pól obliczanych projektowanych za pomocą formuł przypominających formuły programu Microsoft Excel, co pokazano na ilustracji poniżej. Aby uzyskać więcej informacji, zobacz [Projektant formuł w raportowaniu elektronicznym](general-electronic-reporting-formula-designer.md).

[![Projektant formuł](./media/ER-overview-01.png)](./media/ER-overview-01.png) 

Mapowanie modelu obsługujące przychodzące dokumenty elektroniczne ma następujące możliwości:

- Może używać różnych aktualizowanych elementów danych jako celów. Te elementy danych obejmują tabele, jednostki danych i widoki. Dane mogą być aktualizowane przy użyciu danych z przychodzących dokumentów elektronicznych. W jednym mapowaniu modelu można użyć wielu elementów docelowych.
- Obsługuje parametry wejściowe użytkownika, które można zdefiniować jako źródła danych modelu danych, gdy część danych musi być określona w czasie wykonywania.

Składnik typu Model danych jest projektowany dla każdej domeny biznesowej i służy jako ujednolicone źródło danych dla raportowania, które izoluje raportowanie od fizycznej implementacji źródeł danych. Reprezentuje właściwe dla domeny koncepcje i funkcje biznesowe w formie, która upraszcza początkowe projektowanie formatów raportowania i ich dalszą obsługę.

#### <a name="format-components-for-outgoing-electronic-documents"></a>Składniki typu Format dla wychodzących dokumentów elektronicznych

Składnik typu Format określa schemat danych wyjściowych raportowania, które będą generowane w czasie wykonywania. Schemat składa się z następujących elementów:

- Format definiujący strukturę i zawartość wychodzącego dokumentu elektronicznego generowanego podczas wykonywania.
- Źródła danych jako zestaw parametrów wejściowych użytkownika i modelu danych właściwego dla domeny, który wykorzystuje wybrany model mapowania.
- Mapowanie formatu jako zestaw powiązań źródeł danych formatu zawierających poszczególne elementy formatu, które podczas wykonywania określają przepływ danych i reguły generowania danych wyjściowych w tym formacie.
- Sprawdzanie poprawności formatu jako zestaw konfigurowalnych reguł sterujących generowaniem raportu w czasie wykonywania w zależności od kontekstu pracy. Na przykład może istnieć reguła, która zatrzymuje generowanie danych wyjściowych płatności dla dostawcy i zgłasza wyjątek, gdy brakuje określonych atrybutów wybranego dostawcy, takich jak numer konta bankowego.

Składnik typu Format obsługuje następujące funkcje:

- Tworzenie danych wyjściowych raportowania jako pojedynczych plików w różnych formatach, takich tekstowy, XML, dokument programu Microsoft Word lub arkusz.
- Tworzenie wielu plików oddzielnie i hermetyzacja tych plików do plików zip.

Składnik typu Format umożliwia załączanie określonych plików, które mogą być używane w wynikach raportowania:

- Skoroszyty programu Excel zawierające arkusze, których można używać jako szablonów danych wyjściowych w formacie arkusza OPENXML.
- Pliki programu Word zawierające dokumenty, których można używać jako szablonów danych wyjściowych w formacie dokumentów programu Microsoft Word.
- Inne pliki, które mogą zostać włączone w dane wyjściowe formatu jako pliki wstępnie zdefiniowane.

Na poniższej ilustracji przedstawiono sposób przepływu danych w tych formatach.

[![Przepływ danych dla składników typu Format dokumentów wychodzących](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Aby uruchomić jedną konfigurację formatu modułu ER i wygenerować wychodzący dokument elektroniczny, należy określić mapowanie dla konfiguracji formatu.

#### <a name="format-components-for-incoming-electronic-documents"></a>Składniki typu Format dla przychodzących dokumentów elektronicznych
Składnik typu Format określa schemat dokumentu przychodzącego, który jest importowany w czasie wykonywania. Schemat składa się z następujących elementów:

- Format definiujący strukturę i zawartość dokumentu przychodzącego dokumentu elektronicznego zawierającego dane importowane podczas wykonywania. Składnik typu Format służy do analizowania składni przychodzących dokumentów w różnych formatach, takich jak tekst i XML.
- Mapowanie formatu, które wiąże poszczególne elementy formatu z elementami modelu danych konkretnej domeny. W czasie wykonywania elementy w modelu danych określają przepływ danych oraz reguły importowania danych z przychodzącego dokumentu, a następnie zapisują te dane w modelu danych.
- Sprawdzanie poprawności formatu jako zestaw konfigurowalnych reguł sterujących importem danych w czasie wykonywania w zależności od kontekstu pracy. Na przykład może istnieć reguła, która zatrzymuje import danych z wyciągu bankowego zawierającego płatności dla dostawcy i zgłasza wyjątek, gdy brakuje określonych atrybutów dostawcy, takich jak kod identyfikacyjny dostawcy.

Na poniższej ilustracji przedstawiono sposób przepływu danych w tych formatach.

[![Przepływ danych dla składników typu Format dokumentów przychodzących](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Aby uruchomić jedną konfigurację formatu modułu ER w celu zaimportowania danych z przychodzącego dokumentu elektronicznego, należy określić żądane mapowanie konfiguracji formatu oraz punkt integracji mapowania modelu. Tego samego mapowania modelu i miejsc docelowych można używać w połączeniu z różnymi formatami dla różnych rodzajów dokumentów przychodzących.

#### <a name="component-versioning"></a>Przechowywanie wersji składnika

Dla składników ER jest obsługiwane przechowywanie wersji. Poniższy przepływ pracy służy do zarządzania zmianami w składnikach ER:

1. Wersja tworzona pierwotnie jest oznaczona jako **Wersja robocza**. Ta wersja może być edytowana i jest dostępna do testów.
2. Wersję **Wersja robocza** można przekonwertować na wersję **Ukończona**. Ta wersja może być używana w lokalnych procesach raportowania.
3. Wersję **Ukończona** można przekonwertować na wersję **Udostępniona**. Ta wersja jest publikowana w usłudze LCS i może być używana w globalnych procesach sprawozdawczości.
4. Wersję **Udostępniona** można przekonwertować na wersję **Wycofana**. Tę wersję można następnie usunąć.

Wersje ze stanem **Ukończona** lub **Udostępniona** są dostępne dla innych procesów wymiany danych. Na składniku mającym te stany można wykonywać następujące operacje:

- Składnik może być serializowany w formacie XML i eksportowany jako plik w formacie XML.
- Składnik może być reserializowany z pliku XML i importowany do programu Finance and Operations jako nowa wersja składnika raportowania elektronicznego.

#### <a name="component-date-effectivity"></a>Daty obowiązywania składnika

Wersje składników ER mają daty obowiązywania. Dla składnika ER można zdefiniować datę **Obowiązuje od**, aby określić datę, od której ten składnik zaczyna działać dla procesów raportowania. Data sesji programu Finance and Operations pozwala określić, czy składnik może zostać wykonany. Gdy dla danej daty jest dostępnych kilka wersji, najnowsza wersja jest używana w procesach raportowania.

#### <a name="component-access"></a>Dostęp do składnika

Dostęp do składników formatu aplikacji ER zależy od ustawienia kodu ISO kraju/regionu. Gdy to ustawienie jest puste dla wybranej wersji konfiguracji formatu, dostęp do składnika formatu można uzyskać podczas wykonywania z każdej firmy. Gdy to zawiera kody ISO kraju/regionu, składnik formatu jest dostępny tylko z tych firm, których adres główny został zdefiniowany dla jednego z kodów ISO kraju/regionu istniejących w składniku formatu.

Różne wersje składnika formatu danych mogą mieć różne ustawienia kodów ISO kraju/regionu.

#### <a name="configuration"></a>Konfiguracja

Konfiguracja narzędzia ER jest otoką konkretnego składnika ER. Składnik ten może być typu Model danych lub Format. Konfiguracja może zawierać różne wersje składnika ER. Każda konfiguracja jest oznaczona jako należąca do określonego dostawcy konfiguracji. Wersja **Wersja robocza** składnika konfiguracji może być edytowana, gdy właściciel konfiguracji został wybrany jako aktywny dostawca w ustawieniach ER w programie Finance and Operations.

Każda konfiguracja modelu zawiera składnik Model danych. Nowa konfiguracja formatu może zostać wygenerowana na podstawie określonej konfiguracji modelu danych. W drzewie konfiguracji utworzona konfiguracja formatu będzie wyświetlana jako element podrzędny oryginalnej konfiguracji modelu danych.

Tworzona konfiguracja formatu zawiera składnik Format. Składnik Model danych oryginalnej konfiguracji modelu jest automatycznie wstawiany do składnika Format podrzędnej konfiguracji formatu jako domyślne źródło danych.

Konfiguracja ER jest udostępniana firmom w programie Finance and Operations.

#### <a name="provider"></a>Dostawca

Dostawca ER określa stronę (podmiotu) używaną do wskazania autora (właściciela) konfiguracji ER. Aplikacja ER pozwala zarządzać listą dostawców konfiguracji. Konfiguracje formatu publikowane dla dokumentów elektronicznych w ramach rozwiązania Finance and Operations są oznaczone jako należące do dostawcy konfiguracji **Microsoft**.

Aby uzyskać informacje o rejestrowaniu nowego dostawcy ER, odtwórz przewodnik po zadaniu **ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

#### <a name="repository"></a>Repozytorium

Konfiguracje ER są przechowywane w repozytorium ER. Obecnie obsługiwane są dwa typy repozytoriów ER: **Zasoby operacyjne** i **Projekt usługi LCS**.

Repozytorium **Zasoby operacyjne** zapewnia dostęp do listy konfiguracji, które firma Microsoft, jako dostawca konfiguracji raportowania elektronicznego, publikuje w ramach rozwiązania Finance and Operations. Te konfiguracje można importować do bieżącego wystąpienia programu Finance and Operations i używać dla raportowania elektronicznego. Można je również wykorzystywać dla dodatkowych tłumaczeń i dostosowań.

Repozytorium **Projekt usługi LCS** zapewnia dostęp do listy konfiguracji określonego projektu LCS (biblioteki zasobów projektu usługi LCS) wybranego na etapie rejestracji repozytorium. Narzędzie ER umożliwia przekazywanie udostępnionych konfiguracji z bieżącego wystąpienia programu Finance and Operations do konkretnego repozytorium **Projekt usługi LCS**. Można także importować konfiguracje z repozytorium **Projekt usługi LCS** do bieżącego wystąpienia programu Finance and Operations.

Wymagane repozytoria **Projekt usługi LCS** można rejestrować indywidualnie dla każdego dostawcy konfiguracji bieżącego wystąpienia programu Finance and Operations. Każde repozytorium może być dedykowane określonemu dostawcy konfiguracji.

## <a name="supported-scenarios"></a>Obsługiwane scenariusze
### <a name="building-a-data-model"></a>Budowanie modelu danych

Aplikacja ER zawiera projektanta modeli, który może służyć do budowania modeli danych dla konkretnych domen biznesowych. Wszystkie jednostki biznesowe właściwe dla domeny oraz relacje między nimi można przedstawić w modelu danych jako strukturę hierarchiczną. Ilustracja poniżej zawiera przykład tego rodzaju modelu danych (modelu danych dla domeny płatności). 

[![Model danych domeny płatności](./media/ER-overview-04.png)](./media/ER-overview-04.png)

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Projektowanie modelu danych dla konkretnej domeny** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="translating-data-model-content"></a>Tłumaczenie zawartości modelu danych

Zawartość modelu danych (etykiety i opisy) można przetłumaczyć na inne języki obsługiwane przez program Finance and Operations. Powody tłumaczenia zawartości modelu danych mogą być następujące:

-   Podczas projektowania — w celu poprawy czytelności zawartości dla projektantów formatów mówiących w obcych językach, którzy używają modelu danych do mapowania danych składników formatu.
-   Podczas wykonywania — aby zawartość była bardziej przyjazna dla użytkownika poprzez wyświetlanie monitów i pomocy dla parametrów ustawianych w czasie wykonywania, a także wyświetlanie skonfigurowanych komunikatów sprawdzania poprawności (błędów i ostrzeżeń) w języku preferowanym przez aktualnie zalogowanego użytkownika.

Poniższa ilustracja zawiera przykład tłumaczenia zawartości modelu danych z języka angielskiego na japoński. 

[![Zawartość modelu danych w języku angielskim](./media/ER-overview-05.png)](./media/ER-overview-05.png)

[![Zawartość modelu danych przetłumaczona na język japoński](./media/ER-overview-06.png)](./media/ER-overview-06.png)


### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Konfigurowanie mapowań modelu danych dla dokumentów wychodzących

Aplikacja ER zawiera projektanta mapowania modeli, który pozwala użytkownikom mapować zaprojektowane modele danych na konkretne źródła danych programu Finance and Operations. W oparciu o mapowanie dane zostaną zaimportowane w czasie wykonywania z wybranych źródeł danych do modelu danych. Następnie model danych jest używany jako abstrakcyjne źródło danych formatów modułu Raportowanie elektroniczne, które generują wychodzące dokumenty elektroniczne. Na ilustracji poniżej widać przykład takiego mapowania modelu danych (mapowanie modelu danych **Polecenie przelewu SEPA** związanego z domeną płatności). 

[![Przykład mapowania modelu danych](./media/ER-overview-07.png)](./media/ER-overview-07.png)

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodniki po zadaniach **ER Definiowanie mapowania modelu i wybieranie źródeł danych** oraz **ER Mapowanie modelu danych na wybrane źródła danych** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Konfigurowanie mapowań modelu danych dla dokumentów przychodzących
Aplikacja ER zawiera projektanta mapowania modeli, który pozwala użytkownikom mapować zaprojektowane modele danych na konkretne miejsca docelowe. Na przykład modele danych mogą być mapowane na aktualizowalne składniki danych programu Finance and Operations (tabele, jednostki danych i widoki). W oparciu o mapowanie dane programu Finance and Operations będą aktualizowane w czasie wykonywania przy użyciu danych z modelu danych. Jako abstrakcyjny magazyn formatu raportowania elektronicznego model danych jest wypełniany danymi importowanymi z przychodzącego dokumentu elektronicznego. Ilustracja poniżej zawiera przykład tego rodzaju mapowania modelu danych. W tym przykładzie mapowanie modelu danych domeny płatności **Mapowanie importu dla NETS** jest używane do obsługi importu wyciągów bankowych w formacie bankowym NETS dla Norwegii.

[![Przykład mapowania importu dla modelu danych NETS](./media/ER-overview-08.png)](./media/ER-overview-08.png)

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Przechowywanie zaprojektowanego składnika modelu jako konfiguracji modelu

Narzędzie ER może przechowywać zaprojektowany model danych razem powiązanymi mapowaniami danych jako konfigurację modelu bieżącego wystąpienia programu Finance and Operations. Ilustracja poniżej zawiera przykład tego rodzaju konfiguracji modelu danych (konfiguracji modelu płatności). 

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Mapowanie modelu danych na wybrane źródła danych** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Budowanie formatu na podstawie modelu danych

Aplikacja ER zawiera projektanta formatów umożliwiającego tworzenie formatów dokumentów elektronicznych dla wybranej domeny biznesowej poprzez wybranie składnika modelu jako bazy. Ten sam projektant formatów pozwala zmapować utworzony format na mapowanie modelu danych wybranej domeny jako źródło danych. Na ilustracji poniżej widać przykład tego rodzaju formatu (konfiguracji formatu obsługującej format płatności **BACS** dla Wielkiej Brytanii). 

[![Przykład formatu opartego na modelu danych](./media/ER-overview-09.png)](./media/ER-overview-09.png)

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Projektowanie formatu dla konkretnej domeny** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Tworzenie konfiguracji do generowania dokumentów elektronicznych w formacie arkusza OPENXML

Projektant formatów w aplikacji ER może służyć do redagowania dokumentu elektronicznego w formacie arkusza OPENXML. Na ilustracji poniżej widać przykład tego rodzaju formatu (konfiguracji formatu do generowania arkusza OPENXML ze szczegółami wybranego arkusza płatności).

[![Pic-ER-format-Excel](./media/ER-overview-10.png)](./media/ER-overview-10.png)

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Tworzenie konfiguracji dla raportów w formacie OPENXML** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**). W ramach kroku przewodnika po zadaniu importowania szablonu użyj plik programu Excel [Szablon raportu o płatnościach (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202) jako szablonu.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Tworzenie konfiguracji do generowania dokumentów elektronicznych w formacie dokumentu programu Word
Projektant formatów w aplikacji ER może służyć do redagowania dokumentu elektronicznego w formacie dokumentu programu Word. Ilustracja poniżej zawiera przykład tego rodzaju formatu. Należy zauważyć, że ten format wykorzystuje istniejącą konfigurację ER, która została pierwotnie zaprojektowana do generowania danych wyjściowych raportu w formacie OPENXML.

[![Pic-ER-format-Word](./media/ER-overview-11.png)](./media/ER-overview-11.png)

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu ER Projektowanie konfiguracji do generowania raportów w formacie Microsoft WORD (część procesu biznesowego 7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)). W ramach kroku przewodnika po zadaniu importowania szablonu użyj następujących plików programu Word jako szablonów formatu ER:

- [Szablon raportu o płatnościach (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Ograniczony szablon raportu o płatnościach (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Tworzenie konfiguracji do importowania danych z przychodzących dokumentów elektronicznych  
Projektant formatów w aplikacji ER może służyć do opisania dokumentu elektronicznego, którego planuje się używać do importowania danych w formacie XML lub tekstowym. Zaprojektowany format jest używany do analizowania składni przychodzących dokumentów. Projektant mapowania formatów w aplikacji ER może służyć do zdefiniowania powiązań elementów projektowanego formatu z modelem danych. Ilustracja poniżej zawiera przykład tego rodzaju formatu i mapowania formatu. W tym przykładzie są importowane wyciągi bankowe NETS zawierające szczegóły płatności dla dostawców w formacie tekstowym.

[![ER-format-designer](./media/ER-overview-12.png)](./media/ER-overview-12.png)

[![ER-model-mapping-designer](./media/ER-overview-13.png)](./media/ER-overview-13.png)

Aby zapoznać się z tym scenariuszem w szczegółach, odtwórz przewodnik po zadaniu Tworzenie wymaganych konfiguracji ER do importowania danych z pliku zewnętrznego (część procesu biznesowego 7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)). Do odtworzenia tego przewodnika użyj następujących plików:

- [Konfiguracja modelu danych ER (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Konfiguracja formatu ER (1099format.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Przykładowy dokument przychodzący w formacie XML (1099entries.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Przykładowy skoroszyt do zarządzania danymi dokumentu przychodzącego (1099entries.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Przechowywanie zaprojektowanego składnika formatu w konfiguracji formatu

Aplikacja ER może przechowywać zaprojektowany format razem ze skonfigurowanymi mapowaniami danych jako konfigurację formatu bieżącego wystąpienia programu Finance and Operations. Poprzednia ilustracja zawiera przykład tego typu konfiguracji formatu (**BACS (Wielka Brytania)**, która jest obiektem podrzędnym konfiguracji **Model płatności**). Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Projektowanie formatu dla konkretnej domeny** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="configuring-finance-and-operations-to-start-to-use-a-created-format-internally"></a>Konfigurowanie programu Finance and Operations, aby zaczął używać utworzonego formatu wewnętrznie

Program Finance and Operations można skonfigurować w taki sposób, aby zaczął używać utworzonego formatu do generowania raportów elektronicznych. Odwołanie do utworzonej konfiguracji formatu powinno być zdefiniowane w ustawieniach konkretnej domeny. Aby na przykład zacząć używać konfiguracji formatu ER dla płatności elektronicznych do dostawcy w formacie BACS, odwołanie do konfiguracji formatu powinno się znajdować konkretnych metodach płatności, jak przedstawiono na ilustracjach poniższej: 

[![Konfiguracja formatu BACS (Wielka Brytania)](./media/ER-overview-14.png)](./media/ER-overview-14.png)

[![Odwołanie do formatu BACS (Wielka Brytania) w metodzie płatności](./media/ER-overview-15.png)](./media/ER-overview-15.png)

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Używanie formatu do generowania dokumentów elektronicznych dla płatności** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

## <a name="handling-er-components"></a>Obsługa składników raportowania elektronicznego
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publikowanie składnika ER w portalu LCS w celu zaoferowania go na zewnątrz (tłumaczenie)

Właściciel utworzonego składnika (modelu lub formatu) może użyć aplikacji ER do opublikowania ukończonej wersji składnika w usłudze LCS. Potrzebne jest do tego repozytorium typu **Projekt usługi LCS** dla bieżącego dostawcy konfiguracji ER. Gdy stan ukończonej wersji składnika zmieni się z **UKOŃCZONA** na **UDOSTĘPNIONA**, ta wersja jest opublikowana w portalu LCS. Po opublikowaniu składnika w usłudze LCS jego właściciel staje się dostawcą usługi obsługującej ten składnik. Jeśli na przykład zadaniem składnika formatu jest generowanie dokumentów elektronicznych wymaganych prawem (np. zgodnie ze scenariuszem tłumaczenia), zakłada się, że format będzie na bieżąco aktualizowany o zmiany legislacyjne, a dostawca będzie publikował nowe wersje składnika w reakcji na każdy nowy wymóg prawny. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Przekazywanie konfiguracji do usługi Lifecycle Services** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importowanie składnika ER z usługi LCS na potrzeby użytku wewnętrznego

Narzędzie ER pozwala importować składniki ER z usługi LCS do bieżącego wystąpienia programu Finance and Operations. Potrzebne jest do tego repozytorium typu **Projekt usługi LCS**. Po zaimportowaniu składnika ER z portalu LCS do bieżącego wystąpienia programu Finance and Operations właściciel tego wystąpienia staje się konsumentem usługi dostarczanej przez właściciela (autora) zaimportowanego składnika. Na przykład jeśli składnik formatu ma generować określony dokument elektroniczny z programu Finance and Operations w formacie właściwym dla danego kraju/regionu (scenariusz tłumaczenia), zakłada się, że konsument usługi będzie w stanie otrzymywać wszelkie aktualizacje tego formatu, aby zachować zgodność z wymaganiami legislacyjnymi. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Importowanie konfiguracji z usługi Lifecycle Services** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Budowanie formatu na podstawie innego formatu (dostosowywanie)

Aplikacja ER pozwala utworzyć (pochodny) nowy składnik z bieżącej (bazowej) wersji składnika, którą zaimportowano z usługi LCS. Na przykład użytkownik chce utworzyć nowy format pochodny w celu zaimplementowania pewnych szczególnych wymagań dotyczących dokumentu elektronicznego (na przykład dodatkowe pole lub rozszerzony opis) dla scenariusza personalizacji. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Uaktualnianie formatu przez przyjęcie jej nowej wersji bazowej** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Uaktualnianie formatu przez przyjęcie jej nowej wersji bazowej (zmiana bazy)

Narzędzie ER pozwala automatyczne powielać zmiany z najnowszej wersji składnika bazowego do aktualnej wersji roboczej składnika pochodnego. Ten proces jest nazywany *zmianą bazy*. Na przykład nowa zmiana przepisów, którą wprowadzono w najnowszej wersji składnika formatu zaimportowanego z usługi LCS, może być automatycznie scalana do dostosowanej wersji tego formatu dokumentu elektronicznego. Wszelkie zmiany, których nie można scalić automatycznie, są uznawane za konflikty. Te konflikty są wyświetlane do rozstrzygnięcia ręcznego w projektancie odpowiedniego składnika. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Uaktualnianie formatu przez przyjęcie jego nowej wersji bazowej** (część procesu biznesowego **7.5.5.3 Nabywanie/opracowywanie zmienionego składnika usługi/rozwiązania informatycznego (10683)**).

## <a name="list-of-er-configurations-that-are-delivered-in-the-finance-and-operations-solution"></a>Wykaz konfiguracji ER dostarczanych w programie Finance and Operations
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




