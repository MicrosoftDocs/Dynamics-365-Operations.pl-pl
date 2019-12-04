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
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a><span data-ttu-id="12870-103">Rozwiązanie Talent nie jest wyświetlane na liście aplikacji usługi Microsoft Dynamics 365 (Common Data Service 1.0)</span><span class="sxs-lookup"><span data-stu-id="12870-103">Talent doesn't appear among the Microsoft Dynamics 365 apps (Common Data Service 1.0)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="12870-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="12870-104">**Issue**</span></span>

<span data-ttu-id="12870-105">Klient nie widzi aplikacji Microsoft Dynamics 365 Talent wśród aplikacji Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="12870-105">The customer doesn't see the Microsoft Dynamics 365 Talent app among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="12870-106">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="12870-106">**Resolution**</span></span>

<span data-ttu-id="12870-107">Użytkownik musi być dodany do roli Twórca środowisk dla środowiska w Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="12870-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="12870-108">Administrator mający licencję usługi Power Apps planu 2. musi otworzyć [portal administratorów usługi Power Apps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="12870-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>
2. <span data-ttu-id="12870-109">Wybierz **środowiska**, a następnie wybierz poprawne środowisko dla Talent.</span><span class="sxs-lookup"><span data-stu-id="12870-109">Select **Environments**, and select the correct environment for Talent.</span></span>
3. <span data-ttu-id="12870-110">Na karcie **zabezpieczeń** na karcie **ról środowiska** wybierz opcję **Twórca środowiska**.</span><span class="sxs-lookup"><span data-stu-id="12870-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Karta role środowiska](media/environment-roles.png)

4. <span data-ttu-id="12870-112">Na karcie **użytkownicy** dodać użytkownika lub organizację.</span><span class="sxs-lookup"><span data-stu-id="12870-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Karta użytkowników](media/environment-maker.png)

5. <span data-ttu-id="12870-114">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="12870-114">Select **Save**.</span></span>
6. <span data-ttu-id="12870-115">Użytkownik musi teraz zalogować się do [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="12870-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>
7. <span data-ttu-id="12870-116">Wybierz **Synchronizuj**, aby zaktualizować aplikacje użytkownika.</span><span class="sxs-lookup"><span data-stu-id="12870-116">Select **Sync** to update the user apps.</span></span>

    ![Przycisk synchronizacji](media/get-more.png)

    <span data-ttu-id="12870-118">Po zakończeniu synchronizacji aplikacja Talent będzie wyświetlana na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="12870-118">After synchronization is completed, Talent will appear on the home page.</span></span>
