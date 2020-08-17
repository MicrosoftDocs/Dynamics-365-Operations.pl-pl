---
title: Włącz uwierzytelnianie Azure Active Directory w celu autoryzacji w punkcie sprzedaży
description: W tym temacie wyjaśniono, jak skonfigurować środowisko logowania w punkcie sprzedaży dla rozwiązania Microsoft Dynamics 365 Commerce, aby korzystało z uwierzytelniania Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: ccb2d62b09153d03b064d9661227f3499d67bca2
ms.sourcegitcommit: dc1dcd0ccc40be5d45701114fa8c952c13488344
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/30/2020
ms.locfileid: "3641040"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a><span data-ttu-id="cdec6-103">Włącz uwierzytelnianie Azure Active Directory w celu autoryzacji w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="cdec6-103">Enable Azure Active Directory authentication for POS sign-in</span></span>
[!include [banner](includes/banner.md)]


<span data-ttu-id="cdec6-104">Wielu klientów korzystających z rozwiązania Microsoft Dynamics 365 Commerce używa również innych usług firmy Microsoft w chmurze, a także Azure Active Directory (Azure AD), które mogą służyć do zarządzania poświadczeniami użytkowników tych usług.</span><span class="sxs-lookup"><span data-stu-id="cdec6-104">Many customers who use Microsoft Dynamics 365 Commerce also use other Microsoft cloud services, and they might use Azure Active Directory (Azure AD) to manage user credentials for those services.</span></span> <span data-ttu-id="cdec6-105">W takich przypadkach klienci mogą chcieć używać tego samego konta Azure AD w różnych aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="cdec6-105">In those cases, the customers might want to use the same Azure AD account across applications.</span></span> <span data-ttu-id="cdec6-106">W tym temacie wyjaśniono, jak skonfigurować środowisko logowania w punkcie sprzedaży dla rozwiązania Commerce , aby korzystało z uwierzytelniania Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cdec6-106">This topic explains how to configure the Commerce point of sale (POS) sign-in experience to use Azure AD authentication.</span></span>

## <a name="configure-azure-ad-authentication"></a><span data-ttu-id="cdec6-107">Konfigurowanie dostawców uwierzytelniania Azure AD</span><span class="sxs-lookup"><span data-stu-id="cdec6-107">Configure Azure AD authentication</span></span>

<span data-ttu-id="cdec6-108">Aby udostępnić metodę logowania Azure AD w punkcie sprzedaży dla sklepu, należy skonfigurować ustawienia profilu funkcji sklepu, a następnie zastosować te ustawienia dla klientów punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cdec6-108">To make Azure AD available as the authentication method for POS sign-in for a store, you must configure the settings of the store's functionality profile and then apply those setting to POS clients.</span></span>

<span data-ttu-id="cdec6-109">Aby skonfigurować profil funkcji, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="cdec6-109">To configure a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="cdec6-110">Wybierz kolejno opcje **Handel detaliczny i inny** \> **Ustawienia kanału** \> **Ustawienia punktu sprzedaży** \> **Profile punktów sprzedaży** \> **Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="cdec6-110">Go to **Retail and Commerce** \> **Channel setup** \> **POS setup** \> **POS profiles** \> **Functionality profiles**.</span></span>
1. <span data-ttu-id="cdec6-111">Wybierz profil funkcji, który ma zostać zmieniony.</span><span class="sxs-lookup"><span data-stu-id="cdec6-111">Select the functionality profile to change.</span></span>
1. <span data-ttu-id="cdec6-112">W skróconej karcie **funkcje** w sekcji **logowanie pracowników punktu sprzedaży** Zmień wartość w polu **Metoda uwierzytelniania logowania** z **identyfikator pracownika i hasło** na **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="cdec6-112">On the **Functions** FastTab, in the **POS staff logon** section, change the value of the **Logon Authentication Method** field from **Personnel ID and Password** to **Azure Active Directory**.</span></span>

<span data-ttu-id="cdec6-113">Domyślnie wszystkie profile funkcji używają **identyfikatora pracownika i hasła** jako metody uwierzytelniania w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cdec6-113">By default, all functionality profiles use **Personnel ID and Password** as the POS authentication method.</span></span> <span data-ttu-id="cdec6-114">Dlatego też należy zmienić wartość pola **metoda uwierzytelnienia logowania**, jeśli ma używać Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cdec6-114">Therefore, you must change the value of the **Logon Authentication Method** field if you want to use Azure AD.</span></span> <span data-ttu-id="cdec6-115">Ta zmiana będzie miała wpływ na każdy sklep detaliczny połączony z wybranym profilem funkcji.</span><span class="sxs-lookup"><span data-stu-id="cdec6-115">Every retail store that is linked to the selected functionality profile will be affected by this change.</span></span>

<span data-ttu-id="cdec6-116">Aby zastosować ustawienia do klientów punktu sprzedaży, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="cdec6-116">To apply the settings to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="cdec6-117">Wybierz kolejno opcje **Handel detaliczny i inny** \> **Dane IT sprzedaży** \> **Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="cdec6-117">Go to **Retail and Commerce** \> **Retail and Commerce IT** \> **Distribution schedule**.</span></span>
1. <span data-ttu-id="cdec6-118">Uruchom harmonogram dystrybucji **1070** (**Konfiguracja kanału**).</span><span class="sxs-lookup"><span data-stu-id="cdec6-118">Run the **1070** (**Channel configuration**) distribution schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="cdec6-119">Uwierzytelnianie Azure AD wymaga połączenia z Internetem.</span><span class="sxs-lookup"><span data-stu-id="cdec6-119">Azure AD authentication requires an internet connection.</span></span> <span data-ttu-id="cdec6-120">Nie będzie działać, gdy punkt sprzedaży jest w trybie offline.</span><span class="sxs-lookup"><span data-stu-id="cdec6-120">It won't work when POS is in offline mode.</span></span>
> 
> <span data-ttu-id="cdec6-121">Obecnie funkcja **Zastąpienie przez menedżera** nie obsługuje Azure AD jako metody uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="cdec6-121">Currently, the **Manager override** function doesn't support Azure AD as an authentication method.</span></span> <span data-ttu-id="cdec6-122">Identyfikator operatora i hasło są wymagane nawet wtedy, gdy Azure AD jest skonfigurowany jako metoda uwierzytelniania w celu zalogowania się w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="cdec6-122">An operator ID and password are required even if Azure AD is configured as the authentication method for POS sign-in.</span></span>

