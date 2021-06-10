---
title: Zasady uprawnienia do świadczenia
description: Ten artykuł zawiera informacje o zasadach uprawnień do świadczeń, które pomagają określić, kto może otrzymywać określone świadczenia.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 87a080c47e34a3265afea6494ff1733dac5bc384
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053112"
---
# <a name="benefit-eligibility-policies"></a><span data-ttu-id="98359-103">Zasady uprawnień do świadczeń</span><span class="sxs-lookup"><span data-stu-id="98359-103">Benefit eligibility policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="98359-104">Ten artykuł zawiera informacje o zasadach uprawnień do świadczeń, które pomagają określić, kto może otrzymywać określone świadczenia.</span><span class="sxs-lookup"><span data-stu-id="98359-104">This article provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="98359-105">Podczas tworzenia świadczeń określa się, które świadczenia będą dostępne dla których pracowników.</span><span class="sxs-lookup"><span data-stu-id="98359-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="98359-106">W poniższej tabeli przedstawiono przykłady świadczeń, które można udostępnić określonym pracownikom.</span><span class="sxs-lookup"><span data-stu-id="98359-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="98359-107">Świadczenie</span><span class="sxs-lookup"><span data-stu-id="98359-107">Benefit</span></span>          | <span data-ttu-id="98359-108">Dla kogo świadczenie jest dostępne</span><span class="sxs-lookup"><span data-stu-id="98359-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="98359-109">Ubezpieczenie zdrowotne</span><span class="sxs-lookup"><span data-stu-id="98359-109">Health insurance</span></span> | <span data-ttu-id="98359-110">Wszyscy pracownicy</span><span class="sxs-lookup"><span data-stu-id="98359-110">All employees</span></span>                   |
| <span data-ttu-id="98359-111">Telefon komórkowy</span><span class="sxs-lookup"><span data-stu-id="98359-111">Mobile phone</span></span>     | <span data-ttu-id="98359-112">Pracownicy działu sprzedaży, kadra zarządzająca</span><span class="sxs-lookup"><span data-stu-id="98359-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="98359-113">Przepustki parkingowe</span><span class="sxs-lookup"><span data-stu-id="98359-113">Parking passes</span></span>   | <span data-ttu-id="98359-114">Kierownicy</span><span class="sxs-lookup"><span data-stu-id="98359-114">Executives</span></span>                      |

<span data-ttu-id="98359-115">Następujące składniki są używane do tworzenia zasad uprawnień:</span><span class="sxs-lookup"><span data-stu-id="98359-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="98359-116">Typy reguł</span><span class="sxs-lookup"><span data-stu-id="98359-116">Policy rule types</span></span>
-   <span data-ttu-id="98359-117">Zasady uprawnienia do świadczenia</span><span class="sxs-lookup"><span data-stu-id="98359-117">Benefit eligibility policies</span></span>

<span data-ttu-id="98359-118">Typy reguł dla zasad definiują parametry kwerendy, które są używane podczas tworzenia określonych reguł dla zasad.</span><span class="sxs-lookup"><span data-stu-id="98359-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="98359-119">Po utworzeniu typów reguł można utworzyć zasady uprawnień do świadczeń.</span><span class="sxs-lookup"><span data-stu-id="98359-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="98359-120">Zasady pozwalają tworzyć zbiór reguł dotyczące jednego lub kilku podmiotów prawnych.</span><span class="sxs-lookup"><span data-stu-id="98359-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="98359-121">W ramach każdej zasady można wyświetlić każdy z utworzonych wcześniej typów reguł dla zasad uprawnień do świadczenia.</span><span class="sxs-lookup"><span data-stu-id="98359-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="98359-122">Użytkownik określa zakres reguły w obrębie zasady.</span><span class="sxs-lookup"><span data-stu-id="98359-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="98359-123">Jeśli na przykład użytkownik utworzy typ reguły zasady uprawnienia do świadczenia o nazwie **Wykonawczy**, może określić, czym jest ta reguła w ramach zasady.</span><span class="sxs-lookup"><span data-stu-id="98359-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="98359-124">W tym przykładzie reguła może stwierdzać, że powinna ona obejmować każde stanowisko ze słowem „wykonawczy” w nazwie.</span><span class="sxs-lookup"><span data-stu-id="98359-124">In this example, the rule might state that any job title that contains the word "executive" should be included in the rule.</span></span> <span data-ttu-id="98359-125">Po zdefiniowaniu parametrów reguły lub reguł, które są uwzględniane w zasadach, można przypisać regułę do świadczenia.</span><span class="sxs-lookup"><span data-stu-id="98359-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>






[!INCLUDE[footer-include](../includes/footer-banner.md)]