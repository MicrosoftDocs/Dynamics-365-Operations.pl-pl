---
title: Tworzenie listu przewozowego
description: "W tym temacie opisano sposób tworzenia listu przewozowego podczas korzystania z procesów zarządzania magazynem."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ab5aa60198e442237fd85bb295589ae0ebe9c5f5
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="create-a-bill-of-lading"></a>Tworzenie listu przewozowego

[!include[banner](../includes/banner.md)]


W tym temacie opisano sposób tworzenia listu przewozowego podczas korzystania z procesów zarządzania magazynem.  

List przewozowy jest to dokumentem prawnym między firmą wysyłającą towary a przewoźnikiem. Dokument towarzyszy wysyłanym towarom i służy jako potwierdzenie dostawcy, gdy towary są dostarczane do miejsca docelowego. Jeśli używasz zarządzania magazynem, istnieją dwa sposoby generowania listu przewozowego:

  -   Tworzenie raportu ręcznie za pomocą strony **List przewozowy**.
  -   Generowanie raportu z **warsztatu planowania wysyłki ładunku**.

Jeśli generujesz list przewozowy z **warsztatu planowania wysyłki ładunku**, ładunek musi mieć stan **Wysłano**. Jeśli występuje więcej niż jedna wysyłka w ładunku, list przewozowy jest tworzony dla każdej wysyłki. Po utworzeniu listu przewozowego można wprowadzać w nim zmiany na stronie **List przewozowy**.

## <a name="master-bill-of-lading"></a>Główny list przewozowy
Jeśli ładunek obejmuje kilka wysyłek, można utworzyć główny list przewozowy. Ma on taki sam układ i informacje, jak list przewozowy, ale sumuje zawartość wszystkich wysyłek. Jeśli na stronie **Parametry zarządzania transportem** w opcji **Utwórz główny list przewozowy, jeśli ładunek obejmuje kilka wysyłek** jest ustawiona wartość **Tak**, główny list przewozowy jest generowany automatycznie, jeżeli tworzysz list przewozowego z **warsztatu planowania wysyłki ładunku** w warunkach istnienia więcej niż jednej dostawy. Można także wyświetlić spis listów przewozowych, klikając kolejno opcje **Informacje pokrewne** &gt; **List przewozowy**. Jeśli tworzysz listy przewozowe ręcznie, można utworzyć główny list przewozowy na stronie **List przewozowy**.




