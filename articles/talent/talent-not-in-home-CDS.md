---
title: "Aplikacja Talent nie jest wyświetlana na liście aplikacji usługi Microsoft Dynamics 365 (CDS1.0)"
description: "W tym temacie wyjaśniono, co należy zrobić, jeśli klient nie widzi aplikacji Microsoft Dynamics 365 for Talent wśród aplikacji Microsoft Dynamics 365."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

---

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a>Aplikacja Talent nie jest wyświetlana na liście aplikacji usługi Microsoft Dynamics 365 (CDS1.0)

[!include [banner](includes/banner.md)]

**Wydaj**

Klient nie widzi aplikacji Microsoft Dynamics 365 for Talent wśród aplikacji Microsoft Dynamics 365.

**Rozdzielczość**

Użytkownik musi być dodany do roli Twórca środowisk dla środowiska w Microsoft PowerApps.

1. Administrator mający licencję usługi PowerApps planu 2 musi otworzyć [portal administratorów usługi PowerApps](https://preview.admin.powerapps.com/).
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

