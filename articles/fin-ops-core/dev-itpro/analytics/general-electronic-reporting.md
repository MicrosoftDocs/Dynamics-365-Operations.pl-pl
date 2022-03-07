---
title: Omówienie raportowania elektronicznego (RE)
description: Ten temat zawiera omówienie narzędzia Raportowanie elektroniczne. Opisano w nim najważniejsze pojęcia, obsługiwane scenariusze i formaty, które są częścią rozwiązania.
author: NickSelin
ms.date: 11/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "58941"
- intro-internal
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 976a02f51e22c513b988e1ecfcb792d5f93a4b54
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986154"
---
# <a name="electronic-reporting-er-overview"></a>Omówienie raportowania elektronicznego (ER)

[!include [banner](../includes/banner.md)]

Ten temat zawiera omówienie narzędzia Raportowanie elektroniczne. Przedstawiono w nim informacje dotyczące najważniejszych koncepcji, scenariusze obsługiwane przez narzędzie Raportowanie elektroniczne oraz listę formatów zaprojektowanych i udostępnionych w ramach rozwiązania.

Raportowanie elektroniczne (ER) jest konfigurowalnym narzędziem, które pomaga w tworzeniu i obsłudze zgodności z przepisami w zakresie raportowania i płatności elektronicznych. Opiera się ono na trzech koncepcjach:

- Konfiguracja zamiast kodowania:

    - Konfiguracja może zostać wykonana przez użytkownika biznesowego i nie wymaga dewelopera.
    - Model danych jest definiowany jako biznesowy.
    - Edytory wizualizacji służą do tworzenia wszystkich składników konfiguracji ER.
    - Język używany do przekształcania danych przypomina język używany w programie Microsoft Excel.

- Jedna konfiguracja dla wielu wersji aplikacji Dynamics 365 Finance:

    - Zarządzanie modelem danych specyficznym dla domeny, zdefiniowanym w terminach biznesowych.
    - Wyodrębnianie szczegółów zwolnienia aplikacji w mapowaniu modelu danych zależnych od wersji.
    - Obsługa jednej konfiguracji formatu dla wielu wydań bieżącej wersji na podstawie modelu danych.

- Łatwe lub automatyczne uaktualnienie:

    - Przechowywanie wersji konfiguracji ER jest obsługiwane.
    - Biblioteka zasobów usługi Microsoft Dynamics Lifecycle Services (LCS) może być używana jako repozytorium konfiguracji ER, w celu wymiany wersji.
    - Wersje podrzędne można wprowadzać w lokalizacjach opartych na oryginalnych konfiguracjach ER.
    - Drzewo konfiguracji ER jest udostępniane jako narzędzie, które pomaga kontrolować zależności wersji.
    - Rejestrowane są różnice w lokalizacji (konfiguracja różnicowa), aby umożliwić automatyczne uaktualnienie do nowej wersji oryginalnej konfiguracji ER.
    - Można łatwo ręcznie rozwiązać konflikty wykryte podczas automatycznego uaktualniania wersji lokalizacji.

Moduł ER pozwala definiować struktury formatu elektronicznego, a następnie opisywać, jak struktury powinny być wypełniane przy użyciu danych i algorytmów. W przypadku przekształcenia danych można używać języka formuł przypominającego język programu Excel. Aby mapowanie bazy danych do formatu było łatwiejsze do zarządzania, wielokrotnego użytku i niezależne od zmian w formatach, wprowadzona jest koncepcja pośredniego modelu danych. Ta koncepcja umożliwia ukrywanie szczegółów implementacji w mapowaniu formatów oraz ponowne używanie jednego modelu danych w wielu mapowaniach formatów.

Narzędzia ER można używać do konfigurowania formatów dokumentów elektronicznych przychodzących i wychodzących zgodnie z wymogami prawnymi różnych krajów i regionów. ER pozwala zarządzać tymi formatami podczas ich całego cyklu życia. Na przykład można wdrożyć nowe wymogi prawne, a następnie generować dokumenty biznesowe w wymaganym formacie w celu elektronicznej wymiany informacji z organami rządowymi, bankami i innymi stronami.

Aparat ER jest adresowany do użytkowników biznesowych, a nie programistów. Ponieważ konfiguruje się formaty, a nie kod, procesy tworzenia i dostosowywania formatów dokumentów elektronicznych są szybsze i łatwiejsze.

