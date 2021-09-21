---
title: Mieszane typy zapasów podczas używania profilu zarządzania na rampie
description: Aby profil zarządzania na rampie mógł efektywnie zarządzać mieszaniem zapasów, należy najpierw ustawić przerwę w nagłówku pracy. Na tej stronie wyjaśniono, jak to zrobić.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cc660a2f9839e886240c97a7f60d2e264653074a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477292"
---
# <a name="inventory-types-are-being-mixed-when-using-a-dock-management-profile"></a>Typy zapasów są mieszane podczas używania profilu zarządzania na rampie

## <a name="symptoms"></a>Objawy

Korzystasz z *zasad konsolidacji przesyłek*. Skonfigurowano *profil zarządzania na rampie* dla *profilu lokalizacji*, ale po utworzeniu pracy typy zapasów są mieszane w ostatecznej lokalizacji.

## <a name="resolution"></a>Rozwiązanie

Profile zarządzania na rampie wymagają wcześniejszego podziału pracy. Profil zarządzania na rampie oczekuje, że nagłówek pracy nie będzie zawierał wielu lokalizacji odłożyń.

Aby profil zarządzania dokiem mógł efektywnie zarządzać mieszaniem zapasów, należy ustawić przerwę w nagłówku pracy.

W tym przykładzie nasz profil zarządzania dokiem jest skonfigurowany tak, że **Typy zapasów, które nie powinny być mieszane**, są ustawione na *Identyfikator przesyłki*, a my ustawimy przerwę w nagłówku pracy:

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. Wybierz **Typ zlecenia pracy** do edycji (na przykład *Zamówienia zakupu*).
1. Wybierz szablon pracy do edycji.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. Otwórz kartę **Sortowanie** i dodaj wiersz z następującymi ustawieniami:
    - **Tabela** - *Tymczasowe transakcje pracy*
    - **Tabela pochodna** - *Tymczasowe transakcje pracy*
    - **Pole** - *Identyfikator wysyłki*
1. Kliknij przycisk **OK**.
1. Wróć do strony **Szablony pracy**. W okienku akcji wybierz **Podziały nagłówka pracy**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Zaznacz pole wyboru skojarzone z **Polem o nazwie** *Identyfikator wysyłki*.
1. Na okienku akcji wybierz opcję **Zapisz**.
