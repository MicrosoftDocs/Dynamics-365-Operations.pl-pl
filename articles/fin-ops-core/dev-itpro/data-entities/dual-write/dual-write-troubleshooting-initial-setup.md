---
title: Rozwiązywanie problemów podczas konfiguracji początkowej
description: Ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas integracji podwójnego zapisu.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9ffb1378eccf175fbb9bd84228f91ba606125a63
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753997"
---
# <a name="troubleshoot-issues-during-initial-setup"></a><span data-ttu-id="9c5da-103">Rozwiązywanie problemów podczas konfiguracji początkowej</span><span class="sxs-lookup"><span data-stu-id="9c5da-103">Troubleshoot issues during initial setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="9c5da-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9c5da-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="9c5da-105">A dokładniej, ten temat zawiera informacje ułatwiające rozwiązywanie problemów, które mogą wystąpić podczas integracji podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="9c5da-105">Specifically, it provides information that can help you fix issues that might occur during the initial setup of dual-write integration.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c5da-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9c5da-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="9c5da-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="9c5da-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a><span data-ttu-id="9c5da-108">Nie można połączyć aplikacji Finance and Operations z Dataverse</span><span class="sxs-lookup"><span data-stu-id="9c5da-108">You can't link a Finance and Operations app to Dataverse</span></span>

<span data-ttu-id="9c5da-109">**Wymagana rola w celu konfiguracji podwójnego zapisu:** administrator systemu w aplikacjach Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9c5da-109">**Required role to set up dual-write:** System administrator in Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="9c5da-110">Błędy na stronie **Łącze konfiguracji do Dataverse** są zazwyczaj spowodowane niekompletnymi problemami z ustawieniami lub uprawnieniami.</span><span class="sxs-lookup"><span data-stu-id="9c5da-110">Errors on the **Setup link to Dataverse** page are usually caused by incomplete setup or permissions issues.</span></span> <span data-ttu-id="9c5da-111">Upewnij się, że cała kontrola kondycji jest przekazana na stronie **Łącze konfiguracji do Dataverse**, jak to pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="9c5da-111">Make sure that the whole health check passes on the **Setup link to Dataverse** page, as shown in the following illustration.</span></span> <span data-ttu-id="9c5da-112">Nie można połączyć się z podwójnym zapisywaniem, dopóki nie przejdzie cała kontrola kondycji.</span><span class="sxs-lookup"><span data-stu-id="9c5da-112">You can't link dual-write unless the whole health check passes.</span></span>

![Pomyślne sprawdzenie kondycji](media/health_check.png)

<span data-ttu-id="9c5da-114">Aby połączyć środowiska Finance and Operations i Dataverse, trzeba mieć poświadczenia administratora dzierżawy Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9c5da-114">You must have Azure AD tenant admin credentials to link the Finance and Operations and Dataverse environments.</span></span> <span data-ttu-id="9c5da-115">Po połączeniu środowiska użytkownicy mogą się logować przy użyciu swoich poświadczeń konta i aktualizować istniejące mapowanie tabeli.</span><span class="sxs-lookup"><span data-stu-id="9c5da-115">After you link the environments, users can sign in by using their account credentials and update an existing table map.</span></span>

## <a name="error-when-you-open-the-link-to-dataverse-page"></a><span data-ttu-id="9c5da-116">Błąd podczas otwierania łącza do strony Dataverse</span><span class="sxs-lookup"><span data-stu-id="9c5da-116">Error when you open the Link to Dataverse page</span></span>

<span data-ttu-id="9c5da-117">**Wymagane poświadczenia w celu rozwiązania problemu:** administrator dzierżawy Azure AD</span><span class="sxs-lookup"><span data-stu-id="9c5da-117">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="9c5da-118">Może pojawić się następujący komunikat o błędzie podczas otwierania strony **Łącze do Dataverse** w aplikacji Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="9c5da-118">You might receive the following error message when you open the **Link to Dataverse** page in a Finance and Operations app:</span></span>

