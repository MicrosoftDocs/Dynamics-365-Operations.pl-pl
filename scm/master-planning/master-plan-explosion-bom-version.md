---
title: "Rozłożenie wersji BOM"
description: "Ten artykuł wyjaśnia scenariusz planowania głównego, który obejmuje rozłożenie wersji listy składowej (BOM)."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 6461a07f8c8f02f584e5ef70b21ebaf04f29b57b
ms.lasthandoff: 03/31/2017


---

# <a name="explosion-of-a-bom-version"></a>Rozłożenie wersji BOM

[!include[banner](../includes/banner.md)]


Ten artykuł wyjaśnia scenariusz planowania głównego, który obejmuje rozłożenie wersji listy składowej (BOM).

Pomyślne rozłożenie popytu wersji listy składowej (BOM) tworzy popyt na każdy towar wiersza BOM w określonym dziale i prawdopodobnie w określonym magazynie. BOM właściwy dla oddziału może mieć określony magazyn dla każdego wiersza. Ponadto dla każdego wiersza BOM ustawienia wymiarów towaru określają, czy magazyn jest wymagany. Wynikowy popyt poszczególnych towarów wiersza BOM staje się z kolei punktem początkowym dodatkowego rozłożenia popytu. Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:

-   Wymiar oddziału jest obowiązkowy i musi być wprowadzony w transakcji popytu.
-   Wymiar oddziału jest spójny. Oddział związany z popytem niższego poziomu jest identyczny z oddziałem z początkowej transakcji popytu.

Poniższy rysunek przedstawia sposób przetwarzania rozłożenia popytu planu ogólnego. ![Rozłożenie popytu przy użyciu wersji BOM](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="see-also"></a>Informacje dodatkowe
--------

[Planowanie główne — jak określa się wersję BOM](master-plan-bom-version-determined.md)

[Planowanie główne a funkcjonalność wielooddziałowości](master-plan-multisite-functionality.md)




