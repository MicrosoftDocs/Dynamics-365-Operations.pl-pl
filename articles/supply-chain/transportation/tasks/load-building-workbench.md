---
title: Pulpit kompilowania ładunku
description: W tym temacie opisano, jak pracować z pulpitem kompilowania ładunku.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1ed91adba5c7accf9a18d7a754d33b2b35b848f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974238"
---
# <a name="load-building-workbench"></a>Pulpit kompilowania ładunku

Pulpit kompilowania ładunku umożliwia stosowanie strategii kompilowania ładunku podczas tworzenia ładunków.

## <a name="create-a-load-building-strategy"></a>Tworzenie strategii kompilowania ładunku

Strategie kompilowania ładunku są używane do automatycznego kompilowania ładunków. Ta funkcja przydaje się w następujących sytuacjach:

- Jeśli regularnie wysyłasz określony zestaw produktów, strategie te pozwalają zaoszczędzić czas, ponieważ nie musisz za każdym razem od nowa kompilować tego samego ładunku.
- Jeśli zależy Ci na maksymalizacji wydajności i chcesz uniknąć połowicznych ładunków, strategie te pomogą Ci wypełnić każdy ładunek w jak największym zakresie.

Klasa strategii kompilowania ładunku o nazwie `TMSLoadBuildingVolumeStrategy` zawiera strategię kompilowania ładunku o nazwie *Strategia kompilowania ładunku na podstawie objętości*. Pozwala ona stosować maksymalne wartości wysokości i wagi określone w szablonie ładunku albo zastępować te ustawienia wprowadzaniem nowych wartości. Ta strategia jest jedyną strategią, która jest dostarczana jako gotowa. (Możesz jednak również korzystać z kilku strategii niestandardowych).

Aby korzystać z gotowej *Strategii kompilowania ładunku na podstawie objętości*, należy zaznaczyć ją w polu **Strategia kompilowania ładunku** na stronie **Pulpitu kompilowania ładunku** (**Zarządzanie transportem &gt; Planowanie &gt; Pulpit kompilowania ładunku**).

Aby utworzyć strategię kompilowania ładunku, wykonaj poniższe czynności.

1. Wybierz kolejno **Zarządzanie transportem &gt; Ustawienia &gt; Kompilowanie ładunku &gt; Strategie kompilowania ładunku**.
1. W okienku akcji wybierz opcję **Generuj listę klas**, aby upewnić się, że masz najnowsze wersje wszystkich dostępnych klas.
1. W okienku akcji wybierz opcję **Nowy**.
1. Wprowadź unikatową nazwę strategii, wybierz dla niej klasę strategii kompilowania ładunku i wprowadź opis.
1. Na okienku akcji wybierz opcję **Zapisz**.
1. W okienku akcji wybierz pozycję **Parametry**.
1. Na stronie **Parametry strategii tworzenia ładunku** wybierz z listy pozycję **Maksymalna objętość**, a następnie w polu **Wartość** wprowadź wartość procentową łącznej objętości ładunku, która powinna zostać zastosowana do nowej strategii kompilowania ładunku.
1. Wybierz z listy pozycję **Maksymalna masa**, a następnie w polu **Wartość** wprowadź wartość procentową łącznej masy ładunku, która powinna zostać zastosowana do nowej strategii kompilowania ładunku.
1. Zamknij stronę **Parametry strategii tworzenia ładunku**.
1. Zamknij stronę **Strategie kompilowania ładunku**.

Możesz teraz przypisać strategię kompilowania ładunku do szablonu kompilowania ładunku albo skorzystać z niej bezpośrednio na poziomie pulpitu planowania wysyłki ładunku.

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a>Korzystanie ze strategii kompilowania ładunku na poziomie pulpitu kompilowania ładunku

1. Wybierz kolejno opcje **Zarządzanie transportem &gt; Planowanie &gt; Pulpit kompilowania ładunku**.
1. Wykonaj jeden z następujących kroków:

    - Wybierz strategię w polu **Strategia kompilowania ładunku**.
    - Jeśli masz zdefiniowany szablon kompilowania ładunku i przypisano do niego strategię kompilowania ładunku, w okienku akcji na karcie **Zarządzaj szablonami** wybierz opcję **Zastosuj szablon**. Następnie w rozwijanym oknie dialogowym **Zastosuj szablon kompilowania ładunku** wybierz szablon w polu **Nazwa szablonu kompilowania ładunku**.

1. Na skróconej karcie **Ładuj sekwencję szablonów** wybierz co najmniej jeden [szablon ładunku](load-template.md). Pulpit spróbuje dopasować ładunek do kontenerów wybranych typów w kolejności określonej w tym miejscu. Zazwyczaj należy umieścić najmniejsze kontenery u góry listy, aby najmniejszy dostępny kontener został wybrany jako pierwszy.
1. W okienku akcji wybierz pozycję **Proponuj ładunki**.
1. Przejrzyj proponowane ładunki i proponowane wiersze ładunku.
1. W okienku akcji wybierz opcję **Utwórz ładunki**, aby utworzyć ładunki oparte na wierszach dokumentu źródłowego na skróconej karcie **Wiersze proponowanego ładunku**.
1. Zamknij stronę **Pulpit kompilowania ładunku**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]