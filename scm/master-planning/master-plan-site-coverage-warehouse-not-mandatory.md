---
title: "Na pokrycie lokacji, Magazyn nie jest ona obowiązkowa planowania głównego"
description: "W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział”."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 28607f0fc8db99c9fc8e96b4514763b8cf589dd8
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a>Na pokrycie lokacji, Magazyn nie jest ona obowiązkowa planowania głównego

W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział”.

Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:

-   Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.
-   Wymiar magazynowy nie jest skonfigurowany jako obowiązkowy. Magazyn może być znany, ale nie jest uwzględniany w obliczeniach planowania głównego.
-   Wymiar oddziału jest ustawiony dla planowania zapotrzebowania.
-   Wymiar magazynu nie jest ustawiony dla planowania zapotrzebowania. Dlatego podaż i popyt są agregowane według oddziałów oraz ewentualnie według innych wymiarów z planowaniem zapotrzebowania.

Na poniższej ilustracji przedstawiono przebieg planowania głównego. Parametry wymienione na ilustracji i ich lokalizacje są następujące:
-   Jest zdefiniowane zapotrzebowanie na dany towar. Kliknij **zarządzanie informacjami o produktach &gt;produktów&gt; zwolnionych produktów**. Zaznacz element, a następnie kliknij przycisk **Plan &gt;zapotrzebowanie na towar**.
-   Dla magazynu są zdefiniowane relacje uzupełniania. Kliknij **Zarządzanie zapasami &gt;instalacji &gt;Podział magazynu &gt;składów**. Na karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.
-   Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban. Kliknij **zarządzanie informacjami o produktach &gt;produktów&gt; zwolnionych produktów**. Zaznacz element, a następnie kliknij przycisk **Plan &gt;ustawienia domyślne zamówień**. W formularzu **Ustawienia domyślne zamówień** zobacz pole **Domyślny typ zamówienia**.

![Popyt dla zapotrzebowania oddziału, magazyn niewymagany    ](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="see-also"></a>Informacje dodatkowe
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany](master-plan-site-coverage-warehouse-mandatory.md)

[Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn niewymagany](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planowanie główne — jak ustalić wersję BOM](master-plan-bom-version-determined.md)


