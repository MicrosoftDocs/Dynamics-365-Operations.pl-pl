---
title: Rozwiązywanie problemów związanych ze świadomością rozwiązania
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych ze świadomością rozwiązania.
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
ms.openlocfilehash: 013e37269ec3df2bede15b28cffcc175967de9a3
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172628"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a><span data-ttu-id="09c25-103">Rozwiązywanie problemów związanych ze świadomością rozwiązania</span><span class="sxs-lookup"><span data-stu-id="09c25-103">Troubleshoot issues related to solution awareness</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="09c25-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="09c25-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="09c25-105">A dokładniej, ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanych ze świadomością rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="09c25-105">Specifically, it provides information that can help you fix issues that are related to solution awareness.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09c25-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="09c25-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="09c25-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="09c25-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="error-on-the-dual-write-page"></a><span data-ttu-id="09c25-108">Błąd na stronie podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="09c25-108">Error on the Dual-write page</span></span>

<span data-ttu-id="09c25-109">Na stronie **Podwójny zapis** może zostać wyświetlony komunikat o błędzie podobny do następującego przykładu:</span><span class="sxs-lookup"><span data-stu-id="09c25-109">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="09c25-110">*Jednostka o nazwie „msdyn\_dualwriteentitymap” z namemapping = „Logical” nie została znaleziona w MetadataCache.*</span><span class="sxs-lookup"><span data-stu-id="09c25-110">*The entity with a name 'msdyn\_dualwriteentitymap' with namemapping='Logical' was not found in the MetadataCache.*</span></span>

<span data-ttu-id="09c25-111">Aby rozwiązać ten problem, upewnij się, że w Common Data Service jest zainstalowany podstawowe rozwiązanie podwójnego zapisywania.</span><span class="sxs-lookup"><span data-stu-id="09c25-111">To fix the issue, make sure that the dual-write core solution is installed in Common Data Service.</span></span> <span data-ttu-id="09c25-112">Podstawowe rozwiązanie dotyczące podwójnego zapisywania jest warunkiem koniecznym do uzyskania świadomości rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="09c25-112">The dual-write core solution is a prerequisite for solution awareness.</span></span>
