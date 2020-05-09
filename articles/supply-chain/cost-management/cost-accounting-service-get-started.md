---
title: Rozpoczęcie korzystania z usługi rachunku kosztów
description: Ten temat zawiera szczegółowe informacje dotyczące licencjonowania i instrukcje dotyczące instalacji dla usługi rachunku kosztów.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: cbbce7eaac264973bf0b95ad5175bf70ed2b4ae9
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276952"
---
# <a name="get-started-with-the-cost-accounting-service"></a><span data-ttu-id="3919a-103">Rozpoczęcie korzystania z usługi rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="3919a-103">Get started with the cost accounting service</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="3919a-104">Funkcje opisane w tym temacie są dostępne jako część prywatnej wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="3919a-104">The functionality that is described in this topic is available as part of a private preview release.</span></span> <span data-ttu-id="3919a-105">Zawartość tego tematu i funkcjonalność, którą on opisuje, podlegają zmianie.</span><span class="sxs-lookup"><span data-stu-id="3919a-105">The content of this topic and the functionality that it describes are subject to change.</span></span> <span data-ttu-id="3919a-106">Aby uzyskać więcej informacji dotyczących wydań wersji zapoznawczych, zobacz [Aktualizacje do jednej wersji usługi — często zadawane pytania](../../fin-ops-core/fin-ops/get-started/one-version.md).</span><span class="sxs-lookup"><span data-stu-id="3919a-106">For more information about preview releases, see [One version service updates FAQ](../../fin-ops-core/fin-ops/get-started/one-version.md).</span></span>

<span data-ttu-id="3919a-107">Usługa rachunku kosztów umożliwia wielokrotne księgowanie zapasów w księgach rachunku kosztów, które zostały skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="3919a-107">The cost accounting service lets you do multiple inventory accounting in the cost accounting ledgers that you've set up.</span></span> <span data-ttu-id="3919a-108">Poszczególne księgi rachunku kosztów są kojarzone z *konwencją*.</span><span class="sxs-lookup"><span data-stu-id="3919a-108">You associate each cost accounting ledger with a *convention*.</span></span> <span data-ttu-id="3919a-109">Konwencja jest zbiorem następujących rodzajów zasad (polityki) rachunkowości:</span><span class="sxs-lookup"><span data-stu-id="3919a-109">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="3919a-110">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="3919a-110">Cost object</span></span>
- <span data-ttu-id="3919a-111">Podstawa miary danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="3919a-111">Input measurement basis</span></span>
- <span data-ttu-id="3919a-112">Założenie przepływu kosztów</span><span class="sxs-lookup"><span data-stu-id="3919a-112">Cost flow assumption</span></span>
- <span data-ttu-id="3919a-113">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="3919a-113">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="3919a-114">Nawet po włączeniu usługi rachunku kosztów nadal można księgować zapasy w Microsoft Dynamics 365 Supply Chain Management w zwykły sposób.</span><span class="sxs-lookup"><span data-stu-id="3919a-114">Even after you've turned on the cost accounting service, you can still do  inventory accounting in Microsoft Dynamics 365 Supply Chain Management, as usual.</span></span>

<span data-ttu-id="3919a-115">Usługa rachunku kosztów jest dodatkiem.</span><span class="sxs-lookup"><span data-stu-id="3919a-115">The cost accounting service is an add-in.</span></span> <span data-ttu-id="3919a-116">Aby udostępnić swoje funkcje, należy je zainstalować z poziomu Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="3919a-116">To makes its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="3919a-117">Można więc ocenić ją w środowisku testowym przed włączeniem go w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="3919a-117">Therefore, you can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="3919a-118">Usługa rachunku kosztów nie obsługuje obecnie wszystkich funkcji zarządzania kosztem, które są wbudowane w Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3919a-118">The cost accounting service doesn't currently support all the cost management features that are built into Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="3919a-119">Dlatego ważne jest, aby ocenić, czy aktualnie zestaw funkcji jest obecnie dostępny i spełni wymagania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="3919a-119">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="3919a-120">Licencjonowanie</span><span class="sxs-lookup"><span data-stu-id="3919a-120">Licensing</span></span>

