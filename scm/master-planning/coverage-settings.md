---
title: Ustawienia zapotrzebowania
description: "Ustawienia zapotrzebowania są używane przez planowanie główne do obliczania zapotrzebowań na towary."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b42f0515823bd42ec260aa1d175855a923162b62
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="coverage-settings"></a>Ustawienia zapotrzebowania

[!include[banner](../includes/banner.md)]


Ustawienia zapotrzebowania są używane przez planowanie główne do obliczania zapotrzebowań na towary. 

Ustawienia zapotrzebowania można określić na kilka sposobów:

-   Określ ustawienia zapotrzebowania dla grupy zapotrzebowania. Można utworzyć grupę zapotrzebowania zawierająca ustawienia dotyczące wszystkich produktów połączonych z tą grupą zapotrzebowania. Aby utworzyć grupę zapotrzebowania, kliknij kolejno opcje **Planowanie główne &gt; Ustawienia &gt; Zapotrzebowanie &gt; Grupy zapotrzebowania**. Grupę zapotrzebowania można połączyć z produktem. Jeśli łącze jest właściwe dla oddziału, magazynu lub wymiaru produktu, użyj pola **grupa zapotrzebowania** na stronie **zapotrzebowanie na towar**. Jeśli łącze ma charakter ogólny, bez względu na wymiary produktu, należy użyć **grupy zapotrzebowania** na skróconej karcie **Plan** na stronie **Szczegóły produktu**. Jeśli grupa zapotrzebowania nie jest połączona z produktem, planowanie główne używa **ogólnej grupy zapotrzebowania** określonej na stronie **Parametry planowania głównego** jako domyślna.

-   Określ ustawienia zapotrzebowania dla produktu. Ustawienia zapotrzebowania można utworzyć dla określonego produktu. Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty &gt; Zwolnione produkty**. Wybierz produkt, a następnie w **okienku akcji** na karcie **Plan** w obszarze **Grupa zapotrzebowania** kliknij przycisk **Zapotrzebowanie na towar**, aby otworzyć stronę **Zapotrzebowanie na towar**. Jeśli produkt jest połączony z grupą zapotrzebowania, ustawienia grupy zapotrzebowania można zastąpić, korzystając z pola **Zastąp**. Ustawienia zapotrzebowania na stronie**Zapotrzebowanie na towar** mają pierwszeństwo przed ustawieniami na stronie **Grupa zapotrzebowania**.

<!-- -->

-   Określ ustawienia zapotrzebowania dla produktu za pomocą kreatora. Kreator prowadzi krok po kroku przez procedurę konfiguracji podstawowych parametrów zapotrzebowania na towar. Na stronie **Zapotrzebowanie na towar** kliknij **Kreator**, aby otworzyć **Kreator zapotrzebowania na towar**.

<!-- -->

-   Określ ustawienia zapotrzebowania dla grupy wymiarów. Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Wspólne &gt; Zwolnione produkty**. Na stronie **Szczegóły zwolnionego produktu** na karcie **Ogólne** w grupie **Administracja** kliknij łącze **Grupa wymiarów magazynowania**. Na stronie **Grupa wymiarów magazynowania** wybierz pole **Plan zapotrzebowania wg wymiaru**, aby utworzyć ustawienia zapotrzebowania dla wymiaru w grupie wymiarów magazynowania. Wszystkie wymiary produktów, takie jak konfiguracja, kolor, rozmiar, styl, muszą mieć zaznaczone pole **Plan zapotrzebowania wg wymiaru**.



<a name="see-also"></a>Informacje dodatkowe
--------

[Plany główne](master-plans.md)




