---
title: Human Resources nie wyświetla się w ramach aplikacji Microsoft Dynamics 365
description: W tym artykule wyjaśniono, co należy zrobić, jeśli klient nie widzi aplikacji Microsoft Dynamics 365 Human Resources wśród aplikacji Microsoft Dynamics 365.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 658c6a4f17c022c3d0e3e49d16eb89624c4be27c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803976"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a>Human Resources nie wyświetla się w ramach aplikacji Microsoft Dynamics 365

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Wystawienie**

Klient nie widzi programu Dynamics 365 Human Resources wśród aplikacji systemu Microsoft Dynamics 365.

**Rozdzielczość**

Użytkownik musi być dodany do roli Twórca środowisk dla środowiska w Microsoft Power Apps.

1. Administrator mający licencję usługi Power Apps planu 2. musi otworzyć [portal administratorów usługi Power Apps](https://preview.admin.powerapps.com/).

2. Wybierz opcję **Środowiska**, a następnie wybierz poprawne środowisko dla programu Human Resources.

3. Na karcie **zabezpieczeń** na karcie **ról środowiska** wybierz opcję **Twórca środowiska**.

    ![Karta role środowiska](media/environment-roles.png)

4. Na karcie **użytkownicy** dodać użytkownika lub organizację.

    ![Karta użytkowników](media/environment-maker.png)

5. Wybierz opcję **Zapisz**.

6. Użytkownik musi teraz zalogować się do [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Wybierz **Synchronizuj**, aby zaktualizować aplikacje użytkownika.

    ![Przycisk synchronizacji](media/get-more.png)

    Po zakończeniu synchronizacji program Human Resources będzie wyświetlany na stronie głównej.


[!INCLUDE[footer-include](../includes/footer-banner.md)]