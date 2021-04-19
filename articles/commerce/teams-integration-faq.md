---
title: Integracja z usługami Dynamics 365 Commerce i Microsoft Teams — często zadawane pytania
description: Ten temat zawiera odpowiedzi dotyczące często zadawanych pytań dotyczących integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 26e1dc53126c0615332457aa785415c4c7112bbd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842728"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a><span data-ttu-id="2fc18-103">Integracja z usługami Dynamics 365 Commerce i Microsoft Teams — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="2fc18-103">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="2fc18-104">Ten temat zawiera odpowiedzi dotyczące często zadawanych pytań dotyczących integracji Microsoft Dynamics 365 Commerce i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2fc18-104">This topic provides answers to frequently asked questions regarding Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a><span data-ttu-id="2fc18-105">Kto w sklepie staje się właścicielem zespołu podczas inicjowania obsługi Teams z usług Commerce?</span><span class="sxs-lookup"><span data-stu-id="2fc18-105">Who in the store becomes an owner of a team while provisioning Teams from Commerce?</span></span> 

<span data-ttu-id="2fc18-106">Wszyscy menedżerowie sklepu są automatycznie dodawana jako właściciele do odpowiedniej grupy grupę kierownicy, co oznacza, że mogą wykonywać takie operacje, jak dodawanie kanału prywatnego oraz dodawanie lub usuwanie członków.</span><span class="sxs-lookup"><span data-stu-id="2fc18-106">All store managers are automatically added as owners to the corresponding team group so that they can perform operations such as adding a private channel and adding or deleting members.</span></span> 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a><span data-ttu-id="2fc18-107">Jak przypisać rolę „kierownik ds. komunikacji” do pracownika e-mail w Commerce headquarters?</span><span class="sxs-lookup"><span data-stu-id="2fc18-107">How do I assign the "communications manager" role to an employee in Commerce headquarters?</span></span> 

<span data-ttu-id="2fc18-108">Kierownicy ds. komunikacji w Microsoft Teams mogą tworzyć i publikować listy zadań.</span><span class="sxs-lookup"><span data-stu-id="2fc18-108">Communication managers in Microsoft Teams have the ability to create and publish task lists.</span></span> <span data-ttu-id="2fc18-109">Pracownicy organizacji, którzy muszą zostać menedżerami komunikacji, muszą mieć przypisaną rolę „kierownik ds. zadań sieci sprzedaży” w programie Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="2fc18-109">Organization employees who need to become communication managers must have the "retail task manager" role assigned to them in Commerce headquarters.</span></span>

<span data-ttu-id="2fc18-110">Aby przypisać rolę menedżera zadań sieci sprzedaży do pracownika w programie Commerce Headquarters, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2fc18-110">To assign the retail task manager role to an employee in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="2fc18-111">Wybierz kolejno opcje **Retail and Commerce \> Pracownicy \> Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="2fc18-111">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="2fc18-112">Wybierz pracownika.</span><span class="sxs-lookup"><span data-stu-id="2fc18-112">Select an employee.</span></span>
1. <span data-ttu-id="2fc18-113">Na karcie skróconej **Role użytkownika** wybierz opcję **Przypisz role**.</span><span class="sxs-lookup"><span data-stu-id="2fc18-113">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="2fc18-114">W oknie dialogowym **Przypisz role do użytkownika** wybierz rolę **Menedżer zadań sieci sprzedaży**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2fc18-114">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a><span data-ttu-id="2fc18-115">Jak udostępnić do przekazania do Microsoft Teams określoną hierarchię organizacyjną?</span><span class="sxs-lookup"><span data-stu-id="2fc18-115">How do I make a specific organization hierarchy available to upload into Microsoft Teams?</span></span>

<span data-ttu-id="2fc18-116">W programie Commerce Headquarters hierarchia każdej organizacji jest skojarzona z jednym lub większą ich celem.</span><span class="sxs-lookup"><span data-stu-id="2fc18-116">In Commerce headquarters, every organization's hierarchy is associated with one or more purposes.</span></span> <span data-ttu-id="2fc18-117">Upewnij się, że z hierarchią, w której mają być obsługiwane usługi Microsoft Teams, jest skojarzony cel **Raportowania sieci sprzedaży**, tak jak pokazano na poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="2fc18-117">Make sure the hierarchy that you want to provision into Microsoft Teams has the **Retail reporting** purpose associated with it, as shown in the following example image.</span></span> 

