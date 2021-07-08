---
title: Wprowadzenie do Globalnego księgowania zapasów
description: W tym temacie opisano rozpoczęcie pracy z funkcją Globalnego księgowania zapasów.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 59f9db309312bbbc88b4fa47c12c4c02f09e7c6d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301705"
---
# <a name="get-started-with-global-inventory-accounting"></a><span data-ttu-id="30a06-103">Wprowadzenie do Globalnego księgowania zapasów</span><span class="sxs-lookup"><span data-stu-id="30a06-103">Get started with Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="30a06-104">Globalne księgowanie zapasów pozwala na prowadzenie wielu kont inwentaryzacyjnych w utworzonych Globalnych księgach zapasów.</span><span class="sxs-lookup"><span data-stu-id="30a06-104">Global Inventory Accounting lets you do multiple inventory accountings in the Global Inventory Accounting ledgers that you've set up.</span></span> <span data-ttu-id="30a06-105">Poszczególne księgi Globalnych ksiąg zapasów są kojarzone z *konwencją*.</span><span class="sxs-lookup"><span data-stu-id="30a06-105">You must associate each Global Inventory Accounting ledger with a *convention*.</span></span> <span data-ttu-id="30a06-106">Konwencja jest zbiorem następujących rodzajów zasad (polityki) rachunkowości:</span><span class="sxs-lookup"><span data-stu-id="30a06-106">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="30a06-107">Obiekt kosztów</span><span class="sxs-lookup"><span data-stu-id="30a06-107">Cost object</span></span>
- <span data-ttu-id="30a06-108">Podstawa miary danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="30a06-108">Input measurement basis</span></span>
- <span data-ttu-id="30a06-109">Założenie przepływu kosztów</span><span class="sxs-lookup"><span data-stu-id="30a06-109">Cost flow assumption</span></span>
- <span data-ttu-id="30a06-110">Składnik kosztu</span><span class="sxs-lookup"><span data-stu-id="30a06-110">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="30a06-111">Nawet po włączeniu usługi Globalnych ksiąg zapasów nadal można księgować zapasy w Microsoft Dynamics 365 Supply Chain Management w zwykły sposób.</span><span class="sxs-lookup"><span data-stu-id="30a06-111">Even after you turn on Global Inventory Accounting, you can still do inventory accounting in Microsoft Dynamics 365 Supply Chain Management in the usual way.</span></span>

<span data-ttu-id="30a06-112">Globalne księgowanie zapasów jest dodatkiem.</span><span class="sxs-lookup"><span data-stu-id="30a06-112">Global Inventory Accounting is an add-in.</span></span> <span data-ttu-id="30a06-113">Aby udostępnić swoje funkcje, należy je zainstalować z poziomu Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="30a06-113">To make its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="30a06-114">Można więc ocenić ją w środowisku testowym przed włączeniem go w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="30a06-114">You can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="30a06-115">Funkcja Globalnego księgowania zapasów nie obsługuje obecnie wszystkich funkcji zarządzania kosztami, które są wbudowane w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="30a06-115">Global Inventory Accounting doesn't currently support all the cost management features that are built into Supply Chain Management.</span></span> <span data-ttu-id="30a06-116">Dlatego ważne jest, aby ocenić, czy aktualnie zestaw funkcji jest obecnie dostępny i spełni wymagania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="30a06-116">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a><span data-ttu-id="30a06-117">Jak uzyskać dostęp do publicznej wersji zapoznawczej Globalnego księgowania zapasów</span><span class="sxs-lookup"><span data-stu-id="30a06-117">How to get the Global Inventory Accounting public preview</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30a06-118">Aby korzystać z funkcji Globalnego księgowania zapasów, musisz mieć włączone środowisko usługi LCS o wysokiej dostępności (nie środowisko OneBox).</span><span class="sxs-lookup"><span data-stu-id="30a06-118">To use Global Inventory Accounting, you must have an LCS-enabled high-availability environment (not a OneBox environment).</span></span> <span data-ttu-id="30a06-119">Ponadto trzeba korzystać z Supply Chain Management w wersji 10.0.19 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="30a06-119">Additionally, you must be running Supply Chain Management version 10.0.19 or later.</span></span>