ER obecnie obsługuje arkusze w formatach TEKST, XML, JSON, PDF, Microsoft Word, Microsoft Excel i OPENXML.

## <a name="capabilities"></a>Możliwości

Aparat GER ma następujące cechy:

- Stanowi jedno wspólne narzędzie do raportowania elektronicznego w różnych domenach oraz zastępuje ponad 20 różnych innych aparatów obsługujących różne formy raportowania elektronicznego dla Finance and Operations.
- Izoluje format raportu od bieżącej implementacji. Innymi słowy format można stosować do różnych wersji.
- Obsługuje tworzenie niestandardowego formatu opartego na oryginalnym formacie. Zawiera również funkcje automatycznego uaktualniania dostosowanego formatu po dokonaniu zmian w oryginalnym formacie spowodowanych koniecznością przetłumaczenia/dostosowania.
- Staje się podstawowym standardowym narzędziem do obsługi wymagań tłumaczeniowych w raportach elektronicznych — dla oprogramowania zarówno firmy Microsoft, jak i jej partnerów.
- Obsługuje możliwość dystrybucji formatów do partnerów i odbiorców za pomocą portalu Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Podstawowe pojęcia

### <a name="main-data-flow"></a>Główny przepływ danych

[![Główny przepływ danych ER.](./media/ger-main-data-flow.jpg)](./media/ger-main-data-flow.jpg)

### <a name="components"></a>Składniki

ER obsługuje następujące typy składników:

- Model danych
- Mapowanie modelu
- Format
- Metadane

Aby uzyskać więcej informacji, zobacz [Składniki raportowania elektronicznego](er-overview-components.md).


#### <a name="component-versioning"></a>Przechowywanie wersji składnika

Dla składników ER jest obsługiwane przechowywanie wersji. Poniższy przepływ pracy służy do zarządzania zmianami w składnikach ER:

1. Wersja tworzona pierwotnie jest oznaczona jako **Wersja robocza**. Ta wersja może być edytowana i jest dostępna do testów.
2. Wersję **Wersja robocza** można przekonwertować na wersję **Ukończona**. Ta wersja może być używana w lokalnych procesach raportowania.
3. Wersję **Ukończona** można przekonwertować na wersję **Udostępniona**. Ta wersja jest publikowana w usłudze LCS i może być używana w globalnych procesach sprawozdawczości.
4. Wersję **Udostępniona** można przekonwertować na wersję **Wycofana**. Tę wersję można następnie usunąć.

Wersje ze stanem **Ukończona** lub **Udostępniona** są dostępne dla innych procesów wymiany danych. Na składniku mającym te stany można wykonywać następujące operacje:

- Składnik może być serializowany w formacie XML i eksportowany jako plik w formacie XML.
- Składnik może być reserializowany z pliku XML i importowany do aplikacji jako nowa wersja składnika raportowania elektronicznego.

#### <a name="component-date-effectivity"></a>Daty obowiązywania składnika

Wersje składników ER mają daty obowiązywania. Dla składnika ER można zdefiniować datę **Obowiązuje od**, aby określić datę, od której ten składnik zaczyna działać dla procesów raportowania. Data sesji aplikacji pozwala określić, czy składnik może być uruchamiany. Gdy dla danej daty jest dostępnych kilka wersji, najnowsza wersja jest używana w procesach raportowania.

#### <a name="component-access"></a>Dostęp do składnika

Dostęp do składników formatu aplikacji ER zależy od ustawienia kodu ISO kraju/regionu. Gdy to ustawienie jest puste dla wybranej wersji konfiguracji formatu, dostęp do składnika formatu można uzyskać podczas wykonywania z każdej firmy. Gdy to zawiera kody ISO kraju/regionu, składnik formatu jest dostępny tylko z tych firm, których adres główny został zdefiniowany dla jednego z kodów ISO kraju/regionu istniejących w składniku formatu.

Różne wersje składnika formatu danych mogą mieć różne ustawienia kodów ISO kraju/regionu.

#### <a name="configuration"></a><a name="Configuration"></a>Konfiguracja

Konfiguracja narzędzia ER jest otoką konkretnego składnika ER. Składnik ten może być typu Model danych lub Format. Konfiguracja może zawierać różne wersje składnika ER. Każda konfiguracja jest oznaczona jako należąca do określonego dostawcy konfiguracji. Wersja **Wersja robocza** składnika konfiguracji może być edytowana, gdy właściciel konfiguracji został wybrany jako aktywny dostawca w ustawieniach ER w aplikacji.

