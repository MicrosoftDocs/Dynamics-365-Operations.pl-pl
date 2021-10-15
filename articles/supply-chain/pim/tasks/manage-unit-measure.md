---
title: Zarządzanie jednostkami miary
description: W tym temacie opisano sposób definiowania jednostki miary, wprowadzania tłumaczenia i opisu jednostki oraz określania reguł konwersji względem powiązanych jednostek.
author: t-benebo
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e13897396810507bb4b2cbb415b873eb3dd7f4e8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565527"
---
# <a name="manage-units-of-measure"></a>Zarządzanie jednostkami miary

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób definiowania jednostki miary, wprowadzania tłumaczenia i opisu jednostki oraz określania reguł konwersji względem powiązanych jednostek.

## <a name="open-the-units-page"></a>Otwieranie strony Jednostki

Aby utworzyć jednostki miary dostępne w systemie i pracować z nich, przejdź do **Administrowanie organizacją \> Konfiguracja \> Jednostki \> Jednostki**.

Pozostałe sekcje tego tematu zawierają opis tego, co można zrobić na stronie **Jednostki**.

## <a name="create-standard-units-and-conversions"></a>Tworzenie standardowych jednostek i konwersji

Jeśli w systemie nie są jeszcze najczęściej używane jednostki miary w systemie metrycznym i/lub amerykańskim systemie niestandardowym (USCS), kreator konfiguracji jednostek pomoże szybko skonfigurować podstawowe definicje jednostek i konwersje. Aby wykonać kreator, wybierz opcję **Kreator tworzenia jednostek** w okienku akcji, a następnie postępuj zgodnie z instrukcjami wyświetlanymi na ekranie.

## <a name="create-or-edit-a-unit-of-measure"></a>Tworzenie lub edytowanie jednostki miary

Aby utworzyć lub edytować jednostkę miary, wykonaj poniższe kroki.

1. Wykonaj jeden z następujących kroków:

    - Aby zmodyfikować istniejącą jednostkę, zaznacz ją w okienku listy.
    - Aby utworzyć nową jednostkę, wybierz **Nowa** w okienku akcji.

1. W nagłówku rekordu określ następujące pola:

    - **Jednostka** — umożliwia wprowadzenie identyfikatora lub symbolu odwołującego się do jednostki w wersji językowej systemu. Ten identyfikator lub symbol jest zazwyczaj wspólnym skrótem jednostki, takim jak *szt* jako sztuka lub *cm* jako centymetr.
    - **Opis** — Wprowadź opisową nazwę jednostki w wersji językowej systemu. Jest to zazwyczaj pełna nazwa jednostki, np. *Sztuka* lub *Centymetr*.

1. Na skróconej karcie **Ogólne** ustaw następujące pola:<!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - **Klasa jednostek** — umożliwia wybór właściwości miary jednostki (np. długość, obszar, masa lub ilość).
    - **System jednostek** — umożliwia wybór systemu miar, do którego należy jednostka (*jednostki metryczne* lub *tradycyjne jednostki w Stanach Zjednoczonych*).
    - **Jednostka podstawowa** — ta opcja ma wartość *Tak*, jeśli bieżąca jednostka ma być jednostką podstawową w klasie jednostek. W takim przypadku wystarczy określić współczynnik konwersji między jednostką podstawową a każdą dodatkową jednostką w klasie jednostek. System może następnie konwertować między wszystkimi jednostkami w tej klasie jednostek. Wtedy ustawianie konwersji jest łatwiejsze.

        Jeśli na przykład galon jest jednostką podstawową dla klasy jednostek *objętości*, należy skonfigurować tylko współczynniki konwersji z litrów na galon oraz z pinty na galon. System może następnie konwertować z litra na pintę.

        Można mieć tylko jedną jednostkę podstawową w danej klasie jednostek.

    - **Jednostka systemowa** — ta opcja ma wartość *Tak*, jeśli bieżąca jednostka ma być domyślną jednostką wszystkich miar bez określenia jednostki w danej klasie jednostek. Jeśli na przykład pole używane do wprowadzania ilości nie zezwala na podanie jednostki (lub gdy użytkownik nie wybierze jednostki), system użyje jednostki ustawionej jako jednostka systemowa dla klasy jednostek *Ilość*. Można mieć tylko jedną jednostkę systemową w danej klasie jednostek.
    - **Dokładność dziesiętna** — umożliwia określenie liczby miejsc dziesiętnych, do których powinny być zaokrąglane wartości określone w bieżącej jednostce lub przeliczone na nią.

