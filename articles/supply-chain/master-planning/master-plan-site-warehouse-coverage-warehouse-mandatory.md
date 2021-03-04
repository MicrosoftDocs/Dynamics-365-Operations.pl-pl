---
title: Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn wymagany
description: W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”. Wymiar magazynu jest obowiązkowy.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 92160b45590245e2b1caab6732d1b0aaeaabd208
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435101"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a>Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn wymagany

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”. Wymiar magazynu jest obowiązkowy.

Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:

-   Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.
-   Wymiar magazynu jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.
-   Wymiary oddziału i magazynu są ustawione dla planowania zapotrzebowania. Również inne wymiary mogą być ustawione dla planowania zapotrzebowania. Jednak funkcja wielooddziałowości nie ma na nie wpływu.

Na poniższej ilustracji przedstawiono przebieg planowania głównego. Parametry wymienione na ilustracji i ich lokalizacje są następujące:
-   Magazyn ma ustawienie **Ręcznie**. Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**. Na skróconej karcie **Planowanie główne** zobacz pole **Ręcznie**.
-   Jest zdefiniowane zapotrzebowanie na dany towar. Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**. Wybierz pozycję, a następnie w okienku akcji na karcie **Plan** kliknij opcję **Zapotrzebowanie na pozycje**.
-   Dla magazynu są zdefiniowane relacje uzupełniania. Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**. Na skróconej karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.
-   Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban. Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**. Wybierz pozycję, a następnie w okienku akcji na karcie **Plan** kliknij pozycję **Ustawienia domyślne zamówień**. W formularzu **Ustawienia domyślne zamówień** zobacz **Domyślny typ zamówienia**.

![Popyt dla zapotrzebowania oddziału i magazynu, magazyn wymagany](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Omówienie planowania głównego i funkcjonalności wielooddziałowości](master-plan-multisite-functionality.md)

[Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany](master-plan-site-coverage-warehouse-mandatory.md)

[Planowanie główne dla zapotrzebowania oddziału, magazyn niewymagany](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn niewymagany](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Ustalanie wersji BOM](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]