---
title: Tworzenie listu przewozowego
description: "W tym temacie opisano sposób tworzenia listu przewozowego podczas korzystania z procesów zarządzania magazynem."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: b88679f1be00d6a7168c8976f0d7db894c7e77fc
ms.lasthandoff: 03/31/2017


---

# <a name="create-a-bill-of-lading"></a>Tworzenie listu przewozowego

W tym temacie opisano sposób tworzenia listu przewozowego podczas korzystania z procesów zarządzania magazynem.  

List przewozowy jest to dokumentem prawnym między firmą wysyłającą towary a przewoźnikiem. Dokument towarzyszy wysyłanym towarom i służy jako potwierdzenie dostawcy, gdy towary są dostarczane do miejsca docelowego. Jeśli używasz zarządzania magazynem, istnieją dwa sposoby generowania listu przewozowego:

  -   Tworzenie raportu ręcznie za pomocą strony **List przewozowy**.
  -   Generowanie raportu z **warsztatu planowania wysyłki ładunku**.

Jeśli generujesz list przewozowy z **warsztatu planowania wysyłki ładunku**, ładunek musi mieć stan **Wysłano**. W przypadku więcej niż jednej dostawy w ładunku, konosament jest tworzony dla każdej przesyłki. Po listu przewozowego został utworzony użytkownik może wprowadzanie zmian do niej na **listu przewozowego** strony.

## <a name="master-bill-of-lading"></a>Główny list przewozowy
Jeśli ładunek obejmuje kilka wysyłek, można utworzyć główny list przewozowy. Ma on taki sam układ i informacje, jak list przewozowy, ale sumuje zawartość wszystkich wysyłek. Jeśli na stronie **Parametry zarządzania transportem** w opcji **Utwórz główny list przewozowy, jeśli ładunek obejmuje kilka wysyłek** jest ustawiona wartość **Tak**, główny list przewozowy jest generowany automatycznie, jeżeli tworzysz list przewozowego z **warsztatu planowania wysyłki ładunku** w warunkach istnienia więcej niż jednej dostawy. Można także uzyskać listę listy przewozowe klikając **informacje związane z**&gt;**listu przewozowego**. Jeśli tworzysz listy przewozowe ręcznie, można utworzyć główny list przewozowy na stronie **List przewozowy**.


