---
title: Fantomy pozycji
description: W tym temacie szczegółowo opisano, jak typ wiersza Fantom może być wykorzystywany w wierszach listy składowej (BOM) i formule w Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 05/05/2022
ms.topic: article
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-05-05
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5c9768381d35709611e4bec3d2b7793a4d896b34
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713255"
---
# <a name="phantom-items"></a>Towary fantomowe

[!include [banner](../includes/banner.md)]

W tym temacie szczegółowo opisano, jak typ wiersza Fantom może być wykorzystywany w wierszach listy składowej (BOM) i formule.

Na ilustracji 1 (a) to BOM produktu H oraz części F i G, a (b) to arkusz marszruty dla produktu H i części F.

![Rysunek 1: BOM inżynieryjnych.](media/product-H-part-F.png)
*Rysunek 1: BOM inżynieryjnych*

Na ilustracji 1 pokazano przykład struktury BOM na dwóch poziomach. Produkt gotowy H reprezentuje produkt dla zespołu maszyny. Zespół maszyny składa się z dwóch części: jednostki elektrycznej (F) zawierającej dwa materiały (A i B) oraz grupy materiałów opakowaniowych (G), która również zawiera dwa materiały (C i D). Inny materiał (E) jest używany podczas ogólnego składania maszyny.

Ilustracja 1 reprezentuje inżynieryjną listę składową produktu H. Ta struktura dobrze pokazuje ogólny obraz części i składników tworzących cały zespół maszyny. Projektanci produktu mogą preferować przedstawianie BOM w ten sposób, ale ta struktura może nie odzwierciedlać prawidłowo sposobu, w jaki maszyna jest składana na wydziale produkcyjnym.

Na przykład inżynieryjna lista składowa na ilustracji 1 wskazuje, że jednostka elektryczna F jest składana jako oddzielna część w ramach osobnego zlecenia pracy. Jednak na wydziale produkcyjnym może się okazać, że bardziej optymalne będzie składanie jednostki elektrycznej w ramach montażu całego zespołu, a nie oddzielnego zlecenia pracy.

Ta inżynieryjna lista składowa również wskazuje, że część G jest osobną częścią. Jednak w tej strukturze część G nie reprezentuje fizycznej części, ale zbiór materiałów opakowaniowych.

W związku z tym mimo iż inżynieryjna lista składowa jest bardzo przydatna w projektowaniu produktu i bieżącym zarządzaniu projektem, może nie być najbardziej logicznym sposobem wspierania procesu wytwarzania produktu. Z drugiej strony produkcyjna lista składowa przedstawia najlepszy sposób na wytworzenie produktu.

Na ilustracji 2 pokazano, jak inżynieryjna lista BOM przekształca się w produkcyjną listę BOM. Na tej ilustracji 2 (a) to BOM dla produktu H, a (b) to arkusz marszruty dla produktu H.

![Rysunek 2. BOM produkcji.](media/product-H-part-B.png)
*Rysunek 2: BOM produkcji*

W tej strukturze widać, że nie występują części F i G, a materiały, z których składają się te części, zostały przeniesione na następny wyższy poziom w BOM.

W przeciwieństwie do inżynieryjnej listy składowej, w której istniały dwa arkusze operacji, produkcyjna lista składowa ma tylko jeden arkusz operacji. Operacja pakowania, która była połączona z częścią G, również została przeniesiona na wyższy poziom i teraz wchodzi w skład arkusza operacji dla produktu H. Zmontowanie jednostki elektrycznej jest pierwszą operacją. Taka kolejność ma duży sens, ponieważ ta jednostka jest używana w następnej operacji, czyli zmontowaniu maszyny. Ostatnią operacją jest operacja pakowania, która zużywa dwa materiały opakowaniowe (C i D).

W przejście od inżynieryjnej listy BOM do produkcyjnej listy BOM jest realizowane za pomocą typu wiersza BOM Fantom. Jak sugeruje określenie „fantom”, części F i G znikają w trakcie przekształcania typu BOM. W tym przykładzie wiersz typu Fantom jest stosowany do wierszy BOM dla części F i G w inżynieryjnej liście składowej. Podczas tworzenia zlecenia produkcyjnego lub szarży produkcyjnej inżynieryjna lista składowa jest kopiowana do tego zlecenia/szarży. Następnie podczas szacowania zlecenia następuje przejście od inżynieryjnej listy składowej do produkcyjnej listy składowej, jak pokazano na ilustracji 2. Z arkusza operacji na drugiej ilustracji 2 materiały opakowaniowe C i D są wprowadzane dla operacji.

## <a name="multilevel-phantom-bom-structures"></a>Wielopoziomowy fantomowe struktury BOM

Typ wiersza Fantom może być wykorzystywany w wielopoziomowych strukturach BOM, jak pokazano na ilustracji 3. Na ilustracji 3 (a) to BOM dla produktu G, a (b) to arkusz marszruty dla części E i F oraz produktu G.

![Rysunek 3: BOM inżynieryjnych część G.](media/product-G.png)
*Rysunek 3: BOM inżynieryjnych część G*

Ilustracja 4 pokazuje powstałą produkcyjną listę składową i arkusz marszruty, jeśli w wierszach BOM dla części E i F skonfigurowano typ wiersza Fantom. Na tej ilustracji 4 (a) to BOM dla produktu G, a (b) to arkusz marszruty dla produktu G.

![Rysunek 4. BOM produkcji część G.](media/product-G-route-sheet-G.png)
*Rysunek 4: BOM produkcji część G*

## <a name="phantom-and-route-network"></a>Fantom i sieć marszrut

Fantomowych BOM można również używać dla list składowych zawierających sieć marszrut. W sieci marszrut następuje równoległe wykonywanie jednej lub więcej operacji. Ilustracja 5 przedstawia przykład sieci marszrut używanej w wielopoziomowym BOM. Na tej ilustracji 5 (a) to BOM dla produktów G i F, a (b) to arkusz marszruty dla produktu G oraz części E i F zawierającej sieć marszrut.

![Rysunek 5: Część G BOM inżynieryjnego, sieć marszruty.](media/product-G-part-F.png)
*Rysunek 5: Część G BOM inżynieryjnego, sieć marszruty*

Na rysunku 6 (a) to BOM dla produktu G i części F, a (b) to arkusz marszruty dla produktu G i części F.

![Rysunek 6: Produkcja BOM część G, sieć marszruty.](media/product-G-part-F-with-route-sheet.png)
*Rysunek 6: Produkcja BOM część G, sieć marszruty*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]