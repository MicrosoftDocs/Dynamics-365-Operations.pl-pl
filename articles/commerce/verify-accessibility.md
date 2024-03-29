---
title: Weryfikowanie dostępności zawartości strony
description: W tym artykule opisano, jak zweryfikować dostępność zawartości strony w aplikacji Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: retail
ms.search.form: ''
ms.openlocfilehash: 686ec37f24cf68902c4dd918c0ca8aea7612e1a9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291981"
---
# <a name="verify-page-content-accessibility"></a>Weryfikowanie dostępności zawartości strony

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak zweryfikować dostępność zawartości strony w aplikacji Microsoft Dynamics 365 Commerce.

Po zakończeniu zmieniania strony należy upewnić się, że zawartość jest dostępna dla wszystkich użytkowników w Internecie. W narzędziach autorskich usługi Commerce można łatwo zweryfikować dostępność zawartości strony przy użyciu zintegrowanej usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/). Ta usługa weryfikuje zawartość strony względem najnowszych wskazówek dotyczących [ułatwień dostępu organizacji World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).

Integracja usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) musi być włączona na poziomie dzierżawy lub witryny, zanim będzie można jej używać.

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a>Włączanie usługi Microsoft Accessibility Insights dla wszystkich witryn w dzierżawie

Aby włączyć integrację usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) dla wszystkich witryn usługi Commerce w dzierżawie, wykonaj następujące kroki.

> [!NOTE]
> Aby uzyskać dostęp do ustawień dzierżawy, użytkownik musi być zalogowany w usłudze Commerce jako administrator systemu.

1. Zaloguj się do usługi Commerce jako administrator systemu.
1. W okienku nawigacyjnym z lewej strony wybierz pozycję **Ustawienia dzierżawy** (obok symbolu koła zębatego), aby ją rozwinąć.
1. W obszarze **Ustawienia dzierżawy** wybierz pozycję **Funkcje**.
1. Ustaw opcję **Sprawdzanie ułatwień dostępu** na **Wł.**

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a>Włączanie usługi Microsoft Accessibility Insights dla pojedynczej witryny

Aby włączyć integrację usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) dla pojedynczej witryny usługi Commerce, wykonaj następujące kroki.

1. W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).
1. W lewym okienku nawigacji wybierz pozycję **Ustawienia witryny**, aby ją rozwinąć.
1. W obszarze **Ustawienia witryny** wybierz pozycję **Funkcje**.
1. Ustaw opcję **Sprawdzanie ułatwień dostępu** na **Wł.**

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a>Weryfikowanie dostępności zawartości na stronie głównej

Aby używać zintegrowanej usługi [Microsoft Accessibility Insights](https://accessibilityinsights.io/) do skanowania i weryfikowania zawartości strony głównej w usłudze Commerce, wykonaj następujące kroki.

1. W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).
1. W okienku nawigacji po lewej stronie wybierz pozycję **Strony**.
1. Znajdź i wybierz stronę główną, aby otworzyć ją w edytorze stron.
1. Na pasku poleceń wybierz opcję **Sprawdź dostępność**. Zostanie wyświetlona strona **sprawdzania dostępności**.
1. Po zakończeniu skanowania przejrzyj zawartość raportu.
1. Jeśli dowolne testy nie powiodą się, wybierz każdy sprawdzony element z błędem, aby go rozwinąć i wyświetlić więcej szczegółów.
1. Aby zamknąć raport po zakończeniu przeglądania, przewiń w dół strony **sprawdzania dostępności** i wybierz przycisk **OK**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Modyfikacja istniejącej strony witryny](modify-existing-page.md)

[Dodawanie nowej strony witryny](add-new-page.md)

[Wybieranie układów stron](select-page-layouts.md)

[Zarządzanie metadanymi SEO](manage-seo-metadata.md)

[Zapisywanie, pogląd i publikowanie strony](save-preview-publish-page.md)

[Wzbogacanie strony produktu](enrich-product-page.md)

[Wzbogacanie strony docelowej kategorii](enrich-category-page.md)

[Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
