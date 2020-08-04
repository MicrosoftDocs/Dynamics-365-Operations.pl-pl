---
title: Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Commerce
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: aa18e7446a72a907fcad70f92ea529088b6cecbd
ms.sourcegitcommit: 83c7e5ab54c1cad2e21e33769cc524cfa4213f58
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/07/2020
ms.locfileid: "3539886"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Usunięte lub wycofane funkcje w aplikacji Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia z Dynamics 365 Commerce.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

> [!NOTE]
> Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Commerce 10.0.11
### <a name="data-action-hooks"></a>Punkty zaczepienia akcji danych
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Funkcja punktów zaczepienia akcji danych została zaniechana z powodu problemów z wydajnością. |
| **Zamieniona przez inną funkcję?**   | Zalecamy użycie [zastąpień akcji danych](../e-commerce-extensibility/data-action-overrides.md) do modyfikowania logiki biznesowej w warstwie akcji danych.|
| **Powiązane obszary produktów**         | Działania na danych dotyczących rozszerzalności handlu elektronicznego |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Wycofane: począwszy od wydania 10.0.11 |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Obsługa modułu Retail SDK dla Visual Studio 2015, msbuild 14,0 i SDK\Reference biblioteki i narzędzia sieci sprzedaży
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Obsługa modułu Retail SDK dla Visual Studio 2015 została zaniechana i zaktualizowana w celu obsługi a 2017, msbuild 15.0 oraz wszystkie biblioteki referencyjne i narzędzia generatora generatora serwerów commerce w folderze RetailSDK\References są przenoszone do pakietów NuGet w celu uproszczenia modelu rozszerzeń i procesu uaktualniania zestawu SDK.|
| **Zamieniona przez inną funkcję?**   | Zaleca się, aby informacje zawarte w [ramach migracji zestawu Retail SDK z Visual Studio 2015 do Visual Studio 2017](../dev-itpro/retail-sdk/migrate-sdk.md) zostały zaktualizowane w systemie. |
| **Powiązane obszary produktów**         | Rozszerzenia zestawu Retail SDK |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Wycofane: począwszy od wydania 10.0.11 |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Rozszerzenie serwera Retail Server przy użyciu IEdmModelExtender i CommerceController
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Rozszerzenie serwera Retail korzystające z IEdmModelExtender i CommerceController zostało zastąpione w celu zapewnienia uproszczonego modelu rozszerzeń. Nowa implementacja będzie mieć tylko klasę kontrolera bez dodatkowej implementacji klasy IEdmModelExtender. Pozwala to również uniknąć zależności z określoną wersją protokołu OData (jeśli wersja protokołu OData jest zaktualizowana, może spowodować przerwanie rozszerzeń). |
| **Zamieniona przez inną funkcję?**   |  Zaleca się korzystanie z modelu rozszerzeń klasy IController przez zaimportowanie pakietu NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Powiązane obszary produktów**         | Rozszerzania usługi Retail Server |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Wycofane: począwszy od wydania 10.0.11 |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Rozszerzenie Hardware station za pomocą IHardwareStationController
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Rozszerzenie Hardware station używające IHardwareStationController jest przestarzałe, aby zapewnić uproszczony model rozszerzeń. Nowa implementacja będzie mieć tylko klasę IController bez dodatkowej implementacji klasy i aby uniknąć współzależności z podstawowymi bibliotekami stacji sprzętowych, zanim wcześniej rozszerzenie musi odwoływać się do wielu bibliotek.) |
| **Zamieniona przez inną funkcję?**   | Zalecamy korzystanie z modelu rozszerzeń klasy IController przez zaimportowanie pakietu NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Powiązane obszary produktów**         | Rozszerzania aplikacji Hardware Station |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Wycofane: począwszy od wydania 10.0.11 |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Commerce 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Operacja punktu sprzedaży 803 — pobranie i przyjęcie
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Operacje pobrania i przyjęcia są uznawane za przestarzałe z powodu zmian w projekcie nowej operacji. |
| **Zamieniona przez inną funkcję?**   | Tak. Zastępują je dwie nowe operacje punktu sprzedaży: operacja przychodząca (804) i operacja wychodząca (805).|
| **Powiązane obszary produktów**         | Aplikacja punktu sprzedaży |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: od wydania 10.0.10 operacja pobrania i przyjęcia nie będzie już otrzymywać żadnych nowych aktualizacji funkcji. W przyszłych wersjach dla tej operacji będą przeprowadzane tylko krytyczne poprawki usterek. Wszystkich klientów zachęcamy do przejścia do nowych [operacji przychodzących](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) i [operacji wychodzących](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), które będą w dalszym ciągu częścią naszego długoterminowego planu rozwoju produktu. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Usunięte lub przestarzałe funkcje w wydaniu rozwiązania Commerce 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>Interfejsy API rozwiązania Commerce GetProductAvailabilities i GetAvailableInventoryNearby
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Utworzono nowe zoptymalizowane interfejsy API w celu zastąpienia interfejsów API GetProductAvailabilities i GetAvailableInventoryNearby. |
| **Zamieniona przez inną funkcję?**   | Tak: zastępowane przez interfejsy API GetEstimatedAvailability i GetEstimatedProductWarehouseAvailability. |
| **Powiązane obszary produktów**         | Zestaw SDK aplikacji handlu elektronicznego |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Przestarzałe: w przypadku wydania 10.0.7 nie będą już obsługiwane inwestycje inżynieryjne dotyczące interfejsów API GetProductAvailabilities i GetAvailableInventoryNearby. Organizacje korzystające z tych interfejsów API we wdrożeniach handlu elektronicznego należy przekonwertować na nowe interfejsy API GetEstimatedAvailability i GetEstimatedProductWarehouseAvailability oraz włączyć [funkcję obliczania zoptymalizowanej dostępności produktów](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach
Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).
