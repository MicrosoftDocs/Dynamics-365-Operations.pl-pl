---
title: "Zmniejszanie dni na opłaty subskrypcji"
description: "Aby zredukować liczbę dni w ramach już istniejącej opłaty subskrypcji, można utworzyć nową transakcję i usunąć okres, który ma nie należeć do okresu opłaty subskrypcji."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c70e393c125eecef85e8711d1635250f5ff408d9
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

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

  



