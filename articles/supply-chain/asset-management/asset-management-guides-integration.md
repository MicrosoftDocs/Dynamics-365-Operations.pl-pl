---
title: Integrowanie aplikacji Dynamics 365 Supply Chain Management (zarządzanie składnikami majątku) z aplikacją Dynamics 365 Guides
description: W tym temacie objaśniono sposób integrowania modułu zarządzania składnikami majątku w aplikacji Microsoft Dynamics 365 Supply Chain Management z aplikacją Dynamics 365 Guides. Pozwoli to na korzystanie z zalet przewodników po rzeczywistości mieszanej w codziennych przepływach pracy dotyczących usług i konserwacji.
author: kamaybac
manager: tfehr
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f9ee7f1af8e88f56589c84bfaa063ea005aa353a
ms.sourcegitcommit: 88b4a9d19d16b0ef6543adf7c378a08bf0e07b3a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/29/2020
ms.locfileid: "3311788"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a>Integrowanie aplikacji Dynamics 365 Supply Chain Management (zarządzanie składnikami majątku) z aplikacją Dynamics 365 Guides

Możesz zintegrować moduł **Zarządzanie składnikami majątku** w aplikacji Microsoft Dynamics 365 Supply Chain Management z aplikacją Dynamics 365 Guides, aby korzystać z zalet przewodników po rzeczywistości mieszanej w codziennych przepływach pracy dotyczących usług i konserwacji. Jeśli przewodnik został skojarzony ze zleceniem pracy modułu Zarządzanie składnikami majątku, pracownik, który otworzy listę kontrolną konserwowanego składnika majątku ze zlecenia pracy w aplikacji mobilnej Supply Chain Management (Dynamics 365), zobaczy, że przewodnik jest dostępny. Pracownik może następnie znaleźć i otworzyć przewodnik w aplikacji Dynamics 365 Guides dla urządzenia HoloLens.

## <a name="prerequisites"></a>Wymagania wstępne

Przed dołączeniem przewodników do zleceń pracy modułu Zarządzanie składnikami majątku należy spełnić następujące wymagania wstępne:

- [Skonfigurowanie aplikacji Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) w wersji 10.0.9 lub nowszej.
- [Włączenie podwójnego zapisu w aplikacji Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).
- [Włączenie dystrybucji testowej](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) funkcji **MRGuidesFeature**. (W przypadku środowisk produkcyjnych należy najpierw przesłać bilet pomocy technicznej, aby dzierżawa została dodana do grupy dystrybucji testowej).
- [Włączenie następujących kluczy konfiguracji](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) na stronie **Konfiguracja licencji**:

    - Zarządzanie składnikami majątku \> Rzeczywistość mieszana zarządzania składnikami majątku
    - Rzeczywistość mieszana \> Przewodnik w rzeczywistości mieszanej

- [Skonfigurowanie aplikacji Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) w wersji 200.0.0.96 lub nowszej.

## <a name="use-dynamics-365-guides-with-asset-management"></a>Używanie aplikacji Dynamics 365 Guides z zarządzaniem składnikami majątku

Aby skojarzyć przewodnik, należy skorzystać z wiersza listy kontrolnej konserwowanego składnika majątku w module Zarządzanie składnikami majątku. Skojarzenie można utworzyć za pomocą szablonu listy kontrolnej konserwowanego składnika majątku, typu zadania konserwacji lub zlecenia produkcyjnego, ponieważ wszystkie trzy zawierają wiersze listy kontrolnej konserwowanego składnika majątku. Użycie szablonu umożliwi zaoszczędzenie czasu, ponieważ szablon można skojarzyć ze wszystkimi typami zadań konserwacji, które go używają. Na przykład przewodnik skojarzony z typem zadania konserwacji jest automatycznie kojarzony ze wszystkimi zleceniami pracy określającymi ten typ zadania. Z drugiej strony przewodnik skojarzony bezpośrednio ze zleceniem pracy istnieje tylko dla tego zlecenia pracy.

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a>Kojarzenie przewodnika z szablonem listy kontrolnej konserwowanego składnika majątku

Aby skojarzyć przewodnik z szablonem listy kontrolnej konserwowanego składnika majątku, wykonaj poniższe kroki.

