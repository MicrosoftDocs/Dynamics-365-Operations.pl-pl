---
title: Konfigurowanie stawek gotówkowych w punkcie sprzedaży (POS)
description: Nominały gotówki banknotów i monet można zdefiniować w systemach zaplecza, tak aby były używane przez kasjerów, sprzedawców i kierowników w sklepie z poziomu punktu sprzedaży.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b2fb6676f45bc7efa4652de60e829b507292ac37
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213193"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a>Konfigurowanie stawek gotówkowych w punkcie sprzedaży (POS)

[!include [banner](includes/banner.md)]

Nominały gotówki banknotów i monet można zdefiniować w systemach zaplecza, tak aby były używane przez kasjerów, sprzedawców i kierowników w sklepie z poziomu punktu sprzedaży. Te nominały mogą służyć jako pomoc w podliczaniu środków pieniężnych w deklaracjach środków płatniczych na koniec dnia lub do szybkiego opłacenia sprzedaży.

## <a name="define-denominations"></a>Definiowanie nominałów

Nominały definiuje się dla konkretnego sklepu w opcji **Konfiguracja** \> **Deklaracja gotówki** na stronie właściwości sklepu.

![Opcja deklaracji gotówki](./media/image1-denomination.png)

Aby zdefiniować nominał:

1. Kliknij przycisk **Nowy**.
1. Określ typ (moneta lub banknot).
1. Określ kwotę (wartość).

![Strona stawek deklaracji gotówki](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a>Konfigurowanie profilu funkcji

W trakcie płacenia gotówką w punkcie sprzedaży użytkownik może za pomocą nominałów banknotów szybko wprowadzić kwotę płaconą przez odbiorcę. W profilu funkcji można skonfigurować dwie opcje wyświetlania nominałów w punkcie sprzedaży.

- **Większa lub równa kwocie należnej** — Domyślnie w punkcie sprzedaży będą wyświetlane tylko nominały banknotów większe niż kwota należna, co pozwala zapłacić jednym naciśnięciem przycisku. Na przykład jeśli kwota należna wynosi 7,50 USD, w punkcie sprzedaży byłyby wyświetlane następujące nominały: 10 USD, 20 USD, 50 USD i 100 USD. Dotknięcie dowolnej z tych kwot spowoduje automatyczną zapłatę za sprzedaż na tę kwotę. Banknoty 1 USD i 5 USD nie są wyświetlane, ponieważ te wartości są mniejsze niż kwota należna.
- **Wszystkie stawki** — Wybierz tę opcję, aby zawsze wyświetlać wszystkie nominały banknotów w punkcie sprzedaży, bez względu na kwotę należną. Oznacza to, że użytkownika może osiągnąć kwotę należną za pomocą kombinacji banknotów. Na przykład jeśli kwota należna wynosi 25,00 USD, użytkownik może wybrać nominały 20 USD i 5 USD, aby sfinalizować sprzedaż.


[!INCLUDE[footer-include](../includes/footer-banner.md)]