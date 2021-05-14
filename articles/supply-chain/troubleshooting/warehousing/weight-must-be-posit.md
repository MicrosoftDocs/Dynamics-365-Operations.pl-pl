---
title: Waga musi być dodatnia
description: Waga musi być dodatnia
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dcbcde3143cb509b68b277cb7c709263e2659b5b
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924310"
---
# <a name="weight-must-be-positive"></a>Waga musi być dodatnia

Kod błędu: WeightMustBePositive

## <a name="symptoms"></a>Objawy

W systemie wyświetlany jest następujący komunikat o błędzie:

> Waga musi być dodatnia.

## <a name="cause"></a>Powód

W polu **Waga brutto** jest ustawiona wartość *0* (zero) lub wartość ujemna.

## <a name="resolution"></a>Rozdzielczość

Aby określić wagę, wykonaj jedną z następujących czynności.

- W polu **Waga brutto** ustaw wartość. Następnie wybierz jednostkę z listy rozwijanej.
- Wybierz opcję **Pobierz wagę z systemu**, aby obliczyć wartość w polu **Waga brutto**.
