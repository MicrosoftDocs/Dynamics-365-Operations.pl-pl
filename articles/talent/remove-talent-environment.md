---
title: Usuwanie środowisk rozwiązania Talent
description: Ten temat przeprowadzi użytkownika przez proces usuwania środowiska testowego lub produkcyjnego dla oprogramowania Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: d608ee3ad90d23279557e5e9be4d398ffac3a266
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010622"
---
# <a name="remove-talent-environments"></a><span data-ttu-id="cce0c-103">Usuwanie środowisk rozwiązania Talent</span><span class="sxs-lookup"><span data-stu-id="cce0c-103">Remove Talent environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cce0c-104">Ten temat przeprowadzi użytkownika przez proces usuwania środowiska testowego lub produkcyjnego dla oprogramowania Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="cce0c-104">This topic walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Talent.</span></span>

## <a name="removing-a-test-drive-environment"></a><span data-ttu-id="cce0c-105">Usuwanie środowiska testowego</span><span class="sxs-lookup"><span data-stu-id="cce0c-105">Removing a test drive environment</span></span>

<span data-ttu-id="cce0c-106">Środowiska testowe aplikacji Talent mają ustawioną zasadę wygasania po 60 dniach.</span><span class="sxs-lookup"><span data-stu-id="cce0c-106">Talent test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="cce0c-107">Jednak właściciele środowisk testowych mają możliwość wcześniejszego zakończenia okresu próbnego, wykonując następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="cce0c-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="cce0c-108">Przejdź do [Centrum administracyjnego usługi PowerApps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="cce0c-108">Navigate to the [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="cce0c-109">Wybierz opcję **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="cce0c-109">Select **Environments**.</span></span>
3. <span data-ttu-id="cce0c-110">Wybierz środowisko testowe, które ma nazwę o wzorcu podobnym do następującego: TestDrive -alias@domain</span><span class="sxs-lookup"><span data-stu-id="cce0c-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="cce0c-111">Wybierz opcję **Usuń** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="cce0c-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="cce0c-112">Istniejące środowisko testowe zostanie usunięte.</span><span class="sxs-lookup"><span data-stu-id="cce0c-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="cce0c-113">Po usunięciu środowiska możesz się zapisać na nowe środowisko testowe.</span><span class="sxs-lookup"><span data-stu-id="cce0c-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="removing-a-production-environment"></a><span data-ttu-id="cce0c-114">Usuwanie środowiska produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="cce0c-114">Removing a production environment</span></span>

<span data-ttu-id="cce0c-115">Temat te opiera się na założeniu, że użytkownik dokonał zakupu aplikacji Talent u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA).</span><span class="sxs-lookup"><span data-stu-id="cce0c-115">This topic assumes that you've purchased Talent through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="cce0c-116">Ponieważ środowisko aplikacji Talent jest „zawarte” w jednym środowisku usługi PowerApps, dostępne są dwie opcje do rozważenia.</span><span class="sxs-lookup"><span data-stu-id="cce0c-116">Since a single Talent environment is “contained” within a single PowerApps environment, there are two options to consider.</span></span> <span data-ttu-id="cce0c-117">Pierwsza opcja polega na usunięciu całego środowiska usługi PowerApps, a druga na usunięciu tylko modułu Talent.</span><span class="sxs-lookup"><span data-stu-id="cce0c-117">The first option involves removing the entire PowerApps environment; the second option involves removing only Talent.</span></span> <span data-ttu-id="cce0c-118">Pierwsza opcja jest preferowana, jeżeli środowisko usługi PowerApps utworzono specjalnie do obsługi aplikacji Talent i dopiero rozpoczęto wdrażanie lub nie ma żadnych wiążących integracji.</span><span class="sxs-lookup"><span data-stu-id="cce0c-118">The first option is preferred when you have created a PowerApps environment expressly for the purpose of provisioning Talent, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="cce0c-119">Drugą opcję należy zastosować, jeśli istnieje ustabilizowane środowisko usługi PowerApps wypełnione sformatowanymi danymi wykorzystywanymi w usługach PowerApps i przepływach.</span><span class="sxs-lookup"><span data-stu-id="cce0c-119">The second option is appropriate when you have an established PowerApps environment populated with rich data that's leveraged in PowerApps and Flows.</span></span>