## <a name="associate-an-azure-ad-account-with-a-worker"></a><span data-ttu-id="cdec6-123">Skojarz konto Azure AD z pracownikiem</span><span class="sxs-lookup"><span data-stu-id="cdec6-123">Associate an Azure AD account with a worker</span></span>

<span data-ttu-id="cdec6-124">Aby pracownik sklepu mógł skorzystać z konta Azure AD w celu zalogowania się do aplikacji punktu sprzedaży, konto Azure AD musi być skojarzone z tym pracownikiem.</span><span class="sxs-lookup"><span data-stu-id="cdec6-124">Before a store worker can use an Azure AD account to sign in to the POS application, the Azure AD account must be associated with that worker.</span></span>

<span data-ttu-id="cdec6-125">Aby skojarzyć konto Azure AD z pracownikiem, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="cdec6-125">To associate an Azure AD account with a worker, follow these steps.</span></span>

1. <span data-ttu-id="cdec6-126">Wybierz kolejno opcje **Handel detaliczny i inny** \> **Pracownicy** \> **Wszyscy pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="cdec6-126">Go to **Retail and Commerce** \> **Employees** \> **Workers**.</span></span>
1. <span data-ttu-id="cdec6-127">Otwórz stronę szczegółów pracownika.</span><span class="sxs-lookup"><span data-stu-id="cdec6-127">Open the details page for a worker.</span></span>
1. <span data-ttu-id="cdec6-128">Następnie w okienku akcji na karcie **Commerce** w grupie **Tożsamość zewnętrzna** wybierz opcję **Powiązanie istniejącej tożsamości**.</span><span class="sxs-lookup"><span data-stu-id="cdec6-128">On the Action Pane, on the **Commerce** tab, in the **External identity** group, select **Associate existing identity**.</span></span>
1. <span data-ttu-id="cdec6-129">W oknie dialogowym **używanie istniejącej tożsamości zewnętrznej** wybierz opcję **Wyszukaj przy użyciu poczty e-mail**, wprowadź adres e-mail Azure AD, a następnie wybierz opcję **Szukaj**.</span><span class="sxs-lookup"><span data-stu-id="cdec6-129">In the **Use existing external identity** dialog box, select **Search using email**, enter an Azure AD email address, and then select **Search**.</span></span>
1. <span data-ttu-id="cdec6-130">Wybierz konto Azure AD, które jest zwracane, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdec6-130">Select the Azure AD account that is returned, and then select **OK**.</span></span>

<span data-ttu-id="cdec6-131">Pola **alias**, **nazwa UPN** i **zewnętrzny identyfikator podrzędny** na karcie **Commerce** na stronie Szczegóły pracownika zostaną wypełnione.</span><span class="sxs-lookup"><span data-stu-id="cdec6-131">The **Alias**, **UPN**, and **External sub identifier** fields on the **Commerce** tab of the worker's details page will be filled in.</span></span>

> [!NOTE]
> <span data-ttu-id="cdec6-132">Po zaktualizowaniu rekordu pracownika, na przykład w przypadku skojarzenia nowego konta Azure AD, zmiany hasła lub aktualizacji książki adresowej pracownika, zaleca się uruchomienie harmonogramu dystrybucji **1060** (**Pracownicy**) w celu zsynchronizowania najnowszych informacji o pracownikach z kanałem.</span><span class="sxs-lookup"><span data-stu-id="cdec6-132">After a worker record is updated, for example if a new Azure AD account is associated, a password is changed, or an employee address book is updated, it’s recommended that you run **1060** (**Staff**) distribution schedule to synchronize the latest staff information to the channel.</span></span> <span data-ttu-id="cdec6-133">Dzięki temu aplikacja punktu sprzedaży może pobierać poprawne dane na potrzeby sprawdzania uwierzytelniania i autoryzacji użytkowników.</span><span class="sxs-lookup"><span data-stu-id="cdec6-133">That way, the POS application can fetch the correct data for user authentication and authorization check.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cdec6-134">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cdec6-134">Additional resources</span></span>

[<span data-ttu-id="cdec6-135">Konfigurowanie funkcjonalności logowania rozszerzonego w aplikacjach MPOS i Cloud POS</span><span class="sxs-lookup"><span data-stu-id="cdec6-135">Set up extended logon functionality for MPOS and Cloud POS</span></span>](extended-logon.md)

[<span data-ttu-id="cdec6-136">Tworzenie profilu funkcji handlu detalicznego</span><span class="sxs-lookup"><span data-stu-id="cdec6-136">Create a retail functionality profile</span></span>](retail-functionality-profile.md)

[<span data-ttu-id="cdec6-137">Konfigurowanie pracownika</span><span class="sxs-lookup"><span data-stu-id="cdec6-137">Configure a worker</span></span>](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)