Każda konfiguracja modelu zawiera składnik Model danych. Nowa konfiguracja formatu może zostać wygenerowana na podstawie określonej konfiguracji modelu danych. W drzewie konfiguracji utworzona konfiguracja formatu będzie wyświetlana jako element podrzędny oryginalnej konfiguracji modelu danych.

Tworzona konfiguracja formatu zawiera składnik Format. Składnik Model danych oryginalnej konfiguracji modelu jest automatycznie wstawiany do składnika Format podrzędnej konfiguracji formatu jako domyślne źródło danych.

Konfiguracja ER jest udostępniana firmom w aplikacji.

#### <a name="provider"></a><a name="Provider"></a>Dostawca

Dostawca ER określa stronę (podmiotu) używaną do wskazania autora (właściciela) konfiguracji ER. Aplikacja ER pozwala zarządzać listą dostawców konfiguracji. Konfiguracje formatu publikowane dla dokumentów elektronicznych w ramach rozwiązania Finance and Operations są oznaczone jako należące do dostawcy konfiguracji **Microsoft**.

Aby uzyskać informacje o rejestrowaniu nowego dostawcy ER, odtwórz przewodnik po zadaniu **ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

#### <a name="repository"></a><a name="Repository"></a>Repozytorium

Konfiguracje ER są przechowywane w repozytorium ER. Obecnie obsługiwane są następujące typy repozytoriów ER: 

- Biblioteka udostępnionych elementów LCS
- Projekt usługi LCS
- System plików
- RCS
- Zasoby rozwiązania Operations
- Repozytorium globalne

Repozytorium **Biblioteka udostępnionych elementów LCS** zapewnia dostęp do listy konfiguracji w bibliotece aktywów wspólnych w Lifecycle Services (LCS). Tego rodzaju repozytorium ER może być rejestrowane tylko dla dostawcy firmy Microsoft. Z biblioteki aktywów wspólnych LCS można importować najnowsze wersje konfiguracji ER do bieżącego wystąpienia.

Repozytorium **Projekt usługi LCS** zapewnia dostęp do listy konfiguracji określonego projektu LCS (biblioteki zasobów projektu usługi LCS) wybranego podczas rejestracji repozytorium. Narzędzie ER umożliwia przekazywanie udostępnionych konfiguracji z bieżącego wystąpienia do konkretnego repozytorium **Projekt usługi LCS**. Można także importować konfiguracje z repozytorium **Projekt usługi LCS** do bieżącego wystąpienia aplikacji Finanse i Operacje.

Repozytorium **systemu plików** udostępnia listę konfiguracji, które znajdują się w postaci plików xml w określonym folderze lokalnego systemu plików komputera, na którym działa usługa AOS. Wymagany folder jest wybierany w procesie rejestracji repozytorium. Można także importować konfiguracje z repozytorium **System plików** do bieżącego wystąpienia. 

Należy zauważyć, że ten typ repozytorium jest dostępny w następujących środowiskach:

- Środowiska hostowane w chmurze wdrożone na potrzeby programowania (zawierające modele testu zamkniętych pakietów)
- Lokalnie wdrażane środowiska

Aby uzyskać więcej informacji, zobacz [Importowanie konfiguracji raportowania elektronicznego (RE)](./electronic-reporting-import-ger-configurations.md).

Repozytorium **RCS** zapewnia dostęp do listy konfiguracji określonego wystąpienia [Configuration service (RCS)](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) wybranego na etapie rejestracji repozytorium. ER pozwala importować kompletne lub udostępniane konfiguracje z wybranego wystąpienia RCS do bieżącego wystąpienia i używać do raportowania elektronicznego.

Aby uzyskać więcej informacji, zobacz [Importowanie konfiguracji raportowania elektronicznego (RE) z RCS](./rcs-download-configurations.md).

**Repozytorium globalne** umożliwia dostęp do listy konfiguracji w repozytorium globalnym w [Configuration service](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration). Tego rodzaju repozytorium ER może być rejestrowane tylko dla dostawcy firmy Microsoft. Z repozytorium globalnego można importować najnowsze wersje konfiguracji ER do bieżącego wystąpienia.

