---
title: Ustawianie unikatowości ogranicznika planu kont
description: W tym temacie wyjaśniono, dlaczego nie można mieć tego samego separatora dla planu kont i wartości wymiarów. Po uaktualnieniu należy zmienić wartości separatora.
author: panolte
ms.date: 04/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6081a62077f1fc6b6920991ed6faae667c25a47c
ms.sourcegitcommit: e8a2a1e34fa48a42afac9724828f4ec72b6d7085
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2022
ms.locfileid: "8573626"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Ustawianie unikatowości ogranicznika planu kont

[!include [banner](../includes/banner.md)]

W Microsoft Dynamics AX 2012 można używać tego samego separatora dla planu kont i wartości wymiarów. W obecnej wersji aplikacji finansowych i operacyjnych nie można mieć tego samego separatora dla planu kont i wartości lub nazw wymiarów. W razie istnienia zduplikowanych separatorów można je zmienić po uaktualnieniu. 

## <a name="update-delimiter"></a>Aktualizacja separatora
Jeśli występuje konflikt z planem kont, można zmienić separator planu kont i format identyfikatora projektu/podprojektu. Nie można zmieniać żadnych innych separatorów wymiarów. 
- Separator planu kont można zmienić po uaktualnieniu ustawieniu **Parametry księgi głównej** > **Plan kont i wymiary** > **Zmień separator**. 
- Jeśli jedyny konflikt występuje z formatem identyfikatora projektu/podprojektu, można zmienić tę wartość w ustawieniu **Parametry modułu Zarządzanie projektami i ich księgowanie** > **Ogólne** > **Modyfikuj format podprojektu**. 

### <a name="other-considerations"></a>Inne uwagi
Podobnie jak identyfikator projektu/podprojektu, wszelkie inne rekordy danych główne używane jako wymiary finansowe, takie jak dostawcy lub odbiorcy, nie powinny mieć wartości identyfikatorów kont, które używają tego samego znaku co ogranicznik plan kont. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Jak ustalić, czy środowisko wymaga aktualizacji separatorów 
Jeśli separatory w uaktualnionym środowisku powodują konflikt, może występować niestabilność podczas wprowadzania wartości w formancie wpisu podzielonego na segmenty lub formacie wprowadzania wymiarów. Oznacza to, że trzeba będzie zawsze używać wyszukiwań lub wysuwanych menu podczas wprowadzania kombinacji wymiarów i kont.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
