---
title: Rozwiązanie Talent nie jest wyświetlane na liście aplikacji usługi Microsoft Dynamics 365 (Common Data Service 1.0)
description: W tym temacie wyjaśniono, co należy zrobić, jeśli klient nie widzi aplikacji Microsoft Dynamics 365 Talent wśród aplikacji Microsoft Dynamics 365.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7f0cc1c7ec1234b7eedaade0ffadb66965ed2121
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772995"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a>Rozwiązanie Talent nie jest wyświetlane na liście aplikacji usługi Microsoft Dynamics 365 (Common Data Service 1.0)

[!include [banner](includes/banner.md)]

**Wystawienie**

Klient nie widzi aplikacji Microsoft Dynamics 365 Talent wśród aplikacji Microsoft Dynamics 365.

**Rozdzielczość**

Użytkownik musi być dodany do roli Twórca środowisk dla środowiska w Microsoft Power Apps.

1. Administrator mający licencję usługi Power Apps planu 2. musi otworzyć [portal administratorów usługi Power Apps](https://preview.admin.powerapps.com/).
2. Wybierz **środowiska**, a następnie wybierz poprawne środowisko dla Talent.
3. Na karcie **zabezpieczeń** na karcie **ról środowiska** wybierz opcję **Twórca środowiska**.

    ![Karta role środowiska](media/environment-roles.png)

4. Na karcie **użytkownicy** dodać użytkownika lub organizację.

    ![Karta użytkowników](media/environment-maker.png)

5. Wybierz opcję **Zapisz**.
6. Użytkownik musi teraz zalogować się do [Microsoft Dynamics 365](https://home.dynamics.com/).
7. Wybierz **Synchronizuj**, aby zaktualizować aplikacje użytkownika.

    ![Przycisk synchronizacji](media/get-more.png)

    Po zakończeniu synchronizacji aplikacja Talent będzie wyświetlana na stronie głównej.
