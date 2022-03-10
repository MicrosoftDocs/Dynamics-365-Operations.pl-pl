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
ms.openlocfilehash: 1e946adc3a04db60bf15ac7bb44163085e1c19802872964877d3929b1f79bf7d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730113"
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