![Przykład celu hierarchii organizacyjnej w programie Commerce Headquarters](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a><span data-ttu-id="2fc18-119">Jak umożliwić pracownikom sklepu detalicznego logowanie się do usługi Commerce punkt sprzedaży (POS) przy użyciu Azure Active Directory (Azure AD)?</span><span class="sxs-lookup"><span data-stu-id="2fc18-119">How do I enable retail store workers to sign in to Commerce point of sale (POS) using Azure Active Directory (Azure AD)?</span></span>

<span data-ttu-id="2fc18-120">Aby uzyskać informacje dotyczące konfigurowania funkcji logowania w programie Commerce POS do używania uwierzytelniania Azure AD, zobacz temat [Włączanie uwierzytelniania Azure Active Directory przy loganiu się do POS](aad-pos-logon.md)..</span><span class="sxs-lookup"><span data-stu-id="2fc18-120">For information about how to configure the Commerce POS sign-in experience to use Azure AD authentication, see [Enable Azure Active Directory authentication for POS sign-in](aad-pos-logon.md).</span></span>

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a><span data-ttu-id="2fc18-121">Jak mapować sklepy i odpowiadające im zespoły w programie Commerce Headquarters, jeśli w programie Commerce Headquarters moja organizacja utworzyła już zespoły Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2fc18-121">How do I map stores and corresponding teams in Commerce headquarters if my organization has already created teams in Microsoft Teams?</span></span>

<span data-ttu-id="2fc18-122">Aby uzyskać informacje dotyczące mapowania sklepów i zespołów na istniejące zespoły, zobacz temat [Mapowanie sklepów i odpowiednich zespołów, jeśli organizacja ma już istniejące zespoły w Microsoft Teams](map-stores-existing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2fc18-122">For information on how to map stores and teams if there are pre-existing teams, see [Map stores and corresponding teams if your organization has pre-existing teams in Microsoft Teams](map-stores-existing-teams.md).</span></span>

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a><span data-ttu-id="2fc18-123">Jak wyczyścić token interfejsu API programu Microsoft Graph przechowywany w magazynie sesji?</span><span class="sxs-lookup"><span data-stu-id="2fc18-123">How do I clear the Microsoft Graph API token stored in the session storage?</span></span>

<span data-ttu-id="2fc18-124">Użytkownik, który zalogował się do punktu sprzedaży (POS) za pomocą konta Azure Active Directory (Azure AD), powinien wylogować się z punktu sprzedaży lub zamknąć aplikację, aby wyczyścić magazyn sesji.</span><span class="sxs-lookup"><span data-stu-id="2fc18-124">A user who has signed in to the point of sale (POS) with an Azure Active Directory (Azure AD) account should sign out from the POS or close the application to clear the session storage.</span></span> 

> [!TIP]
> <span data-ttu-id="2fc18-125">Zaleca się, aby pracownicy sklepu zawsze zablokowali terminal w aplikacji pos lub wylogowywają się z sesji, gdy terminal nie jest używany.</span><span class="sxs-lookup"><span data-stu-id="2fc18-125">A recommended best practice is to always have store workers lock the POS terminal or sign out from a session when not using the terminal.</span></span> 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a><span data-ttu-id="2fc18-126">Co się stanie, jeśli sklep nie ma kierowników sklepu?</span><span class="sxs-lookup"><span data-stu-id="2fc18-126">What happens if a store doesn't have store managers?</span></span>

<span data-ttu-id="2fc18-127">Jeśli sklep nie ma menedżerów, grupa zespołu nie zostanie utworzona dla sklepu ani w aplikacji Teams.</span><span class="sxs-lookup"><span data-stu-id="2fc18-127">If a store doesn't have managers, a team group will not be created for the store or in Teams.</span></span> 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a><span data-ttu-id="2fc18-128">Co się stanie, gdy kierownik sklepu opuści firmę?</span><span class="sxs-lookup"><span data-stu-id="2fc18-128">What happens if a store manager leaves the company?</span></span>

<span data-ttu-id="2fc18-129">Każdy, kto ma rolę właściciela, może dodać nowego kierownika sklepu w centrali Commerce i ponownie udostępnić zespoły, aby nowy menedżer miał niezbędne uprawnienia w usłudze Teams dla grupy.</span><span class="sxs-lookup"><span data-stu-id="2fc18-129">Anyone with the owner role can add a new store manager in Commerce headquarters and reprovision Teams so that the new manager will have the necessary privileges in Teams for the group.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="2fc18-130">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2fc18-130">Additional resources</span></span>

[<span data-ttu-id="2fc18-131">Omówienie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2fc18-131">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="2fc18-132">Włączanie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2fc18-132">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="2fc18-133">Obsługa Microsoft Teams z Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2fc18-133">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="2fc18-134">Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="2fc18-134">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="2fc18-135">Zarządzanie rolami użytkowników w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2fc18-135">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="2fc18-136">Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2fc18-136">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)
