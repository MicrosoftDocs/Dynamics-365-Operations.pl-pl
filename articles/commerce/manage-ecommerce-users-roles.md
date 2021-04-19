---
title: Zarządzanie użytkownikami i rolami e-Commerce
description: W tym temacie opisano sposób udzielania użytkownikom dostępu do środowiska tworzenia witryny Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 44b02f262136c0d970ca9eee3e5e63ef6dc8ccb7
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794290"
---
# <a name="manage-e-commerce-users-and-roles"></a><span data-ttu-id="3d32d-103">Zarządzanie użytkownikami i rolami e-Commerce</span><span class="sxs-lookup"><span data-stu-id="3d32d-103">Manage e-Commerce users and roles</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3d32d-104">W tym temacie opisano sposób udzielania użytkownikom dostępu do środowiska tworzenia witryny Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3d32d-104">This topic explains how to grant users access to the authoring environment for your Microsoft Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="3d32d-105">Aby ułatwić kontrolowanie dostępu użytkowników i przyznawanie użytkownikom uprawnień do wykonywania konkretnych zadań, środowisko tworzenia witryn używa grup zabezpieczeń utworzonych w Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3d32d-105">To help control user access and grant users permission to perform specific tasks, the site authoring environment uses security groups that you create in Microsoft Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="3d32d-106">Najpierw należy przypisać nową lub istniejącą grupę zabezpieczeń Azure AD do każdej roli w środowisku tworzenia treści.</span><span class="sxs-lookup"><span data-stu-id="3d32d-106">You first assign a new or existing security group from Azure AD to each role in the authoring environment.</span></span> <span data-ttu-id="3d32d-107">Następnie należy przyznać lub odebrać uprawnienia indywidualnym użytkownikom, dodając tych użytkowników do odpowiedniej grupy zabezpieczeń lub usuwając je z grupy zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="3d32d-107">You then grant or revoke permissions for individual users by either adding those users to an appropriate security group or removing them from a security group.</span></span>

## <a name="overview-of-roles-in-the-authoring-environment"></a><span data-ttu-id="3d32d-108">Omówienie ról w środowisku tworzenia</span><span class="sxs-lookup"><span data-stu-id="3d32d-108">Overview of roles in the authoring environment</span></span>

<span data-ttu-id="3d32d-109">Środowisko tworzenia Dynamics 365 for Commerce obsługuje następujące role:</span><span class="sxs-lookup"><span data-stu-id="3d32d-109">The Dynamics 365 for Commerce authoring environment supports the following roles.</span></span>

| <span data-ttu-id="3d32d-110">Rola</span><span class="sxs-lookup"><span data-stu-id="3d32d-110">Role</span></span>                 | <span data-ttu-id="3d32d-111">Opis</span><span class="sxs-lookup"><span data-stu-id="3d32d-111">Description</span></span> |
|----------------------|-------------|
| <span data-ttu-id="3d32d-112">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="3d32d-112">System Administrator</span></span> | <span data-ttu-id="3d32d-113">Użytkownicy, którzy mają tę rolę, mają uprawnienia do wszystkich narzędzi oraz dla wszystkich ocen i przeglądów.</span><span class="sxs-lookup"><span data-stu-id="3d32d-113">Users who have this role have all privileges for all tools, and for all ratings and reviews.</span></span> <span data-ttu-id="3d32d-114">Mogą również tworzyć witryny.</span><span class="sxs-lookup"><span data-stu-id="3d32d-114">They can also create sites.</span></span> |
| <span data-ttu-id="3d32d-115">Administrator</span><span class="sxs-lookup"><span data-stu-id="3d32d-115">Administrator</span></span>   | <span data-ttu-id="3d32d-116">Użytkownicy, którzy mają tę rolę, mają uprawnienia do wszystkich narzędzi i RnR w danej strukturze witryny.</span><span class="sxs-lookup"><span data-stu-id="3d32d-116">Users who have this role have all privileges for all tools and RnR in a given site structure.</span></span> |
| <span data-ttu-id="3d32d-117">Producent Web</span><span class="sxs-lookup"><span data-stu-id="3d32d-117">Web Producer</span></span>         | <span data-ttu-id="3d32d-118">Użytkownicy dysponujący tą rolą mogą tworzyć strony, fragmenty i szablony, przesyłać i zarządzać zasobami oraz wzbogacać produkty i kategorie.</span><span class="sxs-lookup"><span data-stu-id="3d32d-118">Users who have this role can create pages, fragments and templates, upload and manage assets, and enrich products and categories.</span></span> |
| <span data-ttu-id="3d32d-119">Czytelnik</span><span class="sxs-lookup"><span data-stu-id="3d32d-119">Reader</span></span>               | <span data-ttu-id="3d32d-120">Użytkownicy, którzy mają tę rolę, mogą wyświetlać strony, szablony, zasoby, fragmenty, układy i ustawienia, ale nie mogą wprowadzać zmian.</span><span class="sxs-lookup"><span data-stu-id="3d32d-120">Users who have this role can view pages, templates, assets, fragments, layouts and settings, but may not make changes.</span></span> |
| <span data-ttu-id="3d32d-121">Moderator RnR</span><span class="sxs-lookup"><span data-stu-id="3d32d-121">RnR Moderator</span></span>        | <span data-ttu-id="3d32d-122">Użytkownicy, którzy mają tę rolę, mogą moderować recenzje produktów.</span><span class="sxs-lookup"><span data-stu-id="3d32d-122">Users who have this role can moderate product reviews.</span></span> |

