---
title: Rozwiązywanie problemów podczas synchronizacji początkowej
description: Ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas wstępnej synchronizacji.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172721"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="cafe6-103">Rozwiązywanie problemów podczas synchronizacji początkowej</span><span class="sxs-lookup"><span data-stu-id="cafe6-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="cafe6-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="cafe6-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="cafe6-105">A dokładniej, ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas wstępnej synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="cafe6-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="cafe6-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="cafe6-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="cafe6-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="cafe6-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="cafe6-108">Sprawdź, czy w aplikacji Finance and Operations nie występują błędy synchronizacji początkowej</span><span class="sxs-lookup"><span data-stu-id="cafe6-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="cafe6-109">Po włączeniu szablonów mapowania stan map powinien być **Uruchomione**.</span><span class="sxs-lookup"><span data-stu-id="cafe6-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="cafe6-110">Jeśli stan jest **Nie uruchomione**, wystąpiły błędy podczas wstępnej synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="cafe6-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="cafe6-111">Aby wyświetlić błędy, wybierz kartę **Szczegóły wstępnej synchronizacji** na stronie **Podwójny zapis**.</span><span class="sxs-lookup"><span data-stu-id="cafe6-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Karta Szczegóły wstępnej synchronizacji](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="cafe6-113">Nie można ukończyć synchronizacji początkowej: 400 złe żądanie</span><span class="sxs-lookup"><span data-stu-id="cafe6-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="cafe6-114">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="cafe6-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="cafe6-115">Podczas próby uruchomienia mapowania i wstępnej synchronizacji może zostać wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="cafe6-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="cafe6-116">*Serwer zdalny zwrócił błąd: (400) złe żądanie.) Podczas eksportu AX napotkał błąd*</span><span class="sxs-lookup"><span data-stu-id="cafe6-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="cafe6-117">Oto przykład tabeli pełnego komunikatu o błędzie.</span><span class="sxs-lookup"><span data-stu-id="cafe6-117">Here is an example of the full error message.</span></span>

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

<span data-ttu-id="cafe6-118">Jeśli ten błąd występuje zawsze i nie można ukończyć wstępnej synchronizacji, należy wykonać poniższe kroki w celu rozwiązania problemu.</span><span class="sxs-lookup"><span data-stu-id="cafe6-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="cafe6-119">Zaloguj się do maszyny wirtualnej (VM) aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cafe6-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="cafe6-120">Otwórz Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="cafe6-120">Open Microsoft Management Console.</span></span> 
3. <span data-ttu-id="cafe6-121">Upewnij się, że w okienku **Usługi** jest uruchomiona usługa struktury eksportu danych Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cafe6-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="cafe6-122">Uruchom ją ponownie, jeśli została zatrzymana, ponieważ wymaga tego synchronizacja wstępna.</span><span class="sxs-lookup"><span data-stu-id="cafe6-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="cafe6-123">Błąd synchronizacji początkowej: 403 zabroniony</span><span class="sxs-lookup"><span data-stu-id="cafe6-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="cafe6-124">Podczas wstępnej synchronizacji może zostać wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="cafe6-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="cafe6-125">*(\[Zabroniony\], serwer zdalny zwrócił błąd: (403) Zabroniony.) Podczas eksportu AX napotkał błąd*</span><span class="sxs-lookup"><span data-stu-id="cafe6-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="cafe6-126">Aby naprawić problem, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="cafe6-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="cafe6-127">Zaloguj się do aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cafe6-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="cafe6-128">Na stronie **aplikacje Azure Active Directory** usuń klienta **DtAppID**, a następnie dodaj go ponownie.</span><span class="sxs-lookup"><span data-stu-id="cafe6-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Lista aplikacji Azure AD](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a><span data-ttu-id="cafe6-130">Błędy odwołują się do siebie podczas początkowej synchronizacji</span><span class="sxs-lookup"><span data-stu-id="cafe6-130">Self-reference failures during initial synchronization</span></span>

<span data-ttu-id="cafe6-131">Może się pojawić komunikat o błędzie podobnym do następującego przykładu, jeśli dowolne z mapowań ma odwołuje się do siebie:</span><span class="sxs-lookup"><span data-stu-id="cafe6-131">You might receive an error message that resembles the following example if any of your mappings have self-references:</span></span>

<span data-ttu-id="cafe6-132">*W przypadku Dostawców V2 następujący błąd: Identyfikator rekordu: nowy rekord, ErrorMessage: Nie można rozpoznać identyfikatora GUID dla pola: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Nie znaleziono wartości wyszukiwania: CN-001. Spróbuj użyć tych adresów URL, aby sprawdzić, czy istnieją dane referencyjne: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq „CN-001”*</span><span class="sxs-lookup"><span data-stu-id="cafe6-132">*On the Vendors V2, the following error: Record Id: new record, ErrorMessage: Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup value was not found: CN-001. Try this URL(s) to check if the reference data exists: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span></span>

<span data-ttu-id="cafe6-133">Ten typ błędu występuje podczas wstępnej synchronizacji mapowań z odwołaniami do siebie.</span><span class="sxs-lookup"><span data-stu-id="cafe6-133">This type of error occurs during initial synchronization of mappings that have self-references.</span></span> <span data-ttu-id="cafe6-134">W poprzednim przykładzie pole konto faktury odwołuje się do jednostki dostawcy.</span><span class="sxs-lookup"><span data-stu-id="cafe6-134">In the preceding example, the field invoice account references the vendor entity.</span></span>

<span data-ttu-id="cafe6-135">Aby rozwiązać ten problem, konieczne może być uruchomienie mapowania dwa razy przed zakończeniem synchronizacji początkowej.</span><span class="sxs-lookup"><span data-stu-id="cafe6-135">To fix the issue, you might have to run the mapping two times before the initial synchronization is successful.</span></span>

