---
title: "Inicjowanie wstępne wypełnianie danych w nowym środowisku sieci sprzedaży"
description: "W tym artykule opisano dane, który jest tworzony w ramach procesu inicjowania usługi Microsoft Dynamics 365 dla operacji - sieci sprzedaży."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 137c675781cf75d9ce621a84c89224019c161362
ms.lasthandoff: 03/31/2017


---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>Inicjowanie wstępne wypełnianie danych w nowym środowisku sieci sprzedaży

W tym artykule opisano dane, który jest tworzony w ramach procesu inicjowania usługi Microsoft Dynamics 365 dla operacji - sieci sprzedaży.

Po wdrożeniu rozwiązania Sieć sprzedaży za pomocą Microsoft Dynamics Lifecycle Services (LCS) trzeba zainicjować konfigurację sieci sprzedaży, aby utworzyć dane konfiguracji podstawowej. **Ważne:** przed zainicjowaniem konfiguracji sieci sprzedaży, upewnij się, że wybrany został język i adres pocztowy dla każdej firmy, w której konfigurujesz sklepy sieci sprzedaży. Ten krok należy wykonać dla każdej firmy używanej dla sieci sprzedaży. Aby zainicjować konfigurację sieci sprzedaży, wykonaj następujące kroki.

1.  Uruchom usługi Dynamics 365 dla operacji klienta.
2.  Kliknij **sieci sprzedaży i handlu**&gt;**Instalator Centrala**&gt;**parametry**&gt;**handlu detalicznego parametry**.
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

Ponadto oznacza to rejestrowanie związane z branży kart płatniczych (PCI) jest włączone dla usługi Dynamics 365 dla operacji bazy danych. **Uwaga:** istnieje możliwość oddzielnego skonfigurowania modułu Transfer danych. Ta opcja pozwala zresetować konfigurację transfer danych w sieci sprzedaży do ustawień domyślnych. Po zakończeniu inicjowania należy skonfigurować dodatkowe dane sieci sprzedaży. Oto kilka przykładów:

-   Parametry sieci sprzedaży
-   Parametry transferu danych w sieci sprzedaży
-   Kanały sprzedaży detalicznej
-   Kasy i urządzenia
-   Asortymenty



