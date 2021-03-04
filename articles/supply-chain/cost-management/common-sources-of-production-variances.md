---
title: Typowe przyczyny odchyleń produkcji
description: Ten artykuł wyjaśnia różne typowe przyczyny poszczególnych typów odchyleń produkcji.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcVarianceTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc310f1d5e1f99a320b803f68395d0926d39780b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435425"
---
# <a name="common-sources-of-production-variances"></a>Typowe przyczyny odchyleń produkcji

[!include [banner](../includes/banner.md)]

Ten artykuł wyjaśnia różne typowe przyczyny poszczególnych typów odchyleń produkcji. 

Poniżej przedstawiono niektóre typowe źródła odchyleń w **rozmiarze partii**:

-   Właściwa ilość w zleceniu produkcyjnym różni się od ilości obliczania stosowanej w obliczeniach kosztów standardowych. Ilość stanowi podstawę do amortyzowania kosztów stałych.
-   Wartość kosztów stałych w zleceniu produkcyjnym różni się od kosztów stałych stosowanych w obliczeniach kosztów standardowych. Rozbieżność ta może mieć różne przyczyny. Na przykład koszty stałe mogą odzwierciedlać następujące zdarzenia:
    -   Ręcznie zmiany w liście składowej (BOM) lub marszrucie
    -   Wybór innej wersji BOM lub marszruty podczas tworzenia zlecenia produkcyjnego
    -   Zaplanowane zmiany inżynieryjne w wersji BOM lub marszruty przypisanej do towaru

Poniżej przedstawiono niektóre typowe źródła odchyleń w **cenie produkcji**:

-   Kategoria kosztów (i cena w kategorii kosztów) zgłoszonego zużycia w operacji marszruty różni się od kategorii kosztów stosowanej w obliczeniach kosztów standardowych.
-   Aktywny koszt dla kategorii kosztów własnych różni się od kategorii kosztów własnych stosowanej w obliczeniach kosztów standardowych.

Poniżej przedstawiono niektóre typowe źródła odchyleń w **ilości produkcji**:

-   Nadmierne lub niewystarczające wydanie składnika materiałowego.
-   Zawyżony lub zaniżony zgłoszony czas operacji marszruty.
-   Przyjęcie za dużej lub za małej ilości dobrego towaru nadrzędnego względem ilości zamówienia. Jednak wydanie składników i zgłoszenie operacji wykonano kompletnie na podstawie ilości zamówienia dla zlecenia produkcyjnego.

Poniżej przedstawiono niektóre typowe źródła odchyleń w **podstawiania produkcji**:

-   Wydanie składnika materiałowego nienależącego do BOM produkcji.
-   Ręczne dodanie składnika do BOM produkcji i zgłoszenie go jako zużytego.
-   Zgłoszenie towaru jako zużytego bez ręcznego dodania go do BOM produkcji.
-   Ręczne dodanie operacji do marszruty produkcji i zgłoszenie tej operacji jako zużytej.
-   Podczas tworzenia zlecenia produkcyjnego wybrano wersję BOM inną niż wersja BOM używana w obliczeniach kosztów standardowych.
-   Podczas tworzenia zlecenia produkcyjnego wybrano wersję marszruty inną niż wersja marszruty używana w obliczeniach kosztów standardowych.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]