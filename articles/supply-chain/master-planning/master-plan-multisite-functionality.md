---
title: Planowanie główne a funkcjonalność wielooddziałowości
description: Planowanie główne uwzględnia ustawienia wymiarów magazynowych „oddział” i „magazyn”.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10981e0fe201566c83fd28c792000865bc533cd3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1573098"
---
# <a name="master-planning-and-multisite-functionality"></a>Planowanie główne a funkcjonalność wielooddziałowości

[!include [banner](../includes/banner.md)]

Planowanie główne uwzględnia ustawienia wymiarów magazynowych „oddział” i „magazyn”. 

Wymiar oddziału jest obowiązkowy. Można też ustawić wymiar magazynu jako obowiązkowy.

Jeśli dany wymiar jest wymagany, jego wartość należy wprowadzać we wszystkich transakcjach magazynowych. Dlatego podczas planowania głównego jest znany oddział i magazyn, które będą realizować pierwsze zamówienie. Wymiary oddziału także muszą być zgodne, aby podczas dużego wzrostu liczby zamówień niższego poziomu nie zmieniła się wartość oddziału.

Jeśli magazyn nie zostanie ustawiony jako wymagany, może nie zostać rozpoznany przy pierwszym zamówieniu. Aparat planowania, na podstawie zdefiniowanych ustawień towaru, poszczególnych magazynów i szczegółów wiersza zamówienia musi określać, który magazyn ma być użyty.

Poniższe tematy zawierają opisy działania aparatu planowania podczas określania magazynu, który ma być użyty, w przypadku różnych ustawień.

[Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn wymagany](master-plan-site-coverage-warehouse-mandatory.md)

[Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn niewymagany](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planowanie główny — zapotrzebowania oddziału i magazynu, magazyn niewymagany](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planowanie główne — jak określa się wersję BOM](master-plan-bom-version-determined.md)