Aby uzyskać więcej informacji, zobacz [Importowanie konfiguracji raportowania elektronicznego (RE) z repozytorium globalnego w Configuration service](./er-download-configurations-global-repo.md).

Repozytorium **Zasoby operacyjne** zapewnia dostęp do listy konfiguracji, które firma Microsoft, jako dostawca konfiguracji raportowania elektronicznego, publikuje w ramach rozwiązania aplikacji. Te konfiguracje można importować do bieżącego wystąpienia i używać dla raportowania elektronicznego lub odtwarzania instrukcji wykonywania przykładowych zadań. Można je również wykorzystywać dla dodatkowych tłumaczeń i dostosowań. Należy zauważyć, że najnowsze wersje konfiguracji ER udostępnianych przez Microsoft trzeba importować z biblioteki aktywów wspólnych LCS przy użyciu odpowiedniego repozytorium ER.

Wymagane repozytoria **Projekt usługi LCS**, **System plików** i **Regulatory Configuration Services (RCS)** można rejestrować indywidualnie dla każdego dostawcy konfiguracji bieżącego wystąpienia. Każde repozytorium może być dedykowane określonemu dostawcy konfiguracji.

## <a name="supported-scenarios"></a>Obsługiwane scenariusze

### <a name="building-a-data-model"></a>Budowanie modelu danych

Aplikacja ER zawiera projektanta modeli, który może służyć do budowania modeli danych dla konkretnych domen biznesowych. Wszystkie jednostki biznesowe właściwe dla domeny oraz relacje między nimi można przedstawić w modelu danych jako strukturę hierarchiczną. 

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Projektowanie modelu danych dla konkretnej domeny** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="translating-data-model-content"></a>Tłumaczenie zawartości modelu danych

Zawartość modelu danych (etykiety i opisy) można przetłumaczyć na inne języki obsługiwane przez aplikację. Powody tłumaczenia zawartości modelu danych mogą być następujące:

- Podczas projektowania — w celu poprawy czytelności zawartości dla projektantów formatów mówiących w obcych językach, którzy używają modelu danych do mapowania danych składników formatu.
- Podczas wykonywania — aby zawartość była bardziej przyjazna dla użytkownika poprzez wyświetlanie monitów i pomocy dla parametrów ustawianych w czasie wykonywania, a także wyświetlanie skonfigurowanych komunikatów sprawdzania poprawności (błędów i ostrzeżeń) w języku preferowanym przez aktualnie zalogowanego użytkownika.

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Konfigurowanie mapowań modelu danych dla dokumentów wychodzących

Aplikacja ER zawiera projektanta mapowania modeli, który pozwala użytkownikom mapować zaprojektowane modele danych na konkretne źródła danych aplikacji. W oparciu o mapowanie dane zostaną zaimportowane w czasie wykonywania z wybranych źródeł danych do modelu danych. Następnie model danych jest używany jako abstrakcyjne źródło danych formatów modułu Raportowanie elektroniczne, które generują wychodzące dokumenty elektroniczne. 

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodniki po zadaniach **ER Definiowanie mapowania modelu i wybieranie źródeł danych** oraz **ER Mapowanie modelu danych na wybrane źródła danych** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Konfigurowanie mapowań modelu danych dla dokumentów przychodzących

Aplikacja ER zawiera projektanta mapowania modeli, który pozwala użytkownikom mapować zaprojektowane modele danych na konkretne miejsca docelowe. Na przykład modele danych mogą być mapowane na aktualizowalne składniki danych (tabele, jednostki danych i widoki). W oparciu o mapowanie dane będą aktualizowane w czasie wykonywania przy użyciu danych z modelu danych. Jako abstrakcyjny magazyn formatu raportowania elektronicznego model danych jest wypełniany danymi importowanymi z przychodzącego dokumentu elektronicznego. 

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Przechowywanie zaprojektowanego składnika modelu jako konfiguracji modelu

Narzędzie ER może przechowywać zaprojektowany model danych razem powiązanymi mapowaniami danych jako konfigurację modelu bieżącego wystąpienia. Ilustracja poniżej zawiera przykład tego rodzaju konfiguracji modelu danych (konfiguracji modelu płatności).

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Mapowanie modelu danych na wybrane źródła danych** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Budowanie formatu na podstawie modelu danych

