---
title: Przetwórz zmiany stawki
description: Przetwórz zmiany stawki świadczenia w Microsoft Dynamics 365 Human Resources, gdy nowy lub istniejący plan świadczeń ma zmianę w ustawieniach reguły uprawnienia.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c87d98a16431805ad652e28e5ca100a4152ad0c6
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466237"
---
# <a name="process-rate-changes"></a><span data-ttu-id="d0f68-103">Przetwórz zmiany stawki</span><span class="sxs-lookup"><span data-stu-id="d0f68-103">Process rate changes</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d0f68-104">Przetwórz zmiany stawki świadczenia w Microsoft Dynamics 365 Human Resources, gdy nowy lub istniejący plan świadczeń ma zmianę w ustawieniach reguły uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="d0f68-104">Process benefit rate changes in Microsoft Dynamics 365 Human Resources when a new or existing benefit plan has a change in eligibility rule settings.</span></span> <span data-ttu-id="d0f68-105">Jeśli Nowa reguła uprawnienia zostanie utworzona i przypisana do planu, system wyświetli monit o ponowne przetworzenie pracownika, aby sprawdzić, czy pracownicy mogą obecnie kwalifikować się do planu na podstawie nowych opcji dotyczących uprawnień.</span><span class="sxs-lookup"><span data-stu-id="d0f68-105">If a new eligibility rule is created and assigned to the plan, this prompts the system to rerun worker eligibility to check if workers may now be eligible for the plan based on new eligibility options.</span></span> 

1. <span data-ttu-id="d0f68-106">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Przetwarzanie** wybierz opcję **Przetwarzanie aktualizacji zmiany stawki**.</span><span class="sxs-lookup"><span data-stu-id="d0f68-106">In the **Benefits management** workspace, under **Processing**, select **Rate change update processing**.</span></span>

2. <span data-ttu-id="d0f68-107">W oknie dialogowym **Uruchamianie procesu aktualizacji stawki świadczenia** określ wartości następujących pól:</span><span class="sxs-lookup"><span data-stu-id="d0f68-107">In the **Run benefit rate update process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="d0f68-108">Pole</span><span class="sxs-lookup"><span data-stu-id="d0f68-108">Field</span></span> | <span data-ttu-id="d0f68-109">Opis</span><span class="sxs-lookup"><span data-stu-id="d0f68-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d0f68-110">**Okres rejestracji**</span><span class="sxs-lookup"><span data-stu-id="d0f68-110">**Enrollment period**</span></span> | <span data-ttu-id="d0f68-111">Okres rejestracji służący do przetworzenia zmian stawki.</span><span class="sxs-lookup"><span data-stu-id="d0f68-111">The enrollment period to process rate changes for.</span></span> |

3. <span data-ttu-id="d0f68-112">Jeśli chcesz uruchomić ten proces w tle, wybierz opcję **Uruchom w tle** i wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="d0f68-112">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="d0f68-113">Umożliwia wprowadzanie informacji o przetwarzaniu.</span><span class="sxs-lookup"><span data-stu-id="d0f68-113">Enter information for the process.</span></span>

   2. <span data-ttu-id="d0f68-114">Aby skonfigurować zadanie cykliczne, wybierz opcję **cykl**, wprowadź informacje o cyklu i wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0f68-114">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="d0f68-115">Aby skonfigurować alert zadania, wybierz **alerty**, wybierz alerty do odebrania, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0f68-115">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="d0f68-116">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0f68-116">Select **OK**.</span></span> <span data-ttu-id="d0f68-117">Proces będzie uruchamiany z parametrami określonymi przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d0f68-117">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="d0f68-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0f68-118">Select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]