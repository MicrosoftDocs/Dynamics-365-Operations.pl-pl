---
title: Rabaty wysyłkowe
description: W tym artykule opisano możliwości rabatu wysyłkowego w Microsoft Dynamics 365 Commerce oraz konfigurację, która jest wymagana do ich użycia.
author: ShalabhjainMSFT
ms.date: 08/23/2020
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2019-01-31
ms.openlocfilehash: f19566ce64becea4a53a8479cb5a08579567cda1
ms.sourcegitcommit: 1dbff0b5fa1f4722a1720fac35cce94606fa4320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2022
ms.locfileid: "9346396"
---
# <a name="shipping-discount"></a>Rabaty wysyłkowe

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym artykule opisano możliwości rabatu wysyłkowego w Microsoft Dynamics 365 Commerce oraz konfigurację, która jest wymagana do ich użycia.

Wysyłka z rabatem lub bezpłatna to jeden z czynników wpływający na decyzje dotyczące zakupu w trybie online przez odbiorców. Aby zwiększyć przychody z tytułu transakcji, wielu sprzedawców detalicznych korzysta z bezpłatnych usług transportowych, aby motywować odbiorców do zwiększenia rozmiaru koszyka.

Rozwiązanie Commerce obsługuje funkcję rabatu wysyłkowego, dzięki którym sprzedawcy detaliczni konfigurują procent rabatu od opłat za wysyłkę dla określonej metody wysyłki, gdy łączna kwota sprzedaży dla towarów kwalifikowanych w transakcji spełnia określone kryteria. Przykładem scenariusza, w którym jest używany rabat za wysyłkę, jest „Wydaj $50 więcej na bezpłatny transport całonocny”

## <a name="prerequisites"></a>Wymagania wstępne

Funkcja rabatu wysyłkowego jest obsługiwana przez zaawansowane funkcje Commerce [automatycznych opłat wielokanałowych](/dynamics365/unified-operations/retail/omni-auto-charges). Aby można było korzystać z funkcji rabatu wysyłkowego, należy włączyć konfigurację **Użyj zaawansowanej konfiguracji automatycznych opłat** na karcie **Zamówienia odbiorcy** na stronie **Parametry Commerce** w centrali Commerce headquarters. Sprzedawcy detaliczni mogą używać zaawansowanych funkcji automatycznych opłat, aby skonfigurować różne typy opłat, takie jak obsługa, instalacja i likwidacja.

Te rabaty wysyłkowe są stosowane tylko do opłat transportowych. W związku z tym sprzedawca detaliczny musi określić, które opłaty są opłatami transportowymi. Aby określić opłaty transportowe, w centrali w programie Commerce Headquarters przejdź do **Ustawienia kanału \> Opłaty \> Kod opłat** i ustaw opcję **Opłata za wysyłkę** na wartość **Tak** dla żądanych opłat.

![Określanie opłaty jako opłaty transportowej.](./media/Specify_shipping_charge.png)

## <a name="configuration"></a>Konfiguracja

Funkcja rabatu wysyłkowego jest oparta na warstwie i obsługuje tylko typ obliczania **procentu rabatu**. Aby skonfigurować rabat za wysyłkę, w programie Commerce Headquarters przejdź do tematu **Ceny i rabaty \> Progowe rabaty dla wysyłki**. Następnie można określić tryb dostawy, do których odnosi się rabat, zdefiniować co najmniej jeden progi kwotowe i ustawić procent rabatu dla każdego progu. Można również skonfigurować listę kategorii lub produktów jako towary kwalifikowane. W ten sposób tylko kwota sprzedaży w stosunku do towarów w transakcji będzie zliczona, gdy aparat cen oceni, czy suma transakcji nie przekracza progu.

> [!NOTE]
> W przeciwieństwie do innych typów rabatów, rabat wysyłkowy nie tworzy wierszy rabatu. Zamiast tego, bezpośrednio edytuje opłatę transportową i dołącza nazwę rabatu do opisu opłaty.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