<span data-ttu-id="30a06-120">Aby zarejestrować się w publicznej wersji zapoznawczej Globalnego księgowania zapasów, wyślij identyfikator środowiska usługi LCS pocztą e-mail do [zespołu ds. globalnego księgowania zapasów](mailto:GlobalInventoryAccounting@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="30a06-120">To sign up for the Global Inventory Accounting public preview, send your LCS environment ID by email to the [Global Inventory Accounting team](mailto:GlobalInventoryAccounting@service.microsoft.com).</span></span> <span data-ttu-id="30a06-121">Po zatwierdzeniu do programu, zespół wyśle do Ciebie wiadomość e-mail zawierającą klucz beta funkcji Globalnego księgowania zapasów oraz punkty końcowe usługi.</span><span class="sxs-lookup"><span data-stu-id="30a06-121">After you're approved for the program, the team will send you a follow-up email that contains a Global Inventory Accounting beta key and your service endpoints.</span></span> <span data-ttu-id="30a06-122">Po otrzymaniu klucza wersji beta można [zainstalować ten dodatek](#install).</span><span class="sxs-lookup"><span data-stu-id="30a06-122">After you receive the beta key, you can [install the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="30a06-123">Licencjonowanie</span><span class="sxs-lookup"><span data-stu-id="30a06-123">Licensing</span></span>

<span data-ttu-id="30a06-124">Globalna księga zapasów jest licencjonowana wraz z standardowymi funkcjami księgowania zapasów, które są dostępne dla Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="30a06-124">Global Inventory Accounting is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="30a06-125">Nie trzeba kupować dodatkowej licencji, aby móc skorzystać z usługi Globalnego księgowania zapasów.</span><span class="sxs-lookup"><span data-stu-id="30a06-125">You don't have to purchase an additional license to use Global Inventory Accounting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30a06-126">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="30a06-126">Prerequisites</span></span>

### <a name="set-up-microsoft-power-platform-integration"></a><span data-ttu-id="30a06-127">Ustaw integrację z programem Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="30a06-127">Set up Microsoft Power Platform integration</span></span>

<span data-ttu-id="30a06-128">Aby można było włączyć funkcję dodatku, należy ją zintegrować z Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="30a06-128">Before you can enable add-in functionality, you must integrate with Microsoft Power Platform by following these steps.</span></span>

1. <span data-ttu-id="30a06-129">Otwórz środowisko usługi LCS, w którym chcesz dodać usługę.</span><span class="sxs-lookup"><span data-stu-id="30a06-129">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="30a06-130">Przejdź do **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="30a06-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="30a06-131">Wybierz przycisk **Integracja Power Platform**, a następnie wybierz **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="30a06-131">In the **Power Platform Integration** section, select **Setup**.</span></span>
1. <span data-ttu-id="30a06-132">W oknie dialogowym **Ustawienia środowiska Power platform** zaznacz pole wyboru, a następnie wybierz opcję **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="30a06-132">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="30a06-133">Zwykle konfiguracja trwa od 60 do 90 minut.</span><span class="sxs-lookup"><span data-stu-id="30a06-133">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="30a06-134">Po zakończeniu konfigurowania środowiska Microsoft Power Platform na stronie jest przedstawiana nazwa środowiska.</span><span class="sxs-lookup"><span data-stu-id="30a06-134">After setup of the Microsoft Power Platform environment is completed, the page shows the name of your environment.</span></span> <span data-ttu-id="30a06-135">Ponadto w sekcji **Integracja Power Platform** pokazano oświadczenie, że  „Konfiguracja środowiska Power Platform jest ukończona”.</span><span class="sxs-lookup"><span data-stu-id="30a06-135">Additionally, the **Power Platform Integration** section shows the statement, "Power Platform environment setup is complete."</span></span> <span data-ttu-id="30a06-136">Globalne księgowanie zapasów nie wymaga aplikacji do podwójnego zapisu.</span><span class="sxs-lookup"><span data-stu-id="30a06-136">Global Inventory Accounting doesn't require a dual-write application.</span></span>

<span data-ttu-id="30a06-137">Aby uzyskać więcej informacji, zobacz [Konfiguracja po wdrożeniu środowiska](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span><span class="sxs-lookup"><span data-stu-id="30a06-137">For more information, see [Set up after environment deployment](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span></span>

### <a name="set-up-dataverse"></a><span data-ttu-id="30a06-138">Skonfiguruj Dataverse</span><span class="sxs-lookup"><span data-stu-id="30a06-138">Set up Dataverse</span></span>

<span data-ttu-id="30a06-139">Przed skonfigurowaniem Dataverse dodaj do dzierżawy zasady usługi Globalnego księgowania zapasów, wykonując następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="30a06-139">Before you set up Dataverse, add the Global Inventory Accounting service principles to your tenant by following these steps.</span></span>

1. <span data-ttu-id="30a06-140">Zainstaluj moduł Azure AD w Windows PowerShell v2 zgodnie z opisem w [Zainstaluj Azure Active Directory PowerShell dla programu Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="30a06-140">Install Azure AD Module for Windows PowerShell v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
1. <span data-ttu-id="30a06-141">Uruchom następujące polecenie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30a06-141">Run the following PowerShell command.</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

<span data-ttu-id="30a06-142">Następnie utwórz użytkowników aplikacji Globalnego księgowania zapasów w Dataverse w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="30a06-142">Next, create application users for Global Inventory Accounting in Dataverse by following these steps.</span></span>

1. <span data-ttu-id="30a06-143">Otwórz adres URL środowiska Dataverse.</span><span class="sxs-lookup"><span data-stu-id="30a06-143">Open the URL of your Dataverse environment.</span></span>
1. <span data-ttu-id="30a06-144">Przejdź do **Ustawienia zaawansowane \> System \> Zabezpieczenia \> Użytkownicy** i utwórz użytkownika aplikacji.</span><span class="sxs-lookup"><span data-stu-id="30a06-144">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="30a06-145">Użyj menu **Widok**, aby zmienić widok strony na *Użytkowników aplikacji*.</span><span class="sxs-lookup"><span data-stu-id="30a06-145">Use the **View** field to change the page view to *Application users*.</span></span>
1. <span data-ttu-id="30a06-146">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="30a06-146">Select **New**.</span></span>
1. <span data-ttu-id="30a06-147">Ustaw wartość w polu **Identyfikator aplikacji** na *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span><span class="sxs-lookup"><span data-stu-id="30a06-147">Set the **Application ID** field to *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span></span>
1. <span data-ttu-id="30a06-148">Wybierz pozycję **Przypisz rolę**, a następnie pozycję *Administrator systemu*.</span><span class="sxs-lookup"><span data-stu-id="30a06-148">Select **Assign Role**, and then select *System Administrator*.</span></span> <span data-ttu-id="30a06-149">Jeśli istnieje rola o nazwie *Użytkownik Common Data Service* również ją zaznacz.</span><span class="sxs-lookup"><span data-stu-id="30a06-149">If there is a role that is named *Common Data Service User*, select it too.</span></span>
1. <span data-ttu-id="30a06-150">Powtórz poprzednie kroki, ale ustaw w polu **Identyfikator aplikacji** wartość *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span><span class="sxs-lookup"><span data-stu-id="30a06-150">Repeat the preceding steps, but set the **Application ID** field to *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span></span>

<span data-ttu-id="30a06-151">Aby uzyskać więcej informacji, zobacz [Utwórz użytkownika aplikacji](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="30a06-151">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

<span data-ttu-id="30a06-152">Jeśli domyślnym językiem instalacji Dataverse nie jest język angielski, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="30a06-152">If the default language of your Dataverse installation isn't English, follow these steps.</span></span>

1. <span data-ttu-id="30a06-153">Przejdź do **Ustawienia zaawansowane \> Administracja \> Języki**.</span><span class="sxs-lookup"><span data-stu-id="30a06-153">Go to **Advanced Setting \> Administration \> Languages**.</span></span>
1. <span data-ttu-id="30a06-154">Wybierz *Język angielski* (*LanguageCode=1033*) i wybierz opcję **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="30a06-154">Select *English* (*LanguageCode=1033*), and then select **Apply**.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="30a06-155">Instalacja aplikacji dodatkowych</span><span class="sxs-lookup"><span data-stu-id="30a06-155">Install the add-in</span></span>

<span data-ttu-id="30a06-156">Wykonaj poniższe kroki, aby zainstalować dodatek, który umożliwi korzystanie z programu Globalne księgowanie zapasów.</span><span class="sxs-lookup"><span data-stu-id="30a06-156">Follow these steps to install the add-in so that you can use Global Inventory Accounting.</span></span>

1. <span data-ttu-id="30a06-157">Jak [uzyskać dostęp](#sign-up) do publicznej wersji zapoznawczej Globalnego księgowania zapasów.</span><span class="sxs-lookup"><span data-stu-id="30a06-157">[Sign up](#sign-up) for the Global Inventory Accounting public preview.</span></span>
1. <span data-ttu-id="30a06-158">Zaloguj się w [LCS](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="30a06-158">Sign in to [LCS](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="30a06-159">Przejdź do obszaru **Zarządzanie funkcjami w wersji zapoznawczej**.</span><span class="sxs-lookup"><span data-stu-id="30a06-159">Go to **Preview feature management**.</span></span>
1. <span data-ttu-id="30a06-160">Wybierz znak plus (**+**).</span><span class="sxs-lookup"><span data-stu-id="30a06-160">Select the plus sign (**+**).</span></span>
1. <span data-ttu-id="30a06-161">W polu **Kod** wprowadź swój klucz beta dla usługi Globalnego księgowania zapasów.</span><span class="sxs-lookup"><span data-stu-id="30a06-161">In the **Code** field, enter your add-in beta key for Global Inventory Accounting.</span></span> <span data-ttu-id="30a06-162">(Po zalogowaniu się musisz odbierać klucz wersji beta pocztą e-mail)</span><span class="sxs-lookup"><span data-stu-id="30a06-162">(You should have received your beta key by email when you signed up.)</span></span>
1. <span data-ttu-id="30a06-163">Wybierz opcję **Odblokuj**.</span><span class="sxs-lookup"><span data-stu-id="30a06-163">Select **Unblock**.</span></span>
1. <span data-ttu-id="30a06-164">Otwórz środowisko usługi LCS, w którym chcesz dodać usługę.</span><span class="sxs-lookup"><span data-stu-id="30a06-164">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="30a06-165">Przejdź do **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="30a06-165">Go to **Full details**.</span></span>
1. <span data-ttu-id="30a06-166">Przejdź do **Integracji Power Platform** i wybierz pozycję **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="30a06-166">Go to **Power Platform Integration**, and select **Setup**.</span></span>
1. <span data-ttu-id="30a06-167">W oknie dialogowym **Ustawienia środowiska Power platform** zaznacz pole wyboru, a następnie wybierz opcję **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="30a06-167">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="30a06-168">Zwykle konfiguracja trwa od 60 do 90 minut.</span><span class="sxs-lookup"><span data-stu-id="30a06-168">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="30a06-169">Po zakończeniu konfigurowania środowiska Microsoft Power Platform na skróconej karcie **Dodatki środowiska** wybierz pozycję **Zainstaluj nowy dodatek**.</span><span class="sxs-lookup"><span data-stu-id="30a06-169">After setup of the Microsoft Power Platform environment is completed, on the **Environment add-ins** FastTab, select **Install a new add-in**.</span></span>
1. <span data-ttu-id="30a06-170">Wybierz **Globalne księgowanie zapasów**.</span><span class="sxs-lookup"><span data-stu-id="30a06-170">Select **Global inventory accounting**.</span></span>
1. <span data-ttu-id="30a06-171">Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.</span><span class="sxs-lookup"><span data-stu-id="30a06-171">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="30a06-172">Wybierz **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="30a06-172">Select **Install**.</span></span>
1. <span data-ttu-id="30a06-173">Na skróconej karcie **Dodatki środowiska** należy sprawdzić, czy jest instalowana usługa Globalnego księgowania zapasów.</span><span class="sxs-lookup"><span data-stu-id="30a06-173">On the **Environment add-ins** FastTab, you should see that Global Inventory Accounting is being installed.</span></span> <span data-ttu-id="30a06-174">Po kilku minutach stan powinien ulec zmianie z *Instalowane* na *Zainstalowane*.</span><span class="sxs-lookup"><span data-stu-id="30a06-174">After a few minutes, the status should change from *Installing* to *Installed*.</span></span> <span data-ttu-id="30a06-175">(Aby zobaczyć tę zmianę, konieczne może być odświeżenie strony.) W tym momencie Globalnego księgowania zapasów jest gotowa do użycia.</span><span class="sxs-lookup"><span data-stu-id="30a06-175">(You might have to refresh the page to see this change.) At that point, Global Inventory Accounting is ready to use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="30a06-176">Konfiguracja integracji</span><span class="sxs-lookup"><span data-stu-id="30a06-176">Set up the integration</span></span>

<span data-ttu-id="30a06-177">Wykonaj poniższe kroki, aby skonfigurować integrację pomiędzy programem Globalnego księgowania zapasów i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="30a06-177">Follow these steps to set up the integration between Global Inventory Accounting and Supply Chain Management.</span></span>

1. <span data-ttu-id="30a06-178">Zaloguj się do modułu Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="30a06-178">Sign in to Supply Chain Management.</span></span>
1. <span data-ttu-id="30a06-179">Wybierz kolejno opcje **Administrowanie systemem \> Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="30a06-179">Go to **System administration \> Feature Management**.</span></span>
1. <span data-ttu-id="30a06-180">Wybierz **Sprawdź, czy są aktualizacje**.</span><span class="sxs-lookup"><span data-stu-id="30a06-180">Select **Check for updates**.</span></span>
1. <span data-ttu-id="30a06-181">Na karcie **Wszystkie** wyszukaj funkcję o nazwie *Globalne księgowanie zapasów*.</span><span class="sxs-lookup"><span data-stu-id="30a06-181">On the **All** tab, search for the feature that is named *Global inventory accounting*.</span></span>
1. <span data-ttu-id="30a06-182">Wybierz **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="30a06-182">Select **Enable now**.</span></span>
1. <span data-ttu-id="30a06-183">Przejdź do strony **Globalne księgowanie zapasów \> Konfiguracja \> Parametry globalnego księgowania zapasów \> Parametry integracji**.</span><span class="sxs-lookup"><span data-stu-id="30a06-183">Go to **Global inventory accounting \> Setup \> Global inventory accounting parameters \> Integrations parameters**.</span></span>
1. <span data-ttu-id="30a06-184">W polach **Punkt końcowy usługi danych** i **Punkt końcowy globalnego księgowania zapasów** należy wpisać adresy URL z wiadomości e-mail, którą zespół ds. globalnego księgowania zapasów wysłał po zapisaniu się do podglądu.</span><span class="sxs-lookup"><span data-stu-id="30a06-184">In the **Data service endpoint** and **Global inventory accounting endpoint** fields, enter the URLs from the email that the Global Inventory Accounting team sent when you signed up for the preview.</span></span>

<span data-ttu-id="30a06-185">Globalne księgowanie zapasów jest gotowe do użycia.</span><span class="sxs-lookup"><span data-stu-id="30a06-185">Global Inventory Accounting is now ready to use.</span></span>
