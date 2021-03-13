---
title: Rozwiązywanie problemów z podwójnym zapisem w aplikacjach Finance and Operations
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 3ffeb2de0acc1761bccf62a1a124852c504e2a3a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5131252"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a><span data-ttu-id="5a84d-103">Rozwiązywanie problemów z podwójnym zapisem w aplikacjach Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5a84d-103">Troubleshoot dual-write issues in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="5a84d-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5a84d-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="5a84d-105">Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych z modułem **podwójnego zapisu** w aplikacjach Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5a84d-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a84d-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="5a84d-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="5a84d-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="5a84d-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="5a84d-108">Nie można załadować modułu podwójnego zapisywania w aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5a84d-108">You can't load the dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="5a84d-109">Jeśli nie można otworzyć strony **podwójnego zapisywania**, wybierając opcję **podwójnego zapisywania** w obszarze roboczym **zarządzanie danymi**, prawdopodobnie usługa integracji danych jest niemożliwa.</span><span class="sxs-lookup"><span data-stu-id="5a84d-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="5a84d-110">Utwórz bilet pomocy technicznej, aby zażądać ponownego uruchomienia usługi integracji danych.</span><span class="sxs-lookup"><span data-stu-id="5a84d-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-table-map"></a><span data-ttu-id="5a84d-111">Błąd podczas próby utworzenia mapy nowej tabeli</span><span class="sxs-lookup"><span data-stu-id="5a84d-111">Error when you try to create a new table map</span></span>

<span data-ttu-id="5a84d-112">**Wymagane poświadczenia w celu rozwiązania problemu:** Ten sam użytkownik, który skonfigurował podwójne zapisywanie.</span><span class="sxs-lookup"><span data-stu-id="5a84d-112">**Required credentials to fix the issue:** The same user that setup dual-write.</span></span>

<span data-ttu-id="5a84d-113">Podczas próby skonfigurowania nowej tabeli na potrzeby podwójnego zapisu może pojawić się następujący komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="5a84d-113">You might receive the following error message when you try to configure a new table for dual-write.</span></span> <span data-ttu-id="5a84d-114">Jedyny użytkownik, który może stworzyć mapę, jest użytkownikiem, który konfiguruje połączenie podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="5a84d-114">The only user that can create a map is the user who setup the dual-write connection.</span></span>

<span data-ttu-id="5a84d-115">*Kod stanu odpowiedzi nie wskazuje powodzenia: 401 (nieautoryzowany)*</span><span class="sxs-lookup"><span data-stu-id="5a84d-115">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>


## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="5a84d-116">Błąd podczas otwierania interfejsu użytkownika z podwójnym zapisywaniem</span><span class="sxs-lookup"><span data-stu-id="5a84d-116">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="5a84d-117">Podczas próby uzyskania dostępu do podwójnego zapisu w obszarze roboczym **zarządzanie danymi** może zostać wyświetlony następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="5a84d-117">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="5a84d-118">*login.microsoftonline.com odmówił połączenia.*</span><span class="sxs-lookup"><span data-stu-id="5a84d-118">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="5a84d-119">Aby rozwiązać ten problem, zaloguj się przy użyciu okna prywatnego w Microsoft Edge, w oknie incognito w Chromium lub w oknie incognito w usłudze Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="5a84d-119">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="5a84d-120">Należy również odblokować lub wyczyścić pliki cookie innych firm.</span><span class="sxs-lookup"><span data-stu-id="5a84d-120">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a><span data-ttu-id="5a84d-121">Błąd podczas łączenia środowiska w celu wykonania podwójnego zapisywania lub dodania nowego mapowania tabeli</span><span class="sxs-lookup"><span data-stu-id="5a84d-121">Error when you link the environment for dual-write or add a new table mapping</span></span>

<span data-ttu-id="5a84d-122">**Wymagana rola w celu rozwiązania problemu:** administrator systemu w aplikacjach Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5a84d-122">**Required role to fix the issue:** System administrator in both Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="5a84d-123">Podczas łączenia lub tworzenia map może wystąpić następujący błąd:</span><span class="sxs-lookup"><span data-stu-id="5a84d-123">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="5a84d-124">*Kod stanu odpowiedzi nie wskazuje powodzenia: 403 (tokenexchange). <br> Identyfikator sesji: \<your session id\><br> Identyfikator głównego działania: \<your root activity id\>*</span><span class="sxs-lookup"><span data-stu-id="5a84d-124">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="5a84d-125">Ten błąd może wystąpić, jeśli użytkownik nie ma wystarczających uprawnień, aby połączyć podwójny zapis lub utworzyć mapy.</span><span class="sxs-lookup"><span data-stu-id="5a84d-125">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="5a84d-126">Ten błąd może również wystąpić, jeśli środowisko Dataverse zostało zresetowane bez odłączenia podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="5a84d-126">This error can also occur if the Dataverse environment was reset without unlinking dual-write.</span></span> <span data-ttu-id="5a84d-127">Każdy użytkownik z rolą administratora systemu w aplikacjach Finance and Operations i Dataverse może łączyć środowiska.</span><span class="sxs-lookup"><span data-stu-id="5a84d-127">Any user with system administrator role in both Finance and Operations apps and Dataverse can link the environments.</span></span> <span data-ttu-id="5a84d-128">Tylko użytkownik instalujący połączenie podwójnego zapisu może dodawać nowe mapowania tabeli.</span><span class="sxs-lookup"><span data-stu-id="5a84d-128">Only the user who setup the dual-write connection can add new table maps.</span></span> <span data-ttu-id="5a84d-129">Po zakończeniu instalacji każdy użytkownik z rolą administratora systemu może monitorować stan i edytować mapowania.</span><span class="sxs-lookup"><span data-stu-id="5a84d-129">After setup, any user with system administrator role can monitor the status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-table-mapping"></a><span data-ttu-id="5a84d-130">Błąd podczas zatrzymania mapowania tabeli</span><span class="sxs-lookup"><span data-stu-id="5a84d-130">Error when you stop the table mapping</span></span>

