---
title: Human Resources nie wyświetla się w ramach aplikacji Microsoft Dynamics 365
description: W tym artykule wyjaśniono, co należy zrobić, jeśli klient nie widzi aplikacji Microsoft Dynamics 365 Human Resources wśród aplikacji Microsoft Dynamics 365.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
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
ms.openlocfilehash: d39e6ef4168f08f20b92979a296ed088744ad0da
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010276"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a><span data-ttu-id="e4a3d-103">Human Resources nie wyświetla się w ramach aplikacji Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e4a3d-103">Human Resources doesn't appear in Microsoft Dynamics 365 apps</span></span>

<span data-ttu-id="e4a3d-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="e4a3d-104">**Issue**</span></span>

<span data-ttu-id="e4a3d-105">Klient nie widzi programu Dynamics 365 Human Resources wśród aplikacji systemu Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e4a3d-105">The customer doesn't see Dynamics 365 Human Resources among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="e4a3d-106">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="e4a3d-106">**Resolution**</span></span>

<span data-ttu-id="e4a3d-107">Użytkownik musi być dodany do roli Twórca środowisk dla środowiska w Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e4a3d-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="e4a3d-108">Administrator mający licencję usługi Power Apps planu 2. musi otworzyć [portal administratorów usługi Power Apps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="e4a3d-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>

2. <span data-ttu-id="e4a3d-109">Wybierz opcję **Środowiska**, a następnie wybierz poprawne środowisko dla programu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e4a3d-109">Select **Environments**, and select the correct environment for Human Resources.</span></span>

3. <span data-ttu-id="e4a3d-110">Na karcie **zabezpieczeń** na karcie **ról środowiska** wybierz opcję **Twórca środowiska**.</span><span class="sxs-lookup"><span data-stu-id="e4a3d-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Karta role środowiska](media/environment-roles.png)

4. <span data-ttu-id="e4a3d-112">Na karcie **użytkownicy** dodać użytkownika lub organizację.</span><span class="sxs-lookup"><span data-stu-id="e4a3d-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Karta użytkowników](media/environment-maker.png)

5. <span data-ttu-id="e4a3d-114">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e4a3d-114">Select **Save**.</span></span>

6. <span data-ttu-id="e4a3d-115">Użytkownik musi teraz zalogować się do [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="e4a3d-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>

7. <span data-ttu-id="e4a3d-116">Wybierz **Synchronizuj**, aby zaktualizować aplikacje użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e4a3d-116">Select **Sync** to update the user apps.</span></span>

    ![Przycisk synchronizacji](media/get-more.png)

    <span data-ttu-id="e4a3d-118">Po zakończeniu synchronizacji program Human Resources będzie wyświetlany na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="e4a3d-118">After synchronization is completed, Human Resources will appear on the home page.</span></span>
