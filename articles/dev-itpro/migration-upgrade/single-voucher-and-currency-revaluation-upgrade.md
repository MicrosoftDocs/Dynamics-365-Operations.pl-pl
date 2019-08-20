---
title: Uaktualnianie arkuszy z pojedynczymi załącznikami i przeszacowań w walucie
description: W niektórych organizacjach są wprowadzane arkusze zawierające jeden załącznik z więcej niż jednym odbiorcą lub dostawcą, a także wykonują proces przeszacowania w walucie obcej dla rozrachunków z dostawcami i odbiorcami. W tym temacie opisano kroki, które powinny wykonać takie organizacje podczas uaktualniania do programu Microsoft Dynamics 365 for Operations w wersji 1611.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b76354d0b8bb89e09e861e013a0c680c36b6537d
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851688"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>Uaktualnianie arkuszy z pojedynczymi załącznikami i przeszacowań w walucie

[!include [banner](../includes/banner.md)]

W niektórych organizacjach są wprowadzane arkusze zawierające jeden załącznik z więcej niż jednym odbiorcą lub dostawcą, a także wykonują proces przeszacowania w walucie obcej dla rozrachunków z dostawcami i odbiorcami. W tym temacie opisano kroki, które powinny wykonać takie organizacje podczas uaktualniania do programu Microsoft Dynamics 365 for Operations w wersji 1611.

W przypadku uaktualnienia do programu Microsoft Dynamics 365 for Operations w wersji 1611 należy wykonać poniższe kroki.

1.  Przed rozpoczęciem uaktualniania do programu Dynamics 365 for Operations wykonaj procesy przeszacowania w walucie obcej dla modułów Rozrachunki z odbiorcami i Rozrachunki z dostawcami. W polu **Metoda** ustaw wartość **Data faktury**. Zostanie utworzona transakcja przeszacowania, która odwraca ostatnie przeszacowanie w walucie obcej. W efekcie otwarte transakcje są wyceniane w ich oryginalnej walucie rozliczeniowej.
2.  Uaktualnij do programu Dynamics 365 for Operations w wersji 1611.
3.  Ponownie uruchom procesy przeszacowania w walucie obcej dla rozrachunków z odbiorcami i dostawcami. Tym razem w polu **Metoda** ustaw wartość **Standardowo**. Zostanie utworzona nowa transakcja przeszacowania oparta na bieżących kursach wymiany. Ta transakcja zarejestruje niezrealizowane dodatnie/ujemne różnice kursowe i poprawne podsumowujące konto księgowe.




