---
title: Omówienie przedmiotów serwisu
description: Przedmioty serwisu to aktywa i produkty klienta, dla których można wykonać usługi.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 29d2cf6a496fed8d9932d5c6d49f4560d7eabbbb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434910"
---
# <a name="service-objects-overview"></a>Omówienie przedmiotów serwisu

[!include [banner](../includes/banner.md)]

Przedmioty serwisu to aktywa i produkty klienta, dla których można wykonać usługi. W zależności od typu oferowanej usługi przedmioty dzielą się na materialne i niematerialne:

-  przedmioty materialne są to obiekty, na przykład maszyny lub budynki, które można poddać fizycznym działaniom serwisowym,

    Materialny przedmiot serwisu może też być pozycją magazynową utworzoną w formularzu Szczegóły zwolnionego produktu. W zależności od tego, którą grupą wymiarów magazynowych można oznaczyć dany towar, przedmiot serwisu można utworzyć nawet na poziomie numeru seryjnego towaru. Jest to użyteczne wtedy, gdy trzeba śledzić określony towar reprezentowany przez przedmiot serwisu.

    Materialnym przedmiotem serwisu może być jednak coś niezwiązanego bezpośrednio z produkcją firmy lub jej łańcuchem dostaw. Na przykład zestaw narzędzi używany do napraw w ramach zlecenia serwisowego może być przedmiotem serwisu nie uwzględnionym w zapasach. W takim przypadku nie można go zarejestrować jako pozycji magazynowej.

-  Przedmioty niematerialne są to abstrakcyjne elementy, na przykład zbiór kont lub oficjalny dokument, na podstawie których można wykonać działania serwisowe.

## <a name="example-of-an-intangible-service-object"></a>Przykład niematerialnego przedmiotu serwisu

Firma A obsługuje rekordy finansowe dla kilku małych firm. Jednym z klientów firmy A jest lokalna drużyna piłkarska, dla której A wykonuje co tydzień usługi księgowe i coroczny audyt kont klubu. Konta klubu są konfigurowane w formularzu Przedmioty serwisu i określane jako obiekt w umowie serwisowej. Istnieją dwa wiersze umowy serwisowej dla obiektu. Wiersz 1 to cotygodniowa księgowość, a wiersz 2 to coroczny audyt.

## <a name="related-topics"></a>Powiązane tematy

[Tworzenie przedmiotów serwisu](create-service-objects.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]