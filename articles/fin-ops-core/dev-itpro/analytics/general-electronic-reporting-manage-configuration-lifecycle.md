---
title: Zarządzanie cyklem życia konfiguracji raportowania elektronicznego (ER)
description: W tym artykule opisano sposób zarządzania cyklem życia konfiguracji aparatu raportowania elektronicznego (ER) w aplikacji Dynamics 365 Finance.
author: kfend
ms.date: 07/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
ms.openlocfilehash: fe23d4cb2b293af466df2236b153974f95f636f8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271592"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Zarządzanie cyklem życia konfiguracji raportowania elektronicznego (ER)

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób zarządzania cyklem życia konfiguracji aparatu [raportowania elektronicznego](general-electronic-reporting.md) (ER) [w aplikacji](general-electronic-reporting.md#Configuration) Dynamics 365 Finance.

## <a name="overview"></a>Omówienie

Raportowanie elektroniczne (ER) jest aparatem, który obsługuje dokumenty elektroniczne wymagane ustawowo i specyficzne dla danego kraju. Zasadniczo moduł ER umożliwia wykonywanie następujących zadań dla pojedynczego dokumentu elektronicznego. Aby uzyskać więcej szczegółowych informacji, zobacz [Omówienie raportowania elektronicznego (RE)](general-electronic-reporting.md).

- Projektowanie szablonu dokumentu elektronicznego:

    - identyfikacja wymaganych źródeł danych, które mogą być prezentowane w dokumencie:

        - Bazowe dane, takie jak tabele danych, jednostki danych i klasy.
        - Właściwości specyficzne dla procesów, takie jak data i godzina wykonania oraz strefa czasowa.
        - Parametry wejściowe użytkownika, określane przez użytkownika podczas wykonywania.

    - Definiowanie wymaganych elementów dokumentu oraz ich topologii w celu określenia formatu finalnego dokumentu.
    - Konfigurowanie żądanego przepływu danych z wybranych źródeł danych do zdefiniowanych elementów dokumentu (za pomocą powiązań źródeł danych ze składnikami formatu dokumentu) i określanie logiki kontroli procesu.

- Udostępnianie szablonu pozwalające używać go w innych wystąpieniach:

    - Przekształcanie szablonu dokumentu utworzonego na konfigurację raportowania elektronicznego, a następnie eksportowanie konfiguracji z bieżącej aplikacji jako pakietu XML, który może być przechowywany lokalnie lub w usłudze Lifecycle Services (LCS).
    - Przekształcanie konfiguracji ER na szablon dokumentu systemu aplikacji.
    - Import pakietu XML przechowywanego lokalnie lub w usłudze LCS do bieżącego wystąpienia.

- Dostosowywanie szablonu dokumentu elektronicznego:

    - Pobieranie szablonu z usługi LCS do bieżącego wystąpienia jako konfiguracji ER.
    - Projektowanie niestandardowej wersji konfiguracji ER z zachowaniem odniesienia do wersji bazowej.

- Integracja szablonu z określonym procesem biznesowym w celu udostępnienia go w aplikacji.

    - Konfigurowanie ustawień aplikacji, tak aby zaczął używać konfiguracji ER, poprzez utworzenie odwołania do tej konfiguracji w parametrze związanym z procesem. Na przykład utworzenie odwołania do konfiguracji ER w określonej metodzie płatności dla rozrachunków z dostawcami w celu generowania komunikatu płatności elektronicznej do przetwarzania faktur.

- Używanie szablonu w określonym procesie biznesowym:

    - Uruchamianie konfiguracji ER w określonym procesie biznesowym (na przykład w celu generowania komunikatu płatności elektronicznej do przetwarzania faktur po wybraniu metody płatności odwołującej się do konfiguracji ER).

## <a name="concepts"></a>Koncepcje
Następujące role i pokrewne działania są powiązane z cyklem życia konfiguracji ER:

| Rola                                       | Działania                                                      | opis |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| Konsultant funkcjonalny raportowania elektronicznego | Tworzenie i zarządzanie składnikami ER (modelami i formatami).           | Pracownik biznesowy, który projektuje modele danych ER specyficzne dla domeny, projektuje wymagane szablony dokumentów elektronicznych i tworzy im odpowiednie powiązania. |
| Deweloper raportowania elektronicznego             | Tworzenie i zarządzanie mapowaniami modelu danych.                          | Specjalista, który wybiera żądane źródła danych Finance i wiąże je z modelami danych ER specyficznymi dla domeny. |
| Kierownik ds. księgowania                      | Konfigurowanie ustawień procesów odwołujących się do artefaktów ER. | Na przykład rola **Kierownik ds. księgowania**, która pozwala używać ustawień konfiguracji ER w określonej metodzie płatności w module rozrachunków z dostawcami w celu generowania komunikatu płatności elektronicznej do przetwarzania faktur. |
| Pracownik ds. płatności rozrachunków z dostawcami            | Używanie artefaktów ER w określonym procesie biznesowym.                | Na przykład rola **Pracownik ds. płatności rozrachunków z dostawcami** umożliwiająca generowanie komunikatów płatności elektronicznych do przetwarzania faktur na podstawie formatu ER skonfigurowanego dla określonej metody płatności. |

## <a name="er-configuration-development-lifecycle"></a>Cykl życia tworzenia konfiguracji ER
Zalecamy projektować konfiguracje raportowania elektronicznego w środowisku programistycznym jako odrębnym wystąpieniu aplikacji finansowych i operacyjnych z następujących przyczyn:

- Użytkownicy posiadający rolę **Deweloper raportowania elektronicznego** lub **Konsultant funkcjonalny raportowania elektronicznego** mogą edytować konfiguracje i uruchamiać je do celów testowych. Ten scenariusz może powodować wywoływanie metod klas i tabel mogących uszkadzać dane firmy i spowalniać działanie wystąpienia.
- Wywołania metod klas i tabel jako źródeł danych ER konfiguracji ER nie są ograniczone przez punkty wejścia ani logowanie do zasobów firmy. Dlatego poufne dane firmy mogą być dostępne dla użytkowników posiadających rolę **Deweloper raportowania elektronicznego** lub **Konsultant funkcjonalny raportowania elektronicznego**.

Konfiguracje ER zaprojektowane w środowisku programistycznym można [przesłać](#data-persistence-consideration) do środowiska testowego w celu oceny konfiguracji (właściwa integracja procesów, poprawność wyników, wydajność) oraz sprawdzenia jakości (właściwe prawa dostępu według ról, podział obowiązków itd.). Do tego celu mogą służyć funkcje wymieniania się konfiguracją ER. Sprawdzone konfiguracje ER można przesłać do LCS, aby udostępnić je subskrybentom usług lub [zaimportować](#data-persistence-consideration) do środowiska produkcyjnego do użytku wewnętrznego.

![Cykl życia konfiguracji ER.](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a>Uwzględnianie utrwalania danych

Do wystąpienia Finance można indywidualnie [importować](tasks/er-import-configuration-lifecycle-services.md) różne [wersje](general-electronic-reporting.md#component-versioning) [konfiguracji](general-electronic-reporting.md#Configuration) serwera ER. Po zaimportowaniu nowej wersji konfiguracji ER system kontroluje zawartość wersji roboczej tej konfiguracji:

- Gdy zaimportowana wersja jest niższa niż najwyższa wersja tej konfiguracji w bieżącej instancji programu Finance, zawartość wersji roboczej tej konfiguracji pozostaje niezmieniona.
- Gdy zaimportowana wersja jest nowsza niż jakakolwiek inna wersja tej konfiguracji w bieżącej instancji programu Finance, zawartość zaimportowanej wersji jest kopiowana do wersji roboczej tej konfiguracji, aby umożliwić dalsze edytowanie ostatniej ukończonej wersji.

Jeśli ta konfiguracja należy do aktualnie aktywowanego [dostawcy](general-electronic-reporting.md#Provider) konfiguracji, wersja robocza tej konfiguracji jest widoczna na skróconej karcie **Wersje** strony **Konfiguracje** (**Administrowanie organizacją** > **Raportowanie elektroniczne** > **Konfiguracje**). Można wybrać wersję roboczą konfiguracji i [zmodyfikować](er-quick-start2-customize-report.md#ConfigureDerivedFormat) jej zawartość za pomocą odpowiedniego konstruktora ER. Po edycji wersji roboczej konfiguracji ER jej zawartość nie jest już zgodna z zawartością najwyższej wersji tej konfiguracji w bieżącej instancji Finance. Aby zapobiec utracie zmian, system wyświetla błąd informujący, że import nie może być kontynuowany, ponieważ wersja tej konfiguracji jest nowsza niż najwyższa wersja tej konfiguracji w bieżącej instancji Finance. W takim przypadku, na przykład przy konfiguracji formatu **X**, bład **Format wersji „X” nie został zakończony** jest wyświetlany.

Aby cofnąć zmiany wprowadzone w wersji roboczej, wybierz najwyższą ukończoną lub udostępnioną wersję konfiguracji ER w części Finance na skróconej karcie **Wersje**, a następnie wybierz opcję **Pobierz tę wersję**. Zawartość wybranej wersji jest kopiowana do wersji roboczej.

## <a name="applicability-consideration"></a>Uwzględnienie możliwości zastosowania

Podczas projektowania nowej wersji konfiguracji ER można zdefiniować jej [zależność](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md) od innych składników oprogramowania. Ten krok jest uważany za warunek wstępny do sterowania pobieraniem wersji tej konfiguracji z repozytorium ER lub zewnętrznego pliku XML oraz do jakiegokolwiek dalszego korzystania z tej wersji. Przy próbie zaimportowania nowej wersji konfiguracji ER system wykorzystuje skonfigurowane warunki wstępne do kontroli, czy dana wersja może zostać zaimportowana.

W niektórych przypadkach użytkownik może wymagać, aby system ignorował skonfigurowane warunki wstępne podczas importowania nowych wersji konfiguracji ER. Aby system zignorował wymagania wstępne podczas importowania, wykonaj następujące kroki.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. Ustaw opcję **Pomiń aktualizacje produktu i wersję wstępną podczas importowania** na **Tak**.

    > [!NOTE]
    > Ten parametr jest właściwy dla użytkownika i właściwy dla firmy.

## <a name="dependencies-on-other-components"></a>Zależności od innych składników

Konfiguracje ER można skonfigurować jako [zależne](er-download-configurations-global-repo.md#import-filtered-configurations) od innych konfiguracji. Na przykład można [importować](er-download-configurations-global-repo.md) konfigurację ER [modelu danych](er-overview-components.md#data-model-component) z globalnego repozytorium do Twoje [Microsoft Regulatory Configuration Services (RCS)](../../../finance/localizations/rcs-overview.md) lub Dynamics 365 Finance, a następnie utwórz nowy [format](er-overview-components.md#format-component) konfiguracja, która jest [pochodną](er-quick-start2-customize-report.md#DeriveProvidedFormat) z zaimportowanej konfiguracji modelu danych ER. Pochodna konfiguracja formatu ER będzie zależna od konfiguracji podstawowego modelu danych ER.

![Pochodna konfiguracja formatu ER na stronie Konfiguracje.](./media/ger-configuration-lifecycle-img1.png)

Po zakończeniu projektowania formatu możesz zmienić stan początkowe [wersji](general-electronic-reporting.md#component-versioning) konfiguracji formatu raportowania elektronicznego z **Wersja robocza** na **Zakończono**. Można następnie udostępnić ukończoną wersję konfiguracji formatu ER, [publikując](../../../finance/localizations/rcs-global-repo-upload.md) ją w repozytorium globalnym. Następnie można uzyskać dostęp do repozytorium globalnego z dowolnego wystąpienia usługi RCS lub chmury Finance. Następnie można zaimportować dowolną wersję konfiguracji ER, która ma zastosowanie do aplikacji z repozytorium globalnym do tej aplikacji.

![Opublikowana konfiguracja formatu ER na stronie repozytorium konfiguracji.](./media/ger-configuration-lifecycle-img2.png)

Na podstawie zależności konfiguracji po wybraniu konfiguracji formatu raportowania elektronicznego w repozytorium globalnym w celu zaimportowania go do nowo wdrożonego wystąpienia RCS lub Finance podstawowa konfiguracja modelu danych raportowania elektronicznego jest automatycznie znajdowana w repozytorium globalnym i importowana wraz z wybranym formatem raportowania elektronicznego konfiguracja jako konfiguracja podstawowa.

Można także wyeksportować wersję konfiguracji formatu ER z bieżącego wystąpienia serwera RCS lub Finance i zapisać ją lokalnie jako plik XML.

![Eksportowanie wersji konfiguracji formatu ER jako XML na stronie Konfiguracja.](./media/ger-configuration-lifecycle-img3.png)

W wersjach Finanse **przed wersją 10.0.29** podczas próby zaimportowania wersji konfiguracji formatu ER z tego pliku XML lub z dowolnego repozytorium innego niż repozytorium globalne do nowo wdrożonego wystąpienia pliku RCS lub finansowego, które nie zawiera jeszcze żadnych konfiguracji ER, zostanie wygenerowany następujący wyjątek, aby poinformować, że nie można uzyskać konfiguracji podstawowej:

> Pozostały nierozpoznane odwołania<br>
Nie można ustanowić odwołania obiektu „\<imported configuration name\>” do obiektu „Base” (\<globally unique identifier of the missed base configuration\>,\<version of the missed base configuration\>)

![Importowanie wersji konfiguracji formatu ER na stronie repozytorium konfiguracji.](./media/ger-configuration-lifecycle-img4.gif)

W wersji **10.0.29** i późniejszej przy próbie importu tej samej konfiguracji, jeśli nie można odnaleźć konfiguracji podstawowej w bieżącym wystąpieniu aplikacji lub w repozytorium źródłowym, które jest aktualnie stosowane (jeśli ma zastosowanie), narzędzia ER będą automatycznie próbowały znaleźć nazwę brakującej konfiguracji podstawowej w pamięci podręcznej repozytorium globalnego. Następnie w tekście zgłaszanego wyjątku zostanie przedstawiana nazwa i unikatowy identyfikator globalnie unikatowy (GUID) brakującej konfiguracji podstawowej.

> Pozostały nierozpoznane odwołania<br>
Nie można ustanowić odwołania obiektu „\<imported configuration name\>” do obiektu „Base” (\<name of the missed base configuration\> \<globally unique identifier of the missed base configuration\>,\<version of the missed base configuration\>)

![Wyjątek na stronie Repozytorium konfiguracji, gdy nie można odnaleźć konfiguracji podstawowej.](./media/ger-configuration-lifecycle-img5.png)

Podaną nazwę można użyć w celu znalezienia konfiguracji podstawowej, a następnie jej ręcznego zaimportowania.

> [!NOTE]
> Ta nowa opcja działa tylko wtedy, gdy co najmniej jeden użytkownik jest już zalogowany do repozytorium globalnym za pomocą strony [repozytoriów konfiguracji](er-download-configurations-global-repo.md#open-configurations-repository) lub jednego z pól [wyszukiwania](er-extended-format-lookup.md) repozytorium globalnego w bieżącym wystąpieniu finansów i gdy zawartość repozytorium globalnego została buforowana.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)

[Definiowanie zależności konfiguracji raportowania elektronicznego od innych składników](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

