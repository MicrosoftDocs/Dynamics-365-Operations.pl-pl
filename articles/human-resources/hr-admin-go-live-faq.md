---
title: Rozpoczynanie eksploatacji — często zadawane pytania
description: Ten temat zawiera listę często zadawanych pytań dotyczących sposobu przychodzenia do projektu implementacji Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
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
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 64a85840be328702a06779390fe383fd1896fd04
ms.sourcegitcommit: d66fd72342931fad25a696b251c05781280d36c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "4011434"
---
# <a name="go-live-faq"></a><span data-ttu-id="78dce-103">Rozpoczynanie eksploatacji — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="78dce-103">Go-live FAQ</span></span> 

<span data-ttu-id="78dce-104">Ten temat zawiera listę często zadawanych pytań dotyczących sposobu przychodzenia do projektu implementacji Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="78dce-104">This topic lists frequently asked questions about how to go live with a Dynamics 365 Human Resources implementation project.</span></span> 

## <a name="when-can-i-configure-and-request-my-production-environment"></a><span data-ttu-id="78dce-105">Kiedy mogę skonfigurować i zażądać mojego środowiska produkcyjnego?</span><span class="sxs-lookup"><span data-stu-id="78dce-105">When can I configure and request my production environment?</span></span> 

<span data-ttu-id="78dce-106">Zazwyczaj środowisko produkcyjne jest wdrażane po spełnieniu następujących kryteriów:</span><span class="sxs-lookup"><span data-stu-id="78dce-106">Typically, a production environment is deployed after meeting the following criteria:</span></span>

- <span data-ttu-id="78dce-107">Wszystkie dostosowania są wykonane w kodzie.</span><span class="sxs-lookup"><span data-stu-id="78dce-107">All customizations are code-complete.</span></span>
- <span data-ttu-id="78dce-108">Testowanie akceptacji użytkownika (UAT) zostało ukończone.</span><span class="sxs-lookup"><span data-stu-id="78dce-108">User acceptance testing (UAT) is complete.</span></span>
- <span data-ttu-id="78dce-109">Odbiorca wylogował się z rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="78dce-109">The customer has signed off on the solution.</span></span>
- <span data-ttu-id="78dce-110">Brak problemów z blokowaniem dla rozwiązania „Live”.</span><span class="sxs-lookup"><span data-stu-id="78dce-110">There are no blocking issues for go-live.</span></span> 

<span data-ttu-id="78dce-111">Gdy zakwalifikowani odbiorcy znajdują się na tym etapie, zespół Microsoft FastTrack będzie współpracować z zespołem projektu w celu wykonania oceny.</span><span class="sxs-lookup"><span data-stu-id="78dce-111">When qualified customers are at this stage, the Microsoft FastTrack team will work with the project team to do a go-live assessment.</span></span> 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a><span data-ttu-id="78dce-112">Jakie są wymagania wstępne dotyczące wdrażania środowiska produkcyjnego?</span><span class="sxs-lookup"><span data-stu-id="78dce-112">What are the prerequisites to deploying a production environment?</span></span> 

<span data-ttu-id="78dce-113">Aby zapoznać się z listą wymagań wstępnych, przejrzyj temat  [Przygotowywanie do rozpoczęcia eksploatacji](hr-admin-go-live-prepare.md).</span><span class="sxs-lookup"><span data-stu-id="78dce-113">For a list of the prerequisites, see [Prepare for go-live](hr-admin-go-live-prepare.md).</span></span> 

## <a name="what-is-a-go-live-assessment"></a><span data-ttu-id="78dce-114">Co to jest Ocena rozpoczęcia eksploatacji?</span><span class="sxs-lookup"><span data-stu-id="78dce-114">What is a go-live assessment?</span></span>  

