---
title: Rozszerzone filtrowanie w repozytorium RCS/globalnym
description: W tym temacie opisano ulepszone możliwości filtrowania w repozytorium globalnym RCS, które zostało udoskonalone w celu uwzględnienia dodatkowych filtrów.
author: JaneA07
manager: AnnBe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ed5a217b8844bfc76d53370ab4c4c339f5bece36
ms.sourcegitcommit: 0dcdfedec7125562f6b33deb009a3e044a1243eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2020
ms.locfileid: "3099874"
---
# <a name="enhanced-filtering-options-for-finding-configurations-in-the-global-repository"></a>Rozszerzone opcje filtrowania służące do wyszukiwania konfiguracji w repozytorium globalnym

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano ulepszone możliwości filtrowania w repozytorium globalnym Regulatory Configuration Services (RCS), które zostało udoskonalone w celu uwzględnienia następujących filtrów: 
- **Kraj/region** — na podstawie kodów krajów ISO  
- **Znaczniki** — dla obszaru funkcjonalnego/funkcji; Branż; Typu dokumentu biznesowego 

Filtry można stosować pojedynczo lub w grupach w celu wyszukiwania określonych lub powiązanych konfiguracji. Na przykład, aby znaleźć wszystkie konfigurowalne dokumenty biznesowe związane z fakturami od dostawców, można zastosować filtr **typu dokumentu biznesowego**. 

Można dodatkowo uściślić wyszukiwanie, wybierając kod kraju i klikając przycisk **Zastosuj filtr**.  

[![Sekcja filtru dla repozytorium globalnego](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

W poniższym przykładzie przedstawiono wyniki filtrowania **typu dokumentu biznesowego**. 

[![Zastosowano filtr i import dla typu dokumentu biznesowego](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

Wyniki filtrowania mogą być importowane do użytkowników RCS lub środowiska Dynamics 365 Finance pojedynczo lub jako zbiór (przez zaznaczenie grupy konfiguracji) i kliknięcie przycisku **Importuj.**






