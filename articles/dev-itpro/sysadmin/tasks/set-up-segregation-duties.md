---
title: Konfigurowanie podziału obowiązków
description: Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: e3682dbcb72588633fb6b3fe4cbda99f422163a3
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851270"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="148ca-103">Konfigurowanie podziału obowiązków</span><span class="sxs-lookup"><span data-stu-id="148ca-103">Set up segregation of duties</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="148ca-104">Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="148ca-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="148ca-105">Ta koncepcja jest nazywana podziałem obowiązków.</span><span class="sxs-lookup"><span data-stu-id="148ca-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="148ca-106">Na przykład można nie chcieć, aby ta sama osoba potwierdzała przyjęcie towarów i przetwarzała płatność dla dostawcy.</span><span class="sxs-lookup"><span data-stu-id="148ca-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="148ca-107">Podział obowiązków pomaga zmniejszyć ryzyko oszustwa, a także wykrywać błędy lub nieprawidłowości.</span><span class="sxs-lookup"><span data-stu-id="148ca-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="148ca-108">Podział obowiązków może także służyć do wymuszania zasad kontroli wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="148ca-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="148ca-109">Aby utworzyć regułę, wykonaj procedurę opisaną poniżej.</span><span class="sxs-lookup"><span data-stu-id="148ca-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="148ca-110">W celu wykonania procedury musisz być administratorem systemu.</span><span class="sxs-lookup"><span data-stu-id="148ca-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="148ca-111">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DAT.</span><span class="sxs-lookup"><span data-stu-id="148ca-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="148ca-112">Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Reguły podziału obowiązków.</span><span class="sxs-lookup"><span data-stu-id="148ca-112">Go to System administration > Security > Segregation of duties > Segregation of duties rules.</span></span>
2. <span data-ttu-id="148ca-113">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="148ca-113">Click New.</span></span>
3. <span data-ttu-id="148ca-114">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="148ca-114">In the Name field, type a value.</span></span>
    * <span data-ttu-id="148ca-115">Nadaj nazwę regule.</span><span class="sxs-lookup"><span data-stu-id="148ca-115">Enter a name for the rule.</span></span>  
4. <span data-ttu-id="148ca-116">W polu Pierwszy obowiązek kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="148ca-116">In the First duty field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="148ca-117">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="148ca-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="148ca-118">Wybierz pierwszy obowiązek, który będzie kontrolowany przez regułę.</span><span class="sxs-lookup"><span data-stu-id="148ca-118">Select the first duty that is controlled by the rule.</span></span>  
6. <span data-ttu-id="148ca-119">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="148ca-119">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="148ca-120">W polu Drugi obowiązek kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="148ca-120">In the Second duty field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="148ca-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="148ca-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="148ca-122">Wybierz drugi obowiązek, który będzie kontrolowany przez regułę.</span><span class="sxs-lookup"><span data-stu-id="148ca-122">Select the second duty that is controlled by the rule.</span></span>  
9. <span data-ttu-id="148ca-123">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="148ca-123">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="148ca-124">W polu Ważność wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="148ca-124">In the Severity field, select an option.</span></span>
    * <span data-ttu-id="148ca-125">Wybierz priorytet ryzyka występującego wtedy, gdy ten sam użytkownik lub posiadacz roli wykonuje oba obowiązki.</span><span class="sxs-lookup"><span data-stu-id="148ca-125">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="148ca-126">W polu Ryzyko związane z zabezpieczeniami wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="148ca-126">In the Security risk field, type a value.</span></span>
    * <span data-ttu-id="148ca-127">Wprowadź opis ryzyka związanego z zabezpieczeniami.</span><span class="sxs-lookup"><span data-stu-id="148ca-127">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="148ca-128">W polu Ograniczenie zabezpieczeń wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="148ca-128">In the Security mitigation field, type a value.</span></span>
    * <span data-ttu-id="148ca-129">Wprowadź opis czynności, które trzeba wykonać, aby zmniejszyć ryzyko związane z zabezpieczeniami.</span><span class="sxs-lookup"><span data-stu-id="148ca-129">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="148ca-130">Można na przykład ograniczyć ryzyko poprzez wykonanie bardziej szczegółowych przeglądów procesu, przeprowadzanie co miesiąc przeglądu menedżerskiego lub udostępnienie zasobów innym działom.</span><span class="sxs-lookup"><span data-stu-id="148ca-130">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>  
13. <span data-ttu-id="148ca-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="148ca-131">Click Save.</span></span>

