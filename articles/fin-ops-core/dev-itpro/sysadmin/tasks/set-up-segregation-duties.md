---
title: Konfigurowanie podziału obowiązków
description: Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e25fee324ce95cd04b86ee0e4e6a56cfacb61a53
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745748"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="0c85d-103">Konfigurowanie podziału obowiązków</span><span class="sxs-lookup"><span data-stu-id="0c85d-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0c85d-104">Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="0c85d-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="0c85d-105">Ta koncepcja jest nazywana podziałem obowiązków.</span><span class="sxs-lookup"><span data-stu-id="0c85d-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="0c85d-106">Na przykład można nie chcieć, aby ta sama osoba potwierdzała przyjęcie towarów i przetwarzała płatność dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="0c85d-106">For example, you might not want the same person to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="0c85d-107">Podział obowiązków pomaga zmniejszyć ryzyko oszustwa, a także wykrywać błędy lub nieprawidłowości.</span><span class="sxs-lookup"><span data-stu-id="0c85d-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="0c85d-108">Podział obowiązków może także służyć do wymuszania zasad kontroli wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="0c85d-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="0c85d-109">Aby utworzyć regułę, wykonaj procedurę opisaną poniżej.</span><span class="sxs-lookup"><span data-stu-id="0c85d-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="0c85d-110">W celu wykonania procedury musisz być administratorem systemu.</span><span class="sxs-lookup"><span data-stu-id="0c85d-110">You must be a system administrator to complete the procedure.</span></span>

1. <span data-ttu-id="0c85d-111">Wybierz kolejno opcje **Administrowanie systemem** > **Zabezpieczenia** > **Podział obowiązków** > **Reguły podziału obowiązków**.</span><span class="sxs-lookup"><span data-stu-id="0c85d-111">Go to **System administration** > **Security** > **Segregation of duties** > **Segregation of duties rules**.</span></span>
2. <span data-ttu-id="0c85d-112">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0c85d-112">Click **New**.</span></span>
3. <span data-ttu-id="0c85d-113">W polu **Nazwa** wpisz wartość reguły.</span><span class="sxs-lookup"><span data-stu-id="0c85d-113">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="0c85d-114">W polu **Pierwszy obowiązek** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0c85d-114">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="0c85d-115">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="0c85d-115">In the list, find and select the desired record.</span></span> <span data-ttu-id="0c85d-116">Wybierz pierwszy obowiązek, który będzie kontrolowany przez regułę.</span><span class="sxs-lookup"><span data-stu-id="0c85d-116">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="0c85d-117">W polu **Drugi obowiązek** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0c85d-117">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="0c85d-118">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="0c85d-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="0c85d-119">Wybierz drugi obowiązek, który będzie kontrolowany przez regułę.</span><span class="sxs-lookup"><span data-stu-id="0c85d-119">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="0c85d-120">W polu **Ważność** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="0c85d-120">In the **Severity** field, select an option.</span></span> <span data-ttu-id="0c85d-121">Wybierz priorytet ryzyka występującego wtedy, gdy ten sam użytkownik lub posiadacz roli wykonuje oba obowiązki.</span><span class="sxs-lookup"><span data-stu-id="0c85d-121">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="0c85d-122">W polu **Ryzyko związane z zabezpieczeniami** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c85d-122">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="0c85d-123">Wprowadź opis ryzyka związanego z zabezpieczeniami.</span><span class="sxs-lookup"><span data-stu-id="0c85d-123">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="0c85d-124">W polu **Ograniczenie zabezpieczeń** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0c85d-124">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="0c85d-125">Wprowadź opis czynności, które trzeba wykonać, aby zmniejszyć ryzyko związane z zabezpieczeniami.</span><span class="sxs-lookup"><span data-stu-id="0c85d-125">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="0c85d-126">Można na przykład ograniczyć ryzyko poprzez wykonanie bardziej szczegółowych przeglądów procesu, przeprowadzanie co miesiąc przeglądu menedżerskiego lub udostępnienie zasobów innym działom.</span><span class="sxs-lookup"><span data-stu-id="0c85d-126">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="0c85d-127">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0c85d-127">Click **Save**.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="0c85d-128">Podczas tworzenia reguły nie jest sprawdzana zgodność z regułami podziału obowiązków.</span><span class="sxs-lookup"><span data-stu-id="0c85d-128">Compliance with the rules for segregation of duties is not verified when you create a rule.</span></span> <span data-ttu-id="0c85d-129">Można utworzyć regułę, która powoduje konflikt z istniejącymi rolami.</span><span class="sxs-lookup"><span data-stu-id="0c85d-129">You can create a rule that creates a conflict for existing roles.</span></span> <span data-ttu-id="0c85d-130">Istniejące przypisania ról użytkowników mogą także kolidować z nową regułą.</span><span class="sxs-lookup"><span data-stu-id="0c85d-130">Existing user role assignments can also be in conflict with the new rule.</span></span> <span data-ttu-id="0c85d-131">Po utworzeniu lub zmodyfikowaniu reguły należy zweryfikować zgodność.</span><span class="sxs-lookup"><span data-stu-id="0c85d-131">You must validate compliance after you create or modify a rule.</span></span> <span data-ttu-id="0c85d-132">Aby uzyskać więcej informacji, zobacz temat [Identyfikowanie i rozwiązywanie konfliktów w podziale obowiązków](identify-resolve-conflicts-segregation-duties.md)</span><span class="sxs-lookup"><span data-stu-id="0c85d-132">For more information, see [Identify and resolve conflicts in segregation of duties](identify-resolve-conflicts-segregation-duties.md)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]