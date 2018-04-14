---
title: "Ograniczenia dotyczące wersji wyceny opartej na kosztach standardowych."
description: "W tym temacie opisano ograniczenia mające zastosowanie do wersji wyceny kosztów standardowych."
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e14d5d11e987d2dbc841f86c39fc7e94864144d3
ms.openlocfilehash: 658575492597eed91509561f4710f07e271c53c8
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---


#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Ograniczenia dotyczące wersji wyceny opartej na kosztach standardowych.

[!INCLUDE [banner](../includes/banner.md)]

W tym temacie opisano ograniczenia mające zastosowanie do wersji wyceny kosztów standardowych. 

Poniższe ograniczenia zapewniają zgodność ze standardowymi zasadami wyceny:

-  Opłaty muszą być uwzględnione w koszcie towaru. Opłaty dotyczące wytworzonego towaru odzwierciedlają zamortyzowane koszty stałe w informacjach listy składowej (BOM) i marszruty, zatem muszą być uwzględnione w koszcie jednostkowym. W koszcie jednostkowym towaru muszą być również uwzględnione opłaty dotyczące zakupionego towaru.

-  Obliczanie standardowych kosztów wyprodukowanych towarów musi być oparte na rekordach kosztów w wersji wyceny kosztów standardowych. Alternatywne źródła danych kosztów mogą być używane jedynie do wersji wyceny kosztów planowanych, np. w umowach handlowych z ceną zakupu na kupowane towary. Alternatywne źródła danych kosztów są definiowane przez grupę obliczania BOM.

-  Obliczenia BOM muszą być wykonywane w trybie jednopoziomowego rozłożenia.

Dane o kosztach standardowych towaru mogą być kopiowane do rekordów innej wersji wyceny, która obejmuje koszty standardowe i planowane. Dane kosztów planowanych towaru nie mogą być jednak kopiowane do wersji wyceny zawierającej koszty standardowe, ponieważ wymienione powyżej ograniczenia nie mają zastosowania do kosztów planowanych.

<a name="related-topics"></a>Powiązane tematy
--------

[Wersje ceny](costing-versions.md)

[Aktualizacja kosztów standardowych w środowisku nieprodukcyjnym](update-standard-costs-non-manufacturing-environment.md)

[Przygotowanie do zarządzania kosztami standardowymi wyprodukowanych towarów](update-standard-costs-manufacturing-environment.md)


