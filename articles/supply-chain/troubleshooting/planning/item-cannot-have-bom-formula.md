---
title: Pozycja nie może mieć BOM ani formuły
description: Przy próbie złożenia zamówienia pojawia się komunikat o błędzie podczas sprawdzania poprawności pozycji. Stwierdza, że element nie może posiadać listy składowej (BOM) lub wzoru.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294155"
---
# <a name="item-cant-have-a-bom-or-formula"></a>Pozycja nie może mieć BOM ani formuły

Kod błędu: PRO2614

## <a name="symptoms"></a>Objawy

Przy próbie złożenia zamówienia podczas sprawdzania poprawności pozycji pojawia się następujący komunikat o błędzie:

> Pozycja nie może mieć BOM ani formuły

## <a name="resolution"></a>Rozwiązanie

Towary z BOM lub formułą muszą być typu *Planowanie*, *BOM* lub *formuła*. Aby zmienić typ elementu, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Otwórz odpowiedni produkt.
1. Na skróconej karcie **Konstruuj** ustaw pole **Typ produkcji** na *Element planowania*, *BOM* lub *formuła*.
