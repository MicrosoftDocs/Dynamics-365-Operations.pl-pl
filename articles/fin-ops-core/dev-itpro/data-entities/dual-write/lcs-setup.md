---
title: Konfigurowanie podwójnego zapisu z usług Lifecycle Services
description: W tym temacie wyjaśniono, jak skonfigurować połączenie podwójnego zapisywania między nowym środowiskiem Finance and Operations a nowym środowiskiem Common Data Service za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 75765c0cc03c64030fac6bc656f57a143828b85b
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112501"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Konfigurowanie podwójnego zapisu z usług Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W tym temacie wyjaśniono, jak skonfigurować połączenie podwójnego zapisywania między nowym środowiskiem Finance and Operations a nowym środowiskiem Common Data Service za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować połączenie podwójnego zapisywania, należy mieć uprawnienia administratora.

+ Trzeba mieć dostęp do dzierżawy.
+ Użytkownik musi być administratorem w obu środowiskach Finance and Operations i Common Data Service.

## <a name="set-up-a-dual-write-connection"></a>Skonfiguruj połączenie podwójnego zapisywania

Aby skonfigurować połączenie podwójnego zapisu, należy wykonać następujące czynności.

1. W LCS przejdź do projektu.
2. Wybierz przycisk **Konfiguruj**, aby wdrożyć nowe środowisko.
3. Wybierz wersję. 
4. Wybierz topologię. Jeśli dostępna jest tylko jedna topologia, jest ona wybierana automatycznie.
5. Wykonaj pierwsze kroki w Kreatorze **ustawień wdrażania**.
6. Na karcie **Common Data Service** wykonaj jeden z tych kroków:

    - Jeśli już zainicjowano obsługę administracyjną środowiska Common Data Service dla dzierżawy, można ją wybrać.

        1. Ustaw opcję **Konfiguruj Common Data Service** na **Tak**.
        2. W polu **dostępne środowiska** Wybierz środowisko, które ma zostać zintegrowane z danymi Finance and Operations. Lista zawiera wszystkie środowiska, do których użytkownik ma uprawnienia administratora.
        3. Zaznacz pole wyboru **Wyrażam zgodę**, aby wskazać, że zgadzasz się na warunki.

        ![Karta Common Data Service, jeśli zainicjowano już środowisko Common Data Service dla dzierżawy](../dual-write/media/lcs_setup_1.png)

    - Jeśli dzierżawa nie ma jeszcze środowiska Common Data Service, zostanie zainicjowana obsługa nowego środowiska.

        1. Ustaw opcję **Konfiguruj Common Data Service** na **Tak**.
        2. Wprowadź nazwę środowiska Common Data Service.
        3. Wybierz region, w którym ma zostać wdrożone środowisko.
        4. Wybierz domyślny język i walutę dla środowiska.

            > [!NOTE]
            > Nie można zmienić języka i waluty w późniejszym terminie.

        5. Zaznacz pole wyboru **Wyrażam zgodę**, aby wskazać, że zgadzasz się na warunki.

        ![Karta Common Data Service, gdy dzierżawca nie posiada jeszcze środowiska Common Data Service](../dual-write/media/lcs_setup_2.png)

7. Wykonaj pozostałe kroki w Kreatorze **ustawień wdrażania**.
8. Gdy środowisko ma stan **wdrożone**, Otwórz stronę szczegóły środowiska. W sekcji **informacje o środowisku Common Data Service** są wyświetlane nazwy połączonych środowisk Finance and Operations i Common Data Service.

    ![Sekcja informacji o środowisku Common Data Service](../dual-write/media/lcs_setup_3.png)

9. Administrator środowiska Finance and Operations musi zalogować się do usługi LCS i wybrać opcję **Połącz z CDS dla aplikacji**, by zakończyć połączenie. Na stronie Szczegóły środowiska są wyświetlane informacje kontaktowe administratora.

    Po zakończeniu połączenia stan jest aktualizowany do **Pomyślnie zakończone łączenie środowisk**.

10. Aby otworzyć obszar roboczy **integracji danych** w środowisku Finance and Operations i kontrolować dostępne szablony, wybierz **Połącz z CDS dla aplikacji**.

    ![Przycisk Połącz z CDS dla aplikacji w sekcji informacji o środowisku Common Data Service](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> Nie można odłączyć środowisk za pomocą usługi LCS. Aby rozłączyć środowisko, Otwórz obszar roboczy **integracji danych** w środowisku Finance and Operations, a następnie wybierz opcję **Rozłącz**.
