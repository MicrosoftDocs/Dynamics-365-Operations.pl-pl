---
title: Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii
description: W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a5f82426d87cd2e0faa0195a841899bb03f9df08
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697343"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano sposób dodawania kodu skryptów po stronie klienta do stron witryny w celu obsługi zbierania danych telemetrycznych po stronie klienta.

## <a name="overview"></a>Omówienie

Narzędzie Web Analytics jest podstawowym narzędziem, które umożliwia zrozumienie, w jaki sposób klienci współpracują z daną witryną, a następnie podejmujmowanie decyzji, które pozwolą zoptymalizować możliwości konwersji. Dostępnych jest wiele pakietów analiz sieci Web ułatwiających osiągnięcie tych celów, takich jak Google Analytics, Clicky, Moz Analytics, and KISSMetrics. Większość pakietów analiz sieci Web wymaga dodania kodu skryptu po stronie klienta w elemencie **\<head\>** kodu HTML na wszystkich stronach witryny.

> [!NOTE]
> Instrukcje przedstawione w tym temacie dotyczą również innych niestandardowych funkcji po stronie klienta, które Microsoft Dynamics 365 Commerce nie oferuje w sposób macierzysty.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Tworzenie fragmentu wielokrotnego użytku dla kodu skryptu

Po utworzeniu fragmentu kodu skryptu można go użyć do ponownego użycia na wszystkich stronach w witrynie.

1. Umożliwia przejście do **Fragmenty \> Nowy fragment strony**.
2. Wybierz opcję **Skrypt zewnętrzny**, wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.
3. W hierarchii fragmentu wybierz element podrzędny modułu **iniektora skryptu** dla właśnie utworzonego fragmentu.
4. W okienku właściwości po prawej stronie, dodaj skrypt klienta i określ inne opcje konfiguracji, tak jak są wymagane.

## <a name="add-the-fragment-to-templates"></a>Dodawanie fragmentu do szablonów

1. Przejdź do **Szablony** i otwórz szablon stron, do których chcesz dodać kod skryptu.
2. W lewym okienku rozwiń hierarchię szablonów, aby wyświetlić gniazdo **nagłówka HTML**.
3. Wybierz przycisk wielokropka (**...**) dla gniazda **nagłówka HTML**, a następnie wybierz opcję **Dodaj fragment**.
4. Umożliwia wybór fragmentu utworzonego dla kodu skryptu.
5. Zapisz szablon i zaewidencjonuj go.

> [!NOTE]
> Po zakończeniu należy opublikować fragment i szablon główny. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie logo](add-logo.md)

[Wybór motywu witryny](select-site-theme.md)

[Dodawanie ikony favicon](add-favicon.md)

[Dodawanie wiadomości powitalnej](add-welcome-message.md)

[Dodawanie powiadomienia o prawach autorskich](add-copyright-notice.md)

[Dodawanie języków do witryny](add-languages-to-site.md)

