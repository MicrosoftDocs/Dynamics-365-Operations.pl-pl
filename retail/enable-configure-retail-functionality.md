---
title: "Inicjowanie danych początkowych w nowym środowisku sieci sprzedaży"
description: "W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Microsoft Dynamics 365 for Operations — Handel detaliczny."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 534c9ab0f4d95f42d09f35d3197a2258c8d39526
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>Inicjowanie danych początkowych w nowym środowisku sieci sprzedaży

[!include[banner](includes/banner.md)]


W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Microsoft Dynamics 365 for Operations — Handel detaliczny.

Po wdrożeniu rozwiązania Sieć sprzedaży za pomocą Microsoft Dynamics Lifecycle Services (LCS) trzeba zainicjować konfigurację sieci sprzedaży, aby utworzyć dane konfiguracji podstawowej. **Ważne:** przed zainicjowaniem konfiguracji sieci sprzedaży, upewnij się, że wybrany został język i adres pocztowy dla każdej firmy, w której konfigurujesz sklepy sieci sprzedaży. Ten krok należy wykonać dla każdej firmy używanej dla sieci sprzedaży. Aby zainicjować konfigurację sieci sprzedaży, wykonaj następujące kroki.

1.  Uruchom klienta programu Dynamics 365 for Operations.
2.  Kliknij kolejno opcje **Handel detaliczny i inny** &gt; **Ustawienia centrali** &gt; **Parametry** &gt; **Parametry sieci sprzedaży**.
3.  Kliknij **Inicjuj**.

Inicjowanie tworzy następujące dane ogólne konfiguracji domyślnej:

-   Zadania i podzadania transferu danych w sieci sprzedaży
-   Schemat kanału sprzedaży
-   Harmonogramy dystrybucji w sieci sprzedaży
-   Domyślne układy ekranu, które obejmują siatki przycisków, obrazy i kompozycje
-   Informacje o strefie czasowej
-   Operacje punktu sprzedaży
-   Uprawnienia punktu sprzedaży
-   Raporty kanału
-   Metadane atrybutu
-   Szablony weryfikacji jednostek
-   Zadanie wsadowe do usuwania historii sesji Commerce Data Exchange

Oprócz tego protokołowanie związane ze standardem organizacji Payment Card Industry (PCI) jest włączone dla bazy danych programu Dynamics 365 for Operations. **Uwaga:** istnieje możliwość oddzielnego skonfigurowania modułu Transfer danych. Ta opcja pozwala zresetować konfigurację transfer danych w sieci sprzedaży do ustawień domyślnych. Po zakończeniu inicjowania należy skonfigurować dodatkowe dane sieci sprzedaży. Oto kilka przykładów:

-   Parametry sieci sprzedaży
-   Parametry transferu danych w sieci sprzedaży
-   Kanały sprzedaży detalicznej
-   Kasy i urządzenia
-   Asortymenty