Aplikacja ER zawiera projektanta formatów umożliwiającego tworzenie formatów dokumentów elektronicznych dla wybranej domeny biznesowej poprzez wybranie składnika modelu jako bazy. Ten sam projektant formatów pozwala zmapować utworzony format na mapowanie modelu danych wybranej domeny jako źródło danych. 

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Projektowanie formatu dla konkretnej domeny** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Tworzenie konfiguracji do generowania dokumentów elektronicznych w formacie arkusza OPENXML

Projektant formatów w aplikacji ER może służyć do redagowania dokumentu elektronicznego w formacie arkusza OPENXML. 

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Tworzenie konfiguracji dla raportów w formacie OPENXML** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**). W ramach kroku przewodnika po zadaniu importowania szablonu użyj plik programu Excel [Szablon raportu o płatnościach (SampleVendPaymWsReport.xlsx)](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx) jako szablonu.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Tworzenie konfiguracji do generowania dokumentów elektronicznych w formacie dokumentu programu Word

Projektant formatów w aplikacji ER może służyć do redagowania dokumentu elektronicznego w formacie dokumentu programu Word. Ilustracja poniżej zawiera przykład tego rodzaju formatu. Należy zauważyć, że ten format wykorzystuje istniejącą konfigurację ER, która została pierwotnie zaprojektowana do generowania danych wyjściowych raportu w formacie OPENXML.

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu ER Projektowanie konfiguracji do generowania raportów w formacie Microsoft WORD (część procesu biznesowego 7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)). W ramach kroku przewodnika po zadaniu importowania szablonu użyj następujących plików programu Word jako szablonów formatu ER:

- [Szablon raportu o płatnościach (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Ograniczony szablon raportu o płatnościach (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Tworzenie konfiguracji do importowania danych z przychodzących dokumentów elektronicznych

Projektant formatów w aplikacji ER może służyć do opisania dokumentu elektronicznego, którego planuje się używać do importowania danych w formacie XML lub tekstowym. Zaprojektowany format jest używany do analizowania składni przychodzących dokumentów. Projektant mapowania formatów w aplikacji ER może służyć do zdefiniowania powiązań elementów projektowanego formatu z modelem danych. 

Aby zapoznać się z tym scenariuszem w szczegółach, odtwórz przewodnik po zadaniu Tworzenie wymaganych konfiguracji ER do importowania danych z pliku zewnętrznego (część procesu biznesowego 7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)). Do odtworzenia tego przewodnika użyj następujących plików:

- [Konfiguracja modelu danych ER (1099model.xml)](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)
- [Konfiguracja formatu ER (1099format.xml)](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)
- [Przykładowy dokument przychodzący w formacie XML (1099entries.xml)](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)
- [Przykładowy skoroszyt do zarządzania danymi dokumentu przychodzącego (1099entries.xlsx)](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Przechowywanie zaprojektowanego składnika formatu w konfiguracji formatu

Aplikacja ER może przechowywać zaprojektowany format razem ze skonfigurowanymi mapowaniami danych jako konfigurację formatu bieżącego wystąpienia. Poprzednia ilustracja zawiera przykład tego typu konfiguracji formatu (**BACS (Wielka Brytania)**, która jest obiektem podrzędnym konfiguracji **Model płatności**). Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Projektowanie formatu dla konkretnej domeny** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="configuring-finance-to-start-to-use-a-created-format-internally"></a>Konfigurowanie programu Finance, aby zaczął używać utworzonego formatu wewnętrznie

Aplikacja możne skonfigurować w taki sposób, aby zaczął używać utworzonego formatu do generowania raportów elektronicznych. Odwołanie do utworzonej konfiguracji formatu powinno być zdefiniowane w ustawieniach konkretnej domeny. Aby na przykład zacząć używać konfiguracji formatu ER dla płatności elektronicznych do dostawcy w formacie BACS, odwołanie do konfiguracji formatu powinno się znajdować konkretnych metodach płatności.

Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Używanie formatu do generowania dokumentów elektronicznych dla płatności** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

## <a name="handling-er-components"></a>Obsługa składników raportowania elektronicznego

### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publikowanie składnika ER w portalu LCS w celu zaoferowania go na zewnątrz (tłumaczenie)

Właściciel utworzonego składnika (modelu lub formatu) może użyć aplikacji ER do opublikowania ukończonej wersji składnika w usłudze LCS. Potrzebne jest do tego repozytorium typu **Projekt usługi LCS** dla bieżącego dostawcy konfiguracji ER. Gdy stan ukończonej wersji składnika zmieni się z **UKOŃCZONA** na **UDOSTĘPNIONA**, ta wersja jest opublikowana w portalu LCS. Po opublikowaniu składnika w usłudze LCS jego właściciel staje się dostawcą usługi obsługującej ten składnik. Jeśli na przykład zadaniem składnika formatu jest generowanie dokumentów elektronicznych wymaganych prawem (np. zgodnie ze scenariuszem tłumaczenia), zakłada się, że format będzie na bieżąco aktualizowany o zmiany legislacyjne, a dostawca będzie publikował nowe wersje składnika w reakcji na każdy nowy wymóg prawny. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Przekazywanie konfiguracji do usługi Lifecycle Services** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importowanie składnika ER z usługi LCS na potrzeby użytku wewnętrznego

Narzędzie ER pozwala importować składniki ER z usługi LCS do bieżącego wystąpienia. Potrzebne jest do tego repozytorium typu **Projekt usługi LCS**. Po zaimportowaniu składnika ER z portalu LCS do bieżącego właściciel tego wystąpienia staje się konsumentem usługi dostarczanej przez właściciela (autora) zaimportowanego składnika. Na przykład jeśli składnik formatu ma generować określony dokument elektroniczny z aplikacji w formacie właściwym dla danego kraju/regionu (scenariusz tłumaczenia), zakłada się, że konsument usługi będzie w stanie otrzymywać wszelkie aktualizacje tego formatu, aby zachować zgodność z wymaganiami legislacyjnymi. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Importowanie konfiguracji z usługi Lifecycle Services** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Budowanie formatu na podstawie innego formatu (dostosowywanie)

Aplikacja ER pozwala utworzyć (pochodny) nowy składnik z bieżącej (bazowej) wersji składnika, którą zaimportowano z usługi LCS. Na przykład użytkownik chce utworzyć nowy format pochodny w celu zaimplementowania pewnych szczególnych wymagań dotyczących dokumentu elektronicznego (na przykład dodatkowe pole lub rozszerzony opis) dla scenariusza personalizacji. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Uaktualnianie formatu przez przyjęcie jej nowej wersji bazowej** (część procesu biznesowego **7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)**).

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Uaktualnianie formatu przez przyjęcie jej nowej wersji bazowej (zmiana bazy)

Narzędzie ER pozwala automatyczne powielać zmiany z najnowszej wersji składnika bazowego do aktualnej wersji roboczej składnika pochodnego. Ten proces jest nazywany *zmianą bazy*. Na przykład nowa zmiana przepisów, którą wprowadzono w najnowszej wersji składnika formatu zaimportowanego z usługi LCS, może być automatycznie scalana do dostosowanej wersji tego formatu dokumentu elektronicznego. Wszelkie zmiany, których nie można scalić automatycznie, są uznawane za konflikty. Te konflikty są wyświetlane do rozstrzygnięcia ręcznego w projektancie odpowiedniego składnika. Aby zapoznać się z tym scenariuszem w szczegółach, obejrzyj przewodnik po zadaniu **ER Uaktualnianie formatu przez przyjęcie jego nowej wersji bazowej** (część procesu biznesowego **7.5.5.3 Nabywanie/opracowywanie zmienionego składnika usługi/rozwiązania informatycznego (10683)**).

## <a name="list-of-er-configurations-that-have-been-released-in-finance"></a><a name="list-of-configurations"></a>Lista konfiguracji raportowania elektronicznego wydanych w aplikacji Finanse

Lista konfiguracji raportowania elektronicznego dla aplikacji Finanse jest aktualizowana w sposób ciągły. Otwórz [repozytorium globalne](er-download-configurations-global-repo.md), aby przejrzeć listę aktualnie obsługiwanych konfiguracji ER. Na skróconej karcie **Szczegóły wycofania** można przejrzeć informacje o konfiguracjach, które zostały wycofane lub które nie są już obsługiwane. 

![Zawartość repozytorium globalnego na stronie Repozytorium konfiguracji.](./media/er-overview-03.gif)

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Tworzenie konfiguracji raportowania elektronicznego (ER)](electronic-reporting-configuration.md)
- [Zarządzanie cyklem życia konfiguracji modułu Raportowanie elektroniczne (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
