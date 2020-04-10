---
title: Rozwiązywanie problemów z modułem podwójnego zapisu w aplikacjach Finance and Operations
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z modułem podwójnego zapisu w aplikacjach Finance and Operations.
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
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172767"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="9075a-103">Rozwiązywanie problemów z modułem podwójnego zapisu w aplikacjach Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9075a-103">Troubleshoot issues with the Dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="9075a-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9075a-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="9075a-105">Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z modułem **podwójnego zapisu** w aplikacjach Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9075a-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9075a-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9075a-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="9075a-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="9075a-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="9075a-108">Nie można załadować modułu podwójnego zapisywania w aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9075a-108">You can't load the Dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="9075a-109">Jeśli nie można otworzyć strony **podwójnego zapisywania**, wybierając opcję **podwójnego zapisywania** w obszarze roboczym **zarządzanie danymi**, prawdopodobnie usługa integracji danych jest niemożliwa.</span><span class="sxs-lookup"><span data-stu-id="9075a-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="9075a-110">Utwórz bilet pomocy technicznej, aby zażądać ponownego uruchomienia usługi integracji danych.</span><span class="sxs-lookup"><span data-stu-id="9075a-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a><span data-ttu-id="9075a-111">Błąd podczas próby utworzenia mapowania nowej jednostki</span><span class="sxs-lookup"><span data-stu-id="9075a-111">Error when you try to create a new entity mapping</span></span>

<span data-ttu-id="9075a-112">**Wymagane poświadczenia w celu rozwiązania problemu:** administrator dzierżawy Azure AD</span><span class="sxs-lookup"><span data-stu-id="9075a-112">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="9075a-113">Podczas próby skonfigurowania nowej jednostki na potrzeby podwójnego zapisywania może pojawić się następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="9075a-113">You might receive the following error message when you try to configure a new entity for dual-write:</span></span>

<span data-ttu-id="9075a-114">*Kod stanu odpowiedzi nie wskazuje powodzenia: 401 (nieautoryzowany)*</span><span class="sxs-lookup"><span data-stu-id="9075a-114">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>

<span data-ttu-id="9075a-115">Ten błąd występuje, ponieważ tylko Administrator dzierżawy Azure AD może dodać nowe mapowanie jednostki.</span><span class="sxs-lookup"><span data-stu-id="9075a-115">This error occurs because only an Azure AD tenant admin can add a new entity mapping.</span></span>

<span data-ttu-id="9075a-116">Aby rozwiązać ten problem, zaloguj się w aplikacji Finance and Operations jako Administrator dzierżawy Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9075a-116">To fix the issue, sign in to the Finance and Operations app as an Azure AD admin tenant.</span></span> <span data-ttu-id="9075a-117">Należy również przejść do witryny sieci Web.PowerApps.com i ponownie sprawdź poprawność połączenia.</span><span class="sxs-lookup"><span data-stu-id="9075a-117">You must also go to web.PowerApps.com and revalidate your connection.</span></span>

## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="9075a-118">Błąd podczas otwierania interfejsu użytkownika z podwójnym zapisywaniem</span><span class="sxs-lookup"><span data-stu-id="9075a-118">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="9075a-119">Podczas próby uzyskania dostępu do podwójnego zapisu w obszarze roboczym **zarządzanie danymi** może zostać wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="9075a-119">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="9075a-120">*login.microsoftonline.com odmówił połączenia.*</span><span class="sxs-lookup"><span data-stu-id="9075a-120">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="9075a-121">Aby rozwiązać ten problem, zaloguj się przy użyciu okna prywatnego w Microsoft Edge, w oknie incognito w Chromium lub w oknie incognito w usłudze Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="9075a-121">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="9075a-122">Należy również odblokować lub wyczyścić pliki cookie innych firm.</span><span class="sxs-lookup"><span data-stu-id="9075a-122">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="9075a-123">Błąd podczas łączenia środowiska w celu wykonania podwójnego zapisywania lub dodania nowego mapowania jednostki</span><span class="sxs-lookup"><span data-stu-id="9075a-123">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="9075a-124">**Wymagane poświadczenia w celu rozwiązania problemu:** administrator dzierżawy Azure AD</span><span class="sxs-lookup"><span data-stu-id="9075a-124">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="9075a-125">Podczas łączenia lub tworzenia map może wystąpić następujący błąd:</span><span class="sxs-lookup"><span data-stu-id="9075a-125">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="9075a-126">*Kod stanu odpowiedzi nie wskazuje powodzenia: 403 (tokenexchange).<br> Identyfikator sesji: \<twój identyfikator sesji\><br> Identyfikator głównego działania: \<twój identyfikator działania głównego\>*</span><span class="sxs-lookup"><span data-stu-id="9075a-126">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="9075a-127">Ten błąd może wystąpić, jeśli użytkownik nie ma wystarczających uprawnień, aby połączyć podwójny zapis lub utworzyć mapy.</span><span class="sxs-lookup"><span data-stu-id="9075a-127">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="9075a-128">Aby połączyć środowiska i dodać nowe mapowania jednostek, należy skorzystać z konta administratora dzierżawy Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9075a-128">You must use an Azure AD tenant admin account to link environments and add new entity mappings.</span></span> <span data-ttu-id="9075a-129">Jednak po zakończeniu pracy instalatora można za pomocą konta innego niż administrator monitorować stan i edytować mapowania.</span><span class="sxs-lookup"><span data-stu-id="9075a-129">However, after setup, you can use a non-admin account to monitor status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="9075a-130">Błąd podczas zatrzymania mapowania jednostki</span><span class="sxs-lookup"><span data-stu-id="9075a-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="9075a-131">Podczas próby zatrzymania mapowania encji może pojawić się następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="9075a-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="9075a-132">*\[Zabroniony\], \[{„stan”: 403, „źródłowy”: „”, „komunikat”: „błąd wymiany tokenów: Użytkownik nie może uzyskać dostępu do połączenia dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx”}\]”. Serwer zdalny zwrócił błąd: (403) zabroniony.*</span><span class="sxs-lookup"><span data-stu-id="9075a-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="9075a-133">Ten błąd występuje, gdy połączone środowisko Common Data Service jest niedostępne.</span><span class="sxs-lookup"><span data-stu-id="9075a-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="9075a-134">Aby rozwiązać ten problem, utwórz bilet dla zespołu integracji danych.</span><span class="sxs-lookup"><span data-stu-id="9075a-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="9075a-135">Dołącz śledzenie sieci, aby zespół integracji danych mógł oznaczyć mapy jako **Nie uruchomione** na zapleczu.</span><span class="sxs-lookup"><span data-stu-id="9075a-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>
