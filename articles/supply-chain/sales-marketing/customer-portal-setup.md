---
title: Instalowanie, konfigurowanie i aktualizowanie portalu klienta
description: W tym temacie przedstawiono szczegółowe informacje na temat licencjonowania i instrukcje konfiguracji dla portalu klienta.
author: dasani-madipalli
manager: tfehr
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b9d1e742f78254d949dc49fda008d63b8bff4d65
ms.sourcegitcommit: 713b5dfc76a6875d0ba6d86c5cbd585ea502cf9d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2020
ms.locfileid: "3413998"
---
# <a name="install-set-up-and-update-the-customer-portal"></a><span data-ttu-id="9ffdd-103">Instalowanie, konfigurowanie i aktualizowanie portalu klienta</span><span class="sxs-lookup"><span data-stu-id="9ffdd-103">Install, set up, and update the Customer portal</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="9ffdd-104">Wymagania dotyczące licencji</span><span class="sxs-lookup"><span data-stu-id="9ffdd-104">Licensing requirements</span></span>

<span data-ttu-id="9ffdd-105">Aby zaimplementować Portal odbiorców, należy dysponować następującymi licencjami:</span><span class="sxs-lookup"><span data-stu-id="9ffdd-105">To implement the Customer portal, you must have the following licenses:</span></span>

