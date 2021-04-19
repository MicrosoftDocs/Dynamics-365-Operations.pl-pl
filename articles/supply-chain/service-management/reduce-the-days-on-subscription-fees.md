---
title: Zmniejszanie dni na opłaty subskrypcji
description: Aby zredukować liczbę dni w ramach już istniejącej opłaty subskrypcji, można utworzyć nową transakcję i usunąć okres, który ma nie należeć do okresu opłaty subskrypcji.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e8158c99d2447835f3656027fd73d7c22121536
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836093"
---
# <a name="reduce-the-days-on-subscription-fees"></a>Zmniejszanie dni na opłaty subskrypcji 

[!include [banner](../includes/banner.md)]


Aby zredukować liczbę dni w ramach już istniejącej opłaty subskrypcji, można utworzyć nową transakcję i usunąć okres, który ma nie należeć do okresu opłaty subskrypcji.

## <a name="reduce-the-days-on-a-subscription-fee"></a>Redukcja dni opłaty subskrypcji

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Subskrypcje serwisowe** \> **Wszystkie subskrypcje serwisu**. Zaznacz subskrypcję serwisu, a następnie w okienku akcji kliknij opcję **Opłaty subskrypcji**.

2.  W polu **Typ subskrypcji** zaznacz opcję **Dni redukcji**.

3.  W polach **Od dnia** i **Do dnia** określ przedział czasu w ramach opłaty subskrypcji, który ma zostać usunięty z okresu opłaty subskrypcji, a następnie kliknij przycisk **OK**.

Aby przejrzeć utworzoną transakcję, w formularzu **Subskrypcja** kliknij opcję **Transakcje opłat**.

## <a name="example"></a>Przykład

Jeśli okres transakcji subskrypcji trwa od 1 do 31 stycznia i trzeba ten okres zmniejszyć o 10 dni, to należy utworzyć nową transakcję, w której okres redukcji trwa od 1 do 10 stycznia. (Okresem redukcji może też być przedział czasu od 5 do 15 stycznia lub dowolny inny 10-dniowy okres).

Ponadto jeśli w polu **Od dnia** dla okresu redukcji podano dzień 21 stycznia (31 minus 10), to w polu **Do dnia** można wprowadzić dowolny dzień po 31 stycznia, a nadal z okresu transakcji opłaty zostanie odjętych 10 dni.

## <a name="see-also"></a>Informacje dodatkowe

[Przykład dni redukcji](reduction-days-example.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]