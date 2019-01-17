---
title: "Inicjowanie danych początkowych w nowych środowiskach rozwiązania Retail"
description: "W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 52f0c52748958f0bebb6c40df01cfac10c0ed427
ms.contentlocale: pl-pl
ms.lasthandoff: 01/04/2019

---

# <a name="initialize-seed-data-in-new-retail-environments"></a>Inicjowanie danych początkowych w nowych środowiskach rozwiązania Retail

[!include [banner](includes/banner.md)]

W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Microsoft Dynamics 365 for Retail.

Po wdrożeniu rozwiązania Sieć sprzedaży za pomocą Microsoft Dynamics Lifecycle Services (LCS) trzeba zainicjować konfigurację sieci sprzedaży, aby utworzyć dane konfiguracji podstawowej.

> [!IMPORTANT]
> Przed zainicjowaniem konfiguracji sieci sprzedaży, upewnij się, że wybrany został język i adres pocztowy dla każdej firmy, w której konfigurujesz sklepy sieci sprzedaży. Ten krok należy wykonać dla każdej firmy używanej dla sieci sprzedaży.

Aby zainicjować konfigurację sieci sprzedaży, wykonaj następujące kroki.

1. Uruchom klienta programu Dynamics 365 for Retail.
2. Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia centrali** &gt; **Parametry** &gt; **Parametry sieci sprzedaży**.
3. Kliknij **Inicjuj**.

Inicjowanie tworzy następujące dane ogólne konfiguracji domyślnej:

- Zadania i podzadania transferu danych w sieci sprzedaży
- Schemat kanału sprzedaży
- Harmonogramy dystrybucji w sieci sprzedaży
- Domyślne układy ekranu, które obejmują siatki przycisków, obrazy i kompozycje
- Informacje o strefie czasowej
- Operacje punktu sprzedaży
- Uprawnienia punktu sprzedaży
- Raporty kanału
- Metadane atrybutu
- Szablony weryfikacji jednostek
- Zadanie wsadowe do usuwania historii sesji Commerce Data Exchange

Oprócz tego protokołowanie związane ze standardem organizacji Payment Card Industry (PCI) jest włączone dla bazy danych programu Dynamics 365 for Retail.

> [!NOTE]
> Istnieje możliwość oddzielnego skonfigurowania modułu Transfer danych. Ta opcja pozwala zresetować konfigurację transfer danych w sieci sprzedaży do ustawień domyślnych.

Po zakończeniu inicjowania należy skonfigurować dodatkowe dane sieci sprzedaży. Oto kilka przykładów:

- Parametry sieci sprzedaży
- Parametry transferu danych w sieci sprzedaży
- Kanały sprzedaży detalicznej
- Kasy i urządzenia
- Asortymenty

