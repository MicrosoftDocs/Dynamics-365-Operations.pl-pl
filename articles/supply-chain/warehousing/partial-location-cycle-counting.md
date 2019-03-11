---
title: Częściowa inwentaryzacja ciągła w lokalizacji
description: Plany inwentaryzacji ciągłej decydują o faktycznym przebiegu operacji inwentaryzacji. Można poprosić, aby były inwentaryzowane tylko określone produkty i warianty produktu, a nie wszystkie zapasy dostępne w lokalizacji.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd7cb8b35023ed63af191545d01c60c2c7cc8ef5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "320657"
---
# <a name="partial-location-cycle-counting"></a>Częściowa inwentaryzacja ciągła w lokalizacji

[!include [banner](../includes/banner.md)]

Plany inwentaryzacji ciągłej decydują o faktycznym przebiegu operacji inwentaryzacji. Można poprosić, aby były inwentaryzowane tylko określone produkty i warianty produktu, a nie wszystkie zapasy dostępne w lokalizacji.

Tworząc pracę inwentaryzacji za pomocą planów inwentaryzacji ciągłej, można decydować o faktycznym przebiegu operacji inwentaryzacji. Można poprosić, aby były inwentaryzowane tylko określone produkty i warianty produktu, a nie wszystkie zapasy dostępne w lokalizacji. Wyfiltrowując określone produkty, kierownik magazynu może zmniejszyć pracochłonność przeglądu, uniknąć błędów konsolidacji i zaoszczędzić czas.

## <a name="how-to-configure-partial-location-cycle-counting"></a>Jak skonfigurować częściową inwentaryzację ciągłą w lokalizacji
Jeśli do operacji inwentaryzacji wykorzystujesz proces pracy magazynowej, dla każdej lokalizacji jest tworzony nagłówek pracy. Podczas definiowaniu planu inwentaryzacji ciągłej można użyć zapytania **Wybierz lokalizacje**, aby ograniczyć tworzoną pracę inwentaryzacji ciągłej. Po wybraniu produktów do planu inwentaryzacji ciągłej można użyć zapytań o produkty i wariantu produktów w celu doprecyzowania zakresu inwentaryzacji. 

Można skojarzyć **szablon pracy** z planem inwentaryzacji ciągłej w celu zdefiniowania sposobu tworzenia pracy inwentaryzacji ciągłej. Szablon pracy operacji inwentaryzacji wywoływany bezpośrednio z planu inwentaryzacji ciągłej. 

Definiując szczegóły szablonu pracy, można użyć opcji **Podziały wierszy pracy** i określić, czy wiersze pracy inwentaryzacji mają być grupowane według numeru towaru, czy numeru wariantu produktu. Ta konfiguracja jest wymagana, jeśli mają być inwentaryzowane dostępne zapasy tylko dla określonych produktów w lokalizacji. Tworzone wiersze pracy inwentaryzacji ciągłej będą miały poziom informacji zdefiniowany w tym miejscu i sterowane operacje inwentaryzacji będą obsługiwane na podstawie tego poziomu. 

Jeśli skojarzysz plany inwentaryzacji ciągłej z szablonami pracy za pomocą opcji **Podziały wierszy pracy**, dla tworzonej pracy inwentaryzacji ciągłej zostanie zaznaczone pole **Częściowa inwentaryzacja ciągła** oraz zostanie utworzonych wiele wierszy pracy inwentaryzacji, zgodnie z definicją szablonu pracy. 

Aby można było wykonywać pracę częściowej inwentaryzacji ciągłej, należy co najmniej zaznaczyć w menu urządzenia komórkowego opcję **Wyświetl kod pozycji** w konfiguracji inwentaryzacji ciągłej. Operator magazynu będzie musiał rejestrować tylko dane inwentaryzacji powiązane z wierszami inwentaryzacji (numerami towarów i wymiarami produktów). W tym procesie inwentaryzacji wszystkie pozostałe dostępne zapasy będą ignorowane. 

W procesie częściowej inwentaryzacji ciągłej pole daty/godziny **Ostatnie obliczenie cyklu** nie będzie aktualizowane dla lokalizacji.

## <a name="example"></a>Przykład
W tym przykładzie musi być inwentaryzowany tylko towar o numerze A0001 w magazynie 61.

1.  Zostanie utworzony nowy szablon pracy inwentaryzacji ciągłej. Opcja **Podziały wierszy pracy** służy do grupowania wierszy pracy inwentaryzacji według numerów towarów. W związku z tym tworzona praca inwentaryzacji ciągłej będzie miała wiersze dla każdego numeru towaru. Można również grupować wiersze według numeru wariantu produktu.
2.  Tworzony jest nowy plan inwentaryzacji ciągłej, który odwołuje się do nowo utworzonego szablonu pracy. Plan inwentaryzacji ciągłej zawiera wszystkie lokalizacje w magazynie 61 (zapytanie **Wybierz lokalizacje**) przechowujące zapasy towaru o kodzie A0001. Wybór określonych produktów jest definiowany w sekcji **Wybory produktów do inwentaryzacji ciągłej**.
3.  Produkty do planów inwentaryzacji ciągłej można wybrać, ustawiając w polu **Puste lokalizacje** wartość **Wyklucz puste**. Podczas przetwarzania planu inwentaryzacji ciągłej tworzona jest praca inwentaryzacji częściowej dla numeru pozycji A0001. Faktyczny proces inwentaryzacji można przeprowadzić przy użyciu elementu menu wspomaganej inwentaryzacji ciągłej na urządzeniu przenośnym.



<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Inwentaryzacja ciągła](cycle-counting.md)