1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="define-unit-translations"></a>Definiowanie tłumaczeń jednostek

Aby zdefiniować tłumaczenia identyfikatora lub symbolu oraz opisu jednostki miary, należy wykonać następujące kroki.

1. Utwórz lub wybierz jednostkę, której tłumaczenia chcesz utworzyć.
1. W okienku akcji wybierz opcję **Teksty jednostki**.

    Zostanie wyświetlona strona **Teksty jednostki**. Ta strona służy do definiowania tłumaczeń identyfikatora lub symbolu wybranej jednostki. Tłumaczenia te mogą być następnie używane w dokumentach zewnętrznych w językach specyficznych dla odbiorcy lub dostawcy.

1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Język** wybierz język, na który będzie przetłumaczony identyfikator lub symbol jednostki.
1. W polu **Tekst** wprowadź tłumaczenie identyfikatora lub symbolu jednostki na wybrany język.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Zamknij stronę.
1. W **okienku akcji** kliknij pozycję **Przetłumaczone opisy jednostki**.

    Zostanie wyświetlona strona **Przetłumaczone opisy jednostki**. Ta strona służy do definiowania opisów w określonym języku dla wybranej jednostki.

1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Język** wybierz język, na który będzie przetłumaczony opis jednostki.
1. W polu **Opis** wprowadź tłumaczenie opisu jednostki na wybrany język.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. Zamknij stronę.

## <a name="define-unit-conversion-rules"></a>Definiowanie reguł konwersji jednostek

Aby zdefiniować reguły konwersji między jednostkami miary, należy wykonać następujące czynności.

1. Utwórz lub wybierz jednostkę, której reguły konwersji definiujesz.
1. W okienku akcji wybierz opcję **Konwersje jednostek**.

    Zostanie otwarta strona **Konwersje jednostek**. Na tej stronie możesz zdefiniować reguły konwersji wybranej jednostki na i z innych jednostek w tej klasie jednostek.

1. W zależności od typu konwersji, którą chcesz skonfigurować, wybierz jedną z następujących kart:

    - **Standardowe konwersje** – Konfigurowanie standardowych reguł konwersji dla wszystkich produktów.
    - **Konwersje wewnątrz klasy** – Konfigurowanie specyficznych dla produktu reguł konwersji jednostek w tej samej klasie jednostek.
    - **Konwersje między klasami** – Konfigurowanie specyficznych dla produktu reguł konwersji jednostek między klasami jednostek.

1. Wykonaj jeden z następujących kroków:

    - Aby utworzyć nową konwersję, wybierz **Nowa** na pasku narzędzi.
    - Aby edytować istniejącą konwersję, zaznacz konwersję w siatce, a następnie wybierz pozycję **Edytuj** na pasku narzędzi.

1. W wyświetlonym oknie dialogowym listy rozwijanej można ustawić następujące pola:

    - **Produkt** — wybierz określony produkt, do którego odnosi się konwersja. To pole jest dostępne tylko w przypadku konwersji wewnątrz klasy i między klasami.
    - **Układ formuły** – Aby określić prostą konwersję z jednym współczynnikiem, należy pozostawić wartość *Prosta* w tym polu. Ustaw w nim wartość *Zaawansowane*, jeśli chcesz skonfigurować bardziej złożone równanie. Format równań zaawansowanych zmienia się w zależności od klasy jednostek.
    - **Z jednostki** — w tym polu jest wyświetlana wybrana jednostka. Zwykle nie należy zmieniać tej wartości. (W przypadku zmiany tej wartości należy otworzyć stronę **Konwersje jednostek** dla wybranej jednostki, aby wyświetlić nową konwersję po jej zapisaniu).
    - **Na jednostkę** — wybierz jednostkę docelową konwersji.
    - **Zaokrąglanie** — umożliwia wybór sposobu zaokrąglania ułamków na podstawie wartości **dokładności dziesiętnej** wybranej jednostki (*Do najbliższej*, *W górę* lub *W dół*).
    - **Formuła konwersji** — Pozostałe pola w górnej części okna dialogowego służą do określenia formuły konwersji między tymi dwiema jednostkami. Dostępne pola różnią się w zależności od wybranej klasy jednostki i wybranego układu formuły.

1. Kliknij przycisk **OK**.
1. Zamknij stronę.

> [!TIP]
> Można także skonfigurować konwersje jednostek zależnie od wariantu produktu. Więcej informacji zawiera temat [Przeliczanie jednostki miary dla wariantów produktów](../uom-conversion-per-product-variant.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
