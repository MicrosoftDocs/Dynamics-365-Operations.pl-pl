---
title: Zamówienia magazynowe dla jednostek skalowania chmury i urządzenia brzegowego
description: Ten temat zawiera informacje dotyczące możliwości zamówień magazynowych, które są używane jako część obciążenia jednostek skalowania magazynów.
author: perlynne
manager: tfeyr
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c04127b9fe621d962be2d7fe06358b3bd1b78916
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2021
ms.locfileid: "5105724"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a>Zamówienia magazynowe dla jednostek skalowania chmury i urządzenia brzegowego

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Nie wszystkie funkcje biznesowe są w pełni obsługiwane w wersji zapoznawczej, gdy są używane obciążenia jednostek skalowania. Jeśli używasz jednostek skalowania, pamiętaj, aby użyć tylko tych procesów, które opisano w tym temacie jako obsługiwane.

## <a name="what-are-warehouse-orders"></a>Co to są zamówienia magazynowe?

*Zamówienia magazynowe* to rodzaj zamówienia utworzonego w celu obsługi wdrożeń magazynu centrum i jednostki skalowania. Umożliwiają one odbieranie zapasów podczas uruchamiania obciążenia magazynu na jednostce skalowania. Są one obecnie używane tylko z zamówieniami zakupu.

Zamówienia magazynowe są używane w ramach przetwarzania zarządzania magazynem, na przykład gdy aplikacja magazynu służy do rejestrowania fizycznych dostępnych zapasów podczas przetwarzania przychodzącego zamówienia zakupu. Zamówienia magazynowe są tworzone w ramach procesu *Zwalnianie do magazynu* dostępnego dla zamówień zakupu, w których określono magazyn jednostek skalowania oraz towary, dla których można używać procesów zarządzania magazynem.

> [!IMPORTANT]
> Zamówienia magazynowe są dostępne tylko we wdrożeniach, które korzystają z [obciążenia zarządzania magazynem dla jednostek skali chmury i urządzeń brzegowych](cloud-edge-workload-warehousing.md).

## <a name="create-a-warehouse-order"></a>Tworzenie zamówienia magazynowego

Aby utworzyć zamówienie magazynowe, należy wykonać następujące czynności.

1. Zaloguj się do wystąpienia rozwiązania Microsoft Dynamics 365 Supply Chain Management działającego w centrum. (Należy zainicjować proces *zwalniania do magazynu* po zalogowaniu się do centrum).
1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.
1. Aby wyświetlić powiązane wiersze zamówienia magazynowego, otwórz odpowiednie zamówienie zakupu, wybierz wiersz w sekcji **Wiersze zamówienia zakupu**, a następnie na pasku narzędzi wybierz pozycję **Magazyn \> Wiersze zamówienia magazynowego**. Aby wyświetlić wszystkie wiersze, przejdź do pozycji **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówienia magazynowego**.

## <a name="cancel-a-warehouse-order"></a>Anulowanie zamówienia magazynowego

W ramach procesu *zwalniania do magazynu* transakcje magazynowe zamówień zakupu są łączone z zamówieniami magazynowymi i nie są aktualizowane przez centrum. Jeśli przeprowadzono zwalnianie do magazynu przez pomyłkę lub masz inny powód anulowania tworzenia wierszy zamówień magazynowych, można zażądać anulowania wierszy zamówień magazynowych.

Aby anulować wiersze zamówienia magazynowego, należy wykonać następujące czynności.

1. Zaloguj się do wystąpienia rozwiązania Supply Chain Management działającego w centrum.
1. Przejdź do pozycji **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówienia magazynowego**.
1. Wybierz odpowiedni wiersz.
1. W okienku akcji wybierz pozycję **Anuluj wiersze zamówienia magazynowego**.

> [!NOTE]
> Żądanie anulowania wierszy nie będzie realizowane w przypadku wierszy, które już oczekują na anulowanie lub które są aktywnie przetwarzane w magazynie, w których jest uruchomione obciążenie w jednostce skalowania.

## <a name="monitor-a-warehouse-order"></a>Monitorowanie zamówienia magazynowego

W widoku **wierszy zamówienia magazynowego** można monitorować postęp przyjmowania towarów przychodzącego, przeglądając wartości w kolumnie **Ilość pozostała do odebrania**. Aby wyświetlić szczegóły dotyczące pracy wykonanej za pomocą aplikacji magazynu, wykonaj jedną z poniższych czynności.

- Przejdź do obszaru **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówień magazynowych** i użyj filtru, aby znaleźć szukane wiersze.
- Przejdź do pozycji **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu** i otwórz odpowiednie zamówienie zakupu. W sekcji **Wiersze zamówienia zakupu** zaznacz jeden lub więcej wierszy, a następnie na pasku narzędzi wybierz pozycje **Magazyn \> Wpisy przyjęcia do magazynu**.
