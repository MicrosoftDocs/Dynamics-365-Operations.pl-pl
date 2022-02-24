---
title: Praca z predefiniowanymi ustawieniami stylów
description: W tym temacie opisano, jak pracować z predefiniowanymi ustawieniami stylów w konstruktorze witryn Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 250f2386cefee8bef45df66c4eef31b4e7fc2686
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415009"
---
# <a name="work-with-style-presets"></a>Praca z predefiniowanymi ustawieniami stylów

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak pracować z predefiniowanymi ustawieniami stylów w konstruktorze witryn Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Ustawienie predefiniowane stylu jest zapamiętanym zestawem wszystkich wartości stylów, które są tworzone w motywie danej witryny. Można go użyć do natychmiastowego zmiany wyglądu witryny za pomocą konstruktora witryn. Ustawienia predefiniowane stylów umożliwiają autorom modułu Commerce site Builder szybkie zmienianie, przeglądanie i uaktywnianie zbioru wartości stylów w ich oddziale, bez konieczności używania arkuszy stylów kaskadowych (CSS) lub wdrażania motywów. Style czcionek, style przycisków i kolory oddziału są typowymi przykładami zmiennych stylów, którymi można zarządzać za pomocą predefiniowanych ustawień stylu.

Zestaw zmiennych stylów, który jest dostępny w oddziale, jest określany na podstawie motywu i biblioteki modułów wdrożonej w dzierżawie oddziału. Zestaw w trybie online Software Development Kit (SDK) w Dynamics 365 Commerce umożliwia programistom implementowanie dowolnej (lub kilku) zmiennych stylów, które są wymagane dla danej kompozycji. Włączając więcej zmiennych stylów, deweloper motywu może umieścić ostateczne opcje dotyczące stylów witryny w ręce autorów konstruktora witryn. Dlatego też nie deweloperzy mogą aktualizować style witryny i wyświetlać ich podgląd za pomocą narzędzia zestaw narzędzi. Funkcja ta jest również przydatna dla każdego scenariusza, w którym bezpośrednie zmiany w motywie lub CSS mogą spowodować niepotrzebne obciążenie.

Motywy, w których włączono zmienne stylów autorskich, wymagają ustawienia domyślnego stylu. Mogą one opcjonalnie uwzględniać dodatkowe ustawienia wstępne w ramach wdrożonego pakietu kompozycji. Można na przykład wdrożyć motyw z jednym domyślnym stylem „jasny nowoczesny”. Może również zawierać dodatkowe opcje predefiniowanych stylów, w tym ustawienia domyślne, takie jak „ciemny współczesny”, „jasny vintage” lub „ciemny vintage” Te wbudowane ustawienia predefiniowane motywu są tworzone przez deweloperów i mogą być używane jako punkty wyjścia dla nowych projektów witryn.

W konstruktorze oddziałów autorzy mogą wybierać spośród wbudowanych predefiniowanych ustawień motywu lub tworzyć własne ustawienia predefiniowane i dostosowania za pomocą zmiennych stylów włączonych. Styl można wyświetlić w konstruktorze witryn przed jego aktywowaniem w witrynie na żywo. Po przejrzeniu zmian stylu autora, ustawienie predefiniowane stylu można ustawić na „aktywne” dla witryny na żywo.

## <a name="preview-a-style-preset"></a>Podgląd predefiniowanych ustawień stylu

Aby wyświetlić podgląd predefiniowanych ustawień stylu w witrynie w Konstruktorze witryn, należy wykonać następujące kroki.

