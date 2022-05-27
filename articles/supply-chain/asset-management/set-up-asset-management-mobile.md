---
title: Konfigurowanie mobilnego obszaru roboczego zarządzania składnikami majątku
description: W tym temacie opisano sposób konfigurowania rozwiązania Microsoft Dynamics 365 Supply Chain Management i aplikacji mobilnej Finance and Operations (Dynamics 365) w celu uruchomienia mobilnego obszaru roboczego Zarządzanie składnikami majątku, za pomocą których pracownicy mogą wykonywać zadania zarządzania składnikami majątku.
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a056be417d266fd400ce1572312f327dc070cb6a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693508"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>Konfigurowanie mobilnego obszaru roboczego zarządzania składnikami majątku

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfigurowania rozwiązania Microsoft Dynamics 365 Supply Chain Management i aplikacji mobilnej Finance and Operations (Dynamics 365) w celu uruchomienia mobilnego obszaru roboczego **Zarządzanie składnikami majątku**, za pomocą których pracownicy mogą wykonywać zadania zarządzania składnikami majątku.

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a>Konfigurowanie użytkowników konserwatorów w aplikacji Supply Chain Management

Dla każdego użytkownika, który wymaga dostępu do mobilnego obszaru roboczego **Zarządzanie składnikami majątku**, wykonaj następujące kroki.

1. W aplikacji Supply Chain Management przejdź do grupy **Zasoby ludzkie \> Pracownicy** i upewnij się, że dla użytkownika, który ma zostać ustawiony, istnieje rekord pracownika. Utwórz nowy rekord pracownika zgodnie z potrzebami.
1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Ustawienia \> Pracownicy \> Pracownicy** i upewnij się, że rekord pracownika, który został zidentyfikowany (lub utworzony) w poprzednim kroku, jest zamapowany na rekord konserwatora. Utwórz w razie potrzeby nowy rekord konserwatora i ustaw w polu **Pracownik** rekord pracownika z poprzedniego kroku.
1. Przejdź do obszaru **Zarządzanie składnikami majątku \> Ustawienia \> Pracownicy \> Grupy konserwatorów** i upewnij się, że rekord konserwatora, który został zidentyfikowany (lub utworzony) w poprzednim kroku, należy do grupy konserwatorów.
1. Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy**.
1. Wybierz odpowiedniego użytkownika w siatce.
1. Na skróconej karcie **Szczegóły użytkownika** ustaw pole **Osoba** na konto pracownika, które chcesz skojarzyć z bieżącym kontem użytkownika. To konto pracownika powinno być rekordem pracownika, który został zidentyfikowany (lub utworzony) w kroku 1 i zamapowany na rekord konserwatora w kroku 2.

> [!NOTE]
> Uprawnienia użytkowników i role zabezpieczeń mają zastosowanie do funkcji mobilnego obszaru roboczego **Zarządzanie składnikami majątku** w ten sam sposób, jak do funkcji interfejsu użytkownika aplikacji Supply Chain Management. Każdy użytkownik ustawiony do uzyskiwania dostępu do mobilnego obszaru roboczego **Zarządzanie składnikami majątku** musi mieć role zabezpieczeń wymagane do wykonywania podobnych operacji bezpośrednio w aplikacji Supply Chain Management.

## <a name="publish-the-asset-management-mobile-workspace"></a>Publikowanie w mobilnym obszarze roboczym zarządzania składnikami majątku

Aby udostępnić funkcje zarządzania składnikami majątku w aplikacji mobilnej Finance and Operations (Dynamics 365), musisz opublikować mobilny obszar roboczy **Zarządzanie składnikami majątku**.

1. W aplikacji Supply Chain Management wybierz przycisk **Ustawienia** (symbol koła zębatego w prawym górnym rogu), a następnie wybierz w menu pozycję **Aplikacja mobilna**.
1. W oknie dialogowym **Zarządzaj aplikacją mobilną** znajdź kafelek **Zarządzanie składnikami majątku**. Jeśli zawiera on tekst „W metadanych — nie opublikowano”, obszar roboczy nie został jeszcze opublikowany. Jeśli zawiera on tekst „W metadanych — opublikowano”, obszar roboczy został już opublikowany, dlatego możesz pominąć pozostałą część tej procedury.

    ![Okno dialogowe zarządzania aplikacją mobilną.](media/mobile-workspaces.png "Okno dialogowe zarządzania aplikacją mobilną")

1. Wybierz kafelek **Zarządzanie składnikami majątku**, a następnie wybierz pozycję **Publikuj** na pasku narzędzi. Po kilku sekundach powinien zostać wyświetlony komunikat o pomyślnym opublikowaniu obszaru roboczego. Ponadto tekst na kafelku powinien się zmienić na „W metadanych — opublikowano”.

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>Zainstaluj i skonfiguruj aplikację mobilną Finance and Operations (Dynamics 365)

1. Przejdź do jednego z następujących sklepów z aplikacjami, aby zainstalować **aplikacja Microsoft Finance and Operations (Dynamics 365)** na urządzeniu przenośnym:

    - [Dla urządzeń z systemem Android firmy Google](https://go.microsoft.com/fwlink/?linkid=850662)
    - [Dla urządzeń z systemem IOS firmy Apple](https://go.microsoft.com/fwlink/?linkid=850663)

1. Otwórz aplikację Finance and Operations (Dynamics 365). Powinna zostać wyświetlana strona logowania. W polu **Zaloguj się** wprowadź adres URL aplikacji Supply Chain Management lub wybierz ostatni adres URL z listy **Ostatnie środowiska**, a następnie naciśnij pozycję **Połącz**.

    ![Strona logowania.](media/mobile-app-sign-in.png "Strona logowania")

1. Jeśli zostanie wyświetlony monit o potwierdzenie połączenia, zaznacz pole wyboru **Rozumiem**, a następnie kliknij pozycję **Połącz**.
1. Na stronie **Wybierz konto** użyj konta Microsoft, aby zalogować się do aplikacji na urządzenia mobilnej.

    Zostanie wyświetlona strona **Obszary robocze**. Zawiera listę wszystkich mobilnych obszarów roboczych, które zostały opublikowane przez wystąpienie aplikacji Supply Chain Management.

    ![Lista obszarów roboczych.](media/mobile-app-workspaces.png "Lista obszarów roboczych")

1. Jeśli musisz zmienić osobę prawną (firmę), kliknij w lewym górnym rogu przycisk Menu (czasami określany jako menu lub przycisk typu „hamburger”) i kliknij pozycję **Zmień firmę**.

    ![Zmienianie osoby prawnej.](media/mobile-app-change-comp.png "Zmienianie osoby prawnej")

1. Na stronie **Obszary robocze** wybierz obszar roboczy, z którym chcesz pracować, aby go otworzyć.

    ![Mobilny obszar roboczy zarządzania składnikami majątku.](media/mobile-app-asset-workspace.png "Mobilny obszar roboczy zarządzania składnikami majątku")

## <a name="work-with-the-asset-management-mobile-workspace"></a>Praca z mobilnym obszarem roboczym zarządzania składnikami majątku

Aby uzyskać więcej informacji dotyczących pracy z mobilnym obszarem roboczym **Zarządzanie składnikami majątku**, zobacz temat [Korzystanie z mobilnego obszaru roboczego zarządzanie składnikami majątku](asset-management-mobile-workspace.md).

Aby uzyskać więcej informacji o aplikacji mobilnej Finance and Operations (Dynamics 365), zobacz [stronę główną aplikacji mobilnej](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]