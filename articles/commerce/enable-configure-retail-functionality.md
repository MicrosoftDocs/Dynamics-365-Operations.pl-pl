---
title: Inicjowanie danych początkowych w nowych środowiskach rozwiązania Retail
description: W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: e2833c32d557ec3d2dc80808222d1d47860ce6ea
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023718"
---
# <a name="initialize-seed-data-in-new-retail-environments"></a>Inicjowanie danych początkowych w nowych środowiskach rozwiązania Retail

[!include [banner](includes/banner.md)]

W tym artykule opisano dane, które są tworzone w ramach procesu inicjowania w programie Dynamics 365 Commerce.

Po wdrożeniu rozwiązania Commerce sprzedaży za pomocą Microsoft Dynamics Lifecycle Services (LCS) trzeba zainicjować konfigurację sieci sprzedaży Commerce, aby utworzyć dane konfiguracji podstawowej.

> [!IMPORTANT]
> Przed zainicjowaniem konfiguracji handlowej, upewnij się, że wybrany został język i adres pocztowy dla każdej firmy, w której konfigurujesz sklepy sieci sprzedaży. Ten krok należy wykonać dla każdej firmy używanej dla handlu.

Aby zainicjować konfigurację, wykonaj następujące kroki.

1. Uruchom klienta rozwiązania Commerce.
2. Wybierz kolejno opcje **Ustawienia handlu i inne** &gt; **Ustawienia Headquarters** &gt; **Parametry** &gt; **Parametry Commerce**.
3. Kliknij **Inicjuj**.

Inicjowanie tworzy następujące dane ogólne konfiguracji domyślnej:

- Zadania i podzadania transferu danych w Commerce
- Schemat kanału handlowego
- Harmonogramy dystrybucji Commerce
- Domyślne układy ekranu, które obejmują siatki przycisków, obrazy i kompozycje
- Informacje o strefie czasowej
- Operacje punktu sprzedaży
- Uprawnienia punktu sprzedaży
- Raporty kanału
- Metadane atrybutu
- Szablony weryfikacji jednostek
- Zadania wsadowego do usuwania historii sesji Commerce Data Exchange

Oprócz tego logowanie związane z branżą kart płatności (PCI) jest włączone dla bazy danych Commerce.

> [!NOTE]
> Istnieje możliwość oddzielnego skonfigurowania modułu Harmonogram Commerce. Ta opcja pozwala zresetować konfigurację Harmonogramu Commerce w sieci sprzedaży do ustawień domyślnych.

Po zakończeniu inicjowania należy skonfigurować dodatkowe dane handlowe. Oto kilka przykładów:

- Parametry handlu
- Parametry handlu harmonogramu
- Kanały Commerce
- Kasy i urządzenia
- Asortymenty
