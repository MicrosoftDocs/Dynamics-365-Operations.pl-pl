---
title: Tworzenie wymiarów i importowanie członków wymiaru
description: Rachunek kosztów to niezależny moduł, który wymaga danych głównych z innych modułów.
author: ShylaThompson
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 575b27de845d931c990b1d19254b5218fa6e4199
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770857"
---
# <a name="create-dimensions-and-import-dimension-members"></a>Tworzenie wymiarów i importowanie członków wymiaru

[!include [banner](../includes/banner.md)]

Rachunek kosztów to niezależny moduł, który wymaga danych z innych modułów. Te dane są podzielone na następujące kategorie:

-  Składniki kosztów
-  Obiekty kosztów
-  Wymiary statystyczne

**Składnik kosztu** odnosi się do elementu istotnego dla kosztów w planie kont. **Obiekt kosztów** odpowiada dowolnemu typowi wymiaru finansowego, takiego jak produkty, centra kosztów i projekty, które chcesz oszacować, przydzielić do nich koszty lub zmierzyć bezpośrednio. **Wymiar statystyczny** i jego elementy są używane do rejestrowania wpisów niepieniężnych. Elementy członkowskie wymiaru statystycznego mogą służyć jako podstawa alokacji w dystrybucji i alokacji kosztów 

Poniższy schemat przedstawia wymiary, które są używane w module Rachunek kosztów.

[![Wymiary rachunku kosztów](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)

Po zaimportowaniu danych do modułu Rachunek kosztów można ich użyć do tworzenia różnych perspektyw zapewniających informacje menedżerom na wszystkich poziomach organizacji. Poniższe tematy zawierają informacje dotyczące tworzenia wymiarów i importowania elementów wymiarów. 

-  [Wymiary składników kosztów](cost-elements.md)
-  [Tworzenie składników kosztu](./tasks/create-cost-elements.md)
-  [Wymiary obiektów kosztów](cost-objects.md)
-  [Mapowanie elementów członkowskich wymiaru elementu kosztów na wspólny zestaw elementów członkowskich wymiaru](map-cost-elements-dimension-members.md)
-  [Mapowanie wymiaru składnika kosztu](./tasks/map-cost-element-dimension.md)
-  [Elementy członkowskie wymiaru statystycznego i szablony dostawców miar statystycznych](statistical-measure-provider-template.md)






