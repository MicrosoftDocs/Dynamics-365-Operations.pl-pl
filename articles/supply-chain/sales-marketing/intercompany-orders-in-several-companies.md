---
title: Tworzenie międzyfirmowych zamówień zakupu i sprzedaży w kilku firmach
description: W tym temacie opisano sposób tworzenia międzyfirmowych zamówień zakupu lub sprzedaży w kilku firmach
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 8458a08c1a2e5e656c496eb74188d0e2e7257020
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673726"
---
# <a name="creating-intercompany-purchase-and-sales-orders-in-several-companies"></a>Tworzenie międzyfirmowych zamówień zakupu i sprzedaży w kilku firmach

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management nie jest ograniczony do obsługi jednej firmy produkcyjnej i kilku firm zajmujących się sprzedażą. Wszystkie firmy, które są zakładane na potrzeby intercompany, mogą być zarówno firmami handlowymi, jak i firmami produkcyjnymi.

Jeśli więcej firm może dostarczyć ten sam towar, możesz swobodnie wybierać, od kogo kupować, a aktualizacje są przetwarzane nawet wtedy, gdy jedno zamówienie sprzedaży staje się kilkoma zamówieniami zakupu.

W taki sam sposób można automatycznie tworzyć jedno międzyfirmowe zamówienie zakupu, tworzyć oryginalne zamówienie sprzedaży w firmie, a następnie to zamówienie może być realizowane przez kilka międzyfirmowym przedsiębiorstw (dostawców), tworząc więcej niż jedno międzyfirmowe zamówienia sprzedaży. Microsoft Dynamics 365 Supply Chain Management automatycznie tworzy międzyfirmowe zamówienia sprzedaży w firmach dostawców.

W tym celu wszystkie firmy muszą zostać ustawione jako relacje handlowe. Firmy dostawców muszą być ustawione w firmie Microsoft Dynamics 365 Supply Chain Management jako dostawcy międzyfirmowi i muszą być głównym dostawcą odpowiedniego towaru. W zamówieniu sprzedaży w widoku **Nagłówek** należy zaznaczyć pole **Automatycznie twórz zamówienia międzyfirmowe** oraz pole **Dostawa bezpośrednia** na skróconej karcie **Ustawienia międzyfirmowe**. Jest to ustawienie domyślne.

Wiersze sprzedaży tworzy się w zwykły sposób. Po opuszczeniu rekordu pojawi się komunikat informujący o utworzeniu międzyfirmowych zamówień zakupu i międzyfirmowych zamówień sprzedaży. Wiadomość zawiera linki do nowych zamówień. Aby wyświetlić międzyfirmowe zamówienia sprzedaży utworzone w firmach dostawców, otwórz oryginalne zamówienie sprzedaży i na karcie **Ogólne**, w grupie **Informacje pokrewne** wybierz opcję **Odwołania**.

Po otwarciu międzyfirmowych zamówień zakupu dla dostawców można zobaczyć, że Microsoft Dynamics 365 Supply Chain Management automatycznie wypełnia numer oryginalnego zamówienia sprzedaży oraz numer międzyfirmowego zamówienia sprzedaży dla każdego dostawcy.

Podobnie, jeśli otworzysz międzyfirmowe zamówienia sprzedaży dla dostawców, zobaczysz, że Microsoft Dynamics 365 Supply Chain Management automatycznie wypełnia oryginalny numer zamówienia sprzedaży i międzyfirmowy numer zamówienia zakupu dla każdego dostawcy.

> [!NOTE]
> Jeśli towary wymienione na zamówieniu istnieją w jednej z międzyfirmowych firm dostawców, ale nie ma ich w innych, system Microsoft Dynamics 365 Supply Chain Management automatycznie tworzy międzyfirmowe zamówienia dla firmy dostawcy, u którego znajduje się towar, a zatrzymuje tworzenie zamówień dla pozostałych firm. W takiej sytuacji wyświetlany jest komunikat z powiadomieniem.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
