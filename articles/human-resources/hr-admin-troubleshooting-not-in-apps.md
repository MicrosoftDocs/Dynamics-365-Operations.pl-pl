---
title: Human Resources nie wyświetla się w ramach aplikacji Microsoft Dynamics 365
description: W tym artykule wyjaśniono, co należy zrobić, jeśli klient nie widzi aplikacji Microsoft Dynamics 365 Human Resources wśród aplikacji Microsoft Dynamics 365.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 17a454cd32a08db105a13577c32368ad819bed1c
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053383"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a><span data-ttu-id="e90c2-103">Human Resources nie wyświetla się w ramach aplikacji Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e90c2-103">Human Resources doesn't appear in Microsoft Dynamics 365 apps</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e90c2-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="e90c2-104">**Issue**</span></span>

<span data-ttu-id="e90c2-105">Klient nie widzi programu Dynamics 365 Human Resources wśród aplikacji systemu Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e90c2-105">The customer doesn't see Dynamics 365 Human Resources among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="e90c2-106">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="e90c2-106">**Resolution**</span></span>

<span data-ttu-id="e90c2-107">Użytkownik musi być dodany do roli Twórca środowisk dla środowiska w Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e90c2-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="e90c2-108">Administrator mający licencję usługi Power Apps planu 2. musi otworzyć [portal administratorów usługi Power Apps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="e90c2-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>

2. <span data-ttu-id="e90c2-109">Wybierz opcję **Środowiska**, a następnie wybierz poprawne środowisko dla programu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e90c2-109">Select **Environments**, and select the correct environment for Human Resources.</span></span>

3. <span data-ttu-id="e90c2-110">Na karcie **zabezpieczeń** na karcie **ról środowiska** wybierz opcję **Twórca środowiska**.</span><span class="sxs-lookup"><span data-stu-id="e90c2-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Karta role środowiska](media/environment-roles.png)

4. <span data-ttu-id="e90c2-112">Na karcie **użytkownicy** dodać użytkownika lub organizację.</span><span class="sxs-lookup"><span data-stu-id="e90c2-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Karta użytkowników](media/environment-maker.png)

5. <span data-ttu-id="e90c2-114">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e90c2-114">Select **Save**.</span></span>

6. <span data-ttu-id="e90c2-115">Użytkownik musi teraz zalogować się do [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="e90c2-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>

7. <span data-ttu-id="e90c2-116">Wybierz **Synchronizuj**, aby zaktualizować aplikacje użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e90c2-116">Select **Sync** to update the user apps.</span></span>

    ![Przycisk synchronizacji](media/get-more.png)

    <span data-ttu-id="e90c2-118">Po zakończeniu synchronizacji program Human Resources będzie wyświetlany na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="e90c2-118">After synchronization is completed, Human Resources will appear on the home page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]