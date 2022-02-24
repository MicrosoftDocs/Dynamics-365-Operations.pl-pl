---
title: Konfigurowanie podwójnego zapisu z usług Lifecycle Services
description: W tym temacie wyjaśniono, jak skonfigurować połączenie podwójnego zapisywania między nowym środowiskiem Finance and Operations a nowym środowiskiem Dataverse za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS).
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 25db9c58c3d09e44dcf11b48cae1a9eda4241c35
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683532"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Konfigurowanie podwójnego zapisu z usług Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie wyjaśniono, jak skonfigurować połączenie podwójnego zapisywania między nowym środowiskiem Finance and Operations a nowym środowiskiem Dataverse za pośrednictwem Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Wymagania wstępne

Aby skonfigurować połączenie podwójnego zapisywania, należy mieć uprawnienia administratora.

+ Trzeba mieć dostęp do dzierżawy.
+ Użytkownik musi być administratorem w obu środowiskach Finance and Operations i Dataverse.

## <a name="set-up-a-dual-write-connection"></a>Skonfiguruj połączenie podwójnego zapisywania

Aby skonfigurować połączenie podwójnego zapisu, należy wykonać następujące czynności.

1. W LCS przejdź do projektu.
2. Wybierz przycisk **Konfiguruj**, aby wdrożyć nowe środowisko.
3. Wybierz wersję. 
4. Wybierz topologię. Jeśli dostępna jest tylko jedna topologia, jest ona wybierana automatycznie.
5. Wykonaj pierwsze kroki w Kreatorze **ustawień wdrażania**.
6. Na karcie **Dataverse** wykonaj jeden z tych kroków:

    - Jeśli już zainicjowano obsługę administracyjną środowiska Dataverse dla dzierżawy, można ją wybrać.

        1. Ustaw opcję **Konfiguruj Dataverse** na **Tak**.
        2. W polu **dostępne środowiska** Wybierz środowisko, które ma zostać zintegrowane z danymi Finance and Operations. Lista zawiera wszystkie środowiska, do których użytkownik ma uprawnienia administratora.
        3. Zaznacz pole wyboru **Wyrażam zgodę**, aby wskazać, że zgadzasz się na warunki.

        ![Karta Dataverse, jeśli zainicjowano już środowisko Dataverse dla dzierżawy](../dual-write/media/lcs_setup_1.png)

    - Jeśli dzierżawa nie ma jeszcze środowiska Dataverse, zostanie zainicjowana obsługa nowego środowiska.

        1. Ustaw opcję **Konfiguruj Dataverse** na **Tak**.
        2. Wprowadź nazwę środowiska Dataverse.
        3. Wybierz region, w którym ma zostać wdrożone środowisko.
        4. Wybierz domyślny język i walutę dla środowiska.

            > [!NOTE]
            > Nie można zmienić języka i waluty w późniejszym terminie.

        5. Zaznacz pole wyboru **Wyrażam zgodę**, aby wskazać, że zgadzasz się na warunki.

        ![Karta Dataverse, gdy dzierżawca nie posiada jeszcze środowiska Dataverse](../dual-write/media/lcs_setup_2.png)

7. Wykonaj pozostałe kroki w Kreatorze **ustawień wdrażania**.
8. Gdy środowisko ma stan **wdrożone**, Otwórz stronę szczegóły środowiska. W sekcji **informacje o środowisku Dataverse** są wyświetlane nazwy połączonych środowisk Finance and Operations i Dataverse.

    ![Sekcja informacji o środowisku Dataverse](../dual-write/media/lcs_setup_3.png)

9. Administrator środowiska Finance and Operations musi zalogować się do usługi LCS i wybrać opcję **Połącz z CDS dla aplikacji**, by zakończyć połączenie. Na stronie Szczegóły środowiska są wyświetlane informacje kontaktowe administratora.

    Po zakończeniu połączenia stan jest aktualizowany do **Pomyślnie zakończone łączenie środowisk**.

10. Aby otworzyć obszar roboczy **integracji danych** w środowisku Finance and Operations i kontrolować dostępne szablony, wybierz **Połącz z CDS dla aplikacji**.

    ![Przycisk Połącz z CDS dla aplikacji w sekcji informacji o środowisku Dataverse](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> Nie można odłączyć środowisk za pomocą usługi LCS. Aby rozłączyć środowisko, Otwórz obszar roboczy **integracji danych** w środowisku Finance and Operations, a następnie wybierz opcję **Rozłącz**.
