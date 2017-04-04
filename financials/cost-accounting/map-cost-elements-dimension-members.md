---
title: "Mapowania elementów członkowskich wymiaru elementu kosztów różnych wspólny zestaw elementów członkowskich wymiaru"
description: "Poprzez mapowanie elementów członkowskich różnych wymiarów składników kosztów na wspólny zestaw takich elementów można scalić dane we wspólny format umożliwiający efektywną analizę."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-11-01 13 - 45 - 07
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CAMDimension, CAMDimensionMember
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: a1e9817b6ee596ad516531d7597a2a39e115749c
ms.lasthandoff: 03/31/2017


---

# <a name="map-different-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>Mapowania elementów członkowskich wymiaru elementu kosztów różnych wspólny zestaw elementów członkowskich wymiaru

Poprzez mapowanie elementów członkowskich różnych wymiarów składników kosztów na wspólny zestaw takich elementów można scalić dane we wspólny format umożliwiający efektywną analizę.

Jeśli pracujesz w globalnej firmie i musisz spełniać ustawowe wymagania księgowe, prawdopodobnie używasz wielu planów kont. W przypadku importowania elementów członkowskich wymiarów składników kosztów z różnych planów kont możesz otrzymać chaotycznie wyglądający zbiór różnych kont. W rzeczywistości te konta mogą mieć ten sam charakter i może istnieć możliwość ich analizowania oraz przypisywania im kosztów przy użyciu wspólnego formatu.

## <a name="map-cost-element-dimension-members-to-a-common-format"></a>Mapowanie elementów członkowskich wymiarów składników kosztów na wspólny format
W poniższym przykładzie pokazano, jak kontroler kosztów może w module Rachunek kosztów utworzyć nowy wymiar składników kosztów, który mapuje elementy członkowskie wymiarów składników kosztów ze struktur amerykańskiego planu kont i francuskiego planu kont do wspólnego zestawu elementów członkowskich wymiarów składników kosztów. Następnie wspólnego zestawu elementów członkowskich wymiarów składników kosztów można używać do analizowania danych kosztów z dwóch firm w księdze rachunku kosztów.

| Źródło: Amerykański plan kont                                          | Źródło: Francuski plan kont                                          | Nowy wspólny zestaw elementów członkowskich wymiarów składników kosztów                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| Elementy członkowskie wymiarów składników kosztów zaimportowane z amerykańskiego planu kont | Elementy członkowskie wymiarów składników kosztów zaimportowane z francuskiego planu kont | Mapowanie amerykańskich i francuskich elementów członkowskich wymiarów składników kosztów do wspólnego zestawu |
| 5001: Sprzedaż                                                           | 5001: Sprzedaż i reklama                                               | 5000: Sprzedaż i reklama                                             |
| 5030: Reklama                                                     | 6390: czas zakupu\*                                                    | 7000: Wydatki na sprzątanie                                                 |
| 7001: Wydatki na sprzątanie                                               | 7001: Wydatki na podróże służbowe                                                      | 7001: Wydatki na podróżne służbowe                                                   |

\*Element członkowski wymiaru elementu francuski koszt zakupu zapasów nie jest mapowany.

## <a name="currency-conversion"></a>Konwersja walut
Konfiguracja różnych używanych planów kont może określać wykorzystywanie różnych walut. W takim przypadku koniecznie określ konwersję walut, tak aby dane kosztów były przetwarzane we właściwej walucie, zgodnie z definicją w księdze rachunku kosztów, w której są używane elementy członkowskie wymiarów składników kosztów. W przykładzie powyżej jeśli w księdze rachunku kosztów są używane dolary amerykańskie (USD), należy utworzyć konwersję waluty z USD na euro (EUR) na potrzeby przetwarzania transakcji, z których wynikają mapowane elementy członkowskie wymiarów składników kosztów.

## <a name="update-mappings-at-any-time"></a>Aktualizowanie mapowań w dowolnym momencie
Definicje mapowania wymiarów składników kosztów można w każdej chwili zaktualizować. Ponieważ mapowania nie mają daty obowiązywania, zmiany zostaną zastosowane przy następnym przetwarzaniu transakcji kosztowych lub wykonywaniu obliczenia kosztów.


