---
title: Integracja z programem Microsoft Dynamics 365 for Field Service
description: Ten temat zawiera omówienie integracji z programem Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 02/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: efda4e39f63155785386ecec6d21973e01a0f69f
ms.sourcegitcommit: 704d273485dcdc25c97a222bc0ef0695aad334d2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2019
ms.locfileid: "770900"
---
# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a>Integracja z programem Microsoft Dynamics 365 for Field Service

[!include[banner](../includes/banner.md)]

Program Microsoft Dynamics 365 for Finance and Operations umożliwia synchronizowanie procesów biznesowych między programami Microsoft Dynamics 365 for Field Service. Scenariusze integracji konfiguruje się przy użyciu rozszerzalnych szablonów integratora danych oraz usługi Common Data Service (CDS), co umożliwia synchronizowanie procesów biznesowych.
Można używać standardowych szablonów do tworzenia niestandardowych projektów integracji, gdzie dodatkowe pola standardowe i niestandardowe, a także jednostki, mogą być mapowane w celu skorygowania integracji i spełnienia określonych wymagań biznesowych. 

Integracja z rozwiązaniem Field Service opiera się na istniejących funkcjach Od prospekta do środków pieniężnych.

![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/field-service-integration.png)

Pierwsza faza integracji między programami Field Service i Finance and Operations skupia się na umożliwieniu fakturowania zleceń pracy i umów z programu Field Service w programie Finance and Operations. Obsługiwany przepływ rozpoczyna się w programie Field Service, gdzie informacje ze zleceń pracy są synchronizowane z programem Finance and Operations jako zamówienia sprzedaży. W programie Finance and Operations zamówienia sprzedaży są fakturowane w celu wygenerowania dokumentów faktur. Ponadto informacje z faktur za umowy w programie Field Service są synchronizowane z programem Finance and Operations. Integrator danych programu Microsoft Dynamics 365 synchronizuje dane przy użyciu konfigurowalnych projektów. Można używać standardowych szablonów do tworzenia niestandardowych projektów integracji, gdzie dodatkowe pola standardowe i niestandardowe, a także jednostki, mogą być mapowane w celu skorygowania integracji i spełnienia określonych wymagań.

Pierwsza faza integracji między programami Field Service i Finance and Operations umożliwia synchronizowanie następujących elementów:

- [Produkty w programie Finance and Operations z produktami w programie Field Service zawierającymi informacje o typach produktów](field-service-product.md)
- [Zlecenia pracy w rozwiązaniu Field Service z zamówieniami sprzedaży w rozwiązaniu Finance and Operations](field-service-work-order.md)
- [Faktury w programie Field Service z fakturami niezależnymi w programie Finance and Operations](field-service-invoice.md)

Aby zobaczyć przykład jak synchronizować zlecenie produkcyjne między Field Service a Finance and Operations, zobacz krótki film w serwisie YouTube [Jak zsynchronizować zlecenie pracy za pomocą mechanizmu integracji z rozwiązaniem Microsoft Dynamics 365](https://www.youtube.com/watch?v=46ylO7raZAo)

## <a name="integration-with-microsoft-dynamics-365-for-field-service-including-inventory-and-project-information"></a>Integracja z programem Microsoft Dynamics 365 for Field Service, w tym informacje i zapasach i projektach

Dodatkowe funkcje w tej drugiej fazie koncentrują się na zapewnieniu serwisantom w terenie informacji o zapasach z Finance and Operations, umożliwiając im aktualizowanie poziom zapasów i przenoszenie materiałów. Ponadto firmy instalujące lub serwisujące sprzedawane towary skorzystają na lepszej kontroli i widoczności pełnego procesu sprzedaży i serwisowania z integracją z projektów.

### <a name="functionality-includes-integration-of"></a>Funkcja obejmuje integrację następujących elementów:
- Informacje o magazynie
- Informacje o bieżących zapasach
- Przeniesienie zapasów
- Korekty zapasów
- Projekty programu Dynamics 365 for Finance and Operations połączone ze zleceniami Dynamics 365 for Field Service
- Zlecenia w rozwiązaniu Dynamics 365 for Field Service z łączami do projektów Dynamics 365 for Finance and Operations stosują ten numer projektu do zamówień sprzedaży Dynamics 365 for Finance and Operations, aby umożliwić fakturowanie z projektu. 

![Synchronizacja procesów biznesowych między aplikacjami Finance and Operations i Field Service](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-finance-and-operations-enables-synchronization-with-the-following-templates"></a>Druga faza integracji między programami Field Service i Finance and Operations umożliwia synchronizowanie następujących szablonów:
- Magazyny (Fin and Ops do Field Service) - Magazyny z Finance and Operations do Field Service [Zaawansowane zapytanie] 
- Zapasy produktu (Fin and Ops do Field Service) - Informacje poziomu zapasów z Finance and Operations do Field Service [Zaawansowane zapytanie] 
- Korekta zapasów (Field Service do Fin and Ops) - Korekta zapasów z Field Service do Finance and Operations [Zaawansowane zapytanie] 
- Przeniesienia zapasów (Field Service do Fin and Ops) - Przeniesienia zapasów z Field Service do Finance and Operations [Zaawansowane zapytanie] 
- Projekty (Fin and Ops do Field Service) - Lista projektów z Finance and Operations do Field Service 
- Zlecenia z projektem (Field Service do Fin and Ops) - Zlecenia w Field Service do zamówień sprzedaży w Finance and Operations z obsługą projektu [Zaawansowane zapytanie] 
- Produkty Field Service z jednostką magazynową (Fin and Ops do Sales) - 'Zwolnione produkty możliwe do sprzedaży' Finance and Operations do 'Produksty' Sales dla Field Service, w tym jednostka magazynowa 

## <a name="system-requirements"></a>Wymagania systemowe

### <a name="system-requirements-for-finance-and-operations"></a>Wymagania systemowe dla rozwiązania Finance and Operations
Program Field Service można integrować z następującymi wersjami:

- Program Dynamics 365 for Finance and Operations w wersji 8.1.2 (grudzień 2018) został wydany w grudniu 2018 r. i ma numer kompilacji aplikacji 8.1.195 oraz aktualizację Platform Update 22 (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>Wymagania systemowe programu Field Service
Aby korzystać z rozwiązania integracyjnego Field Service, należy zainstalować następujące składniki:

- Field Service for Dynamics 365 (wersja 8.2.0.286) lub nowsza wersja w programie Dynamics 365 9.1.x - z listopada 2018
- Rozwiązanie Prospekt na gotówkę (P2C) dla programu Dynamics 365, wersja 1.15.0.1 lub nowsza. To rozwiązanie jest dostępne do pobrania z usługi [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Rozwiązanie 'Field Service Integration, Project and Inventory' dla programu Dynamics 365, wersja 2.0.0.0 lub nowsza. To rozwiązanie jest dostępne do pobrania z usługi [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).
