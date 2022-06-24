---
title: Ograniczenia dotyczące wersji wyceny opartej na kosztach standardowych.
description: W tym artykule opisano ograniczenia mające zastosowanie do wersji wyceny kosztów standardowych.
author: JennySong-SH
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5c00ae8952e2c80d97d039271a6f5c63e9a72f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867993"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Ograniczenia dotyczące wersji wyceny opartej na kosztach standardowych.

[!include [banner](../includes/banner.md)]

W tym artykule opisano ograniczenia mające zastosowanie do wersji wyceny kosztów standardowych. 

Poniższe ograniczenia zapewniają zgodność ze standardowymi zasadami wyceny:

-  Opłaty muszą być uwzględnione w koszcie towaru. Opłaty dotyczące wytworzonego towaru odzwierciedlają zamortyzowane koszty stałe w informacjach listy składowej (BOM) i marszruty, zatem muszą być uwzględnione w koszcie jednostkowym. W koszcie jednostkowym towaru muszą być również uwzględnione opłaty dotyczące zakupionego towaru.

-  Obliczanie standardowych kosztów wyprodukowanych towarów musi być oparte na rekordach kosztów w wersji wyceny kosztów standardowych. Alternatywne źródła danych kosztów mogą być używane jedynie do wersji wyceny kosztów planowanych, np. w umowach handlowych z ceną zakupu na kupowane towary. Alternatywne źródła danych kosztów są definiowane przez grupę obliczania BOM.

-  Obliczenia BOM muszą być wykonywane w trybie jednopoziomowego rozłożenia.

Dane o kosztach standardowych towaru mogą być kopiowane do rekordów innej wersji wyceny, która obejmuje koszty standardowe i planowane. Dane kosztów planowanych towaru nie mogą być jednak kopiowane do wersji wyceny zawierającej koszty standardowe, ponieważ wymienione powyżej ograniczenia nie mają zastosowania do kosztów planowanych.

## <a name="related-articles"></a>Powiązane artykuły

[Omówienie wersji wyceny](costing-versions.md)

[Aktualizowanie kosztów standardowych w środowisku nieobejmującym wytwarzania](update-standard-costs-non-manufacturing-environment.md)

[Przygotowanie do zarządzania kosztami standardowymi wyprodukowanych towarów](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]