---
title: Usuń wystąpienie
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5c5f875ad9361c31af4fbe863488b881cdd97a6e
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010155"
---
# <a name="remove-an-instance"></a><span data-ttu-id="59ebb-102">Usuń wystąpienie</span><span class="sxs-lookup"><span data-stu-id="59ebb-102">Remove an instance</span></span>

<span data-ttu-id="59ebb-103">Ten artykuł przeprowadzi użytkownika przez proces usuwania środowiska testowego lub produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="59ebb-103">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="59ebb-104">Usuń środowisko testowe</span><span class="sxs-lookup"><span data-stu-id="59ebb-104">Remove a test drive environment</span></span>

<span data-ttu-id="59ebb-105">Środowiska testowe aplikacji Human Resources mają ustawioną zasadę wygasania po 60 dniach.</span><span class="sxs-lookup"><span data-stu-id="59ebb-105">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="59ebb-106">Jednak właściciele środowisk testowych mają możliwość wcześniejszego zakończenia okresu próbnego, wykonując następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="59ebb-106">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="59ebb-107">Przejdź do [Centrum administracyjnego usługi Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="59ebb-107">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="59ebb-108">Wybierz opcję **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="59ebb-108">Select **Environments**.</span></span>
3. <span data-ttu-id="59ebb-109">Wybierz środowisko testowe, które ma nazwę o wzorcu podobnym do następującego: TestDrive -alias@domain</span><span class="sxs-lookup"><span data-stu-id="59ebb-109">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="59ebb-110">Wybierz opcję **Usuń** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="59ebb-110">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="59ebb-111">Istniejące środowisko testowe zostanie usunięte.</span><span class="sxs-lookup"><span data-stu-id="59ebb-111">The existing test drive environment will be removed.</span></span> <span data-ttu-id="59ebb-112">Po usunięciu środowiska możesz się zapisać na nowe środowisko testowe.</span><span class="sxs-lookup"><span data-stu-id="59ebb-112">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="59ebb-113">Usuń środowisko produkcyjne</span><span class="sxs-lookup"><span data-stu-id="59ebb-113">Remove a production environment</span></span>

<span data-ttu-id="59ebb-114">Temat ten opiera się na założeniu, że użytkownik dokonał zakupu aplikacji Human Resources u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA).</span><span class="sxs-lookup"><span data-stu-id="59ebb-114">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="59ebb-115">Ponieważ środowisko aplikacji Human Resources jest „zawarte” w jednym środowisku usługi Power Apps, dostępne są dwie opcje do rozważenia.</span><span class="sxs-lookup"><span data-stu-id="59ebb-115">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="59ebb-116">Pierwsza opcja polega na usunięciu całego środowiska usługi Power Apps, a druga na usunięciu tylko modułu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="59ebb-116">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="59ebb-117">Pierwsza opcja jest preferowana, jeżeli środowisko usługi Power Apps utworzono specjalnie do obsługi aplikacji Human Resources i dopiero rozpoczęto wdrażanie lub nie ma żadnych wiążących integracji.</span><span class="sxs-lookup"><span data-stu-id="59ebb-117">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="59ebb-118">Drugą opcję należy zastosować, jeśli istnieje ustabilizowane środowisko usługi Power Apps wypełnione sformatowanymi danymi wykorzystywanymi w usługach Power Apps i Power Automate.</span><span class="sxs-lookup"><span data-stu-id="59ebb-118">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="59ebb-119">Przed usunięciem środowiska usługi Power Apps upewnij się, że nie jest ono używane do integrowania sformatowanych danych poza zakresem Human Resources.</span><span class="sxs-lookup"><span data-stu-id="59ebb-119">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="59ebb-120">Należy również zwrócić uwagę, że nie można usuwać domyślnych środowisk usługi Power Apps.</span><span class="sxs-lookup"><span data-stu-id="59ebb-120">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="59ebb-121">Aby usunąć całe środowisko usługi Power Apps, w tym aplikację Human Resources oraz powiązane aplikacje i przepływy:</span><span class="sxs-lookup"><span data-stu-id="59ebb-121">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="59ebb-122">Przejdź do [Centrum administracyjnego usługi Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="59ebb-122">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="59ebb-123">Wybierz opcję **Środowiska**.</span><span class="sxs-lookup"><span data-stu-id="59ebb-123">Select **Environments**.</span></span>
3. <span data-ttu-id="59ebb-124">Zaznacz środowisko, które chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="59ebb-124">Select the environment to be removed.</span></span>
4. <span data-ttu-id="59ebb-125">Wybierz opcję **Usuń** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="59ebb-125">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="59ebb-126">Poczekaj na zakończenie usuwania.</span><span class="sxs-lookup"><span data-stu-id="59ebb-126">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="59ebb-127">Zaloguj się w usłudze [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) za pomocą konta użytego do zasubskrybowania aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="59ebb-127">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="59ebb-128">Wybierz projekt z aplikacją Human Resources, który zawiera środowisko.</span><span class="sxs-lookup"><span data-stu-id="59ebb-128">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="59ebb-129">W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="59ebb-129">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="59ebb-130">Wybierz wystąpienie do usunięcia.</span><span class="sxs-lookup"><span data-stu-id="59ebb-130">Select the instance to remove.</span></span> 
10. <span data-ttu-id="59ebb-131">Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="59ebb-131">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="59ebb-132">Aby usunąć środowisko Human Resources z istniejącego środowiska usługi Power Apps, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="59ebb-132">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="59ebb-133">Należy zauważyć, że konieczność zaangażowania działu pomocy technicznej i skontaktowania się z zespołem DevOps aplikacji Human Resources są tymczasowe, do czasu włączenia tej funkcji bezpośrednio w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="59ebb-133">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="59ebb-134">Skontaktuj się z działem pomocy technicznej i zainicjuj wniosek o usunięcie.</span><span class="sxs-lookup"><span data-stu-id="59ebb-134">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="59ebb-135">Dział pomocy technicznej zainicjuje wniosek o usunięcie razem z zespołem DevOps aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="59ebb-135">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="59ebb-136">Po otrzymaniu informacji, że środowisko zostało usunięte, kontynuuj procedurę.</span><span class="sxs-lookup"><span data-stu-id="59ebb-136">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="59ebb-137">Zaloguj się w usłudze LCS za pomocą konta używanego do subskrypcji rozwiązania Human Resources.</span><span class="sxs-lookup"><span data-stu-id="59ebb-137">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="59ebb-138">Wybierz projekt z aplikacją Human Resources, który zawiera środowisko.</span><span class="sxs-lookup"><span data-stu-id="59ebb-138">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="59ebb-139">W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="59ebb-139">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="59ebb-140">Zaznacz wystąpienie, które chcesz usunąć. Powinno być ono oznaczone stanem wdrożenia **Niepowodzenie**.</span><span class="sxs-lookup"><span data-stu-id="59ebb-140">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="59ebb-141">Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję.</span><span class="sxs-lookup"><span data-stu-id="59ebb-141">Select **Remove instance** and confirm your decision.</span></span> 
