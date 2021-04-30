---
title: Zamówienia magazynowe dla jednostek skalowania chmury i urządzenia brzegowego
description: Ten temat zawiera informacje dotyczące możliwości zamówień magazynowych, które są używane jako część obciążenia jednostek skalowania magazynów.
author: perlynne
ms.date: 04/13/2021
ms.topic: article
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c24c08771c83453bb65312700cf994c7a800b7fd
ms.sourcegitcommit: 639175a39da38edd13e21eeb5a1a5ca62fa44d99
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/15/2021
ms.locfileid: "5899126"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a>Zamówienia magazynowe dla jednostek skalowania chmury i urządzenia brzegowego

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Nie wszystkie funkcje biznesowe są w pełni obsługiwane w wersji zapoznawczej, gdy są używane obciążenia jednostek skalowania. Jeśli używasz jednostek skalowania, pamiętaj, aby użyć tylko tych procesów, które opisano w tym temacie jako obsługiwane.

## <a name="what-are-warehouse-orders"></a>Co to są zamówienia magazynowe?

*Zamówienia magazynowe* to rodzaj zamówienia utworzonego w celu obsługi wdrożeń magazynu centrum i jednostki skalowania. Umożliwiają one odbieranie zapasów podczas uruchamiania obciążenia magazynu na jednostce skalowania. Są one obecnie używane tylko z zamówieniami zakupu.

Zamówienia magazynowe są używane w ramach przetwarzania zarządzania magazynem, na przykład gdy aplikacja Warehouse Management służy do rejestrowania fizycznych dostępnych zapasów podczas przetwarzania przychodzącego zamówienia zakupu. Zamówienia magazynowe są tworzone w ramach procesu *Zwalnianie do magazynu* dostępnego dla zamówień zakupu, w których określono magazyn jednostek skalowania oraz towary, dla których można używać procesów zarządzania magazynem.

> [!IMPORTANT]
> Zamówienia magazynowe są dostępne tylko we wdrożeniach, które korzystają z [obciążenia zarządzania magazynem dla jednostek skali chmury i urządzeń brzegowych](cloud-edge-workload-warehousing.md).

## <a name="create-a-warehouse-order"></a>Tworzenie zamówienia magazynowego

Aby utworzyć zamówienie magazynowe, należy wykonać następujące czynności.

1. Zaloguj się do wystąpienia rozwiązania Microsoft Dynamics 365 Supply Chain Management działającego w centrum. (Należy zainicjować proces *zwalniania do magazynu* po zalogowaniu się do centrum).
1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. W okienku akcji na karcie **Magazyn** w grupie **Akcje** wybierz opcję **Zwolnienie do magazynu**.
1. Aby wyświetlić powiązane wiersze zamówienia magazynowego, otwórz odpowiednie zamówienie zakupu, wybierz wiersz w sekcji **Wiersze zamówienia zakupu**, a następnie na pasku narzędzi wybierz pozycję **Magazyn \> Wiersze zamówienia magazynowego**. Aby wyświetlić wszystkie wiersze, przejdź do pozycji **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówienia magazynowego**.

Proces *Zwalniania do magazynu* można również wyzwolić z zadania wsadowego, przechodząc na pozycję **Zarządzanie magazynem > Zwolnij do magazynu > Automatyczne zwalnianie zamówień zakupu**. Podczas konfigurowania zadania wsadowego można wybrać określone wiersze zamówienia zakupu na podstawie zapytania. Typowym scenariuszem byłoby skonfigurowanie powtarzającego się zadania wsadowego, które zwalnia wszystkie potwierdzone wiersze zamówienia zakupu, które mają nadejść następnego dnia.

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

W widoku **wierszy zamówienia magazynowego** można monitorować postęp przyjmowania towarów przychodzącego, przeglądając wartości w kolumnie **Ilość pozostała do odebrania**. Aby wyświetlić szczegóły dotyczące pracy wykonanej za pomocą aplikacji Warehouse Management, wykonaj jedną z poniższych czynności.

- Przejdź do obszaru **Zarządzanie magazynem \> Zapytania i raporty \> Wiersze zamówień magazynowych** i użyj filtru, aby znaleźć szukane wiersze.
- Przejdź do pozycji **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu** i otwórz odpowiednie zamówienie zakupu. W sekcji **Wiersze zamówienia zakupu** zaznacz jeden lub więcej wierszy, a następnie na pasku narzędzi wybierz pozycje **Magazyn \> Wpisy przyjęcia do magazynu**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