<span data-ttu-id="5a84d-131">Podczas próby zatrzymania mapowania tabeli może pojawić się następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="5a84d-131">You might receive the following error message when you try to stop the table mappings:</span></span>

<span data-ttu-id="5a84d-132">*\[Zabroniony\], \[{„stan”: 403, „źródłowy”: „”, „komunikat”: „błąd wymiany tokenów: Użytkownik nie może uzyskać dostępu do połączenia dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx”}\]”. Serwer zdalny zwrócił błąd: (403) zabroniony.*</span><span class="sxs-lookup"><span data-stu-id="5a84d-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="5a84d-133">Ten błąd występuje, gdy połączone środowisko Dataverse jest niedostępne.</span><span class="sxs-lookup"><span data-stu-id="5a84d-133">This error occurs when the linked Dataverse environment isn't available.</span></span>

<span data-ttu-id="5a84d-134">Aby rozwiązać ten problem, utwórz bilet dla zespołu integracji danych.</span><span class="sxs-lookup"><span data-stu-id="5a84d-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="5a84d-135">Dołącz śledzenie sieci, aby zespół integracji danych mógł oznaczyć mapy jako **Nie uruchomione** na zapleczu.</span><span class="sxs-lookup"><span data-stu-id="5a84d-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>

## <a name="error-while-trying-to-start-a-table-mapping"></a><span data-ttu-id="5a84d-136">Błąd podczas próby uruchomienia mapowania tabeli</span><span class="sxs-lookup"><span data-stu-id="5a84d-136">Error while trying to start a table mapping</span></span>

<span data-ttu-id="5a84d-137">Podczas próby ustawienia tego stanu mapowania na **Uruchomione** może się pojawić komunikat o błędzie podobny do następującego:</span><span class="sxs-lookup"><span data-stu-id="5a84d-137">You might receive an error like the following when you try to set that state of a mapping to **Running**:</span></span>

<span data-ttu-id="5a84d-138">*Nie można ukończyć wstępnej synchronizacji danych. Błąd: błąd podwójnego zapisu — Rejestracja wtyczki nie powiodła się: nie można zbudować metadanych wyszukiwania przy podwójnym zapisie. Odwołanie do obiektu błędu nie jest ustawione na wystąpienie obiektu.*</span><span class="sxs-lookup"><span data-stu-id="5a84d-138">*Unable to complete initial data sync. Error: dual-write failure - plugin registration failed: Unable to build dual-write lookup metadata. Error object reference not set to an instance of an object.*</span></span>

<span data-ttu-id="5a84d-139">Poprawka dla tego błędu jest zależna od przyczyny błędu:</span><span class="sxs-lookup"><span data-stu-id="5a84d-139">The fix for this error depends on the cause of the error:</span></span>

+ <span data-ttu-id="5a84d-140">Jeśli mapowanie ma zależne mapowania, należy pamiętać, aby włączyć mapowania zależne tego mapowania tabeli.</span><span class="sxs-lookup"><span data-stu-id="5a84d-140">If the mapping has dependent mappings, then make sure to enable the dependent mappings of this table mapping.</span></span>
+ <span data-ttu-id="5a84d-141">Być może w mapowaniu brakuje kolumn źródłowych lub docelowych.</span><span class="sxs-lookup"><span data-stu-id="5a84d-141">The mapping might be missing source or destination columns.</span></span> <span data-ttu-id="5a84d-142">Jeśli w aplikacji Finance and Operations nie ma kolumny, należy wykonać kroki w sekcji [Problem związany z brakiem kolumn tabeli na mapach](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps).</span><span class="sxs-lookup"><span data-stu-id="5a84d-142">If a column in the Finance and Operations app is missing, then follow the steps in the section [Missing table columns issue on maps](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps).</span></span> <span data-ttu-id="5a84d-143">Jeśli w usłudze Dataverse brakuje pola, w mapowaniu należy kliknąć przycisk **Odśwież tabele**, tak aby kolumny były automatycznie wstawiane ponownie do mapowania.</span><span class="sxs-lookup"><span data-stu-id="5a84d-143">If a column in Dataverse is missing, then click **Refresh tables** button on the mapping so that the columns are automatically populated back into the mapping.</span></span>
