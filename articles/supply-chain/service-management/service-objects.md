---
title: Przedmioty serwisu
description: "Przedmioty serwisu to aktywa i produkty klienta, dla których można wykonać usługi."
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 221b9dae7e83e7f4a535ac60f2a2011533d7861c
ms.openlocfilehash: a69fd6a1b07683383d88c7f5c7986529c7bb1875
ms.contentlocale: pl-pl
ms.lasthandoff: 02/21/2018

---

# <a name="service-objects"></a>Przedmioty serwisu 

[!include[banner](../includes/banner.md)]

Przedmioty serwisu to aktywa i produkty klienta, dla których można wykonać usługi. W zależności od typu oferowanej usługi przedmioty dzielą się na materialne i niematerialne:

-  przedmioty materialne są to obiekty, na przykład maszyny lub budynki, które można poddać fizycznym działaniom serwisowym,

    Materialny przedmiot serwisu może też być pozycją magazynową utworzoną w formularzu Szczegóły zwolnionego produktu. W zależności od tego, którą grupą wymiarów magazynowych można oznaczyć dany towar, przedmiot serwisu można utworzyć nawet na poziomie numeru seryjnego towaru. Jest to użyteczne wtedy, gdy trzeba śledzić określony towar reprezentowany przez przedmiot serwisu.

    Materialnym przedmiotem serwisu może być jednak coś niezwiązanego bezpośrednio z produkcją firmy lub jej łańcuchem dostaw. Na przykład zestaw narzędzi używany do napraw w ramach zlecenia serwisowego może być przedmiotem serwisu nie uwzględnionym w zapasach. W takim przypadku nie można go zarejestrować jako pozycji magazynowej.

-  Przedmioty niematerialne są to abstrakcyjne elementy, na przykład zbiór kont lub oficjalny dokument, na podstawie których można wykonać działania serwisowe.

## <a name="example-of-an-intangible-service-object"></a>Przykład niematerialnego przedmiotu serwisu

Firma A obsługuje rekordy finansowe dla kilku małych firm. Jednym z klientów firmy A jest lokalna drużyna piłkarska, dla której A wykonuje co tydzień usługi księgowe i coroczny audyt kont klubu. Konta klubu są konfigurowane w formularzu Przedmioty serwisu i określane jako obiekt w umowie serwisowej. Istnieją dwa wiersze umowy serwisowej dla obiektu. Wiersz 1 to cotygodniowa księgowość, a wiersz 2 to coroczny audyt.

## <a name="related-topics"></a>Powiązane tematy

[Tworzenie przedmiotów serwisu](create-service-objects.md)