- <span data-ttu-id="9ffdd-106">**Portale Power Apps** — Ta licencja jest wymagana do obsługi portalu klienta.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-106">**Power Apps portals** – This license is required to host the Customer portal.</span></span> <span data-ttu-id="9ffdd-107">Portale są licencjonowane na podstawie użycia.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-107">Portals are licensed based on usage.</span></span> <span data-ttu-id="9ffdd-108">Aby uzyskać więcej informacji, zajrzyj do [wymagań licencyjnych dotyczących portali Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span><span class="sxs-lookup"><span data-stu-id="9ffdd-108">For more information, see the [Power Apps portals licensing requirements](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span></span>
- <span data-ttu-id="9ffdd-109">**Podwójny zapis** — wymagane są licencje niezbędne do włączenia podwójnego zapisywania dla jednostek Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-109">**Dual-write** – You must have the necessary licenses to enable dual-write for Supply Chain Management entities.</span></span> <span data-ttu-id="9ffdd-110">Aby uzyskać więcej informacji, zobacz [Wymagania systemowe dotyczące podwójnego zapisu](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span><span class="sxs-lookup"><span data-stu-id="9ffdd-110">For more information, see the [system requirements for dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span></span>

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a><span data-ttu-id="9ffdd-111">Zależności od podwójnego zapisu i portali Power Apps</span><span class="sxs-lookup"><span data-stu-id="9ffdd-111">Dependencies on dual-write and Power Apps portals</span></span>

<span data-ttu-id="9ffdd-112">Portal klienta zależy od portali Power Apps i podwójnego zapisu, co pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-112">The Customer portal depends on Power Apps portals and dual-write, as shown in the following illustration.</span></span>

![![Zależności portalu klienta](media/customer-portal-elements.png "Zależności portalu klienta")](media/customer-portal-elements.png "Customer portal dependencies")

<span data-ttu-id="9ffdd-114">W przeciwieństwie do innych funkcji Supply Chain Management, szablon Portalu klienta znajduje się w portalach Power Apps.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-114">Unlike other features from Supply Chain Management, the Customer portal template resides in Power Apps portals.</span></span> <span data-ttu-id="9ffdd-115">Z tego względu Portal klienta jest ograniczony przez funkcje i możliwości dostarczane przez portale Power Apps i podmioty zamawiające z podwójnym zapisem.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-115">Therefore, the Customer portal is limited by the functionality and capabilities that are provided by Power Apps portals and the entities in dual-write.</span></span>

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a><span data-ttu-id="9ffdd-116">Konfiguracja wymagana do włączenia portalu klienta</span><span class="sxs-lookup"><span data-stu-id="9ffdd-116">Required setup to enable the Customer portal</span></span>

<span data-ttu-id="9ffdd-117">Po upewnieniu się, że użytkownik dysponuje wymaganymi licencjami, można skonfigurować podwójny zapis w sposób opisany w [instrukcjach wstępnej synchronizacji podwójnego zapisu](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span><span class="sxs-lookup"><span data-stu-id="9ffdd-117">After you've made sure that you have the required licenses, you can set up dual-write as described in the [dual-write initial synchronization instructions](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span></span>

<span data-ttu-id="9ffdd-118">Należy pamiętać, aby w podwójnym zapisywaniu włączyć następujące mapowania jednostek:</span><span class="sxs-lookup"><span data-stu-id="9ffdd-118">Be sure to enable the following entity mappings in dual-write:</span></span>

- <span data-ttu-id="9ffdd-119">Nagłówek zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9ffdd-119">Sales Order Header</span></span>
- <span data-ttu-id="9ffdd-120">Szczegóły zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9ffdd-120">Sales Order Details</span></span>
- <span data-ttu-id="9ffdd-121">Konta</span><span class="sxs-lookup"><span data-stu-id="9ffdd-121">Accounts</span></span>
- <span data-ttu-id="9ffdd-122">Kontakty</span><span class="sxs-lookup"><span data-stu-id="9ffdd-122">Contacts</span></span>
- <span data-ttu-id="9ffdd-123">Produkty</span><span class="sxs-lookup"><span data-stu-id="9ffdd-123">Products</span></span>

<span data-ttu-id="9ffdd-124">Po zakończeniu tych ustawień można zastrzec szablon Portal klienta.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-124">After this setup is completed, you can provision the Customer portal template.</span></span>

## <a name="provision-the-customer-portal"></a><span data-ttu-id="9ffdd-125">Ustanowienie portalu klienta</span><span class="sxs-lookup"><span data-stu-id="9ffdd-125">Provision the Customer portal</span></span>

<span data-ttu-id="9ffdd-126">Przed rozpoczęciem należy upewnić się, że wykonano już [wymagane ustawienia](#required-setup).</span><span class="sxs-lookup"><span data-stu-id="9ffdd-126">Before you begin, make sure that you've already completed the [required setup](#required-setup).</span></span> <span data-ttu-id="9ffdd-127">Następnie należy wykonać poniższe kroki w celu zainicjowania obsługi portalu klienta.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-127">Then follow these steps to provision the Customer portal.</span></span>

1. <span data-ttu-id="9ffdd-128">Przejdź do [make.powerapps.com](https://make.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="9ffdd-128">Go to [make.powerapps.com](https://make.powerapps.com/).</span></span>
2. <span data-ttu-id="9ffdd-129">Upewnij się, że korzystasz z środowiska, w którym jest włączony podwójny zapis.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-129">Make sure that you're using the environment where you enabled dual-write.</span></span>
3. <span data-ttu-id="9ffdd-130">Na karcie **Tworzenie** przewiń w dół do sekcji **Rozpocznij od szablonu**, a następnie wybierz szablon o nazwie **Klient Supply Chain Management**.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-130">On the **Create** tab, scroll down to the **Start from template** section, and select the template that is named **Supply Chain Management Customer**.</span></span>
4. <span data-ttu-id="9ffdd-131">Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-131">Follow the on-screen instructions.</span></span>

<span data-ttu-id="9ffdd-132">Po zakończeniu obsługi administracyjnej można uzyskać dostęp do portalu klienta w sekcji **Twoje aplikacje** na stronie **Głównej**.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-132">After provisioning is completed, you can access the Customer portal in the **Your apps** section of the **Home** page.</span></span>

> [!NOTE]
> <span data-ttu-id="9ffdd-133">Jeśli rozwiązanie podwójnego zapisywania nie jest zainstalowane w środowisku, w którym pracujesz, zostanie wyświetlony komunikat o błędzie, a Portal klienta nie zostanie zainicjowany.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-133">If the dual-write solution isn't installed in the environment that you're working in, you will receive an error message, and the Customer portal won't be provisioned.</span></span>

## <a name="update-the-customer-portal"></a><span data-ttu-id="9ffdd-134">Aktualizacja portalu klienta</span><span class="sxs-lookup"><span data-stu-id="9ffdd-134">Update the Customer portal</span></span>

<span data-ttu-id="9ffdd-135">Do portalu klienta można później dodać więcej funkcji.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-135">More functionality might be added to the Customer portal later.</span></span> <span data-ttu-id="9ffdd-136">Wszelkie zmiany, które firma Microsoft wprowadza w podstawowych składnikach rozwiązania, będą automatycznie widoczne w danym środowisku.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-136">Any changes that Microsoft makes to the underlying solution components will automatically appear in your environment.</span></span> <span data-ttu-id="9ffdd-137">Jednak witryna sieci Web, która jest zainicjowana w środowisku, nie będzie automatycznie uwzględniać zmian wprowadzonych w danych konfiguracyjnych.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-137">However, the website that is provisioned in your environment won't automatically reflect changes that are made to the configuration data.</span></span> <span data-ttu-id="9ffdd-138">Należy ręcznie zastosować te zmiany, pobierając kod z nowego szablonu i scalając go z zainicjowaną witryną sieci Web.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-138">You will have to manually apply those changes by getting the code from the new template and merging it with the provisioned website.</span></span>

## <a name="resources"></a><span data-ttu-id="9ffdd-139">Zasoby</span><span class="sxs-lookup"><span data-stu-id="9ffdd-139">Resources</span></span>

<span data-ttu-id="9ffdd-140">Aby dowiedzieć się, jak można skonfigurować i dostosować Portal klienta, należy zacząć od przejrzenia następującej dokumentacji dla podstawowych technologii:</span><span class="sxs-lookup"><span data-stu-id="9ffdd-140">To learn how you can set up and customize the Customer portal, you should start by reviewing the following documentation for the underlying technologies:</span></span>

- [<span data-ttu-id="9ffdd-141">Dokumentacja portali Power Apps</span><span class="sxs-lookup"><span data-stu-id="9ffdd-141">Power Apps portals documentation</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [<span data-ttu-id="9ffdd-142">Dokumentacja podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="9ffdd-142">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

<span data-ttu-id="9ffdd-143">Aby efektywnie zarządzać portalami, należy zrozumieć portale Power Apps i cykl życia Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9ffdd-143">To effectively manage your portals, you must understand the Power Apps portals and Common Data Service lifecycle.</span></span> <span data-ttu-id="9ffdd-144">Aby uzyskać więcej informacji, zobacz następujące zasoby:</span><span class="sxs-lookup"><span data-stu-id="9ffdd-144">For more information, see the following resources:</span></span>

- [<span data-ttu-id="9ffdd-145">Cykl życia portalu — informacje</span><span class="sxs-lookup"><span data-stu-id="9ffdd-145">About portal lifecycle</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="9ffdd-146">Uaktualnianie portalu</span><span class="sxs-lookup"><span data-stu-id="9ffdd-146">Upgrade a portal</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="9ffdd-147">Migruj konfigurację portalu</span><span class="sxs-lookup"><span data-stu-id="9ffdd-147">Migrate portal configuration</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="9ffdd-148">Zarządzanie cyklem życia rozwiązania: Dynamics 365 dla aplikacji Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="9ffdd-148">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)