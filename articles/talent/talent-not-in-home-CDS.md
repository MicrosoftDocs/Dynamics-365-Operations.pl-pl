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

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a><span data-ttu-id="94ee0-103">Aplikacja Talent nie jest wyświetlana na liście aplikacji usługi Microsoft Dynamics 365 (CDS1.0)</span><span class="sxs-lookup"><span data-stu-id="94ee0-103">Talent doesn't appear among the Microsoft Dynamics 365 apps (CDS1.0)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="94ee0-104">**Wydaj**</span><span class="sxs-lookup"><span data-stu-id="94ee0-104">**Issue**</span></span>

<span data-ttu-id="94ee0-105">Klient nie widzi aplikacji Microsoft Dynamics 365 for Talent wśród aplikacji Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="94ee0-105">The customer doesn't see the Microsoft Dynamics 365 for Talent app among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="94ee0-106">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="94ee0-106">**Resolution**</span></span>

<span data-ttu-id="94ee0-107">Użytkownik musi być dodany do roli Twórca środowisk dla środowiska w Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="94ee0-107">The user must be added to the Environment Maker role for the environment in Microsoft PowerApps.</span></span>

1. <span data-ttu-id="94ee0-108">Administrator mający licencję usługi PowerApps planu 2 musi otworzyć [portal administratorów usługi PowerApps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="94ee0-108">The admin user who has a PowerApps Plan 2 license must open the [PowerApps Admin portal](https://preview.admin.powerapps.com/).</span></span>
2. <span data-ttu-id="94ee0-109">Wybierz **środowiska**, a następnie wybierz poprawne środowisko dla Talent.</span><span class="sxs-lookup"><span data-stu-id="94ee0-109">Select **Environments**, and select the correct environment for Talent.</span></span>
3. <span data-ttu-id="94ee0-110">Na karcie **zabezpieczeń** na karcie **ról środowiska** wybierz opcję **Twórca środowiska**.</span><span class="sxs-lookup"><span data-stu-id="94ee0-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Karta role środowiska](media/environment-roles.png)

4. <span data-ttu-id="94ee0-112">Na karcie **użytkownicy** dodać użytkownika lub organizację.</span><span class="sxs-lookup"><span data-stu-id="94ee0-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Karta użytkowników](media/environment-maker.png)

5. <span data-ttu-id="94ee0-114">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="94ee0-114">Select **Save**.</span></span>
6. <span data-ttu-id="94ee0-115">Użytkownik musi teraz zalogować się do [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="94ee0-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>
7. <span data-ttu-id="94ee0-116">Wybierz **Synchronizuj**, aby zaktualizować aplikacje użytkownika.</span><span class="sxs-lookup"><span data-stu-id="94ee0-116">Select **Sync** to update the user apps.</span></span>

    ![Przycisk synchronizacji](media/get-more.png)

    <span data-ttu-id="94ee0-118">Po zakończeniu synchronizacji aplikacja Talent będzie wyświetlana na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="94ee0-118">After synchronization is completed, Talent will appear on the home page.</span></span>

