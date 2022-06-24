---
title: Użyj źródeł danych USER INPUT PARAMETER, aby określić parametry dla raportu
description: Ten artykuł wyjaśnia, jak używać źródeł danych USER INPUT PARAMETER do określania parametrów dla raportów, które generujesz.
author: NickSelin
ms.date: 04/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.27
ms.openlocfilehash: 62b7a8173416a1d36a2985823d186a7a0e6a7e60
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872980"
---
# <a name="use-user-input-parameter-data-sources-to-specify-parameters-for-a-report"></a>Użyj źródeł danych USER INPUT PARAMETER, aby określić parametry dla raportu

[!include[banner](../includes/banner.md)]

Kiedy projektujesz komponenty [Raportowanie elektroniczne](general-electronic-reporting.md) (ER) [mapowanie modelu](er-overview-components.md#model-mapping-component) i [format](er-overview-components.md#format-component) ER, możesz użyć źródeł danych typu *USER INPUT PARAMETER*, aby uzyskać wymagane wartości, które mogą być określone w polach wprowadzania danych w oknie dialogowym w czasie działania, zanim rozpocznie się wykonywanie formatu ER. Ten artykuł opisuje źródła danych *USER INPUT PARAMETER*, które są obecnie obsługiwane.

## <a name="mandatory-properties"></a><a name="mandatory-properties"></a>Właściwości obowiązkowe

Musisz określić następujące właściwości dla źródeł danych każdego typu *USER INPUT PARAMETER*:

- W polu **Nazwa** wpisz wewnętrzną nazwę źródła danych. Możesz używać tej nazwy w innych [wyrażeniach](er-formula-language.md) i wiązaniach skonfigurowanego odwzorowania modelu lub komponentu formatu.

## <a name="optional-properties"></a><a name="optional-properties"></a>Właściwości opcjonalne

Dla źródeł danych typu *USER INPUT PARAMETER* możesz opcjonalnie określić następujące właściwości:

- W polu **etykieta** określ etykietę, która będzie używana dla powiązanego pola wprowadzania danych w oknie dialogowym w czasie rzeczywistym. Możesz dodać różne teksty etykiet dla różnych kodów językowych, aktywując pole **etykieta**, a następnie wybierając **tłumaczenie**.
- W polu **Pomoc** określ tekst pomocy, który jest wyświetlany w czasie projektowania na dole strony **Projektanta formatu** lub strony **Projektanta odwzorowania modelu**, gdy wybrane jest edytowalne źródło danych typu *USER INPUT PARAMETER*. Tekst ten może zawierać dodatkowe informacje o źródle danych, które pomogą użytkownikom skonfigurować format edytowalny lub komponent odwzorowujący model. Możesz dodać różne teksty pomocy dla różnych kodów językowych, wybierając **Tłumaczenie**.

    > [!NOTE]
    > Przycisk **Tłumacz**, którego możesz użyć, aby dodać [etykiety i tekst specyficzne dla danego języka](er-design-multilingual-reports.md#format-component), staje się dostępny dopiero po dodaniu źródła danych, zapisaniu zmian, a następnie ponownym otwarciu źródła danych do edycji.

- W polu **Tylko do odczytu** skonfiguruj wyrażenie, które zwraca *[wartość logiczną](er-formula-supported-data-types-primitive.md#boolean)*.

    - Jeśli skonfigurowane wyrażenie zwróci wartość **True** w czasie wykonywania, powiązane pole wprowadzania danych zostanie wygaszone w oknie dialogowym i nie można zmienić jego wartości.
    - Jeśli skonfigurowane wyrażenie zwróci wartość **False** w czasie wykonywania lub jeśli nie jest skonfigurowane żadne wyrażenie, odpowiednie pole wprowadzania danych jest dostępne w oknie dialogowym i możesz zmienić jego wartość.

- W polu **Wartość domyślna** skonfiguruj wyrażenie, do których zwracana jest wartość typu parametru, do których ma być odwołanie. Ta wartość może być użyta do wypełnienia domyślnej wartości powiązanego pola wprowadzania danych w oknie dialogowym w czasie działania.

    Gdy uruchamiasz format ER, wartość wprowadzona w powiązanym polu wprowadzania danych w oknie dialogowym podczas uruchamiania jest zapisywana w pamięci jako poprzednio używana wartość. Poprzednio używane wartości są zapisywane indywidualnie dla każdego pola, bieżącego formatu ER, bieżącego użytkownika i bieżącej organizacji (firmy).

    - Ustaw opcję **Zawsze przywracana jest wartość domyślna** na **Tak**, jeśli wartość zwracana przez wyrażenie **Wartość domyślna** ma być zawsze używana jako wartość domyślna, niezależnie od poprzednio używanej wartości.
    - Ustaw opcję **Zawsze przywracana jest wartość domyślna** na **Nie**, jeśli wartość zwracana przez wyrażenie **Wartość domyślna** powinna być używana jako wartość domyślna tylko wtedy, gdy brakuje poprzednio używanej wartości.

    > [!NOTE]
    > Jeśli ustawisz opcję **Zawsze przywracaj wartość domyślną** na **Tak**, w polu **Wartość domyślna** musi być skonfigurowane wyrażenie.

- Jeśli ustawisz opcję **Zezwalaj na wielokrotny wybór** na **Tak**, będziesz mógł wybrać wiele wartości dla skonfigurowanego parametru w czasie działania. Jeśli zostanie ustawiona wartość **Nie**, można wybrać tylko jedną wartość.

    > [!NOTE]
    > Ta opcja nie ma zastosowania do wszystkich typów *USER INPUT PARAMETER*. W czasie projektowania jest rzucany wyjątek informujący użytkownika, że skonfigurowany parametr wejściowy użytkownika nie obsługuje wielokrotnego wyboru i że można wybrać lub wprowadzić tylko jedną wartość.
    >
    > Jeśli ustawiłeś opcję **Zezwalaj na wielokrotny wybór** na **Tak** i podałeś wyrażenie w polu **Wartość domyślna**, to wyrażenie to może być użyte do ustawienia tylko jednej wartości domyślnej.

- Wybierz opcję **Widoczność edycji**, aby określić, czy skonfigurowany parametr ma być widoczny w oknie dialogowym w czasie pracy.

    > [!NOTE]
    > Domyślna widoczność źródeł danych typu *USER INPUT PARAMETER* zależy od składnika ER, który je przechowuje.
    >
    > - Jeśli źródło danych jest skonfigurowane w składniku formatu, jest ono domyślnie widoczne.
    > - Jeśli źródło danych jest skonfigurowane w składniku odwzorowującym model, jest ono widoczne tylko wtedy, gdy wartość źródła danych ma wpływ na wynik działania składnika ER. Na przykład, dodałeś źródło danych, ale nie użyłeś go w wyrażeniach i wiązaniach aktualnego komponentu odwzorowującego model. W tym przypadku domyślnie odpowiednie pole do wprowadzania danych nie będzie wyświetlane w oknie dialogowym w czasie działania. 

    Na stronie **Projektant formuł**, w polu **Formuła**, skonfiguruj wyrażenie, które zwraca *wartość logiczna*.

    - Jeśli skonfigurowane wyrażenie zwróci wartość **True** w czasie wykonywania lub jeśli nie jest skonfigurowane żadne wyrażenie, odpowiednie pole wprowadzania danych jest widoczne w oknie dialogowym w czasie działania.
    - Jeśli skonfigurowane wyrażenie zwraca wartość **False**, powiązane pole wprowadzania danych jest ukryte w oknie dialogowym w czasie wykonywania. Gdy jest ono wywoływane przez inne wyrażenia w czasie działania, zwraca wartość domyślną, poprzednio używaną wartość lub wartość domyślną dla bieżącego typu danych, w zależności od innych ustawień.

## <a name="type-specific-properties"></a>Właściwości specyficzne dla typu

### <a name="application-dependent-user-input-parameter"></a>Parametr wejściowy użytkownika zależny od aplikacji

Użyj źródła danych typu **Ogólne** \> **Parametr wejściowy użytkownika**, aby uzyskać wymaganą wartość lub wartości typu danych, który jest określony dla bieżącej instancji aplikacji Microsoft Dynamics 365 Finance. Kiedy dodajesz źródło danych tego typu do komponentu ER, określ następujące właściwości:

- W polu **Nazwa typu danych operacyjnych (EDT, enum)** wybierz aplikacyjny [rozszerzony typ danych (EDT)](../extensibility/extensible-edts.md) lub wyliczenie aplikacyjne.

> [!NOTE]
> Zalecamy, abyś przejrzał wyrażenia skonfigurowane w polach **Tylko do odczytu** i **Wartość domyślna**, gdy zmieniasz **nazwę typu danych operacji (EDT, enum)** w edytowalnym źródle danych tego typu *USER INPUT PARAMETER*.

Poniższa ilustracja pokazuje właściwości źródła danych `$TaxRegNum`, które zostało skonfigurowane w konfiguracji **Instat XML (DE)** w formacie ER. To źródło danych jest skonfigurowane w taki sposób, że używa EDT *Opis*, aby w czasie działania oferowało pole wprowadzania danych **Numer Rejestracji Podatkowej** w oknie dialogowym.

![Właściwości źródła danych typu USER INPUT PARAMETER w oknie dialogowym na stronie Projektanta formatu.](./media/er-user-input-parameter-data-sources-01.png)

Poniższa ilustracja przedstawia okno dialogowe, które jest wyświetlane podczas uruchamiania konfiguracji **Instat XML (DE)** w formacie ER w celu [wygenerowania](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md) deklaracji Intrastat. Zwróć uwagę, że skonfigurowane pole **numeru rejestracji podatkowej** jest dostępne do wprowadzania danych.

![Okno dialogowe raportu Intrastat o uruchomionym formacie raportu ER na stronie Intrastat.](./media/er-user-input-parameter-data-sources-02.png)

### <a name="data-model-enumeration-user-input-parameter"></a>Parametr wejściowy użytkownika wyliczenia modeli danych

Użyj źródła danych typu **Model danych** \> **Parametr wejściowy użytkownika**, aby uzyskać wymaganą wartość lub wartości pojedynczego modelu danych [wyliczenie](er-formula-supported-data-types-primitive.md#enumeration). Kiedy dodajesz źródło danych tego typu do komponentu ER, określ następujące właściwości:

- W polu **Model** określ odwołanie do podstawowego modelu danych.
- W polu **Wyliczenie modeli** określ odwołanie do wyliczenia modelu danych, do którego ma być odwołanie.
- W polu **Wersja** wybierz numer rewizji składnika modelu danych ER, który zawiera wyliczenie modelu, do którego się odwołujesz.

    > [!TIP]
    > W czasie projektowania możesz pozostawić pole **Wersja** puste, aby uzyskać dostęp do listy wyliczeń dla komponentu modelu danych, który znajduje się w wersji roboczej odpowiedniej konfiguracji modelu danych ER. W ten sposób możesz jednocześnie edytować wersję roboczą komponentu odwzorowania lub formatu modelu oraz wersję roboczą komponentu modelu danych bazowych.
    >
    > Pamiętaj jednak, że pole **Wersja** może pozostać puste tylko w wersji roboczej komponentu odwzorowującego model lub formatu. Kiedy zmieniasz status odwzorowania modelu ER lub konfiguracji formatu z **Wersja robocza** na **Zakończono**, to pole jest automatycznie wypełniane najwyższym numerem rewizji modelu, jaki jest dostępny w bieżącej instancji Finansów. Jeśli wprowadzasz nowe wyliczenie lub nową wartość wyliczenia w wersji roboczej swojego bazowego modelu danych i odwołujesz się do niego w edytowalnym komponencie odwzorowania lub formatu modelu, zakończ konfigurację wersji roboczej bazowego modelu danych przed zakończeniem konfiguracji wersji roboczej odwzorowania lub formatu modelu ER. W przeciwnym razie, gdy zmienisz status odwzorowania modelu lub konfiguracji formatu z **Wersja robocza** na **Zakończono**, zostanie podany wyjątek "Nie znaleziono ścieżki". Komunikat poinformuje cię, że w podstawowym modelu danych brakuje wyliczenia lub wartości wyliczeniowej, do której się odwołujemy.

Poniższa ilustracja pokazuje właściwości źródła danych `$ReportDirection`, które zostało skonfigurowane w konfiguracji **Instat XML (DE) Contoso** w formacie ER. Konfiguracja **Instat XML (DE) Contoso** została [wyprowadzona](general-electronic-reporting.md#Configuration) z konfiguracji **Instat XML (DE)**. To źródło danych jest skonfigurowane tak, by używało wyliczenia modelu *ReportDirection* w celu zaoferowania odpowiedniego pola wyszukiwania w oknie dialogowym w trybie uruchomieniowym.

![Właściwości źródła danych typu USER INPUT PARAMETER w oknie dialogowym na stronie Projektanta formatu.](./media/er-user-input-parameter-data-sources-03.png)

### <a name="format-enumeration-user-input-parameter"></a>Parametr wejściowy użytkownika wyliczenia formatów

Użyj źródła danych typu **Format wyliczenia** \> **Wyliczeniowy parametr wejściowy użytkownika**, aby uzyskać wymaganą wartość lub wartości pojedynczego wyliczenia formatu. Kiedy dodajesz źródło danych tego typu do komponentu ER, określ następujące właściwości:

- W polu **Format wyliczenia** podaj wyliczenie formatu, który można edytować.

> [!NOTE]
> Źródła danych tego typu mogą być konfigurowane tylko w ramach komponentu formatu edytowalnego.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Inicjowanie wartości źródła danych typu USER INPUT PARAMETER z kodu źródłowego](er-initiate-uip-data-source-value-from-source-code.md)