<span data-ttu-id="3919a-121">Usługa rachunku kosztów jest licencjonowana wraz z standardowymi funkcjami księgowania zapasów, które są dostępne dla Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3919a-121">The cost accounting service is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="3919a-122">Nie trzeba kupować dodatkowej licencji, aby móc skorzystać z usługi rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="3919a-122">You don't have to purchase an additional license to use the cost accounting service.</span></span>

## <a name="install-the-add-in"></a><span data-ttu-id="3919a-123">Instalacja aplikacji dodatkowych</span><span class="sxs-lookup"><span data-stu-id="3919a-123">Install the add-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3919a-124">Aby można było korzystać z usługi rachunku kosztów, należy posiadać środowisko o wysokiej dostępności z włączonymi usługami LCS (a nie środowisko OneBox) i musi być uruchomione Dynamics 365 Supply Chain Management w wersji 10.0.11 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="3919a-124">To use the cost accounting service, you must have an LCS-enabled high-availability environment (not a OneBox environment), and you must be running Dynamics 365 Supply Chain Management version 10.0.11 or later.</span></span>

<span data-ttu-id="3919a-125">Aby skorzystać z usługi rachunku kosztów, należy zainstalować dodatek usługi rachunku kosztów w Supply Chain Management w sposób opisany w poniższej procedurze.</span><span class="sxs-lookup"><span data-stu-id="3919a-125">To use the cost accounting service, install the cost accounting service add-in for Supply Chain Management as described in the following procedure.</span></span>

1. <span data-ttu-id="3919a-126">Zaloguj się w LCS.</span><span class="sxs-lookup"><span data-stu-id="3919a-126">Sign in to LCS.</span></span>

1. <span data-ttu-id="3919a-127">Przejdź do obszaru **Zarządzanie funkcjami w wersji zapoznawczej**.</span><span class="sxs-lookup"><span data-stu-id="3919a-127">Go to **Preview feature management**.</span></span>

1. <span data-ttu-id="3919a-128">Wybierz znak plus (**+**).</span><span class="sxs-lookup"><span data-stu-id="3919a-128">Select the plus sign (**+**).</span></span>

1. <span data-ttu-id="3919a-129">W polu **Kod** wprowadź swój klucz beta dla usługi rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="3919a-129">In the **Code** field, enter your add-in beta key for the cost accounting service.</span></span> <span data-ttu-id="3919a-130">(Twój klucz powinien zostać dostarczony pocztą e-mail.)</span><span class="sxs-lookup"><span data-stu-id="3919a-130">(You should have received your key by email.)</span></span>

1. <span data-ttu-id="3919a-131">Wybierz opcję **Odblokuj**.</span><span class="sxs-lookup"><span data-stu-id="3919a-131">Select **Unblock**.</span></span>

1. <span data-ttu-id="3919a-132">Otwórz środowisko usługi LCS, w którym chcesz dodać usługę.</span><span class="sxs-lookup"><span data-stu-id="3919a-132">Open the LCS environment where you want to add the service.</span></span>

1. <span data-ttu-id="3919a-133">Przejdź do **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="3919a-133">Go to **Full details**.</span></span>

1. <span data-ttu-id="3919a-134">Przewiń w dół do pozycji skróconej karty **Zarządzaj dodatkami środowiskowymi**.</span><span class="sxs-lookup"><span data-stu-id="3919a-134">Scroll down to the **Environment add-ins** FastTab.</span></span>

1. <span data-ttu-id="3919a-135">Wybierz opcję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="3919a-135">Select **Install a new add-in**.</span></span>

1. <span data-ttu-id="3919a-136">Wybierz **Usługa rachunku kosztów**.</span><span class="sxs-lookup"><span data-stu-id="3919a-136">Select **Cost accounting service**.</span></span>

1. <span data-ttu-id="3919a-137">Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.</span><span class="sxs-lookup"><span data-stu-id="3919a-137">Follow the installation guide, and agree to the terms and conditions.</span></span>

1. <span data-ttu-id="3919a-138">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="3919a-138">Select **Install**.</span></span>

