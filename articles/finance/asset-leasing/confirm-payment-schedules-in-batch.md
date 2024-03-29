---
title: Potwierdzanie harmonogramów płatności wynajmu składnika majątku w partii
description: W tym artykule opisano sposób zatwierdzania wielu harmonogramów płatności w partii.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymConfirmationDetails
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: bd75e22f6407d6bc25a78c1dfeacf70022238e94
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895059"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a>Potwierdzanie harmonogramów płatności wynajmu składnika majątku w partii

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób zatwierdzania wielu harmonogramów płatności w partii. Harmonogramy płatności są potwierdzane na zasadzie od wynajmu do wynajmu lub w procesie wsadowym potwierdzenia. Wpis w arkuszu może być księgowany tylko w odniesieniu do wynajmu o potwierdzonym harmonogramie płatności. Potwierdzenie harmonogramu płatności służy jako ostateczne zatwierdzenie informacji finansowych dotyczących wynajmu. Wszystkie przyszłe zmiany informacji finansowych dotyczących wynajmu, takie jak płatności i okres wynajmu, stanowią korektę wynajmu i powinny być przetwarzane w ten sposób.

Aby potwierdzić wiele harmonogramów płatności, należy wykonać następujące kroki.

1. Przejdź do **Wynajem składnika majątku \> Okresowe \> Potwierdzenie w partii**.
2. Na stronie **Potwierdzenie w partii** wybierz pozycję **Potwierdzenie w partii**.
3. W wyświetlonym oknie dialogowym odfiltruj księgi, które chcesz potwierdzić.

    - Aby potwierdzić wszystkie księgi z danej grupy wynajmu, zaznacz tę grupę w polu **Grupa wynajmu**.
    - Aby potwierdzić określone księgi, wybierz księgi w polu **Identyfikator księgi**.
    - Aby potwierdzić wszystkie księgi, włącz parametr **Dla wszystkich ksiąg**.

Informacje dotyczące nowo potwierdzonych ksiąg są wyświetlane na stronie **Potwierdzone księgi**. Po potwierdzeniu harmonogramów płatności początkowe wpisy w arkuszu rozpoznawania mogą być księgowane za wynajmy.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