1. W lewym okienku nawigacji dla witryny przejdź do **Ustawienia witryny \> Projekt**.
1. Na karcie **Predefiniowane ustawienia stylu** w górnej części edytora projektu, na liście **Dostępne ustawienia predefiniowane** wybierz ustawienie wstępne, a następnie wybierz opcję **Widok**, aby przejść do edytora ustawień domyślnych.

    Jeśli na liście **Dostępnych ustawień predefiniowanych** nie ma obecnie żadnych ustawień predefiniowanych, zapoznaj się z tematem [Tworzenie niestandardowego ustawienia predefiniowanego stylu](#create-a-custom-style-preset), aby uzyskać informacje na temat tworzenia predefiniowanych ustawień stylu.

    > [!NOTE]
    > Ustawienia predefiniowane, które zostały dołączone do motywu, są wskazywane przez **Wbudowaną** plakietkę. Te wbudowane ustawienia wstępne są tylko do odczytu. Aby skopiować wbudowane ustawienie wstępne jako nowy dostosowywany styl, wybierz przycisk wielokropka (**...**) dla ustawień predefiniowanych, a następnie wybierz opcję **Zapisz jako**.

1. Na pasku poleceń wybierz opcję **Podgląd**.
1. Wybierz adres URL z witryny, który ma być używany do wyświetlania podglądu predefiniowanych stylów, a następnie wybierz **OK**.
1. Wybierz odpowiedni dla danego kanału unikatowy wariant adresu URL, aby wyświetlić podgląd, wybierając nazwę wariantu. Zostanie otwarte nowe okno przeglądarki podglądu, w którym do określonej strony zostanie zastosowane wybrane ustawienie stylu.

> [!NOTE]
> Adres URL podglądu jest trwały i uwierzytelniony. Można więc skopiować, wkleić i wysłać go do innych uwierzytelnionych współpracowników w celu przejrzenia, zanim ustawisz ją na „aktywną” w witrynie na żywo. Adres URL podglądu jest również przydatny do sprawdzania stylów na różnych urządzeniach, w różnych przeglądarkach i na różnych ekranach.

> [!TIP]
> Podczas edycji predefiniowanych ustawień stylu może okazać się przydatne pozostawienie otwartego okna przeglądarki podglądu w osobnym oknie przeglądarki, dzięki czemu można szybko sprawdzić poprawność zmian. Po zapisaniu zmian w predefiniowanych polach odśwież otwarte okno przeglądarki, aby sprawdzić poprawność pracy użytkownika.

## <a name="create-a-custom-style-preset"></a>Tworzenie predefiniowanych ustawień stylu

Aby utworzyć niestandardowy styl predefiniowany w kreatorze witryn, wykonaj następujące kroki.

1. W lewym okienku nawigacji dla witryny przejdź do **Ustawienia witryny \> Projekt**.
1. Na karcie **Predefiniowane ustawienia stylu** u góry edytora projektu, na pasku poleceń, wybierz opcję **Nowe ustawienie wstępne**.
1. Wprowadź nazwę i opis nowego ustawienia wstępnego, a następnie wybierz **Zapisz**. Tworzone jest nowe predefiniowane ustawienie, które w punkcie początkowym używa wartości domyślnych motywu.

> [!NOTE]
> Można również utworzyć nowe ustawienie wstępne stylu niestandardowego na podstawie dowolnego istniejącego ustawienia wstępnego, wybierając przycisk wielokropka (**...**) dla tego ustawienia wstępnego, a następnie wybierając opcję **Zapisz jako**. Alternatywnie wybierz opcję **Zapisz jako** na pasku poleceń edytora ustawień predefiniowanych.

## <a name="modify-global-and-module-type-style-values"></a>Modyfikuj wartości w polach styl globalny i typ modułu

Niektóre zmienne stylu motywu są współużytkowane przez wiele typów modułów. Te zmienne stylu są określane mianem zmiennych stylu *globalnego*. Przykładem mogą być podstawowe kolory oddziałów, domyślne style czcionek oraz style przycisków. Ustawienie zmiennych globalnych może zmienić wygląd wielu różnych typów modułów.

Niektóre wartości stylów mogą być unikatowe dla danego typu modułu lub mogą być opcjonalnie zastąpione domyślną wartością globalną. Jeśli w motywie witryny zaimplementowano zmienne stylu typu modułu, autorzy konstruktora witryn mogą dostosowywać styl typu modułu niezależnie od ustawień globalnych. Zmienne typu modułu mogą rozszerzać lub zastępować zmienne stylu globalnego w motywie.

> [!NOTE]
> Hierarchia wartości stylów w witrynie zachowuje się w następujący sposób. Wartości stylu wyświetlane dalej po prawej stronie zastępują wartości stylów po ich lewej stronie.
>
> Wartości domyślne motywu \< Wartości stylu globalnego \< Wartości stylu typu modułu \< CSS zastąpienie

Aby zmienić styl globalny lub typ modułu w konstruktorze witryn, należy wykonać następujące kroki.

1. W lewym okienku nawigacji dla witryny przejdź do **Ustawienia witryny \> Projekt**.
1. Na karcie **Predefiniowane ustawienia stylu** u góry edytora projektu wybierz opcję **Widok** dla dowolnego stylu, aby przejść do edytora ustawień predefiniowanych.
1. Wybierz opcję **Podgląd**, a następnie postępuj zgodnie z procedurami wyboru adresu URL, aby otworzyć Podgląd w oknie w trybie pełnoekranowym. Pozostaw otwarte okno przeglądarki podglądu.
1. W edytorze predefiniowanych wybierz opcję **Edytuj** w prawym górnym rogu.
1. Aby zmienić niektóre globalne wartości stylów, należy skorzystać z formantów zmiennych stylów w edytorze.
1. U góry edytora na karcie **Moduły** na prawo od karty **Globalne** wybierz typ modułu, który musi mieć styl.
1. Aby zmienić niektóre wartości typu modułu, należy skorzystać z formantów stylów.
1. Gdy zechcesz wyświetlić podgląd zmian, wybierz opcję **Zapisz** na pasku poleceń.
1. Wróć do okna otwartej przeglądarki podglądu i odśwież. Podgląd okien w trybie pełnoekranowym jest przydatny do sprawdzania zmian stylów w różnych punktach przerwania widoku, w różnych przeglądarkach i na różnych platformach urządzeń.
1. Po zakończeniu i sprawdzeniu wszystkich zmian wybierz opcję **Zakończ edycję** w prawym górnym rogu edytora.

> [!NOTE]
> W przypadku edycji predefiniowanych ustawień stylów, które są aktualnie aktywne w witrynie, w edytorze zostanie wyświetlony niebieska plakietka **Aktywny**. Ten znaczek wskazuje, że bieżące ustawienie jest aktywne na stronie. W przypadku zmiany aktywnego ustawienia wstępnego wybierz opcję **Publikuj**, aby wypchnąć te zmiany w witrynie na żywo.

## <a name="make-a-new-style-preset-active-on-your-live-site"></a>Umożliwia ustawienie nowego wstępnie ustawionego stylu w aktywnej witrynie

Aby ustawić styl predefiniowany dla nowego aktywnego ustawienia w witrynie, wykonaj następujące kroki.

- Wybierz **Przycisk Ustawiaj jako aktywny** w jednym z następujących miejsc:

    - Pasek poleceń w edytorze predefiniowanych stylów
    - Menu wielokropka (**...**) dla dowolnego dostępnego ustawienia wstępnego w widoku głównym na karcie **Ustawienia predefiniowane stylu** w **Ustawienia witryny \> Projekt**

Wartości stylu ustawienia wstępnego są aktywne w całej publicznej witrynie sieci Web.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie logo](add-logo.md)

[Wybór motywu witryny](select-site-theme.md)

[Praca z plikami zastępowania CSS](css-override-files.md)

[Dodawanie ikony favicon](add-favicon.md)

[Dodawanie wiadomości powitalnej](add-welcome-message.md)

[Dodawanie powiadomienia o prawach autorskich](add-copyright-notice.md)

[Dodawanie języków do witryny](add-languages-to-site.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)
