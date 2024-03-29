---
title: Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany
description: W tym artykule opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział”. Magazyn jest wymiarem obowiązkowym.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df58017c25737cc946d09bf86ff7ad8bd33f4176
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741048"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób planowania towaru, który ma wymiar zapotrzebowania „oddział”. Magazyn jest wymiarem obowiązkowym.

Niniejszy scenariusz planowania głównego wymaga spełnienia następujących warunków:

-   Wymiar lokalizacji jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu. Tego ustawienia nie można zmodyfikować.
-   Wymiar magazynu jest ustawiony jako wymagany i musi być wprowadzony w transakcji popytu.
-   Wymiar oddziału jest ustawiony dla planowania zapotrzebowania. Również inne wymiary mogą być ustawione dla planowania zapotrzebowania. Jednak funkcja wielooddziałowości nie ma na nie wpływu.
-   Wymiar magazynu nie jest ustawiony dla planowania zapotrzebowania. Dlatego podaż i popyt są agregowane według oddziałów oraz ewentualnie według innych wymiarów z planowaniem zapotrzebowania.

Na poniższej ilustracji przedstawiono przebieg planowania głównego. Parametry wymienione na ilustracji i ich lokalizacje są następujące:
-   Jest zdefiniowane zapotrzebowanie na dany towar. Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**. Zaznacz towar i kliknij kolejno opcje **Plan &gt; Zapotrzebowanie na towary**.
-   Dla magazynu są zdefiniowane relacje uzupełniania. Kliknij kolejno opcje **Zarządzanie zapasami &gt; Ustawienia &gt; Podział magazynu &gt; Magazyny**. Na karcie **Planowanie główne** zobacz grupę pól **Magazyn główny**.
-   Domyślny typ zamówienia to Produkcja, Zamówienie zakupu lub Kanban. Kliknij kolejno opcje **Zarządzanie informacjami o produktach &gt; Produkty&gt; Zwolnione produkty**. Wybierz odpowiedni towar i kliknij kolejno opcje **Plan &gt; Ustawienia domyślne zamówień**. W formularzu **Ustawienia domyślne zamówień** zobacz **Domyślny typ zamówienia**.

![Popyt dla zapotrzebowania oddziału, magazyn wymagany.](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie planowania głównego i funkcjonalności wielooddziałowości](master-plan-multisite-functionality.md)
- [Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn wymagany](master-plan-site-warehouse-coverage-warehouse-mandatory.md)
- [Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany](master-plan-site-coverage-warehouse-mandatory.md)
- [Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn niewymagany](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)
- [Ustalanie wersji BOM](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]