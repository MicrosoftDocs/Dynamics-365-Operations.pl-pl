---
title: Etapy zleceń serwisowych
description: Definiowanie etapów zlecenia serwisowego i przypisanie ich do pracowników pozwala kontrolować przepływ zlecenia serwisowego przez zadania wykonywane przez różne osoby w dziale serwisowym.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d126b68bea8d2083fcf1d08e168b9ead1511b25c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001256"
---
# <a name="service-order-stages"></a>Etapy zleceń serwisowych   

[!include [banner](../includes/banner.md)]


Można skonfigurować etapy zlecenia serwisowego w celu zdefiniowania zadań, które trzeba wykonać, kolejności ich wykonywania oraz pracowników odpowiedzialnych za ich przeprowadzenie. Definiowanie etapów zlecenia serwisowego i przypisanie ich do pracowników pozwala kontrolować przepływ zlecenia serwisowego przez zadania wykonywane przez różne osoby w organizacji usługi. Sekwencja etapów musi zawierać etap początkowy.

Można także zdefiniować działania, które są dozwolone na każdym etapie. Na przykład wyczyszczenie pola wyboru **Księguj** dla wszystkich etapów poza etapem ostatnim spowoduje, że wszelkie zlecenia serwisowe będą księgowane dopiero po przetworzeniu zleceń serwisowych na wszystkich kolejnych etapach.

## <a name="branching-in-service-order-stages"></a>Odgałęzienia na etapach zlecenia serwisowego

Konfigurując etap usługi, możesz utworzyć wiele opcji lub odgałęzień możliwych do wyboru na następnym etapie usługi. Wszystkich utworzone odgałęzienia są dostępne do wyboru po wykonaniu etapu początkowego. Załóżmy, że etapem początkowym **Planowanie**. Tworzysz dwa etapy o nazwie **W trakcie realizacji** i **Anulowanie**, a następnie wybierasz **Planowanie** jako element nadrzędny. Przypisujesz etap **Planowanie** do zamówienia sprzedaży. Kiedy etap planowania dla zamówienia sprzedaży zostanie wykonany, możesz wybrać etap **W trakcie realizacji** jeśli zamówienie sprzedaży jest gotowe do przetworzenia lub możesz wybrać etap **Anulowanie**, jeśli zamówienie sprzedaży zostało anulowane.

## <a name="see-also"></a>Informacje dodatkowe

[Ustawianie etapów zlecenia serwisowego](set-up-service-order-stages.md)

[Zmiana etapu zlecenia serwisowego](change-service-order-stage.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]