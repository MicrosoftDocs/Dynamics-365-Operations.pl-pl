---
title: Dodatkowe strefy lokalizacji
description: Ten artykuł zawiera przegląd nowych stref lokalizacji, które zostały dodane do rozwiązania Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 819330e0f6e6cd419da441f919d68ff996b6475c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336524"
---
# <a name="additional-location-zones"></a>Dodatkowe strefy lokalizacji

[!include [banner](../includes/banner.md)]

W rozwiązaniu Microsoft Dynamics 365 Supply Chain Management są dostępne trzy nowe pola strefy. Kierownicy magazynów mogą używać ich do stworzenia dodatkowych organizacji lub układów magazynu. Nowe pola stref można ustawiać ręcznie lub przy użyciu kreatora **konfiguracji lokalizacji**. Można ich używać w dowolnej kwerendzie lub filtrowaniu, w której jest używana tabela lokalizacje.

Do użycia pól strefy nie są wymagane żadne dodatkowe ustawienia.

## <a name="turn-the-additional-location-zone-feature-on-or-off"></a>Włącz lub wyłącz funkcję Dodatkowa strefa lokalizacji

Aby używać tej funkcji, należy ją włączyć dla systemu. Od wersji 10.0.25 Supply Chain Management funkcja jest domyślnie włączona. Od wersji 10.0.29 Supply Chain Management funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.29, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Dodatkowa strefa lokalizacji* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]