---
title: Mapowanie elementów członkowskich wymiaru elementu kosztów na wspólny zestaw elementów członkowskich wymiaru
description: Poprzez mapowanie elementów członkowskich różnych wymiarów składników kosztów na wspólny zestaw takich elementów można scalić dane we wspólny format umożliwiający efektywną analizę.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember, CAMDimensionMapping
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 835a542ad5f7606f76805e54fda9f49ecc79205f
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759287"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>Mapowanie elementów członkowskich wymiaru elementu kosztów na wspólny zestaw elementów członkowskich wymiaru

[!include [banner](../includes/banner.md)]

Poprzez mapowanie elementów członkowskich różnych wymiarów składników kosztów na wspólny zestaw takich elementów można scalić dane we wspólny format umożliwiający efektywną analizę.

Jeśli pracujesz w globalnej firmie i musisz spełniać ustawowe wymagania księgowe, prawdopodobnie używasz wielu planów kont. W przypadku importowania elementów członkowskich wymiarów składników kosztów z różnych planów kont możesz otrzymać chaotycznie wyglądający zbiór różnych kont. W rzeczywistości te konta mogą mieć ten sam charakter i może istnieć możliwość ich analizowania oraz przypisywania im kosztów przy użyciu wspólnego formatu.

## <a name="map-cost-element-dimension-members-to-a-common-format"></a>Mapowanie elementów członkowskich wymiarów składników kosztów na wspólny format
W poniższym przykładzie pokazano, jak kontroler kosztów może w module Rachunek kosztów utworzyć nowy wymiar składników kosztów, który mapuje elementy członkowskie wymiarów składników kosztów ze struktur amerykańskiego planu kont i francuskiego planu kont do wspólnego zestawu elementów członkowskich wymiarów składników kosztów. Następnie wspólnego zestawu elementów członkowskich wymiarów składników kosztów można używać do analizowania danych kosztów z dwóch firm w księdze rachunku kosztów.

| Źródło: Amerykański plan kont                                          | Źródło: Francuski plan kont                                          | Nowy wspólny zestaw elementów członkowskich wymiarów składników kosztów                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| Elementy członkowskie wymiarów składników kosztów zaimportowane z amerykańskiego planu kont | Elementy członkowskie wymiarów składników kosztów zaimportowane z francuskiego planu kont | Mapowanie amerykańskich i francuskich elementów członkowskich wymiarów składników kosztów do wspólnego zestawu |
| 5001: Sprzedaż                                                           | 5001: Sprzedaż i reklama                                               | 5000: Sprzedaż i reklama                                             |
| 5030: Reklama                                                     | 6390: Zakup zapasów\*                                                    | 7000: Wydatki na sprzątanie                                                 |
| 7001: Wydatki na sprzątanie                                               | 7001: Wydatki na podróże służbowe                                                      | 7001: Wydatki na podróżne służbowe                                                   |

\*Francuski element członkowski wymiaru składników kosztów Zakup zapasów nie jest mapowany.

## <a name="currency-conversion"></a>Konwersja walut
Konfiguracja różnych używanych planów kont może określać wykorzystywanie różnych walut. W takim przypadku koniecznie określ konwersję walut, tak aby dane kosztów były przetwarzane we właściwej walucie, zgodnie z definicją w księdze rachunku kosztów, w której są używane elementy członkowskie wymiarów składników kosztów. W przykładzie powyżej jeśli w księdze rachunku kosztów są używane dolary amerykańskie (USD), należy utworzyć konwersję waluty z USD na euro (EUR) na potrzeby przetwarzania transakcji, z których wynikają mapowane elementy członkowskie wymiarów składników kosztów.

## <a name="update-mappings-at-any-time"></a>Aktualizowanie mapowań w dowolnym momencie
Definicje mapowania wymiarów składników kosztów można w każdej chwili zaktualizować. Ponieważ mapowania nie mają daty obowiązywania, zmiany zostaną zastosowane przy następnym przetwarzaniu transakcji kosztowych lub wykonywaniu obliczenia kosztów.



