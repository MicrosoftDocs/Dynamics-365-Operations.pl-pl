---
title: "Konfigurowanie nominałów gotówki dla punktu sprzedaży"
description: "Nominały gotówki banknotów i monet można zdefiniować w systemach zaplecza, tak aby były używane przez kasjerów, sprzedawców i kierowników w sklepie z poziomu punktu sprzedaży."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d280a11670b5887ae5ae582cedf30c093b4b5d7c
ms.openlocfilehash: 9abcbb706d7120c6bcd91fc759b33cb518802a5b
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="configure-cash-denominations-for-pos"></a>Konfigurowanie nominałów gotówki dla punktu sprzedaży

[!include[banner](includes/banner.md)]

Nominały gotówki banknotów i monet można zdefiniować w systemach zaplecza, tak aby były używane przez kasjerów, sprzedawców i kierowników w sklepie z poziomu punktu sprzedaży. Te nominały mogą służyć jako pomoc w podliczaniu środków pieniężnych w deklaracjach środków płatniczych na koniec dnia lub do szybkiego opłacenia sprzedaży.

## <a name="define-denominations"></a>Definiowanie nominałów
Nominały definiuje się dla konkretnego sklepu za pomocą opcji **Konfiguracja** >  strona właściwości sklepu > opcja **Deklaracja gotówki**. 

![nominały gotówki](./media/image1-denomination.png)

Aby zdefiniować nominał:
1. Kliknij przycisk **Nowy**.
1. Określ typ (moneta lub banknot).
1. Określ kwotę (wartość).

![nominały gotówki](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a>Konfigurowanie profilu funkcji
W trakcie płacenia gotówką w punkcie sprzedaży użytkownik może za pomocą nominałów banknotów szybko wprowadzić kwotę płaconą przez odbiorcę. W profilu funkcji można skonfigurować dwie opcje wyświetlania nominałów w punkcie sprzedaży.

**Większa lub równa kwocie należnej**: Domyślnie w punkcie sprzedaży będą wyświetlane tylko nominały banknotów większe niż kwota należna, co pozwala zapłacić jednym naciśnięciem przycisku. Na przykład jeśli kwota należna wynosi 7,50 USD, w punkcie sprzedaży byłyby wyświetlane następujące nominały: 10 USD, 20 USD, 50 USD i 100 USD. Dotknięcie dowolnej z tych kwot spowoduje automatyczną zapłatę za sprzedaż na tę kwotę. Banknoty 1 USD i 5 USD nie są wyświetlane, ponieważ te wartości są mniejsze niż kwota należna.

**Wszystkie stawki**: Wybierz tę opcję, aby zawsze wyświetlać wszystkie nominały banknotów w punkcie sprzedaży, bez względu na kwotę należną. Oznacza to, że użytkownika może osiągnąć kwotę należną za pomocą kombinacji banknotów. Na przykład jeśli kwota należna wynosi 25,00 USD, użytkownik może wybrać nominały 20 USD i 5 USD, aby sfinalizować sprzedaż.