1. <span data-ttu-id="3919a-139">Na skróconej karcie **Dodatki środowiska** należy sprawdzić, czy jest instalowana usługa rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="3919a-139">On the **Environment add-ins** FastTab, you should see that the cost accounting service is being installed.</span></span> <span data-ttu-id="3919a-140">Po kilku minutach stan powinien ulec zmianie z **Instalowane** na **Zainstalowane**.</span><span class="sxs-lookup"><span data-stu-id="3919a-140">After a few minutes, the status should change from **Installing** to **Installed**.</span></span> <span data-ttu-id="3919a-141">(Aby zobaczyć tę zmianę, konieczne może być odświeżenie strony.) W tym momencie usługa rachunku kosztów jest gotowa do użycia.</span><span class="sxs-lookup"><span data-stu-id="3919a-141">(You might have to refresh the page to see this change.) At that point, the cost accounting service is ready for use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="3919a-142">Konfiguracja integracji</span><span class="sxs-lookup"><span data-stu-id="3919a-142">Set up the integration</span></span>

<span data-ttu-id="3919a-143">Aby skonfigurować integrację między usługą rachunku kosztów a Dynamics 365 Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="3919a-143">To set up the integration between the cost accounting service and Dynamics 365 Supply Chain Management:</span></span>

1. <span data-ttu-id="3919a-144">Wybierz kolejno opcje **Administrowanie systemem > Obszary robocze > Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="3919a-144">Go to **System administration > Feature Management**.</span></span>

1. <span data-ttu-id="3919a-145">Wybierz **Sprawdź, czy są aktualizacje**.</span><span class="sxs-lookup"><span data-stu-id="3919a-145">Select **Check for updates**.</span></span>

1. <span data-ttu-id="3919a-146">Otwórz kartę **Wszystkie** i wyszukaj funkcję o nazwie *Usługa rachunku kosztów*.</span><span class="sxs-lookup"><span data-stu-id="3919a-146">Open the **All** tab and search for the feature named *Cost accounting service*.</span></span>

1. <span data-ttu-id="3919a-147">Wybierz **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="3919a-147">Select **Enable now**.</span></span>

1. <span data-ttu-id="3919a-148">Przejdź do **Zarządzanie kosztami > Usługa rachunku kosztów > Konfiguracja > Prametry usługi rachunku kosztów > Prametry integracji**.</span><span class="sxs-lookup"><span data-stu-id="3919a-148">Go to **Cost management > Cost accounting service > Setup > Cost accounting service parameters > Integrations parameters**.</span></span>

1. <span data-ttu-id="3919a-149">W polu **Identyfikator aplikacji** wprowadź następujący kod:</span><span class="sxs-lookup"><span data-stu-id="3919a-149">In the **Application ID** field, enter the following code:</span></span><br> <span data-ttu-id="3919a-150">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span><span class="sxs-lookup"><span data-stu-id="3919a-150">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span></span>

1. <span data-ttu-id="3919a-151">W polu **Punkt końcowy usługi danych** wprowadź następujący adres URL:</span><span class="sxs-lookup"><span data-stu-id="3919a-151">In the **Data service endpoint** field, enter the following URL:</span></span><br>https://operationsdataservice.operations365.dynamics.com/

1. <span data-ttu-id="3919a-152">W polu **Punkt końcowy usługi rachunku kosztu** wprowadź następujący adres URL:</span><span class="sxs-lookup"><span data-stu-id="3919a-152">In the **Cost accounting service endpoint** field, enter the following URL:</span></span><br>https://costaccountingservice.operations365.dynamics.com/

1. <span data-ttu-id="3919a-153">Usługa rachunku kosztów jest teraz gotowa do użycia.</span><span class="sxs-lookup"><span data-stu-id="3919a-153">The cost accounting service is now ready for use.</span></span>

## <a name="related-resources"></a><span data-ttu-id="3919a-154">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="3919a-154">Related resources</span></span>

[<span data-ttu-id="3919a-155">Usługa rachunu kosztów — strona główna</span><span class="sxs-lookup"><span data-stu-id="3919a-155">Cost accounting service home page</span></span>](cost-accounting-service-home.md)