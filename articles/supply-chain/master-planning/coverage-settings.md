---
title: Ustawienia zapotrzebowania
description: Ten temat zawiera informacje o ustawieniach zapotrzebowania, których planowanie główne używa do obliczania zapotrzebowania na towar.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538901"
---
# <a name="coverage-settings"></a>Ustawienia zapotrzebowania

[!include [banner](../includes/banner.md)]

Ustawienia zapotrzebowania są używane przez planowanie główne do obliczania zapotrzebowań na towary.

Ustawienia zapotrzebowania można określić na kilka sposobów:

- Określ ustawienia zapotrzebowania dla grupy zapotrzebowania.

    Można utworzyć grupę zapotrzebowania zawierająca ustawienia dotyczące wszystkich produktów połączonych z tą grupą zapotrzebowania. Aby utworzyć grupę zapotrzebowania, kliknij kolejno opcje **Planowanie główne &gt; Ustawienia &gt; Zapotrzebowanie &gt; Grupy zapotrzebowania**. Grupę zapotrzebowania można połączyć z produktem. Jeśli łącze jest właściwe dla oddziału, magazynu lub wymiaru produktu, użyj pola **grupa zapotrzebowania** na stronie **zapotrzebowanie na towar**. Jeśli łącze ma charakter ogólny, bez względu na wymiary produktu, należy użyć **grupy zapotrzebowania** na skróconej karcie **Plan** na stronie **Szczegóły produktu**. Domyślnie, jeśli grupa zapotrzebowania nie jest połączona z produktem, planowanie główne używa ogólnej grupy zapotrzebowania określonej na stronie **Parametry planowania głównego**.

- Określ ustawienia zapotrzebowania dla produktu.

    Ustawienia zapotrzebowania można utworzyć dla określonego produktu. Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**. Wybierz produkt, a następnie w okienku akcji na karcie **Plan** w obszarze **Grupa zapotrzebowania** wybierz **Zapotrzebowanie na towar**, aby otworzyć stronę **Zapotrzebowanie na towar**. Jeśli produkt jest połączony z grupą zapotrzebowania, ustawienia grupy zapotrzebowania można zastąpić, korzystając z pola **Zastąp**. Ustawienia zapotrzebowania na stronie**Zapotrzebowanie na towar** mają pierwszeństwo przed ustawieniami na stronie **Grupa zapotrzebowania**.

- Określ ustawienia zapotrzebowania dla produktu za pomocą kreatora.

    Kreator przeprowadzi Cię krok po kroku przez proces konfigurowania podstawowych parametrów zapotrzebowania na towar. Na stronie **Zapotrzebowanie na towar** w okienku akcji kliknij **Kreator**, aby otworzyć **Kreator zapotrzebowania na towar**.

- Określ ustawienia zapotrzebowania dla grupy wymiarów.

    Przejdź do **Zarządzanie informacjami o produktach&gt; Produkty &gt; Zwolnione produkty**. Na stronie **Szczegóły zwolnionego produktu** na skróconej karcie **Ogólne** w grupie **Administracja** kliknij łącze w polu **Grupa wymiarów magazynowania**. Na stronie **Grupy wymiarów magazynowania** zaznacz pole **Plan zapotrzebowania wg wymiaru**, aby utworzyć ustawienia zapotrzebowania dla wymiaru w grupie wymiarów magazynowania. Wszystkie wymiary produktów, takie jak konfiguracja, kolor, rozmiar, styl, muszą mieć zaznaczone pole **Plan zapotrzebowania wg wymiaru**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Plany główne](master-plans.md)
