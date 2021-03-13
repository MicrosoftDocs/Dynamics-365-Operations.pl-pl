---
title: Konfigurowanie podwójnego zapisu z usług Lifecycle Services
description: W tym temacie opisano sposób skonfigurowania połączenia podwójnego zapisu z usługi Microsoft Dynamics Lifecycle Services (LCS).
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
ms.openlocfilehash: df67e498b963af3ded7464f46f37bb4b2ca7d852
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127600"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Konfigurowanie podwójnego zapisu z usług Lifecycle Services

[!include [banner](../../includes/banner.md)]

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
        2. W kolumnie **Dostępne środowiska** wybierz środowisko, które ma zostać zintegrowane z danymi Finance and Operations. Lista zawiera wszystkie środowiska, do których użytkownik ma uprawnienia administratora.
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
8. Gdy środowisko ma stan **wdrożone**, Otwórz stronę szczegóły środowiska. W sekcji **integracji z platformą Power Platform** są wyświetlane nazwy połączonych środowisk Finance and Operations i Dataverse.

    ![Sekcja integracji z platformą Power Platform](../dual-write/media/lcs_setup_3.png)

9. Administrator środowiska Finance and Operations musi zalogować się do usługi LCS i wybrać opcję **Połącz z CDS dla aplikacji**, by zakończyć połączenie. Na stronie Szczegóły środowiska są wyświetlane informacje kontaktowe administratora.

    Po zakończeniu połączenia stan jest aktualizowany do **Pomyślnie zakończone łączenie środowisk**.

10. Aby otworzyć obszar roboczy **integracji danych** w środowisku Finance and Operations i kontrolować dostępne szablony, wybierz **Połącz z CDS dla aplikacji**.

    ![Link do przycisku CDS for Apps w sekcji integracji z platformą Power Platform](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> Nie można odłączyć środowisk za pomocą usługi LCS. Aby rozłączyć środowisko, Otwórz obszar roboczy **integracji danych** w środowisku Finance and Operations, a następnie wybierz opcję **Rozłącz**.

