---
title: Nie można skonfigurować grupy zabezpieczeń dla Konstruktora witryn portalu Commerce podczas początkowego wdrażania
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy grupa zabezpieczeń rozwiązania Microsoft Azure Active Directory (Azure AD) dla Konstruktora witryn Commerce nie pojawia się jako opcja podczas tworzenia składników usługi handlu elektronicznego w u usługach Microsoft Dynamics Lifecycle Services (LCS) podczas początkowego wdrażania nowej dzierżawy usług handlu elektronicznego.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: aa00e9331693600ced2f4ead399a0c005b77ad08
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801514"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a><span data-ttu-id="9c0e1-103">Nie można skonfigurować grupy zabezpieczeń dla Konstruktora witryn portalu Commerce podczas początkowego wdrażania</span><span class="sxs-lookup"><span data-stu-id="9c0e1-103">Can't configure a security group for Commerce site builder during initial deployment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9c0e1-104">Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy grupa zabezpieczeń rozwiązania Microsoft Azure Active Directory (Azure AD) dla Konstruktora witryn Commerce nie pojawia się jako opcja podczas tworzenia składników usługi handlu elektronicznego w u usługach Microsoft Dynamics Lifecycle Services (LCS) podczas początkowego wdrażania nowej dzierżawy usług handlu elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="9c0e1-104">This topic provides troubleshooting guidance that can help when the Microsoft Azure Active Directory (Azure AD) security group for Commerce site builder doesn't appear as an option when you create e-commerce components in Microsoft Dynamics Lifecycle Services (LCS) during initial deployment of a new e-commerce tenant.</span></span>

## <a name="description"></a><span data-ttu-id="9c0e1-105">opis</span><span class="sxs-lookup"><span data-stu-id="9c0e1-105">Description</span></span>

<span data-ttu-id="9c0e1-106">Podczas tworzenia składników portalu handlu elektronicznego w ramach procesu wdrażania nowej dzierżawy usługi handlu elektronicznego, która zawiera składnik Konstruktora witryn commerce, grupa zabezpieczeń Azure AD nie jest wyświetlana jako opcja w oknie dialogowym.</span><span class="sxs-lookup"><span data-stu-id="9c0e1-106">When you create the e-commerce components as part of the process of deploying a new e-commerce tenant that includes the Commerce site builder component, the Azure AD security group doesn't appear as an option in the dialog box.</span></span>

## <a name="resolution"></a><span data-ttu-id="9c0e1-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="9c0e1-107">Resolution</span></span>

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a><span data-ttu-id="9c0e1-108">Inicjowanie obsługi witryny e-commerce z użytkownikiem w odpowiedniej dzierżawie</span><span class="sxs-lookup"><span data-stu-id="9c0e1-108">Provision the e-commerce site with a user in the correct tenant</span></span>

1. <span data-ttu-id="9c0e1-109">Przejdź do [portalu Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="9c0e1-109">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="9c0e1-110">W dzierżawie, dla których został obsługiny projekt usługi LCS dla witryny e-commerce, postępuj zgodnie z instrukcjami w obszarze [Tworzenie grupy podstawowej i dodaj członków, używając Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="9c0e1-110">Under the tenant that the LCS project for your e-commerce site was provisioned for, follow the instructions in [Create a basic group and add members using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span>
1. <span data-ttu-id="9c0e1-111">Przejdź do usługi [LCS](https://lcs.dynamics.com/) i zaloguj się, używając konta, które ma tę samą dzierżawę co utworzona właśnie grupa zabezpieczeń Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9c0e1-111">Go to [LCS](https://lcs.dynamics.com/), and sign in by using an account that shares the same tenant as the Azure AD security group that you just created.</span></span> <span data-ttu-id="9c0e1-112">Konto musi mieć dostęp do wyświetlania grupy zabezpieczeń Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9c0e1-112">The account must have access to view the Azure AD security group.</span></span>
1. <span data-ttu-id="9c0e1-113">Aby skonfigurować witrynę e-commerce, należy wykonać kroki konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="9c0e1-113">Complete the setup steps to configure the e-commerce site.</span></span> <span data-ttu-id="9c0e1-114">Podczas inicjowania obsługi składników handlu elektronicznego grupa zabezpieczeń powinna być wyświetlana jako opcja w oknie dialogowym.</span><span class="sxs-lookup"><span data-stu-id="9c0e1-114">When you provision the e-commerce components, the security group should now appear as an option in the dialog box.</span></span>

> [!NOTE]
> <span data-ttu-id="9c0e1-115">Aby mieć pewność, że pole w oknie dialogowym jest wypełnione listą grup zabezpieczeń, należy wybrać opcję **Enter** po wprowadzeniu nazwy utworzonej grupy zabezpieczeń Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9c0e1-115">To ensure that the field in the dialog box is filled with the list of security groups, you must select **Enter** after you enter the name of the Azure AD security group that you created.</span></span> <span data-ttu-id="9c0e1-116">W wynikach wyszukiwania zostaną wyświetlona lista wszystkich grup zabezpieczeń Azure AD, których nazwa rozpoczyna się wyszukiwany tekstem i do których użytkownik ma dostęp.</span><span class="sxs-lookup"><span data-stu-id="9c0e1-116">The search results will list all the Azure AD security groups that start with the search text, and that the user has access to.</span></span> <span data-ttu-id="9c0e1-117">Aby uzyskać szerszy wynik wyszukiwania, można użyć krótszych wyszukiwań.</span><span class="sxs-lookup"><span data-stu-id="9c0e1-117">You can use a shorter search term to allow for broader search results.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c0e1-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9c0e1-118">Additional resources</span></span>

[<span data-ttu-id="9c0e1-119">Utwórz podstawową grupę i dodaj członków za pomocą Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9c0e1-119">Create a basic group and add members using Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[<span data-ttu-id="9c0e1-120">Wdrażanie nowej dzierżawy handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="9c0e1-120">Deploy a new e-commerce tenant</span></span>](../deploy-ecommerce-site.md)
