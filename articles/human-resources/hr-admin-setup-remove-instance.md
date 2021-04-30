---
title: Usuwanie wystąpienie
description: Ten artykuł przeprowadzi użytkownika przez proces usuwania środowiska testowego lub produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a6f23adedc287b85018fe0b0af445677f6dc597c
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889915"
---
# <a name="remove-an-instance"></a><span data-ttu-id="68466-103">Usuwanie wystąpienie</span><span class="sxs-lookup"><span data-stu-id="68466-103">Remove an instance</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="68466-104">Ten artykuł przeprowadzi użytkownika przez proces usuwania środowiska testowego lub produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="68466-104">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="68466-105">Usuń środowisko testowe</span><span class="sxs-lookup"><span data-stu-id="68466-105">Remove a test drive environment</span></span>

<span data-ttu-id="68466-106">Środowiska testowe aplikacji Human Resources mają ustawioną zasadę wygasania po 60 dniach.</span><span class="sxs-lookup"><span data-stu-id="68466-106">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="68466-107">Jednak właściciele środowisk testowych mają możliwość wcześniejszego zakończenia okresu próbnego, wykonując następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68466-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="68466-108">Przejdź do [Centrum administracyjnego usługi Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="68466-108">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="68466-109">Wybierz opcję **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="68466-109">Select **Environments**.</span></span>
3. <span data-ttu-id="68466-110">Wybierz środowisko testowe, które ma nazwę o wzorcu podobnym do następującego: TestDrive -alias@domain</span><span class="sxs-lookup"><span data-stu-id="68466-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="68466-111">Wybierz opcję **Usuń** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="68466-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="68466-112">Istniejące środowisko testowe zostanie usunięte.</span><span class="sxs-lookup"><span data-stu-id="68466-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="68466-113">Po usunięciu środowiska możesz się zapisać na nowe środowisko testowe.</span><span class="sxs-lookup"><span data-stu-id="68466-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="68466-114">Usuń środowisko produkcyjne</span><span class="sxs-lookup"><span data-stu-id="68466-114">Remove a production environment</span></span>

<span data-ttu-id="68466-115">Temat ten opiera się na założeniu, że użytkownik dokonał zakupu aplikacji Human Resources u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA).</span><span class="sxs-lookup"><span data-stu-id="68466-115">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="68466-116">Ponieważ środowisko aplikacji Human Resources jest „zawarte” w jednym środowisku usługi Power Apps, dostępne są dwie opcje do rozważenia.</span><span class="sxs-lookup"><span data-stu-id="68466-116">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="68466-117">Pierwsza opcja polega na usunięciu całego środowiska usługi Power Apps, a druga na usunięciu tylko modułu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="68466-117">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="68466-118">Pierwsza opcja jest preferowana, jeżeli środowisko usługi Power Apps utworzono specjalnie do obsługi aplikacji Human Resources i dopiero rozpoczęto wdrażanie lub nie ma żadnych wiążących integracji.</span><span class="sxs-lookup"><span data-stu-id="68466-118">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="68466-119">Drugą opcję należy zastosować, jeśli istnieje ustabilizowane środowisko usługi Power Apps wypełnione sformatowanymi danymi wykorzystywanymi w usługach Power Apps i Power Automate.</span><span class="sxs-lookup"><span data-stu-id="68466-119">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="68466-120">Przed usunięciem środowiska usługi Power Apps upewnij się, że nie jest ono używane do integrowania sformatowanych danych poza zakresem Human Resources.</span><span class="sxs-lookup"><span data-stu-id="68466-120">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="68466-121">Należy również zwrócić uwagę, że nie można usuwać domyślnych środowisk usługi Power Apps.</span><span class="sxs-lookup"><span data-stu-id="68466-121">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="68466-122">Aby usunąć całe środowisko usługi Power Apps, w tym aplikację Human Resources oraz powiązane aplikacje i przepływy:</span><span class="sxs-lookup"><span data-stu-id="68466-122">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="68466-123">Przejdź do [Centrum administracyjnego usługi Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="68466-123">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="68466-124">Wybierz opcję **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="68466-124">Select **Environments**.</span></span>
3. <span data-ttu-id="68466-125">Zaznacz środowisko, które chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="68466-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="68466-126">Wybierz opcję **Usuń** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="68466-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="68466-127">Poczekaj na zakończenie usuwania.</span><span class="sxs-lookup"><span data-stu-id="68466-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="68466-128">Zaloguj się w usłudze [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) za pomocą konta użytego do zasubskrybowania aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="68466-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="68466-129">Wybierz projekt z aplikacją Human Resources, który zawiera środowisko.</span><span class="sxs-lookup"><span data-stu-id="68466-129">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="68466-130">W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="68466-130">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="68466-131">Wybierz wystąpienie do usunięcia.</span><span class="sxs-lookup"><span data-stu-id="68466-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="68466-132">Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="68466-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="68466-133">Aby usunąć środowisko Human Resources z istniejącego środowiska usługi Power Apps, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="68466-133">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="68466-134">Należy zauważyć, że konieczność zaangażowania działu pomocy technicznej i skontaktowania się z zespołem DevOps aplikacji Human Resources są tymczasowe, do czasu włączenia tej funkcji bezpośrednio w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="68466-134">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="68466-135">Skontaktuj się z działem pomocy technicznej i zainicjuj wniosek o usunięcie.</span><span class="sxs-lookup"><span data-stu-id="68466-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="68466-136">Dział pomocy technicznej zainicjuje wniosek o usunięcie razem z zespołem DevOps aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="68466-136">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="68466-137">Po otrzymaniu informacji, że środowisko zostało usunięte, kontynuuj procedurę.</span><span class="sxs-lookup"><span data-stu-id="68466-137">Continue after you receive word that the environment has been removed.</span></span>
4. <span data-ttu-id="68466-138">Zaloguj się w usłudze LCS za pomocą konta używanego do subskrypcji rozwiązania Human Resources.</span><span class="sxs-lookup"><span data-stu-id="68466-138">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="68466-139">Wybierz projekt z aplikacją Human Resources, który zawiera środowisko.</span><span class="sxs-lookup"><span data-stu-id="68466-139">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="68466-140">W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="68466-140">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="68466-141">Zaznacz wystąpienie, które chcesz usunąć. Powinno być ono oznaczone stanem wdrożenia **Usunięte**.</span><span class="sxs-lookup"><span data-stu-id="68466-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Deleted**.</span></span>
8. <span data-ttu-id="68466-142">Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="68466-142">Select **Remove instance** and confirm your decision.</span></span> 

## <a name="recover-a-soft-deleted-environment"></a><span data-ttu-id="68466-143">Odzyskiwanie wstępnie usuniętego środowiska</span><span class="sxs-lookup"><span data-stu-id="68466-143">Recover a soft-deleted environment</span></span>

<span data-ttu-id="68466-144">W przypadku usunięcia środowiska Power Apps, z którym jest połączone środowisko Human Resources, stan środowiska Human Resources w usługach w ramach Lifecycle Services zostanie **Delikatnie usunięty**.</span><span class="sxs-lookup"><span data-stu-id="68466-144">If you delete the Power Apps environment that your Human Resources environment is connected to, the status of the Human Resources environment in Lifecycle Services will be **Soft deleted**.</span></span> <span data-ttu-id="68466-145">W takim przypadku użytkownicy nie mogą łączyć się z Human Resources.</span><span class="sxs-lookup"><span data-stu-id="68466-145">In this case, users can't connect to Human Resources.</span></span>

<span data-ttu-id="68466-146">Aby przywrócić środowisko:</span><span class="sxs-lookup"><span data-stu-id="68466-146">To restore the environment:</span></span>

1. <span data-ttu-id="68466-147">Wykonaj instrukcje w [Odzyskaj środowisko Power Apps](/power-platform/admin/recover-environment.md).</span><span class="sxs-lookup"><span data-stu-id="68466-147">Follow the instructions in [Recover the Power Apps environment](/power-platform/admin/recover-environment.md).</span></span>

2. <span data-ttu-id="68466-148">Skontaktuj się z pomocą techniczną w celu przywrócenia środowiska Human Resources.</span><span class="sxs-lookup"><span data-stu-id="68466-148">Contact Support to restore the Human Resources environment.</span></span> <span data-ttu-id="68466-149">Aby uzyskać więcej informacji, zobacz [Uzyskiwanie pomocy technicznej](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="68466-149">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

> [!Warning]
> <span data-ttu-id="68466-150">Środowiska Power Apps są zapisywane tylko przez siedem dni po usunięciu.</span><span class="sxs-lookup"><span data-stu-id="68466-150">Power Apps environments are only saved for seven days after deletion.</span></span> <span data-ttu-id="68466-151">Musisz odzyskać środowisko w okresie siedmiu dni.</span><span class="sxs-lookup"><span data-stu-id="68466-151">You must recover the environment within the seven day period.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]