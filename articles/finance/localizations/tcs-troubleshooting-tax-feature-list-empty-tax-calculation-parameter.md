---
title: Pusta lista funkcji podatku w parametrach obliczania podatku
description: W tym temacie wyjaśniono, jak rozwiązać problem, gdy lista funkcji podatku na stronie Parametry obliczania podatku jest pusta.
author: wangchen
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: ef8158c2ada18e7d132eebbedef559b3f80ab19f
ms.sourcegitcommit: 2977e92a76211875421e608555311c363cfbdc25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2022
ms.locfileid: "8612297"
---
# <a name="empty-tax-feature-list-in-tax-calculation-parameters"></a>Pusta lista funkcji podatku w parametrach obliczania podatku

[!include [banner](../includes/banner.md)]


## <a name="symptom"></a>Objaw

Opublikowano funkcję w usłudze Regulatory Configuration Service (RCS), dzięki czemu można jej używać w Microsoft Dynamics 365 Finance. Jednak po otwarciu Finansów przejdź do **Podatek** \> **Ustawienia** \> **Konfiguracja podatku** \> **Parametry obliczania podatku** i spróbuj wybrać wartość w polu **Nazwa konfiguracji funkcji**, lista wartości jest pusta.

## <a name="reason"></a>Przyczyna

Ten problem zazwyczaj występuje, ponieważ twoje środowisko finansowe i środowisko RCS nie są w tej samej dzierżawie.

### <a name="rcs-tenant"></a>Dzierżawca RCS

Aby znaleźć identyfikator dzierżawy usługi RCS, należy wykonać następujące kroki.

1. Skopiuj pełny adres URL serwera RCS. Może to być na przykład adres URL `https://rcs-rts-sf-ed22b5aeea8-int-westus2.configure.global.int.dynamics.com/namespaces/817ff7a0-0d77-4aba-9360-3c9749e2c5de/?cmp=dat&mi=RCSFeatureDomainsWorkspace`.
2. Otwórz okno przeglądarki InPrivate, wklej adres URL z kodem RCS na pasku adresu, a następnie wybierz **Enter**. Zostanie skierowane do strony logowania, na której możesz znaleźć identyfikator dzierżawy usługi RCS. Na przykład, jeśli adres URL strony logowania to `https://login.microsoftonline.com/d335a570-a05b-4bc5-8eb3-c42c65f9560d`, identyfikator dzierżawy to informacje wyświetlane po `https://login.microsoftonline.com/` lub **d335a570-a05b-4bc5-8eb3-c42c65f9560d**.

### <a name="finance-environment-tenant-id"></a>Identyfikator najemcy środowiska finansowego

Aby znaleźć identyfikator dzierżawy dla środowiska finansowego, wykonaj te same kroki, aby znaleźć dzierżawę usługi RCS. Jednak zamiast pełnego adresu URL serwera RCS skopiuj i wklej pełny adres URL środowiska finansowego.

## <a name="resolution"></a>Rozwiązanie

Jeśli identyfikatory dwóch dzierżawców różnią się, występuje problem opisany w tym temacie. Jeśli są takie same, występuje niezwiązany problem. W takim przypadku zalecane jest skontaktowanie się z pomocą techniczną firmy Microsoft.

### <a name="solution-1"></a>Rozwiązanie 1

Zarejestruj środowisko z usługi RCS w tej samej dzierżawie, do którego jest zalogowane środowisko finansowe. Następnie utwórz i opublikuj funkcję podatku.

### <a name="solution-2"></a>Rozwiązanie 2

Udostępnij funkcję podatku dzierżawcy finansów w usługach RCS.

1. W RCS wybierz kolejno opcje **Funkcje globalizacji** \> **Obliczanie podatku**.
2. Wybierz funkcję, która ma być współużytkowana, a następnie na **karcie Organizacje** wybierz pozycję **Udostępnij**.
3. W polu **Nazwa domeny organizacji** wprowadź nazwę pliku. Na przykład wprowadź **contoso.onmicrosoft.com**.
4. Wybierz opcję **Udostępnij**.

![Rozwijane okno dialogowe Udostępnij organizacji zewnętrznej.](media/ShareTaxFeature.png)
