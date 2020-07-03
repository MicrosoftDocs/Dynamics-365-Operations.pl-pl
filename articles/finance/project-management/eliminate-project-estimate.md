---
title: Eliminowanie szacowania projektu
description: Ten temat zawiera informacje dotyczące eliminowania szacowania projektu po jego zakończeniu.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410254"
---
# <a name="eliminate-a-project-estimate"></a>Eliminowanie szacowania projektu

[!include [banner](../includes/banner.md)]

Szacowania projektu zapewniają informacje finansowe dla pracy, która jest szacowana i planowana dla projektu. Aby wykorzystywać szacowania dla projektu, należy dołączyć projekt do projektu szacunkowego. Projekt szacunkowy jest zawsze oparty na istniejącym projekcie, jednak wiele projektów może odnosić się do jednego projektu szacunkowego. Tylko projekty o stałej cenie i inwestycje mogą być dołączone do projektów szacunkowych, a projekty te muszą należeć do tej samej grupy projektów, co projekt szacunkowy.

Aby wyeliminować projekt szacunkowy, musi on być ukończony. Poniższe kroki wyjaśniają, jak wyeliminować szacowanie.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** > **Wszystkie projekty** i otworzyć projekt. 
2. Na karcie **Zarządzanie** wybierz opcję **Szacowanie**, a następnie na stronie **Szacowanie** wybierz pozycję **Eliminacja**.
3. Na stronie **Eliminuj oszacowania** na karcie **Ogólne** określ następujące opcje:

   - **Kod okresu**: Umożliwia wybór kodu okresu pozwalającego na wybór odpowiednich projektów szacowanych. 
   - **Data szacowania**: Umożliwia wybór daty szacowania do usunięcia.
   - **Eliminuj z ostrzeżeniami PWT**: Włącz tę opcję, aby zapewnić powiadamianie, gdy szacowanie, które jest skojarzone z pracą w toku (PWT) zostanie wyeliminowane. Jeśli ta opcja nie jest włączona, nie można kontynuować eliminacji, jeśli istnieją nieoszacowane transakcje. 
   > [!NOTE]
   > Ta opcja jest dostępna tylko wtedy, gdy do projektu szacowanego zastosowano eliminację. Jest ona niedostępna w przypadku korzystania z księgowania okresowego. To ustawienie działa z ustawieniami na karcie **Szacowanie** na stronie **Parametry projektu** w grupie pól **Zezwalaj na eliminacje, gdy istnieją nieoszacowane transakcje**.
   - **Określ etap jako zakończony**: Włącz tę opcję, aby po uruchomieniu eliminacji ustawić etap projektu szacunkowego na **Zakończone**.
   - **Wydrukuj listę szacunkową**: Umożliwia wybór informacji, które będą uwzględniane podczas drukowania listy szacunkowej.
   - **Wyświetl dziennik informacyjny**: Włącz tę opcję, aby wyświetlić dziennik informacyjny.
   - **Data księgowania**: Należy wybrać datę księgowania w księdze.

4.  Kliknij przycisk **OK**.
5. Po zakończeniu procesu eliminacji zostanie wyświetlony usunięty projekt szacunkowy z wartością ujemną. 

Jeśli nie zamierzasz wyeliminować oszacowania, możesz wybrać wyeliminowane oszacowanie i wybrać pozycję **Wycofanie eliminacji**.   
