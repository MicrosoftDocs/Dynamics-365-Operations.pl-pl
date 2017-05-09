---
title: "Uaktualnianie pojedynczych załączników i przeszacowań w walucie w programie Microsoft Dynamics 365 for Operations w wersji 1611"
description: "W niektórych organizacjach są wprowadzane arkusze zawierające jeden załącznik z więcej niż jednym odbiorcą lub dostawcą, a także wykonują proces przeszacowania w walucie obcej dla rozrachunków z dostawcami i odbiorcami. W tym temacie opisano kroki, które powinny wykonać takie organizacje podczas uaktualniania do programu Microsoft Dynamics 365 for Operations w wersji 1611."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-28 16 - 04 - 17
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d42c753d0dc8b8efc2a0d2a26da32a4951d85503
ms.lasthandoff: 03/31/2017


---

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Uaktualnianie pojedynczych załączników i przeszacowań w walucie w programie Microsoft Dynamics 365 for Operations w wersji 1611

W niektórych organizacjach są wprowadzane arkusze zawierające jeden załącznik z więcej niż jednym odbiorcą lub dostawcą, a także wykonują proces przeszacowania w walucie obcej dla rozrachunków z dostawcami i odbiorcami. W tym temacie opisano kroki, które powinny wykonać takie organizacje podczas uaktualniania do programu Microsoft Dynamics 365 for Operations w wersji 1611.

W przypadku uaktualnienia do programu Microsoft Dynamics 365 for Operations w wersji 1611 należy wykonać poniższe kroki.

1.  Przed rozpoczęciem uaktualniania do programu Dynamics 365 for Operations wykonaj procesy przeszacowania w walucie obcej dla modułów Rozrachunki z odbiorcami i Rozrachunki z dostawcami. W polu **Metoda** ustaw wartość **Data faktury**. Zostanie utworzona transakcja przeszacowania, która odwraca ostatnie przeszacowanie w walucie obcej. W efekcie otwarte transakcje są wyceniane w ich oryginalnej walucie rozliczeniowej.
2.  Uaktualnij do programu Dynamics 365 for Operations w wersji 1611.
3.  Ponownie uruchom procesy przeszacowania w walucie obcej dla rozrachunków z odbiorcami i dostawcami. Tym razem w polu **Metoda** ustaw wartość **Standardowo**. Zostanie utworzona nowa transakcja przeszacowania oparta na bieżących kursach wymiany. Ta transakcja zarejestruje niezrealizowane dodatnie/ujemne różnice kursowe i poprawne podsumowujące konto księgowe.



