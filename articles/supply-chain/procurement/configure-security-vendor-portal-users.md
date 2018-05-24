---
title: "Zabezpieczenia użytkowników portalu dostawców"
description: "W tym artykule wyjaśniono, jak skonfigurować zabezpieczenia dla zewnętrznych dostawców używających portalu dostawców. Informacje te dotyczą tylko wersji systemu Dynamics AX z lutego i maja 2016 roku."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5819d21a91ac2a7c91f19fd6d80fd7b983411545
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="vendor-portal-user-security"></a><span data-ttu-id="517d4-104">Zabezpieczenia użytkowników portalu dostawców</span><span class="sxs-lookup"><span data-stu-id="517d4-104">Vendor portal user security</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="517d4-105">W tym artykule wyjaśniono, jak skonfigurować zabezpieczenia dla zewnętrznych dostawców używających portalu dostawców.</span><span class="sxs-lookup"><span data-stu-id="517d4-105">This article explains how to set up security for external vendors who use the Vendor portal.</span></span> <span data-ttu-id="517d4-106">Informacje te dotyczą tylko wersji systemu Dynamics AX z lutego i maja 2016 roku.</span><span class="sxs-lookup"><span data-stu-id="517d4-106">This information applies only to the February 2016 &amp; May 2016 versions of Dynamics AX.</span></span>

