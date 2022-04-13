---
title: Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn niewymagany
description: W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”. Wymiar magazynu nie jest obowiązkowy.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 396c07fa8cd5a915d5be39837cfdda3404dc402e
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470325"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Planowanie główne dla zapotrzebowań oddziału i magazynu, magazyn niewymagany

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział” i „magazyn”. Wymiar magazynu nie jest obowiązkowy.

Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:

-   Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu. Tego ustawienia nie można zmodyfikować.
-   Wymiar magazynowy nie jest skonfigurowany jako obowiązkowy. Magazyn może być znany, ale nie jest uwzględniany w obliczeniach planowania głównego.
-   Wymiary oddziału i magazynu są ustawione dla planowania zapotrzebowania. Również inne wymiary mogą być ustawione dla planowania zapotrzebowania. Jednak funkcja wielooddziałowości nie ma na nie wpływu.

Na poniższej ilustracji przedstawiono przebieg planowania głównego. Parametry wymienione na ilustracji i ich lokalizacje są następujące:
-   Magazyn ma ustawienie Ręcznie. Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**. Na skróconej karcie **Planowanie główne** zobacz pole **Ręcznie**.
-   Jest zdefiniowane zapotrzebowanie na dany towar. Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**. Wybierz pozycję, a następnie w okienku akcji na karcie **Plan** kliknij opcję **Zapotrzebowanie na pozycje**.
-   Dla magazynu są zdefiniowane relacje uzupełniania. Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**. Na skróconej karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.
-   Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban. Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**. Wybierz pozycję, a następnie w okienku akcji na karcie **Plan** kliknij pozycję **Ustawienia domyślne zamówień**. W formularzu **Ustawienia domyślne zamówień** zobacz **Domyślny typ zamówienia**.

![Popyt dla oddziału i magazynu, magazyn niewymagany.](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie planowania głównego i funkcjonalności wielooddziałowości](master-plan-multisite-functionality.md)

[Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn wymagany](master-plan-site-coverage-warehouse-mandatory.md)

[Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn niewymagany](master-plan-site-coverage-warehouse-not-mandatory.md)

[Ustalanie wersji BOM](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]