---
title: Omówienie planowania głównego i funkcjonalności wielooddziałowości
description: Planowanie główne uwzględnia ustawienia wymiarów magazynowych „oddział” i „magazyn”.
author: ChristianRytt
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2434"
- intro-internal
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edcf35ea0a5be870d8a57cd782664d0a0b77de5c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575687"
---
# <a name="master-planning-and-multisite-functionality-overview"></a>Omówienie planowania głównego i funkcjonalności wielooddziałowości

[!include [banner](../includes/banner.md)]

Planowanie główne uwzględnia ustawienia wymiarów magazynowych „oddział” i „magazyn”. 

Wymiar oddziału jest obowiązkowy. Można też ustawić wymiar magazynu jako obowiązkowy.

Jeśli dany wymiar jest wymagany, jego wartość należy wprowadzać we wszystkich transakcjach magazynowych. Dlatego podczas planowania głównego jest znany oddział i magazyn, które będą realizować pierwsze zamówienie. Wymiary oddziału także muszą być zgodne, aby podczas dużego wzrostu liczby zamówień niższego poziomu nie zmieniła się wartość oddziału.

Jeśli magazyn nie zostanie ustawiony jako wymagany, może nie zostać rozpoznany przy pierwszym zamówieniu. Aparat planowania, na podstawie zdefiniowanych ustawień towaru, poszczególnych magazynów i szczegółów wiersza zamówienia musi określać, który magazyn ma być użyty.

Poniższe tematy zawierają opisy działania aparatu planowania podczas określania magazynu, który ma być użyty, w przypadku różnych ustawień.

[Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn wymagany](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planowanie główne dla zapotrzebowania oddziału, magazyn wymagany](master-plan-site-coverage-warehouse-mandatory.md)

[Planowanie główne dla zapotrzebowania oddziału i magazynu, magazyn niewymagany](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planowanie główne dla zapotrzebowania oddziału, magazyn niewymagany](master-plan-site-coverage-warehouse-not-mandatory.md)

[Ustalanie wersji BOM](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]