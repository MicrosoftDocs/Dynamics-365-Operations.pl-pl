---
title: Human Resources nie wyświetla się w ramach aplikacji Microsoft Dynamics 365
description: W tym temacie wyjaśniono, co należy zrobić, jeśli aplikacja Microsoft Dynamics 365 Human Resources nie jest wyszczególniona na liście aplikacji Microsoft Dynamics 365.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dfed82463eece882bed66c7b2dac1dd30e04720e
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413408"
---
# <a name="human-resources-app-doesnt-appear-in-microsoft-dynamics-365-apps"></a>Aplikacja Human Resources nie jest wyświetlana wśród aplikacji Microsoft Dynamics 365

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problem**

Klient nie widzi programu Dynamics 365 Human Resources wśród aplikacji systemu Microsoft Dynamics 365.

**Rozdzielczość**

Użytkownik musi być dodany do roli Twórca środowisk dla środowiska w Microsoft Power Apps.

1. Administrator mający licencję usługi Power Apps planu 2. musi otworzyć [portal administratorów usługi Power Apps](https://preview.admin.powerapps.com/).

2. Wybierz opcję **Środowiska**, a następnie wybierz poprawne środowisko dla programu Human Resources.

3. Na karcie **zabezpieczeń** na karcie **ról środowiska** wybierz opcję **Twórca środowiska**.

    ![Karta role środowiska.](media/environment-roles.png)

4. Na karcie **użytkownicy** dodać użytkownika lub organizację.

    ![Karta użytkowników.](media/environment-maker.png)

5. Wybierz opcję **Zapisz**.

6. Użytkownik musi teraz zalogować się do [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Wybierz **Synchronizuj**, aby zaktualizować aplikacje użytkownika.

    ![Przycisk synchronizacji.](media/get-more.png)

    Po zakończeniu synchronizacji program Human Resources będzie wyświetlany na stronie głównej.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
