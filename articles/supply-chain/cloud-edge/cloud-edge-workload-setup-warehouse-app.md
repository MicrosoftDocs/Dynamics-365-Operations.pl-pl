---
title: Konfiguracja aplikacji mobilnej Warehouse Management do zarządzania jednostkami skali chmury i brzegowymi
description: Ten temat wyjaśnia, jak skonfigurować aplikacje mobilne Warehouse Management dla magazynów, które są obsługiwane przez chmurę lub jednostkę brzegową.
author: perlynne
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 1fa00b40db2f6246029876964dca9d3229567848
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071660"
---
# <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>Konfiguracja aplikacji mobilnej Warehouse Management do zarządzania jednostkami skali chmury i brzegowymi

[!include [banner](../includes/banner.md)]

Ten temat wyjaśnia, jak skonfigurować aplikacje mobilne Warehouse Management, aby mogły być używane przez magazyny, które są obsługiwane przez chmurę lub jednostkę brzegową.

## <a name="prerequisites"></a>Wymagania wstępne

Zanim zaczniesz konfigurować swoje urządzenia mobilne, aby łączyły się z chmurą lub jednostką brzegową, sprawdź, czy mogą się one połączyć z hubem przedsiębiorstwa. Aby uzyskać więcej informacji, zobacz temat [Instalowanie i łączenie aplikacji mobilnej Warehouse Management](../warehousing/install-configure-warehouse-management-app.md).

## <a name="additional-setup-when-you-run-the-warehouse-management-mobile-app-against-a-scale-unit"></a>Dodatkowe ustawienia podczas uruchamiania aplikacji mobilnej Warehouse Management na jednostce skalowania

W ramach [procesu wdrażania obciążeń jednostek skalowania magazynu](cloud-edge-landing-page.md#scale-unit-manager-portal) większość danych, które są wymagane do podłączenia urządzeń aplikacji mobilnej Warehouse Management, jest automatycznie synchronizowana z węzła przedsiębiorstwa do jednostki skalowania. Musisz jednak wprowadzić te dane na stronie **Aplikacje Azure Active Directory** (**Administracja systemu \> Konfiguracja \> Aplikacje Azure Active Directory**) we wdrożeniu jednostki skalowania. Dodatkowo, być może będziesz musiał zaktualizować domyślną wartość **Firmy** dla ID użytkownika lub stworzyć nowego użytkownika. Użytkownicy powiązani z firmą, która nie istnieje na wdrożeniu jednostki wagi, nie będą mogli się zalogować, gdy aplikacja mobilna Warehouse Management jest połączona z tą jednostką wagi.

> [!NOTE]
> Ponieważ dane na stronie **Aplikacje Azure Active Directory** nie są zsynchronizowane, trzeba ręcznie zachować te dane, jeśli chcesz przenieść obciążenia pracą magazynu do innej jednostki skalowania.

Pamiętajcie, że w ramach konfiguracji połączenia każdej aplikacji mobilnej Warehouse Management, podany adres URL zasobów Azure Active Directory musi być dla jednostki skalowania, a nie dla węzła korporacyjnego.
