---
title: Tworzenie listu przewozowego
description: W tym temacie opisano sposób tworzenia listu przewozowego podczas korzystania z procesów zarządzania magazynem.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench, WHSBillOfLadingCarrier, WHSBillOfLadingOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b001ef8936e7e35db89163683c023211f79b24c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996480"
---
# <a name="create-a-bill-of-lading"></a>Tworzenie listu przewozowego

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia listu przewozowego podczas korzystania z procesów zarządzania magazynem.  

List przewozowy jest to dokumentem prawnym między firmą wysyłającą towary a przewoźnikiem. Dokument towarzyszy wysyłanym towarom i służy jako potwierdzenie dostawcy, gdy towary są dostarczane do miejsca docelowego. Jeśli używasz zarządzania magazynem, istnieją dwa sposoby generowania listu przewozowego:

  -   Tworzenie raportu ręcznie za pomocą strony **List przewozowy**.
  -   Generowanie raportu z **warsztatu planowania wysyłki ładunku**.

Jeśli generujesz list przewozowy z **warsztatu planowania wysyłki ładunku**, ładunek musi mieć stan **Wysłano**. Jeśli występuje więcej niż jedna wysyłka w ładunku, list przewozowy jest tworzony dla każdej wysyłki. Po utworzeniu listu przewozowego można wprowadzać w nim zmiany na stronie **List przewozowy**.

## <a name="master-bill-of-lading"></a>Główny list przewozowy
Jeśli ładunek obejmuje kilka wysyłek, można utworzyć główny list przewozowy. Ma on taki sam układ i informacje, jak list przewozowy, ale sumuje zawartość wszystkich wysyłek. Jeśli na stronie **Parametry zarządzania transportem** w opcji **Utwórz główny list przewozowy, jeśli ładunek obejmuje kilka wysyłek** jest ustawiona wartość **Tak**, główny list przewozowy jest generowany automatycznie, jeżeli tworzysz list przewozowego z **warsztatu planowania wysyłki ładunku** w warunkach istnienia więcej niż jednej dostawy. Można także wyświetlić spis listów przewozowych, klikając kolejno opcje **Informacje pokrewne** &gt; **List przewozowy**. Jeśli tworzysz listy przewozowe ręcznie, można utworzyć główny list przewozowy na stronie **List przewozowy**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]