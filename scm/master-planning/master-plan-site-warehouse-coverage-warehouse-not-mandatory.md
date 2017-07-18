---
title: "Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn niewymagany"
description: "W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”. Wymiar magazynu nie jest obowiązkowy."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ec5150abd297a7c00ac180db581adb30bef65b3f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn niewymagany

[!include[banner](../includes/banner.md)]


W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”. Wymiar magazynu nie jest obowiązkowy.

Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:

-   Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu. Tego ustawienia nie można zmodyfikować.
-   Wymiar magazynowy nie jest skonfigurowany jako obowiązkowy. Magazyn może być znany, ale nie jest uwzględniany w obliczeniach planowania głównego.
-   Wymiary oddziału i magazynu są ustawione dla planowania zapotrzebowania. Również inne wymiary mogą być ustawione dla planowania zapotrzebowania. Jednak funkcja wielooddziałowości nie ma na nie wpływu.

Na poniższej ilustracji przedstawiono przebieg planowania głównego. Parametry wymienione na ilustracji i ich lokalizacje są następujące:
-   Magazyn ma ustawienie Ręcznie. Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**. Na skróconej karcie **Planowanie główne** zobacz pole **Ręcznie**.
-   Jest zdefiniowane zapotrzebowanie na dany towar. Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**. Wybierz towar, a następnie w okienku akcji na karcie **Plan** kliknij opcję **Zapotrzebowanie na towary**.
-   Dla magazynu są zdefiniowane relacje uzupełniania. Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**. Na skróconej karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.
-   Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban. Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**. Wybierz towar, a następnie w okienku akcji na karcie **Plan** kliknij **Ustawienia domyślne zamówień**. W formularzu **Ustawienia domyślne zamówień** zobacz **Domyślny typ zamówienia**.

![Popyt dla oddziału i magazynu, magazyn niewymagany](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)

 
-



<a name="see-also"></a>Informacje dodatkowe
--------

[Planowanie główne a funkcjonalność wielooddziałowości](master-plan-multisite-functionality.md)

[Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany](master-plan-site-coverage-warehouse-mandatory.md)

[Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn niewymagany](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planowanie główne — jak określa się wersję BOM](master-plan-bom-version-determined.md)




