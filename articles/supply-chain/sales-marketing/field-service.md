---
title: Omówienie integracji z Microsoft Dynamics 365 Field Service
description: Ten artykuł zawiera omówienie integracji z programem Microsoft Dynamics 365 Field Service.
author: Henrikan
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 12a9c57e2587150914c6087c041d63af9783c1f3
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103706"
---
# <a name="integration-with-microsoft-dynamics-365-field-service-overview"></a>Omówienie integracji z Microsoft Dynamics 365 Field Service

[!include[banner](../includes/banner.md)]



Synchronizacja procesów biznesowych między rozwiązaniami Dynamics 365 Supply Chain Management i Dynamics 365 Field Service jest włączona dzięki Supply Chain Management. Scenariusze integracji konfiguruje się przy użyciu rozszerzalnych szablonów integratora danych oraz usługi Microsoft Dataverse, co umożliwia synchronizowanie procesów biznesowych.
Można używać standardowych szablonów do tworzenia niestandardowych projektów integracji, gdzie dodatkowe kolumny standardowe i niestandardowe, a także tabele, mogą być mapowane w celu skorygowania integracji i spełnienia określonych wymagań biznesowych. 

Integracja z rozwiązaniem Field Service opiera się na istniejących funkcjach Od prospekta do środków pieniężnych.

![Synchronizacja procesów biznesowych między rozwiązaniami Supply Chain Management i Field Service.](./media/field-service-integration.png)

Pierwsza faza integracji między programami Field Service i Supply Chain Management skupia się na umożliwieniu fakturowania zleceń pracy i umów z programu Field Service w programie Supply Chain Management. Obsługiwany przepływ rozpoczyna się w programie Field Service, gdzie informacje ze zleceń pracy są synchronizowane z programem Supply Chain Management jako zamówienia sprzedaży. W Supply Chain Management zamówienia sprzedaży są fakturowane w celu generowania dokumentów faktur. Ponadto informacje z faktur za umowy w programie Field Service są synchronizowane z programem Supply Chain Management. Integrator danych programu Microsoft Dynamics 365 synchronizuje dane przy użyciu konfigurowalnych projektów. Można używać standardowych szablonów do tworzenia niestandardowych projektów integracji, gdzie dodatkowe kolumny standardowe i niestandardowe, a także tabele, mogą być mapowane w celu skorygowania integracji i spełnienia określonych wymagań.

Pierwsza faza integracji między programami Field Service i Supply Chain Management umożliwia synchronizowanie następujących elementów:

- [Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Field Service](field-service-product.md)
- [Synchronizowanie zleceń pracy w rozwiązaniu Field Service z zamówieniami sprzedaży w rozwiązaniu Supply Chain Management](field-service-work-order.md)
- [Synchronizowanie faktur dotyczących umowy w rozwiązaniu Field Service z fakturami niezależnymi w rozwiązaniu Supply Chain Management](field-service-invoice.md)

Aby zobaczyć przykład jak synchronizować zlecenie produkcyjne między Field Service a Supply Chain Management, zobacz krótki film w serwisie YouTube [Jak zsynchronizować zlecenie pracy za pomocą mechanizmu integracji z rozwiązaniem Microsoft Dynamics 365](https://www.youtube.com/watch?v=46ylO7raZAo)

## <a name="integration-with-field-service-including-inventory-and-project-information"></a>Integracja z programem Field Service, w tym informacje i zapasach i projektach

Dodatkowe funkcje w tej drugiej fazie koncentrują się na zapewnieniu serwisantom w terenie informacji o zapasach z Supply Chain Management, umożliwiając im aktualizowanie poziom zapasów i przenoszenie materiałów. Ponadto firmy instalujące lub serwisujące sprzedawane towary skorzystają na lepszej kontroli i widoczności pełnego procesu sprzedaży i serwisowania z integracją z projektów.

### <a name="functionality-includes-integration-of"></a>Funkcja obejmuje integrację następujących elementów:
- Informacje o magazynie
- Informacje o bieżących zapasach
- Przeniesienie zapasów
- Korekty zapasów
- Projekty Supply Chain Management powiązane Dynamics 365 Field Service z zleceniami pracy
- Zlecenia w rozwiązaniu Dynamics 365 Field Service z łączami do projektów Supply Chain Management stosują ten numer projektu do zamówień sprzedaży , aby umożliwić fakturowanie z projektu. 

![Synchronizacja procesów biznesowych między Supply Chain Management i Field Service, w tym informacje o zapasach i projektach.](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-supply-chain-management-enables-synchronization-with-the-following-templates"></a>Druga faza integracji między programami Field Service i Supply Chain Management umożliwia synchronizowanie następujących szablonów:
- Magazyny (Supply Chain Management do Field Service) — magazyny z modułu Supply Chain Management do Field Service [zapytanie zaawansowane] 
- Zapasy produktu (Supply Chain Management do Field Service) — informacje o poziomie zapasów w Supply Chain Management do Field Service [zapytanie zaawansowane] 
- Korekta zapasów (Field Service do Supply Chain Management) — informacje o korektach zapasów w Field Service do Supply Chain Management [zapytanie zaawansowane] 
- Przeniesienie zapasów (Field Service do Supply Chain Management) — informacje o przeniesieniu zapasów w Field Service do Supply Chain Management [zapytanie zaawansowane] 
- Projekty (Supply Chain Management do Field Service) — listy projektów z Supply Chain Management do Field Service 
- Zlecenia pracy z projektem (Field Service do Supply Chain Management) - Zlecenia pracy w Field Service do zamówień sprzedaży w Supply Chain Management z obsługą projektu [Zaawansowane zapytanie] 
- Produkty Field Service z jednostką magazynową (Supply Chain Management do Sales) - „Zwolnione produkty możliwe do sprzedaży” Supply Chain Management do „Produkty” Sales dla Field Service, w tym jednostka magazynowa 

## <a name="system-requirements"></a>Wymagania systemowe

### <a name="system-requirements-for-supply-chain-management"></a>Wymagania systemowe dotyczące Supply Chain Management
Program Field Service można integrować z następującymi wersjami:

- Program Dynamics 365 for Finance and Operations w wersji 8.1.2 (grudzień 2018) został wydany w grudniu 2018 r. i ma numer kompilacji aplikacji 8.1.195 oraz aktualizację Platform Update 22 (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>Wymagania systemowe programu Field Service
Aby korzystać z rozwiązania integracyjnego Field Service, należy zainstalować następujące składniki:

- Field Service (wersja 8.2.0.286) lub nowsza wersja w programie Dynamics 365 9.1.x - z listopada 2018
- Rozwiązanie Prospekt na gotówkę (P2C) dla programu Dynamics 365, wersja 1.15.0.1 lub nowsza. To rozwiązanie jest dostępne do pobrania z usługi [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Rozwiązanie 'Field Service Integration, Project and Inventory' dla programu Dynamics 365, wersja 2.0.0.0 lub nowsza. To rozwiązanie jest dostępne do pobrania z usługi [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
