---
title: Zarządzanie cyklem życia konfiguracji modułu Raportowanie elektroniczne (ER)
description: W tym temacie opisano sposób zarządzania cyklem życia konfiguracji aparatu raportowania elektronicznego (ER) w Dynamics 365 Finance.
author: NickSelin
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52aba53b5323a9c6c4331cd8de7e932bb9c3547e
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893208"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Zarządzanie cyklem życia konfiguracji raportowania elektronicznego (ER)

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób zarządzania cyklem życia konfiguracji aparatu raportowania elektronicznego (ER) w Dynamics 365 Finance.

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
Zalecamy projektować konfiguracje raportowania elektronicznego w środowisku programistycznym jako odrębnym wystąpieniu systemu Finance and Operations z następujących przyczyn:

- Użytkownicy posiadający rolę **Deweloper raportowania elektronicznego** lub **Konsultant funkcjonalny raportowania elektronicznego** mogą edytować konfiguracje i uruchamiać je do celów testowych. Ten scenariusz może powodować wywoływanie metod klas i tabel mogących uszkadzać dane firmy i spowalniać działanie wystąpienia.
- Wywołania metod klas i tabel jako źródeł danych ER konfiguracji ER nie są ograniczone przez punkty wejścia ani logowanie do zasobów firmy. Dlatego poufne dane firmy mogą być dostępne dla użytkowników posiadających rolę **Deweloper raportowania elektronicznego** lub **Konsultant funkcjonalny raportowania elektronicznego**.

Konfiguracje ER zaprojektowane w środowisku programistycznym można [przesłać](#data-persistence-consideration) do środowiska testowego w celu oceny konfiguracji (właściwa integracja procesów, poprawność wyników, wydajność) oraz sprawdzenia jakości (właściwe prawa dostępu według ról, podział obowiązków itd.). Do tego celu mogą służyć funkcje wymieniania się konfiguracją ER. Sprawdzone konfiguracje ER można przesłać do LCS, aby udostępnić je subskrybentom usług lub [zaimportować](#data-persistence-consideration) do środowiska produkcyjnego do użytku wewnętrznego.

![Cykl życia konfiguracji ER](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a><a name="data-persistence-consideration" />Uwzględnianie utrwalania danych

Do wystąpienia Finance można indywidualnie [importować](tasks/er-import-configuration-lifecycle-services.md) różne [wersje](general-electronic-reporting.md#component-versioning) [konfiguracji](general-electronic-reporting.md#Configuration) serwera ER. Po zaimportowaniu nowej wersji konfiguracji ER system kontroluje zawartość wersji roboczej tej konfiguracji:

   - Gdy zaimportowana wersja jest niższa niż najwyższa wersja tej konfiguracji w bieżącej instancji programu Finance, zawartość wersji roboczej tej konfiguracji pozostaje niezmieniona.
   - Gdy zaimportowana wersja jest nowsza niż jakakolwiek inna wersja tej konfiguracji w bieżącej instancji programu Finance, zawartość zaimportowanej wersji jest kopiowana do wersji roboczej tej konfiguracji, aby umożliwić dalsze edytowanie ostatniej ukończonej wersji.

Jeśli ta konfiguracja należy do aktualnie aktywowanego [dostawcy](general-electronic-reporting.md#Provider) konfiguracji, wersja robocza tej konfiguracji jest widoczna na skróconej karcie **Wersje** strony **Konfiguracje** (**Administrowanie organizacją** > **Raportowanie elektroniczne** > **Konfiguracje**). Można wybrać wersję roboczą konfiguracji i [zmodyfikować](er-quick-start2-customize-report.md#ConfigureDerivedFormat) jej zawartość za pomocą odpowiedniego konstruktora ER. Po edycji wersji roboczej konfiguracji ER jej zawartość nie jest już zgodna z zawartością najwyższej wersji tej konfiguracji w bieżącej instancji Finance. Aby zapobiec utracie zmian, system wyświetla błąd informujący, że import nie może być kontynuowany, ponieważ wersja tej konfiguracji jest nowsza niż najwyższa wersja tej konfiguracji w bieżącej instancji Finance. W takim przypadku, na przykład przy konfiguracji formatu **X**, bład **Format wersji „X” nie został zakończony** jest wyświetlany.

Aby cofnąć zmiany wprowadzone w wersji roboczej, wybierz najwyższą ukończoną lub udostępnioną wersję konfiguracji ER w części Finance na skróconej karcie **Wersje**, a następnie wybierz opcję **Pobierz tę wersję**. Zawartość wybranej wersji jest kopiowana do wersji roboczej.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
