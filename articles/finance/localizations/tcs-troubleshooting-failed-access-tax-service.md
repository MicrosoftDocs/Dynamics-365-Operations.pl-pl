---
title: Nie można uzyskać dostępu do usługi podatkowej
description: W tym artykule wyjaśniono, jak rozwiązywać problemy z dostępem do usługi obliczania podatków.
author: hangwan
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 02/16/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 65d819b97be3d1238bc0ecfc201b4e24edac8616
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861230"
---
# <a name="failed-to-access-tax-service"></a>Nie można uzyskać dostępu do usługi podatkowej

[!include [banner](../includes/banner.md)]


W tym artykule wyjaśniono, jak naprawić błąd „Nie można uzyskać dostępu do usługi podatkowej” usługi obliczania podatku.

## <a name="symptoms"></a>Objawy

W Microsoft Dynamics 365 Finance wybierz opcje **Podatek** \> **Ustawienia** \> **Konfiguracja podatku** \> **Parametry usług podatkowych**. Na karcie **Ogólne** włącz opcję **Włącz obliczanie** podatku. Po wybraniu wartości w polu **Nazwa konfiguracji funkcji** wystąpi błąd. Komunikat o błędzie mówi „Nie udało się uzyskać dostępu do usługi podatkowej”.

## <a name="cause"></a>Powód

Ten błąd występuje, ponieważ Finance nie może uzyskać dostępu do usługi obliczania podatków.

## <a name="resolution"></a>Rozwiązanie 

1. Zaloguj się do Microsoft Dynamics LifeCycle Services (LCS).
2. Na stronie **Środowisko**, na **karcie Dodatki środowiska** znajdź element **Obliczenia podatku** i przejrzyj jego stan. Stan powinien mieć stan **Instalowanie** lub **Zainstalowane**. Jeśli dodatek Usługa obliczania podatku nie jest zainstalowany, zostanie wyświetlony komunikat o błędzie.

## <a name="mitigation"></a>Sposób minimalizacji

1. W LCS, na stronie **Finanse**, w sekcji **Integracja z Power Platform** wybierz pozycję **Zainstaluj nowy dodatek**.
2. Przewiń w dół strony i wybierz dodatek **Obliczanie podatku**, aby go zainstalować.
3. Wróć do środowiska finansowego i spróbuj uzyskać dostęp do usługi obliczania podatku.

> [!NOTE]
> Przed zainstalowaniem usługi obliczania podatku przejrzyj wstępnie [wymagane wymagania wstępne usługi obliczania podatku](global-get-started-with-tax-calculation-service.md#prerequisites).
> 
> Jeśli nie możesz zainstalować tego dodatku, ponieważ sekcja **Integracja z Power Platform** jest niedostępny, zobacz [omówienie dodatku](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Jeśli mimo to wystąpi błąd po zainstalowaniu dodatku, skontaktuj się z administratorem systemu.
