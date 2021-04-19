---
title: Wykluczanie produktów z określonymi stanami cyklu życia produktu
description: W tym temacie wyjaśniono, jak wykluczyć produkty na podstawie ich stanu cyklu życia, gdy używana jest funkcja optymalizacji planowania.
author: ChristianRytt
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7028a509aa884589958542f7ec627d69dffcfcec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839254"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a>Wykluczanie produktów z określonymi stanami cyklu życia produktu

[!include [banner](../../includes/banner.md)]

Zwolnione produkty i zwolnione wersje produktu zawierają pole **Stan cyklu życia produktu**. To pole umożliwia między innymi kontrolowanie, które produkty są uwzględniane podczas planowania głównego. Istnieje możliwość dodawania, usuwania i edytowania stanów cyklu zgodnie z potrzebami, przechodząc do **Zarządzanie informacjami o produktach \> Konfiguracja \> Stan cyklu życia produktu**. Dla każdego stanu cyklu życia produktu ustaw opcję **Jest aktywna dla planowania** na *Tak*, jeśli produkty, które mają ten stan, powinny być uwzględnione podczas planowania głównego. Jeśli opcja jest ustawiona na wartość *Nie*, skojarzone produkty i warianty będą wykluczone ze wszystkich planów głównych i wszystkich obliczeń na poziomie BOM.

Zwolnione produkty i warianty, w których pole **Stan cyklu życia produktu** pozostaje puste, są traktowane tak, jakby miały stan cyklu życia produktu, w którym opcja **Jest aktywna dla planowania** jest ustawiona na wartość *Tak*. Innymi słowy, zostaną one uwzględnione podczas planowania głównego.

> [!NOTE]
> Aby uniknąć niepotrzebnych sugestii dotyczących dostaw, zdecydowanie zaleca się, aby skojarzyć wszystkie przestarzałe zwolnione produkty i warianty z stanem cyklu życia produktu, w którym opcja **Jest aktywna dla planowania** jest ustawiona na wartość *Nie*. Ta metoda jest szczególnie ważna podczas pracy z wariantami konfiguracji produktu, które nie są ponownie używane, ponieważ ułatwiają one zapobieganie powstawania odpadów.

## <a name="related-resources"></a>Powiązane zasoby

Aby uzyskać więcej informacji na temat stanów cyklu życia produktów, zapoznaj się z [Omówienie stanów cyklu życia produktu](../../pim/product-lifecycle.md).

Aby uzyskać szczegółowe informacje, które obejmują kroki korzystania ze stanów cyklu życia produktu w celu wykluczenia produktów z planowania głównego i obliczeń na poziomie BOM, zobacz [Tworzenie stanu cyklu życia produktu w celu wykluczania produktów z planowania głównego](../../pim/tasks/exclude-products-master-planning.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]