<span data-ttu-id="9c5da-119">*Kod stanu odpowiedzi nie wskazuje powodzenia: 404 (Nie znaleziono).*</span><span class="sxs-lookup"><span data-stu-id="9c5da-119">*Response status code does not indicate success: 404 (Not Found).*</span></span>

<span data-ttu-id="9c5da-120">Ten błąd występuje, gdy krok zgody nie został ukończony.</span><span class="sxs-lookup"><span data-stu-id="9c5da-120">This error occurs when the consent step hasn't been completed.</span></span> <span data-ttu-id="9c5da-121">Aby sprawdzić, czy krok zgody został zakończony, zaloguj się do portal.Azure.com przy użyciu konta administratora dzierżawy Azure AD i sprawdź, czy strona trzecia o identyfikatorze **33976c19-1db5-4c02-810e-c243db79efde** jest na liście w Azure AD **Aplikacji przedsiębiorstwa**.</span><span class="sxs-lookup"><span data-stu-id="9c5da-121">To validate whether the consent step has been completed, sign in to portal.Azure.com by using the Azure AD tenant admin account, and see whether the third-party app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** appears in the Azure AD **Enterprise applications** list.</span></span> <span data-ttu-id="9c5da-122">Jeśli nie, musisz podać zgodę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9c5da-122">If it doesn't, you must provide app consent.</span></span>

<span data-ttu-id="9c5da-123">Aby zapewnić zgodę aplikacji, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="9c5da-123">To provide app consent, follow these steps.</span></span>

1. <span data-ttu-id="9c5da-124">Otwórz następujący adres URL, używając poświadczeń administratora.</span><span class="sxs-lookup"><span data-stu-id="9c5da-124">Open the following URL by using your admin credentials.</span></span> <span data-ttu-id="9c5da-125">Powinien zostać wyświetlony monit o zgodę.</span><span class="sxs-lookup"><span data-stu-id="9c5da-125">You should be prompted for consent.</span></span>

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. <span data-ttu-id="9c5da-126">Wybierz przycisk **Akceptuj**, aby wskazać, że wyrażasz zgodę na zainstalowanie aplikacji o identyfikatorze **33976c19-1db5-4c02-810e-c243db79efde** w dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="9c5da-126">Select **Accept** to indicate that you're giving your consent to install the app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** in your tenant.</span></span>

    > [!TIP]
    > <span data-ttu-id="9c5da-127">Ta aplikacja jest wymagana do łączenia Dataverse i aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9c5da-127">This app is required to link Dataverse and Finance and Operations apps.</span></span> <span data-ttu-id="9c5da-128">Jeśli występują problemy z tym krokiem, należy otworzyć przeglądarkę w trybie incognito (w usłudze Google Chrome) lub w trybie InPrivate ( w Microsoft Edge).</span><span class="sxs-lookup"><span data-stu-id="9c5da-128">If you have trouble with this step, open your browser in incognito mode (in Google Chrome) or InPrivate mode (in Microsoft Edge).</span></span>

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a><span data-ttu-id="9c5da-129">Sprawdź, czy dane firmy i zespoły podwójnego zapisywania są poprawnie skonfigurowane podczas łączenia</span><span class="sxs-lookup"><span data-stu-id="9c5da-129">Verify that company data and dual-write teams are set up correctly during linking</span></span>

<span data-ttu-id="9c5da-130">Aby zapewnić poprawne działanie funkcji podwójnego zapisywania, w środowisku Dataverse zostaną utworzone firmy wybrane podczas konfigurowania.</span><span class="sxs-lookup"><span data-stu-id="9c5da-130">To ensure that dual-write works correctly, the companies that you select during configuration are created in the Dataverse environment.</span></span> <span data-ttu-id="9c5da-131">Domyślnie te firmy są tylko do odczytu, a właściwość **IsDualWriteEnable** ma wartość **prawda**.</span><span class="sxs-lookup"><span data-stu-id="9c5da-131">By default, these companies are read-only, and the **IsDualWriteEnable** property is set to **True**.</span></span> <span data-ttu-id="9c5da-132">Ponadto tworzony jest domyślny właściciel i zespół jednostki biznesowej będący właścicielem, który zawiera nazwę firmy.</span><span class="sxs-lookup"><span data-stu-id="9c5da-132">In addition, the default owning business unit owner and team are created and include the company name.</span></span> <span data-ttu-id="9c5da-133">Przed włączeniem map należy sprawdzić, czy jest określony domyślny właściciel zespołu.</span><span class="sxs-lookup"><span data-stu-id="9c5da-133">Before you enable the maps, verify that the default team owner is specified.</span></span> <span data-ttu-id="9c5da-134">Aby znaleźć tabelę **firmy (CDM\_Company)**, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="9c5da-134">To find the **Companies (CDM\_Company)** table, follow these steps.</span></span>

