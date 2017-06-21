---
title: "Jednostka miary i zasady składowania"
description: "W tym artykule opisano, jak domyślne jednostki, sekwencje jednostek i konwersje jednostek są używane w procesach magazynowych."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetails, EcoResProductDetailsExtended, EcoResStorageDimensionGroup, InventItemOrderSetup, UnitOfMeasureConversion, WHSRFMenuItem, WHSUOMSeqGroupTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29611
ms.assetid: 4b5ca875-9a06-416d-9ac0-cc3ab8f7338e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 240174c1399f778313a800e0ed5f19fdd899fc07
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="unit-of-measure-and-stocking-policies"></a>Jednostka miary i zasady składowania

[!include[banner](../includes/banner.md)]


W tym artykule opisano, jak domyślne jednostki, sekwencje jednostek i konwersje jednostek są używane w procesach magazynowych.

Grupy sekwencji jednostek definiują kolejność jednostek, które mogą być używane w operacjach magazynowych. Tworzy się je na stronie **Grupy sekwencji jednostek**. Kolejność pokazuje relacje różnych jednostek. Można na przykład zapisać palety zawierające opakowania z pojedynczymi sztukami towaru. W takim przypadku trzeba podać trzy różne jednostki i logiczną kolejność warstw. Grupy sekwencji jednostek umożliwiają definiowanie zasad dla grupowania numerów identyfikacyjnych i domyślnych jednostek, które mają być używane dla różnych procesów magazynowych. Ten artykuł dotyczy zarówno zaawansowanych rozwiązań magazynowych dostępnych w module Zarządzanie magazynem i bardziej podstawowe rozwiązanie magazynowe, które jest dostępne w module Zarządzanie zapasami.

## <a name="unit-sequence-groups-for-released-products"></a>Grupy sekwencji jednostek dla zwolnionych produktów
Jeśli chcesz użyć zwolnionych produktów w procesach roboczych magazynu, grupa sekwencji jednostek musi być do nich przypisana. Przy sprawdzaniu poprawności produktu, który jest skojarzony z grupą wymiarów magazynowania i opcja **Użyj procesów zarządzania magazynami** ma wartość **Tak**, zostanie wyświetlony komunikat o błędzie, jeśli identyfikator grupy sekwencji jednostek nie jest zdefiniowany dla produktu. Jeśli używana grupa sekwencji jednostek zawiera wiele wierszy (i z tego względu wiele jednostek), trzeba skonfigurować konwersję jednostek między jednostkami. Te ustawienia wprowadza się na stronie **Konwersje jednostek**. Najmniejsza jednostka grupy sekwencji kojarzona ze zwolnionym produktem musi odpowiadać jednostce magazynowej określonej dla odpowiadającego produktu. Jednostka magazynowa jest jednostką, która jest używana w podstawowych obliczeniach dostępnych zapasów. Można także skonfigurować konwersje jednostki miary dla wariantów produktów głównych za pomocą opcji **Włącz konwersje jednostek miary**.

## <a name="license-plate-grouping"></a>Grupowanie numerów identyfikacyjnych
Można określić, czy przyjęcia mniej niż jednej lub więcej niż określona jednostka powinny być grupowane w ramach jednego numeru identyfikacyjnego, czy podzielone na osobne numery identyfikacyjne dla każdej jednostki. Aby skonfigurować to zachowanie, należy użyć opcji **Grupowanie numerów identyfikacyjnych** na karcie **Szczegóły wiersza** na stronie **Grupy sekwencji jednostek**. Aby używać grupowania według numerów identyfikacyjnych podczas przetwarzania pracy za pomocą urządzenia przenośnego, opcja **Grupowanie numerów identyfikacyjnych** w menu **Urządzenie przenośne**
musi być zaznaczona. Załóżmy na przykład, że używasz urządzenia przenośnego do rejestracji towaru, który jest skojarzony z grupą sekwencji, która ma dwa wiersze. Pierwszy wiersz odnosi się do Sztuk, a opcja **Grupowanie numerów identyfikacyjnych** ma wartość **Tak**. Drugi wiersz odnosi się do Palety, a opcja **Grupowanie numerów identyfikacyjnych** ma wartość **Nie**. W takim przypadku system może automatycznie przeprowadzić podział i utworzyć numery rejestracyjne dla 100 sztuk.

## <a name="units-for-cycle-counting"></a>Jednostki do inwentaryzacji ciągłej
Aby zdefiniować, które jednostki powinny być używane w ramach procesu inwentaryzacji ciągłej, wybierz opcję **Użyj jednostki do inwentaryzacji ciągłej** na stronie **Grupy sekwencji jednostek**. Można wybrać maksymalnie cztery jednostki w grupie sekwencji. Jeśli zaznaczy się więcej niż cztery jednostki, dodatkowe jednostki nie będą wyświetlane na urządzeniu przenośnym.

## <a name="default-units-for-mobile-device-receiving-processes"></a>Domyślne jednostki do obsługi procesu przyjmowania na urządzeniu przenośnym
Aby ustawić domyślne jednostki, które mają być używane do obsługi procesów przyjmowania na urządzeniach przenośnych, włącz opcje **Jednostka domyślna dla zakupu i przeniesienia** i **Jednostka domyślna dla produkcji** na stronie **Grupy sekwencji jednostek**. Na przykład można określić, że domyślnie system powinien używać Ilości palety po otrzymaniu dostępnych zapasów dla zamówienia zakupu za pomocą urządzenia przenośnego, ale jednostką składowania zapasu powinny być Sztuki. Aby uzyskać konwersję dla liczby sztuk, jaką zawiera każda paleta, trzeba zdefiniować konwersję jednostki, np. 100 szt. = 1 paleta.

## <a name="default-order-settings"></a>Ustawienia domyślne zamówień
W ramach tworzenia zwolnionych produktów należy wybrać domyślne jednostki dla zakupów, sprzedaży i zapasów do przetwarzania różnych zamówień. Można ustawić domyślne jednostki i ilości dla różnych dokumentów źródłowych za pomocą stron **Ustawienia domyślne zamówień** i **Ustawienia zamówień właściwe dla oddziału**. Są one dostępne ze strony **Zwolnione produkty**.




