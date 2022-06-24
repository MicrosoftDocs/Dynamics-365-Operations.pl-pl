---
title: Rozszerzone filtrowania RCS w repozytorium RCS/globalnym
description: W tym artykule opisano ulepszone możliwości filtrowania w repozytorium globalnym RCS, które zostało udoskonalone w celu uwzględnienia dodatkowych filtrów.
author: JaneA07
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: a343b9f1af68a727cb2a8d1e390f85e10aab2d39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901220"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>Rozszerzone z RCS opcje filtrowania służące do wyszukiwania konfiguracji w RCS/repozytorium globalnym

[!include [banner](../includes/banner.md)]

W tym artykule opisano ulepszone możliwości filtrowania w repozytorium globalnym Regulatory Configuration Services (RCS), które zostało udoskonalone w celu uwzględnienia możliwości filtrowania następujących kryteriów: 
- **Kraj/region** — Na podstawie kodów krajów ISO  
- Typy **Znaczników** dla:
  - Obszar funkcjonalny
  - Obszar funkcji
  - Branża 
  - Dokument biznesowy 

Aby ułatwić odkrywanie określonych lub powiązanych konfiguracji, można zastosować filtry, pojedynczo lub jako grupę. Aby na przykład znaleźć pojedynczy typ dokumentów biznesowych, które są związane z fakturami od dostawców, można zastosować filtr **Typu dokumentu biznesowego** w celu wyszukania tego typu dokumentu. 

[![Sekcja filtru dla repozytorium globalnego.](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

Można dodatkowo uściślić wyszukiwanie, wybierając typ dokumentu, na przykład „faktura od dostawcy”, i klikając przycisk **Zastosuj filtr**. W poniższym przykładzie przedstawiono wyniki filtrowania **typu dokumentu biznesowego** z dodanym typem dokumentu. 

[![Zastosowano filtr i import dla typu dokumentu biznesowego.](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

Przefiltrowane wyniki mogą być importowane do repozytorium RCS lub środowiska Dynamics 365 Finance albo indywidualnie, albo jako zbiór. W tym celu należy wybrać grupę konfiguracji i kliknąć przycisk **Importuj**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]