1. <span data-ttu-id="9c5da-135">W aplikacji opartej na modelu w Dynamics 365 wybierz filtr w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="9c5da-135">In the model-driven app in Dynamics 365, select the filter in the upper-right corner.</span></span>
2. <span data-ttu-id="9c5da-136">Z listy rozwijanej wybierz **Firma**.</span><span class="sxs-lookup"><span data-stu-id="9c5da-136">In the drop-down list, select **Company**.</span></span>
3. <span data-ttu-id="9c5da-137">Wybierz opcję **Uruchom**, aby zobaczyć wyniki.</span><span class="sxs-lookup"><span data-stu-id="9c5da-137">Select **Run** to see the results.</span></span>
4. <span data-ttu-id="9c5da-138">Umożliwia wybór firmy połączonej w przypadku skonfigurowania podwójnego zapisywania.</span><span class="sxs-lookup"><span data-stu-id="9c5da-138">Select the company that was linked when you configured dual-write.</span></span>
5. <span data-ttu-id="9c5da-139">Sprawdź, czy w kolumnie **Domyślnego zespołu będącego właścicielem** znajduje się wartość.</span><span class="sxs-lookup"><span data-stu-id="9c5da-139">Verify that the **Default owning team** column has a value.</span></span> <span data-ttu-id="9c5da-140">Na poniższej ilustracji kolumna **Domyślny zespół będący właścicielem** jest ustawiona na **USMF podwójnego zapisywania**.</span><span class="sxs-lookup"><span data-stu-id="9c5da-140">In the following illustration, the **Default owning team** column is set to **USMF Dual Write**.</span></span>

    ![Weryfikowanie domyślnego zespołu będącego właścicielem](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a><span data-ttu-id="9c5da-142">Umożliwia znalezienie limitu liczby tabel prawnych lub firm, które mogą być połączone w celu wykonania podwójnego odpisu</span><span class="sxs-lookup"><span data-stu-id="9c5da-142">Find the limit on the number of legal tables or companies that can be linked for dual-write</span></span>

<span data-ttu-id="9c5da-143">Podczas próby włączenia map może pojawić się następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="9c5da-143">You might receive the following error message when you try to enable maps:</span></span>

<span data-ttu-id="9c5da-144">*Błąd podwójnego zapisywania — Rejestracja wtyczki nie powiodła się: \[(nie można uzyskać mapy partycji Menedżera okien pulpitu-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Błąd przekracza maksymalną liczbę partycji dozwoloną w mapowaniu Menedżera okien pulpitu-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\]. Wystąpił co najmniej jeden błąd.*</span><span class="sxs-lookup"><span data-stu-id="9c5da-144">*Dual write failure - Plugin registration failed: \[(Unable to get partition map for project DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Error Exceeds the maximum partitions allowed for mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], One or more errors occurred.*</span></span>

<span data-ttu-id="9c5da-145">Bieżący limit czasu połączenia ze środowiskiem wynosi około 40 tabel prawnych.</span><span class="sxs-lookup"><span data-stu-id="9c5da-145">The current limit when you link the environments is approximately 40 legal tables.</span></span> <span data-ttu-id="9c5da-146">Ten błąd występuje podczas próby włączenia map, a więcej niż 40 tabel prawnych jest połączonych między środowiskami.</span><span class="sxs-lookup"><span data-stu-id="9c5da-146">This error occurs if you try to enable maps, and more than 40 legal tables are linked between the environments.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]