<span data-ttu-id="517d4-107">Funkcjonalność portalu dostawców została zastąpiona rozszerzoną funkcjonalnością portalu współpracy z dostawcami w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="517d4-107">The Vendor portal functionality has been replaced by extended vendor collaboration functionality in Dynamics 365 for Operations version 1611.</span></span> <span data-ttu-id="517d4-108">Aby uzyskać więcej informacji o konfigurowaniu zabezpieczeń w portalu współpracy z dostawcami, zobacz [Konfigurowanie i obsługa współpracy z dostawcami](set-up-maintain-vendor-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="517d4-108">For more information about setting up security for vendor collaboration, see [Set up and maintain vendor collaboration](set-up-maintain-vendor-collaboration.md).</span></span> <span data-ttu-id="517d4-109">Portal dostawców pokazuje ograniczone informacje o zamówieniach zakupu zewnętrznym dostawcom.</span><span class="sxs-lookup"><span data-stu-id="517d4-109">The Vendor portal exposes a limited set of information about purchase orders (POs) to external vendors.</span></span> <span data-ttu-id="517d4-110">Konieczne jest prawidłowe ustawienie uprawnień użytkowników Portalu dostawców w systemie Microsoft Dynamics AX, aby dostawcy nie mieli dostępu do dodatkowych informacji w Twojej instalacji systemu Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="517d4-110">It's important that you correctly set up user permissions for the Vendor portal in Microsoft Dynamics AX, so that vendors don't have unintended access to additional information in your Dynamics AX installation.</span></span> <span data-ttu-id="517d4-111">**Ważne:** w przeciwieństwie do innych użytkowników dostawcy zewnętrzni nie powinni mieć przypisanej roli **SystemUser**.</span><span class="sxs-lookup"><span data-stu-id="517d4-111">**Important:** Unlike other users, external vendors should not have the **SystemUser** role.</span></span> <span data-ttu-id="517d4-112">Rola **SystemUser** przyznaje dostęp do zestawu uprawnień, do których nie powinni mieć dostępu użytkownicy zewnętrzni.</span><span class="sxs-lookup"><span data-stu-id="517d4-112">The **SystemUser** role grants access to a set of privileges that aren't suitable for external users.</span></span>

## <a name="setting-up-a-vendor-portal-user"></a><span data-ttu-id="517d4-113">Konfigurowanie użytkownika portalu dostawców</span><span class="sxs-lookup"><span data-stu-id="517d4-113">Setting up a Vendor portal user</span></span>
<span data-ttu-id="517d4-114">Przed utworzeniem konta użytkownika dla kogoś, kto będzie korzystał z Portalu dostawców, trzeba ustawić użytkownikowi możliwość współpracy na Portalu dostawców.</span><span class="sxs-lookup"><span data-stu-id="517d4-114">Before you create a user account for someone who will use the Vendor portal, you must set up the vendor to allow for Vendor portal collaboration.</span></span> <span data-ttu-id="517d4-115">Użyj pola **Współpraca dotycząca zamówienia zakupu** na karcie **Ogólne** na stronie **Dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="517d4-115">Use the **Purchase order collaboration** field on the **General** tab on the **Vendors** page.</span></span> <span data-ttu-id="517d4-116">Dostawcy zewnętrzni korzystający z Portalu dostawców muszą mieć następującą konfigurację:</span><span class="sxs-lookup"><span data-stu-id="517d4-116">External vendors that use the Vendor portal must have the following setup:</span></span>

-   <span data-ttu-id="517d4-117">Konto użytkownika Microsoft Azure Active Directory (AAD) musi być zarejestrowane dla dostawcy na stronie **użytkowników** w systemie Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="517d4-117">A Microsoft Azure Active Directory (AAD) user account must be registered for the vendor on the **Users** page in Dynamics AX.</span></span>
-   <span data-ttu-id="517d4-118">Dostawca musi mieć rolę zabezpieczeń **Vendor (zewnętrzna)**, a nie **SystemUser**.</span><span class="sxs-lookup"><span data-stu-id="517d4-118">The vendor must have the **Vendor (external)** security role, not the **SystemUser** role.</span></span> <span data-ttu-id="517d4-119">**Uwaga:** Rola **SystemUser** jest przyznawana automatycznie podczas tworzenia nowego konta użytkownika w systemie Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="517d4-119">**Note:** The **SystemUser** role is automatically granted when you create a new user account in Dynamics AX.</span></span> <span data-ttu-id="517d4-120">W związku z tym należy usunąć tę rolę i potwierdzić otrzymaną wiadomość z ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="517d4-120">Therefore, you must remove that role and acknowledge the warning message that you receive.</span></span>
-   <span data-ttu-id="517d4-121">Użytkownik Dostawca nie powinien mieć uprawnień dodawania pól z tabel zamówienia zakupu do widoku zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="517d4-121">The vendor user should not be granted permission to add additional fields from the PO tables to their view of the PO.</span></span> <span data-ttu-id="517d4-122">Na karcie **personalizacji** na karcie **użytkowników** należy ustawić opcję **Jawne personalizacje dozwolone** jako **Nie**.</span><span class="sxs-lookup"><span data-stu-id="517d4-122">On the **Personalization** tab, on the **Users** tab, set the **Explicit personalization allowed** option for the user to **No**.</span></span>
-   <span data-ttu-id="517d4-123">Konto użytkownika należy skojarzyć z zarejestrowaną osobą kontaktową.</span><span class="sxs-lookup"><span data-stu-id="517d4-123">The user account must be associated with a registered contact person.</span></span> <span data-ttu-id="517d4-124">Na stronie **użytkowników** wybierz osobę kontaktową w polu **Imię i nazwisko**.</span><span class="sxs-lookup"><span data-stu-id="517d4-124">On the **Users** page, select a contact person in the **Name** field.</span></span> <span data-ttu-id="517d4-125">Wybrana osoba powinna mieć rolę **kontakt** dla odpowiednich dostawców.</span><span class="sxs-lookup"><span data-stu-id="517d4-125">The person that you select should have the **Contact** role for the relevant vendor.</span></span>

<span data-ttu-id="517d4-126">Jeśli ta sama osoba wymaga dostępu do portalu dostawców dla wielu kont dostawców (dla różnych podmiotów prawnych), każde konto użytkownika tej osoby musi być skojarzone z tą samą osobą kontaktową.</span><span class="sxs-lookup"><span data-stu-id="517d4-126">If the same person requires access to the Vendor portal for multiple vendor accounts (for different legal entities, perhaps), each of that person's user accounts must be associated with the same registered contact person.</span></span> <span data-ttu-id="517d4-127">Rola **dostawcy (zewnętrzna)** zawiera wszystkie podstawowe funkcje, które są niezbędne, aby korzystać z funkcji portalu dostawców.</span><span class="sxs-lookup"><span data-stu-id="517d4-127">The **Vendor (external)** role includes all the basic capabilities that are required in order to use the functionality that is available in the Vendor portal.</span></span> <span data-ttu-id="517d4-128">Ta konfiguracja pomaga zagwarantować, że interfejs użytkownika, który widzi użytkownik zewnętrzny, zawiera tylko odpowiednie informacje.</span><span class="sxs-lookup"><span data-stu-id="517d4-128">This setup helps guarantee that the user interface that the external user sees is focused on the intended scenario only.</span></span>

<a name="additional-resources"></a><span data-ttu-id="517d4-129">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="517d4-129">Additional resources</span></span>
--------

[<span data-ttu-id="517d4-130">Portal współpracy z dostawcami</span><span class="sxs-lookup"><span data-stu-id="517d4-130">Vendor collaboration</span></span>](collaborate-vendors-vendor-portal.md)




