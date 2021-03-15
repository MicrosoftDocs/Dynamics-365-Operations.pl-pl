---
title: Ograniczenia dotyczące wersji wyceny opartej na kosztach standardowych.
description: W tym temacie opisano ograniczenia mające zastosowanie do wersji wyceny kosztów standardowych.
author: AndersGirke
manager: tfehr
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5339c3c4a62b94a06cbffc200ed1e9b227d6b6af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963795"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Ograniczenia dotyczące wersji wyceny opartej na kosztach standardowych.

[!include [banner](../includes/banner.md)]

W tym temacie opisano ograniczenia mające zastosowanie do wersji wyceny kosztów standardowych. 

Poniższe ograniczenia zapewniają zgodność ze standardowymi zasadami wyceny:

-  Opłaty muszą być uwzględnione w koszcie towaru. Opłaty dotyczące wytworzonego towaru odzwierciedlają zamortyzowane koszty stałe w informacjach listy składowej (BOM) i marszruty, zatem muszą być uwzględnione w koszcie jednostkowym. W koszcie jednostkowym towaru muszą być również uwzględnione opłaty dotyczące zakupionego towaru.

-  Obliczanie standardowych kosztów wyprodukowanych towarów musi być oparte na rekordach kosztów w wersji wyceny kosztów standardowych. Alternatywne źródła danych kosztów mogą być używane jedynie do wersji wyceny kosztów planowanych, np. w umowach handlowych z ceną zakupu na kupowane towary. Alternatywne źródła danych kosztów są definiowane przez grupę obliczania BOM.

-  Obliczenia BOM muszą być wykonywane w trybie jednopoziomowego rozłożenia.

Dane o kosztach standardowych towaru mogą być kopiowane do rekordów innej wersji wyceny, która obejmuje koszty standardowe i planowane. Dane kosztów planowanych towaru nie mogą być jednak kopiowane do wersji wyceny zawierającej koszty standardowe, ponieważ wymienione powyżej ograniczenia nie mają zastosowania do kosztów planowanych.

<a name="related-topics"></a>Powiązane tematy
--------

[Omówienie wersji wyceny](costing-versions.md)

[Aktualizowanie kosztów standardowych w środowisku nieobejmującym wytwarzania](update-standard-costs-non-manufacturing-environment.md)

[Przygotowanie do zarządzania kosztami standardowymi wyprodukowanych towarów](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]