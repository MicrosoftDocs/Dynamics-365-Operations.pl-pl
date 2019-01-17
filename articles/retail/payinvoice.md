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
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: b7132dc9b3c78fa04fcfc38ea72b5678ad08deb2
ms.contentlocale: pl-pl
ms.lasthandoff: 01/04/2019

---
# <a name="set-up-pay-invoice-scenarios"></a>Konfigurowanie scenariuszy płatności za faktury

[!include [banner](includes/banner.md)]

Funkcja Zapłać fakturę w rozwiązaniu Dynamics 365 for Retail została rozszerzona, aby obsługiwać:

- zapłatę za wiele faktur zamówienia sprzedaży w ramach pojedynczej transakcji w punkcie sprzedaży,
- płatność za różne typy faktur dla odbiorców, takie jak faktury niezależne, projektu i korygujące.

Aby te scenariusze były dostępne, należy skonfigurować profil funkcji dla sklepów zgodnie z poniższym opisem.

1. Przejdź do opcji **Handel detaliczny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji** i wybierz powiązany ze sklepami profil, dla którego chcesz wprowadzić zmiany.
2. Na karcie **Funkcje** skonfiguruj poniższe parametry zgodnie z potrzebami.

    - **Faktura zamówienia sprzedaży** — wybierz opcję **Tak**, aby umożliwić użytkownikom opłacenie co najmniej jednej faktury utworzonej na podstawie zamówienia sprzedaży w ramach pojedynczej transakcji w punkcie sprzedaży.
    - **Faktura niezależna** — wybierz opcję **Tak**, aby umożliwić użytkownikom opłacenie co najmniej jednej faktury niezależnej w ramach pojedynczej transakcji w punkcie sprzedaży.
    - **Faktura projektu** — wybierz opcję **Tak**, aby umożliwić użytkownikom opłacenie co najmniej jednej faktury utworzonej na podstawie projektu w ramach pojedynczej transakcji w punkcie sprzedaży.
    - **Faktura korygująca zamówienia sprzedaży** — wybierz opcję **Tak**, aby umożliwić użytkownikom rozliczenie wielu faktur korygujących na podstawie zamówień sprzedaży dla otwartych faktur lub przetworzyć zwrot dla odbiorcy na podstawie otwartej faktury korygującej.

> [!NOTE]
> Płatność lub rozliczenie kwot częściowych nie są jeszcze obsługiwane.