1. Utwórz przewodnik, korzystając z aplikacji Dynamics 365 Guides na komputer i urządzenie HoloLens. Aby uzyskać więcej informacji dotyczących sposobu tworzenia przewodnika, zobacz następujące tematy:

    - [Tworzenie przewodnika przy użyciu aplikacji komputerowej](https://docs.microsoft.com/dynamics365/mixed-reality/guides/pc-app-overview)
    - [Umieszczanie hologramów przy użyciu aplikacji HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-overview)

1. W aplikacji Supply Chain Management [utwórz szablon listy konserwowanego składnika majątku](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).
1. Skojarz utworzony przewodnik z wierszem listy kontrolnej konserwowanego składnika majątku w nowym szablonie listy kontrolnej konserwowanego składnika majątku:

    1. Na skróconej karcie **Wiersze listy kontrolnej konserwowanego składnika majątku** wybierz wiersz, z którym chcesz skojarzyć przewodnik.
    1. Na skróconej karcie **Skojarzone przewodniki** wybierz pozycję **Dodaj przewodnik**.

        ![Kojarzenie przewodnika z wierszem listy kontrolnej konserwowanego składnika majątku](media/am-guides-integration-add-guide.png "Kojarzenie przewodnika z wierszem listy kontrolnej konserwowanego składnika majątku")

    1. W polu **Nazwa** wybierz przewodnik, a następnie wybierz pozycję **Zapisz**.

        ![Wybieranie przewodnika w polu Nazwa](media/am-guides-integration-select-guide.png "Wybieranie przewodnika w polu Nazwa")

1. Skojarz szablon listy kontrolnej konserwowanego składnika majątku z typem pracy:

    1. [Utwórz typ zadania konserwacji](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) lub wybierz istniejący typ zadania konserwacji.
    1. W okienku akcji wybierz pozycję **Ustawienia domyślne typu zadania konserwacji**.

        ![Przycisk Ustawienia domyślne typu zadania konserwacji](media/am-guides-integration-job-defaults.png "Przycisk Ustawienia domyślne typu zadania konserwacji")

    1. Utwórz wiersz i wybierz pozycję **Zapisz**.

        ![Tworzenie wiersza](media/am-guides-integration-add-line.png "Tworzenie wiersza")

    1. W okienku akcji wybierz pozycję **Lista kontrolna konserwowanego składnika majątku**.

        ![Przycisk Lista kontrolna konserwowanego składnika majątku](media/am-guides-integration-maintenance-checklist.png "Przycisk Lista kontrolna konserwowanego składnika majątku")

    1. Na skróconej karcie **Wiersze listy kontrolnej konserwowanego składnika majątku** dodaj wiersz, a następnie zmień wartość w polu **Typ** na **Szablon**.

        ![Zmienianie wartości typu](media/am-guides-integration-checklist-lines.png "Zmienianie wartości typu")

    1. Na skróconej karcie **Szczegóły wiersza** w polu **Szablon** wybierz szablon, z którym został skojarzony przewodnik, a następnie wybierz pozycję **Zapisz**.

        ![Wybieranie szablonu](media/am-guides-integration-checklist-line-details.png "Wybieranie szablonu")

1. [Utwórz zlecenie pracy](work-orders/manually-created-workorders.md#create-work-order), a następnie wybierz typ zadania konserwacji, w którym jest używany szablon listy kontrolnej konserwowanego składnika majątku, z którym skojarzono dany przewodnik. Przewodnik zostanie automatycznie skojarzony ze zleceniem pracy.

    ![Wybieranie typu zadania konserwacji](media/am-guides-integration-create-work-order.png "Wybieranie typu zadania konserwacji")

1. Wyświetl przewodnik skojarzony ze zleceniem pracy i pracownikami:

    1. Otwórz [obszar roboczy zarządzania składnikami majątku](asset-management-mobile-workspace.md), aby uzyskać dostęp do zlecenia pracy.
    1. [Otwórz listę kontrolną konserwowanego składnika majątku](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) dla zlecenia pracy.
    1. Wybierz wiersz listy kontrolnej, aby wyświetlić skojarzony przewodnik.

        ![Przewodnik skojarzony z wierszem listy kontrolnej](media/am-guides-integration-show-guide.png "Przewodnik skojarzony z wierszem listy kontrolnej")

    1. Otwórz przewodnik na urządzeniu HoloLens.

        ![Otwieranie przewodnika na urządzeniu HoloLens](media/am-guides-integration-hololens-select.png "Otwieranie przewodnika na urządzeniu HoloLens")

> [!NOTE]
> Można również skojarzyć przewodnik bezpośrednio z listą kontrolną konserwowanego składnika majątku zlecenia pracy lub typu pracy.

> [!IMPORTANT]
> Znany jest problem polegający na tym, że w przypadku skojarzenia szablonu listy kontrolnej konserwowanego składnika majątku z domyślnym typem zadania konserwacji przewodnik połączony z szablonem nie jest wyświetlany na skróconej karcie **Skojarzone przewodniki** strony **Ustawienia domyślne typu zadania konserwacji**. Jednak przewodnik będzie wyświetlany po zastosowaniu tego typu zadania do zlecenia pracy na skróconej karcie **Skojarzone przewodniki**.

## <a name="see-also"></a>Informacje dodatkowe

- [Przegląd o podwójnym zapisie](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [Omówienie zarządzania składnikami majątku](index.md)