## <a name="system-administrator-role"></a><span data-ttu-id="3d32d-123">Rola administratora systemu</span><span class="sxs-lookup"><span data-stu-id="3d32d-123">System Administrator role</span></span>

<span data-ttu-id="3d32d-124">Podczas udostępniania Dynamics 365 Commerce w środowisku Microsoft Dynamics Lifecycle Services (LCS), użytkownik jest proszony o podanie grupy zabezpieczeń dla roli **Administratora systemu**.</span><span class="sxs-lookup"><span data-stu-id="3d32d-124">When you provision Dynamics 365 Commerce in the Microsoft Dynamics Lifecycle Services (LCS) environment, you're asked to provide a security group for the **System Administrator** role.</span></span> <span data-ttu-id="3d32d-125">Ta rola jest następnie automatycznie stosowana do wszystkich witryn, które są tworzone w konfigurowanym środowisku.</span><span class="sxs-lookup"><span data-stu-id="3d32d-125">This role is then automatically applied to all sites that you create in the environment that you're configuring.</span></span> <span data-ttu-id="3d32d-126">Grupę zabezpieczeń dla tej roli można aktualizować tylko w usługi LCS.</span><span class="sxs-lookup"><span data-stu-id="3d32d-126">The security group for this role can be updated only in LCS.</span></span> <span data-ttu-id="3d32d-127">Na stronie **Administracja witryny** dla wszystkich witryn jest ona wyświetlana w trybie tylko do odczytu i służy tylko do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="3d32d-127">On the **Site Administration** page for all sites, it appears as read-only and is for informational purposes only.</span></span>

## <a name="administrator-role"></a><span data-ttu-id="3d32d-128">Rola administratora</span><span class="sxs-lookup"><span data-stu-id="3d32d-128">Administrator role</span></span>

<span data-ttu-id="3d32d-129">Podczas tworzenia nowej witryny w module Commerce użytkownik jest monitowany o podanie grupy zabezpieczeń dla roli **Administratora**.</span><span class="sxs-lookup"><span data-stu-id="3d32d-129">When you create a new site in Commerce, you're asked to provide a security group for the **Administrator** role.</span></span> <span data-ttu-id="3d32d-130">Aby zapoznać się z omówieniem uprawnień udzielanych przez tę rolę, zajrzyj do tabeli wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="3d32d-130">See the table earlier in this topic for an overview of the permissions that this role grants.</span></span>

## <a name="add-or-update-security-groups"></a><span data-ttu-id="3d32d-131">Dodaj lub zaktualizuj grupy zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="3d32d-131">Add or update security groups</span></span>

<span data-ttu-id="3d32d-132">Po utworzeniu witryny użytkownik będący w grupach zabezpieczeń skojarzonych z rolami **Administratora systemu** i **Administratora** może uzyskać dostęp do środowiska tworzenia tej witryny.</span><span class="sxs-lookup"><span data-stu-id="3d32d-132">After your site is created, only users who are in the security groups that are associated with the **System Administrator** and **Administrator** roles can access the authoring environment for that site.</span></span> <span data-ttu-id="3d32d-133">Aby przypisać użytkowników do ról **Producent Web**, **Moderator RnR** i **Czytelnik**, należy przypisać do nich grupy zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="3d32d-133">To assign users to the **Web Producer**, **RnR Moderator**, and **Reader** roles, you must assign security groups to those roles.</span></span> <span data-ttu-id="3d32d-134">Aby dodać grupę zabezpieczeń do roli lub zaktualizować grupę zabezpieczeń, która jest aktualnie przypisana do roli, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3d32d-134">To add a security group to a role, or to update a security group that is currently assigned to a role, follow these steps.</span></span>

1. <span data-ttu-id="3d32d-135">Przejdź do strony, którą chcesz zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="3d32d-135">Go to the site that you want to update.</span></span>
1. <span data-ttu-id="3d32d-136">W module **Zarządzanie witryną** otwórz stronę **Zabezpieczenia**.</span><span class="sxs-lookup"><span data-stu-id="3d32d-136">In **Site management**, open the **Security** page.</span></span>
1. <span data-ttu-id="3d32d-137">Wybierz rolę do zmodyfikowania.</span><span class="sxs-lookup"><span data-stu-id="3d32d-137">Select the role to modify.</span></span>
1. <span data-ttu-id="3d32d-138">Dodawanie grup zabezpieczeń do ról lub usuwanie grup zabezpieczeń z ról.</span><span class="sxs-lookup"><span data-stu-id="3d32d-138">Add security groups to roles, or remove security groups from roles.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3d32d-139">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3d32d-139">Additional resources</span></span>

[<span data-ttu-id="3d32d-140">Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii</span><span class="sxs-lookup"><span data-stu-id="3d32d-140">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="3d32d-141">Zagadnienia optymalizacji wyszukiwarki dla witryny</span><span class="sxs-lookup"><span data-stu-id="3d32d-141">Search engine optimization (SEO) considerations for your site</span></span>](search-engine-optimization-considerations.md)

[<span data-ttu-id="3d32d-142">Zarządzanie zasadami zabezpieczeń zawartości (CSP)</span><span class="sxs-lookup"><span data-stu-id="3d32d-142">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]