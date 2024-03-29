---
title: Włączanie spójnej obsługi trybu dostawy w kanałach handlu elektronicznego
description: W tym artykule opisano, jak włączyć obsługę spójnych trybów dostarczania w celu rozwiązania możliwych problemów związanych z przepływami opłat w kanałach handlu elektronicznego Microsoft Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 43450c9d380bd57c234bb1c9acfbe296ab115f14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279658"
---
# <a name="enable-consistent-delivery-mode-handling-in-e-commerce-channels"></a>Włączanie spójnej obsługi trybu dostawy w kanałach handlu elektronicznego 

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak włączyć obsługę spójnych trybów dostarczania w celu rozwiązania możliwych problemów związanych z przepływami opłat w kanałach handlu elektronicznego Microsoft Microsoft Dynamics 365 Commerce.

W Dynamics 365 Commerce w przypadku opłat nieocenionych na poziomie nagłówka domyślnie nie są stosowane w kanałach e-commerce. Takie zachowanie może spowodować jeden lub obydwa z następujących problemów w kanałach e-commerce:

- Nie są wyświetlane opłaty na poziomie nagłówka nieocenionych.
- Opłaty dla trybów dostawy nie są spójne między trybem wyboru dostawy a podsumowaniem zamówienia realizacji.

Aby rozwiązać te problemy, musisz włączyć funkcję **Włącz obsługę spójnych trybów dostawy w kanale**. Ta funkcja zapewnia, że nieproporcjonalne opłaty na poziomie nagłówka pojawiają się w kanałach handlu elektronicznego, a informacje o dostawie zamówienia sprzedaży są obsługiwane w sposób spójny w ramach tego samego przepływu pracy żądania.

## <a name="turn-on-the-enable-consistent-delivery-mode-handling-in-channel-feature"></a>Włącz opcję Włącz obsługę spójnych trybów dostarczania w funkcji kanału

Aby włączyć funkcję **Włączanie spójnej obsługi trybu dostawy w funkcji kanału** sprzedaży w programie Commerce Headquarters, należy wykonać następujące kroki.

1. Otwórz obszar roboczy **Zarządzanie funkcjami** (**Administracja systemu \> obszary robocze \> Zarządzanie funkcjami**).
1. Z listy dostępnych funkcji wyszukaj i wybierz opcję **Włącz spójną obsługę trybu dostawy w kanale**.
1. W okienku po prawej stronie włącz pozycję **Włącz teraz**.