> [!Important]
> <span data-ttu-id="cce0c-120">Przed usunięciem środowiska usługi PowerApps upewnij się, że nie jest ono używane do integrowania sformatowanych danych poza zakresem Talent.</span><span class="sxs-lookup"><span data-stu-id="cce0c-120">Before removing the PowerApps environment, ensure it is not being used for rich data integrations outside the scope of Talent.</span></span> <span data-ttu-id="cce0c-121">Należy również zwrócić uwagę, że nie można usuwać domyślnych środowisk usługi PowerApps.</span><span class="sxs-lookup"><span data-stu-id="cce0c-121">Also note that the default PowerApps environments cannot be removed.</span></span> 

<span data-ttu-id="cce0c-122">Aby usunąć całe środowisko usługi PowerApps, w tym aplikację Talent oraz powiązane aplikacje i przepływy:</span><span class="sxs-lookup"><span data-stu-id="cce0c-122">To remove the entire PowerApps environment, including Talent and the associated Apps and Flows:</span></span>

1. <span data-ttu-id="cce0c-123">Przejdź do [Centrum administracyjnego usługi PowerApps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="cce0c-123">Navigate to the [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="cce0c-124">Wybierz opcję **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="cce0c-124">Select **Environments**.</span></span>
3. <span data-ttu-id="cce0c-125">Zaznacz środowisko, które chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="cce0c-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="cce0c-126">Wybierz opcję **Usuń** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="cce0c-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="cce0c-127">Poczekaj na zakończenie usuwania.</span><span class="sxs-lookup"><span data-stu-id="cce0c-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="cce0c-128">Zaloguj się w usłudze [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) za pomocą konta użytego do zasubskrybowania aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="cce0c-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Talent.</span></span> 
7. <span data-ttu-id="cce0c-129">Wybierz projekt z aplikacją Talent , który zawiera środowisko.</span><span class="sxs-lookup"><span data-stu-id="cce0c-129">Select the Talent Project that contains the environment.</span></span> 
8. <span data-ttu-id="cce0c-130">W projekcie LCS wybierz kafel **Zarządzanie aplikacją Talent**.</span><span class="sxs-lookup"><span data-stu-id="cce0c-130">In your LCS project, select the **Talent App Management** tile.</span></span> 
9. <span data-ttu-id="cce0c-131">Wybierz wystąpienie do usunięcia.</span><span class="sxs-lookup"><span data-stu-id="cce0c-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="cce0c-132">Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="cce0c-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="cce0c-133">Aby usunąć środowisko Talent z istniejącego środowiska usługi PowerApps, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="cce0c-133">To remove a Talent environment from an existing PowerApps environment, complete the following steps.</span></span> <span data-ttu-id="cce0c-134">Należy zauważyć, że konieczność zaangażowania działu pomocy technicznej i skontaktowania się z zespołem DevOps aplikacji Talent są tymczasowe, do czasu włączenia tej funkcji bezpośrednio w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="cce0c-134">Note that the need to involve support and contact the Talent DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="cce0c-135">Skontaktuj się z działem pomocy technicznej i zainicjuj wniosek o usunięcie.</span><span class="sxs-lookup"><span data-stu-id="cce0c-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="cce0c-136">Dział pomocy technicznej zainicjuje wniosek o usunięcie razem z zespołem DevOps aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="cce0c-136">The Support team will initiate a removal request with the Talent DevOps team.</span></span> 
3. <span data-ttu-id="cce0c-137">Po otrzymaniu informacji, że środowisko zostało usunięte, kontynuuj procedurę.</span><span class="sxs-lookup"><span data-stu-id="cce0c-137">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="cce0c-138">Zaloguj się w usłudze LCS za pomocą konta używanego do subskrypcji rozwiązania Talent.</span><span class="sxs-lookup"><span data-stu-id="cce0c-138">Sign in to LCS using the account that you used to subscribe to Talent.</span></span> 
5. <span data-ttu-id="cce0c-139">Wybierz projekt z aplikacją Talent , który zawiera środowisko.</span><span class="sxs-lookup"><span data-stu-id="cce0c-139">Select the Talent project that contains the environment.</span></span> 
6. <span data-ttu-id="cce0c-140">W projekcie LCS wybierz kafel **Zarządzanie aplikacją Talent**.</span><span class="sxs-lookup"><span data-stu-id="cce0c-140">In your LCS project, select the **Talent App Management** tile.</span></span> 
7. <span data-ttu-id="cce0c-141">Zaznacz wystąpienie, które chcesz usunąć. Powinno być ono oznaczone stanem wdrożenia **Niepowodzenie**.</span><span class="sxs-lookup"><span data-stu-id="cce0c-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="cce0c-142">Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="cce0c-142">Select **Remove instance** and confirm your decision.</span></span> 

