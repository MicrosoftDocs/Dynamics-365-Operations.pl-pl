---
title: Połączone aplikacje
description: W tym artykule wyjaśniono, jak skonfigurować połączone aplikacje w fakturowaniu elektronicznym.
author: gionoder
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: aa6c80914301cc0403974a6acc5e95ff61c9c1a7
ms.sourcegitcommit: a5a4c45bb265758c6e5c3483c8552503b1799a89
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2022
ms.locfileid: "9524697"
---
# <a name="connected-applications"></a>Połączone aplikacje

[!include [banner](../includes/banner.md)]

Połączone aplikacje to wystąpienia Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management, do których możesz chcieć uzyskać dostęp za pośrednictwem Regulatory Configuration Service (RCS). Za pośrednictwem połączonych aplikacji można skonfigurować część funkcji globalizacji w programie Finance lub Supply Chain Management, aby umożliwić działanie scenariusza fakturowania elektronicznego.

Po wdrożeniu funkcji globalizacji informacje o konfiguracji, które mają zastosowanie do aplikacji Finance lub Supply Chain Management, mogą być publikowane bezpośrednio z RCS w odpowiedniej połączonej aplikacji.

Dostępność parametrów Finance lub Supply Chain Management w RCS jest przydatna, gdy masz kilka środowisk aplikacji, takich jak testy akceptacji użytkownika (UAT) i środowiska produkcyjne, i chcesz zachować spójność konfiguracji, wdrażając te same parametry w różnych środowiskach.

## <a name="create-a-connected-application"></a>Utwórz połączoną aplikację

1. Zaloguj się do swojego konta RCS.
2. W obszarze roboczym **Funkcja globalizacji**, w obszarze **Powiązane łącza** wybierz **Konfiguracja środowiska**.
3. Na stronie **Konfiguracja środowiska** w okienku akcji wybierz pozycję **Połączone aplikacje**.
4. Wybierz pozycję **Nowy**, aby utworzyć połączoną aplikację.
5. W polu **Nazwa** wprowadź nazwę aplikacji do połączenia.
6. W polu **Typ** zaznacz opcję **Dynamics 365 Finance**.
7. W polu **Zastosowanie** wprowadź URL środowiska do połączenia.
8. W polu **Dzierżawca** wpisz najemcę środowiska.
9. Wybierz opcję **Zapisz**.
10. W okienku akcji wybierz opcję **Sprawdź połączenie**, aby przetestować połączenie ze środowiskiem. Następnie zamknij stronę.

## <a name="link-connected-applications-to-environments"></a>Połącz połączone aplikacje ze środowiskami

1. Na stronie **Konfiguracja środowiska** wybierz pozycję **Nowy**, aby przypisać połączoną aplikację do środowiska.
2. W polu **Połączona aplikacja** wybierz połączoną aplikację.
3. W polu **Środowisko usługi** wybierz środowisko usługi.
4. Wybierz przycisk **Zapisz** i zamknij stronę.
