---
title: Dodatkowe strefy lokalizacji
description: Ten temat zawiera przegląd nowych stref lokalizacji, które zostały dodane do rozwiązania Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: AnnBe
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9727187ad555f9e3d09beed3f3447a22c29ed22a
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530174"
---
# <a name="additional-location-zones"></a>Dodatkowe strefy lokalizacji

[!include [banner](../includes/banner.md)]

W rozwiązaniu Microsoft Dynamics 365 Supply Chain Management są dostępne trzy nowe pola strefy. Kierownicy magazynów mogą używać ich do stworzenia dodatkowych organizacji lub układów magazynu. Nowe pola stref można ustawiać ręcznie lub przy użyciu kreatora **konfiguracji lokalizacji**. Można ich używać w dowolnej kwerendzie lub filtrowaniu, w której jest używana tabela lokalizacje.

Do użycia pól strefy nie są wymagane żadne dodatkowe ustawienia.

## <a name="turn-on-the-additional-location-zone-feature"></a>Włącz funkcję dodatkowej strefy lokalizacji

Aby móc używać funkcji *Dodatkowa strefa lokalizacji*, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Dodatkowa strefa lokalizacji*

## <a name="use-location-zones"></a>Używanie stref lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.
2. Ustaw następujące wartości:

    - W polu **Magazyn** wybierz wartość _62_.
    - W polu **Identyfikator strefy** wpisz wartość _FLOOR_.
    - W polu **Dodatkowa strefa 1** wybierz wartość _PICKZONE1_.
    - W polu **Dodatkowa strefa 2** wybierz wartość _WEBSHOP1_.
    - W polu **Identyfikator profilu lokalizacji** wybierz _FLOOR_.

3. Wybierz wiersz **Piętro**.
4. W polu **Od numeru** wprowadź wartość _1_. W polu **Do numeru** wprowadź wartość _3_.
5. Wybierz wiersz **Korytarz**.
6. W polu **Od numeru** wprowadź wartość _1_. W polu **Do numeru** wprowadź wartość _5_.
7. Wybierz opcję **Utwórz**.
8. Otrzymujesz komunikaty informujące o dodaniu nowych lokalizacji. Wybierz przycisk **Pokaż komunikaty**, aby wyświetlić komunikaty.
9. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**. Nowe lokalizacje są wyświetlane na liście – dostępne są wszystkie pola strefy (to znaczy, istniejące pole strefy i nowe dodatkowe pola).
