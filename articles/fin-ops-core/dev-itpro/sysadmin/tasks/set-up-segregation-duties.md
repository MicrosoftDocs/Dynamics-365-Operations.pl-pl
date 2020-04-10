---
title: Konfigurowanie podziału obowiązków
description: Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników.
author: maertenm
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 712cc90bef4f3ad56291e99edd9f963ae88add48
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143519"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="5e5c9-103">Konfigurowanie podziału obowiązków</span><span class="sxs-lookup"><span data-stu-id="5e5c9-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5e5c9-104">Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="5e5c9-105">Ta koncepcja jest nazywana podziałem obowiązków.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="5e5c9-106">Na przykład można nie chcieć, aby ta sama osoba potwierdzała przyjęcie towarów i przetwarzała płatność dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="5e5c9-107">Podział obowiązków pomaga zmniejszyć ryzyko oszustwa, a także wykrywać błędy lub nieprawidłowości.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="5e5c9-108">Podział obowiązków może także służyć do wymuszania zasad kontroli wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="5e5c9-109">Aby utworzyć regułę, wykonaj procedurę opisaną poniżej.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="5e5c9-110">W celu wykonania procedury musisz być administratorem systemu.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="5e5c9-111">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DAT.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="5e5c9-112">Wybierz kolejno **okienko nawigacji > Moduły > Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Reguły podziału obowiązków**.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-112">Go to **Navigation pane > Modules > System administration > Security > Segregation of duties > Segregation of duties rules**.</span></span>
2. <span data-ttu-id="5e5c9-113">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-113">Click **New**.</span></span>
3. <span data-ttu-id="5e5c9-114">W polu **Nazwa** wpisz wartość reguły.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-114">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="5e5c9-115">W polu **Pierwszy obowiązek** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-115">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="5e5c9-116">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="5e5c9-117">Wybierz pierwszy obowiązek, który będzie kontrolowany przez regułę.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-117">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="5e5c9-118">W polu **Drugi obowiązek** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-118">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="5e5c9-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-119">In the list, find and select the desired record.</span></span> <span data-ttu-id="5e5c9-120">Wybierz drugi obowiązek, który będzie kontrolowany przez regułę.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-120">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="5e5c9-121">W polu **Ważność** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-121">In the **Severity** field, select an option.</span></span> <span data-ttu-id="5e5c9-122">Wybierz priorytet ryzyka występującego wtedy, gdy ten sam użytkownik lub posiadacz roli wykonuje oba obowiązki.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-122">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="5e5c9-123">W polu **Ryzyko związane z zabezpieczeniami** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-123">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="5e5c9-124">Wprowadź opis ryzyka związanego z zabezpieczeniami.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-124">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="5e5c9-125">W polu **Ograniczenie zabezpieczeń** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-125">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="5e5c9-126">Wprowadź opis czynności, które trzeba wykonać, aby zmniejszyć ryzyko związane z zabezpieczeniami.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-126">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="5e5c9-127">Można na przykład ograniczyć ryzyko poprzez wykonanie bardziej szczegółowych przeglądów procesu, przeprowadzanie co miesiąc przeglądu menedżerskiego lub udostępnienie zasobów innym działom.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-127">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="5e5c9-128">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="5e5c9-128">Click **Save**.</span></span>

