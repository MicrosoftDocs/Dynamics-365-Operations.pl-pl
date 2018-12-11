---
title: "Konfigurowanie scenariuszy płatności za faktury"
description: "W tym temacie opisano sposób konfigurowania rozwiązania Dynamics 365 for Retail pod kątem obsługi różnych scenariuszy związanych z płatnościami za faktury."
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 3331b984693c58c6ee8c49b98ed7d3a8df5b79ff
ms.openlocfilehash: 53c4b9a9c9dac1add7021d909b2c8900d11e5c0c
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

---
# <a name="set-up-pay-invoice-scenarios"></a>Konfigurowanie scenariuszy płatności za faktury

[!include [banner](includes/banner.md)]

Funkcja Zapłać fakturę w rozwiązaniu Dynamics 365 for Retail została rozszerzona, aby obsługiwać:
- zapłatę za wiele faktur zamówienia sprzedaży w ramach pojedynczej transakcji w punkcie sprzedaży,
- płatność za różne typy faktur dla odbiorców, takie jak faktury niezależne, projektu i korygujące.

Aby te scenariusze były dostępne, należy skonfigurować profil funkcji dla sklepów zgodnie z poniższym opisem.  

1. Przejdź do opcji **Handel detaliczny > Ustawienia kanału > Ustawienia punktu sprzedaży > Profile punktów sprzedaży > Profile funkcji** i wybierz powiązany ze sklepami profil, dla którego chcesz wprowadzić zmiany.

1. Na karcie **Funkcje** skonfiguruj poniższe parametry zgodnie z potrzebami.

    - **Faktura zamówienia sprzedaży** — wybierz opcję **Tak**, aby umożliwić użytkownikom opłacenie co najmniej jednej faktury na podstawie zamówienia sprzedaży w ramach pojedynczej transakcji w punkcie sprzedaży.

    - **Faktura niezależna** — wybierz opcję **Tak**, aby umożliwić użytkownikom opłacenie co najmniej jednej faktury niezależnej w ramach pojedynczej transakcji w punkcie sprzedaży.

    - **Faktura projektu** — wybierz opcję **Tak**, aby umożliwić użytkownikom opłacenie co najmniej jednej faktury na podstawie projektu w ramach pojedynczej transakcji w punkcie sprzedaży.

    - **Faktura korygująca zamówienia sprzedaży** — wybierz opcję **Tak**, aby umożliwić użytkownikom rozliczenie wielu faktur korygujących na podstawie zamówień sprzedaży dla otwartych faktur lub przetworzyć zwrot odbiorcy dla otwartej faktury korygującej.

> [!NOTE]
> Płatność lub rozliczenie kwot częściowych nie są jeszcze obsługiwane.