<span data-ttu-id="78dce-115">Ocena rozpoczęcia eksploatacji jest częścią  [programu Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span><span class="sxs-lookup"><span data-stu-id="78dce-115">The go-live assessment is part of the [Microsoft FastTrack program](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span></span> <span data-ttu-id="78dce-116">Podczas tego przeglądu architekt rozwiązania ocenia, czy projekt implementacji jest gotowy do pomyślnej migracji i przejścia do rozpoczęcia eksploatacji.</span><span class="sxs-lookup"><span data-stu-id="78dce-116">During this review, a solution architect assesses whether an implementation project is ready for a successful cutover and go-live.</span></span> <span data-ttu-id="78dce-117">Ten przegląd jest wymagany dla każdego projektu implementacji, zanim będzie można zażądać jego wdrożenia w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="78dce-117">This review is mandatory for every implementation project before you can request to go live in a production environment.</span></span> 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a><span data-ttu-id="78dce-118">Nasze środowiska piaskownicy są wdrażane w centrum danych w środkowych Stanach Zjednoczonych.</span><span class="sxs-lookup"><span data-stu-id="78dce-118">Our Sandbox environments are deployed in the Central US datacenter.</span></span> <span data-ttu-id="78dce-119">Chcemy, aby nasze środowiska produkcyjne były wdrażane w centrum danych w zachodnich Stanach Zjednoczonych.</span><span class="sxs-lookup"><span data-stu-id="78dce-119">We want our Production environments to be deployed in the West US datacenter.</span></span> <span data-ttu-id="78dce-120">Czy mogę wybrać Zachodnie stany USA jako centrum danych w mojej konfiguracji produkcyjnej?</span><span class="sxs-lookup"><span data-stu-id="78dce-120">Can I select West US as the datacenter in my Production configuration?</span></span> 

<span data-ttu-id="78dce-121">USŁUGI LCS nie ogranicza wyboru innego centrum danych podczas wdrażania środowiska Human Resources, ale zdecydowanie zaleca się, aby nie wybierać innego centrum danych.</span><span class="sxs-lookup"><span data-stu-id="78dce-121">LCS doesn't restrict you from selecting a different data center when you deploy a Human Resources environment, but we strongly recommend not selecting a different data center.</span></span>  

<span data-ttu-id="78dce-122">Jeśli chcesz, aby środowisko produkcyjne znajdowało się w centrum danych w zachodnich Stanach Zjednoczonych, najpierw należy ponownie wdrożyć środowiska piaskownicy w centrum danych w zachodnich Stanach Zjednoczonych, przetestować je i się wylogować.</span><span class="sxs-lookup"><span data-stu-id="78dce-122">If you want your Production environment to be in the West US datacenter, you should first redeploy your Sandbox environments to the West US datacenter, test them, and sign off.</span></span> 

<span data-ttu-id="78dce-123">Aby uzyskać informacje dotyczące wyboru odpowiedniego centrum danych, zapoznaj się z [Wymaganiami sieciowymi](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="78dce-123">For information about selecting the correct datacenter, see [Network requirements](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span></span> 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a><span data-ttu-id="78dce-124">Jaki poziom dostępu muszę posiadać do zasobów systemu Azure dla środowisk z Human Resources?</span><span class="sxs-lookup"><span data-stu-id="78dce-124">What level of access do I have to the Azure resources for my Human Resources environments?</span></span>  

<span data-ttu-id="78dce-125">Dostęp do środowisk Human Resources jest ograniczony.</span><span class="sxs-lookup"><span data-stu-id="78dce-125">Access to the Human Resources environments is limited.</span></span> <span data-ttu-id="78dce-126">Nie możesz uzyskać dostępu do maszyny wirtualnej (VM) ani Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="78dce-126">You can't access the virtual machine (VM) or Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="78dce-127">Nie można również uzyskać dostępu do bazy danych za pośrednictwem programu Management Studio Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="78dce-127">You also can't access the database through Microsoft SQL Server Management Studio.</span></span> 

<span data-ttu-id="78dce-128">Chociaż nie możesz uzyskać bezpośredniego dostępu do zasobów platformy Azure lub środowiska Dynamics 365 Human Resources, istnieją dodatkowe funkcje, których możesz użyć, aby uzyskać dostęp do swoich danych:</span><span class="sxs-lookup"><span data-stu-id="78dce-128">Although you can't access your Azure resources or Dynamics 365 Human Resources environment directly, there are additional features you can use to access your data:</span></span>

- <span data-ttu-id="78dce-129">Bazę danych SQL Azure można wdrożyć we własnej dzierżawie Azure i za pomocą funkcji Używanie własnej bazy danych w celu zsynchronizowania danych.</span><span class="sxs-lookup"><span data-stu-id="78dce-129">You can deploy an Azure SQL database in your own Azure tenant and use the Bring Your Own Database (BYOD) feature to synchronize data.</span></span> <span data-ttu-id="78dce-130">Aby uzyskać więcej informacji, zapoznaj się z tematem [Dobierz własną bazę danych (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="78dce-130">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span>

- <span data-ttu-id="78dce-131">Funkcji integracji Common Data Service można wykorzystywać do synchronizowania wybranych jednostek w bazie danych Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="78dce-131">You can use Common Data Service integration to synchronize select entities into the Common Data Service database.</span></span> <span data-ttu-id="78dce-132">Aby uzyskać więcej informacji, zobacz [Jednostki usługi Common Data Service](hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="78dce-132">For more information, see [Common Data Service entities](hr-developer-entities.md).</span></span> 

## <a name="how-often-is-my-production-database-backed-up"></a><span data-ttu-id="78dce-133">Jak często jest wykonywana kopia zapasowa bazy danych produkcji?</span><span class="sxs-lookup"><span data-stu-id="78dce-133">How often is my production database backed up?</span></span> 

<span data-ttu-id="78dce-134">Automatyczne wykonywanie kopii zapasowych baz danych jest chronione przy użyciu następujących częstotliwości:</span><span class="sxs-lookup"><span data-stu-id="78dce-134">Databases are protected by automatic backups at the following frequencies:</span></span>

| <span data-ttu-id="78dce-135">Typ kopii zapasowej</span><span class="sxs-lookup"><span data-stu-id="78dce-135">Type of backup</span></span> | <span data-ttu-id="78dce-136">Częstotliwość</span><span class="sxs-lookup"><span data-stu-id="78dce-136">Frequency</span></span> |
| --- | --- |
| <span data-ttu-id="78dce-137">Tworzenie pełnej kopii zapasowych bazy danych</span><span class="sxs-lookup"><span data-stu-id="78dce-137">Full database backup</span></span> | <span data-ttu-id="78dce-138">Tygodniowa</span><span class="sxs-lookup"><span data-stu-id="78dce-138">Weekly</span></span> |
| <span data-ttu-id="78dce-139">Różnicowa kopia zapasowa bazy danych</span><span class="sxs-lookup"><span data-stu-id="78dce-139">Differential database backup</span></span> | <span data-ttu-id="78dce-140">Co 12-24 godzin</span><span class="sxs-lookup"><span data-stu-id="78dce-140">Every 12-24 hours</span></span> |
| <span data-ttu-id="78dce-141">Kopia zapasowa dziennika transakcji</span><span class="sxs-lookup"><span data-stu-id="78dce-141">Transaction log backup</span></span> | <span data-ttu-id="78dce-142">Co 5 do 10 minut</span><span class="sxs-lookup"><span data-stu-id="78dce-142">Every 5 to 10 minutes</span></span> |

<span data-ttu-id="78dce-143">Firma Microsoft zachowuje wystarczające kopie zapasowe, aby umożliwić Przywracanie bazy danych do punktu w czasie (PITR) w ciągu ostatnich siedmiu dni.</span><span class="sxs-lookup"><span data-stu-id="78dce-143">Microsoft retains sufficient backups to allow for Point in Time Restore (PITR) within the last seven days.</span></span> 

<span data-ttu-id="78dce-144">Aby uzyskać więcej informacji, zobacz  [Więcej informacji na temat automatycznego wykonywania kopii zapasowych bazy danych SQL](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span><span class="sxs-lookup"><span data-stu-id="78dce-144">For more information, see [Learn about automatic SQL Database backups](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span></span> 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a><span data-ttu-id="78dce-145">Czy mogę zażądać kopii kopii zapasowej bazy danych produkcji?</span><span class="sxs-lookup"><span data-stu-id="78dce-145">Can I request a copy of the backup of my production database?</span></span> 

<span data-ttu-id="78dce-146">Nr</span><span class="sxs-lookup"><span data-stu-id="78dce-146">No.</span></span> <span data-ttu-id="78dce-147">Można jednak przesłać żądanie usługi odświeżania bazy danych w celu skopiowania środowiska produkcyjnego do środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="78dce-147">You can submit a database refresh service request to copy your Production environment to your Sandbox environment, however.</span></span> <span data-ttu-id="78dce-148">Bazę danych SQL Azure można wdrożyć we własnej dzierżawie Azure i za pomocą funkcji Używanie własnej bazy danych w celu zsynchronizowania danych ze środowiska produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="78dce-148">You can deploy an Azure SQL database in your own Azure tenant and use the BYOD feature to synchronize data from your Production environment.</span></span> <span data-ttu-id="78dce-149">Aby uzyskać więcej informacji, zapoznaj się z tematem [Dobierz własną bazę danych (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="78dce-149">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span> 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a><span data-ttu-id="78dce-150">Jak przenieść środowisko piaskownicy do produkcji, aby rozpocząć eksploatację?</span><span class="sxs-lookup"><span data-stu-id="78dce-150">How do I move my Sandbox environment to Production for go-live?</span></span> 

<span data-ttu-id="78dce-151">Ponieważ funkcja kopiowania nie jest dostępna w celu przeniesienia środowiska z piaskownicy do środowiska produkcyjnego, należy skorzystać z pakietów danych w celu przeniesienia danych do środowiska produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="78dce-151">Because a copy feature isn't available to move your environment from a Sandbox to a Production environment, you must use data packages to move data into your Production environment.</span></span>  

<span data-ttu-id="78dce-152">Zalecamy obsługiwanie jasnej listy jednostek skonfigurowanych w obszarze izolowanym w całym projekcie.</span><span class="sxs-lookup"><span data-stu-id="78dce-152">We recommend maintaining a clear list of entities configured in your Sandbox throughout the project.</span></span> <span data-ttu-id="78dce-153">Następnie przetestuj proces migracji i migracji wszystkich pakietów danych potrzebnych do tego celu.</span><span class="sxs-lookup"><span data-stu-id="78dce-153">Then test the process of cutover and migration of any data packages needed for your go-live.</span></span> <span data-ttu-id="78dce-154">Wszystkie pakiety danych trzeba przenieść ręcznie do środowiska produkcyjnego, gdy będzie gotowe do pracy.</span><span class="sxs-lookup"><span data-stu-id="78dce-154">You must manually move any data packages into the Production environment when you are ready to go live.</span></span> 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a><span data-ttu-id="78dce-155">Co należy zrobić, jeśli środowisko produkcyjne jest wyłączone?</span><span class="sxs-lookup"><span data-stu-id="78dce-155">What should I do if my Production environment is down?</span></span> 

<span data-ttu-id="78dce-156">Aby zgłosić awarię środowiska produkcji, należy wykonać proces opisany w temacie  [Zgłaszanie awarii produkcji](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span><span class="sxs-lookup"><span data-stu-id="78dce-156">To report a Production outage, follow the process described in [Report a production outage](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span></span> 

 ## <a name="see-also"></a><span data-ttu-id="78dce-157">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="78dce-157">See also</span></span>

 [<span data-ttu-id="78dce-158">Przygotowywanie do rozpoczęcia eksploatacji</span><span class="sxs-lookup"><span data-stu-id="78dce-158">Prepare for go-live</span></span>](hr-admin-go-live-prepare.md)