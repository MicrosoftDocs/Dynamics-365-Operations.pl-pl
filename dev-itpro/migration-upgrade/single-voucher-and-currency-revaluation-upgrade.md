---
title: "Pojedynczego załącznika i przeszacowanie w walucie uaktualnienia Microsoft Dynamics 365 dla wersji operacji 1611"
description: "W niektórych organizacjach wprowadź arkuszy, które zawierają jeden załącznik, który ma więcej niż jednego odbiorcy lub dostawcy, a oni również uruchomić rozrachunków z odbiorcami lub procesowi aktualizacji wyceny waluty obcej płatne konta. W tym temacie opisano kroki, które organizacje te należy wykonać podczas uaktualniania do usługi Microsoft Dynamics 365 dla wersji operacji 1611."
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

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Pojedynczego załącznika i przeszacowanie w walucie uaktualnienia Microsoft Dynamics 365 dla wersji operacji 1611

W niektórych organizacjach wprowadź arkuszy, które zawierają jeden załącznik, który ma więcej niż jednego odbiorcy lub dostawcy, a oni również uruchomić rozrachunków z odbiorcami lub procesowi aktualizacji wyceny waluty obcej płatne konta. W tym temacie opisano kroki, które organizacje te należy wykonać podczas uaktualniania do usługi Microsoft Dynamics 365 dla wersji operacji 1611.

Po uaktualnieniu do systemu Microsoft Dynamics 365 dla wersji operacji 1611, wykonaj następujące kroki.

1.  Przed uaktualnieniem do systemu Dynamics 365 dla operacji, uruchomić procesy przeszacowania waluty obcej dla rozrachunków z odbiorcami i Rozrachunki z dostawcami. Ustaw **metody** na **Data faktury**. Tworzona jest transakcja przeszacowania, która Odwraca działanie ostatniego przeszacowania w walucie obcej. W związku z tym otwarte transakcje są wyceniane w ich oryginalnej walucie rozliczeniowej.
2.  Uaktualnienie do systemu Dynamics 365 dla wersji operacji 1611.
3.  Ponownie uruchom rozrachunków z odbiorcami i procesów przeszacowania waluty obcej płatne konta. Ten czas ustawiony **metody** na **Standard**. Tworzona jest nowa transakcja przeszacowania, która opiera się na bieżących kursów wymiany. Ta transakcja rejestruje niezrealizowany zysk/strata i odpowiednie podsumowującego konta księgowego.



