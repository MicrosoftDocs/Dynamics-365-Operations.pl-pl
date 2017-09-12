--- 
title: "Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości"
description: "Menedżer ds. wynagrodzenia i świadczeń może rejestrować pracowników w planach wynagrodzeń o zmiennej wysokości w celu obliczania dla nich nagród pieniężnych i niepieniężnych."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: eb162e22276fc19cf11999380d551b29ba6a6d45
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a><span data-ttu-id="d6e80-103">Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="d6e80-103">Enroll an employee in a variable compensation plan</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d6e80-104">Menedżer ds. wynagrodzenia i świadczeń może rejestrować pracowników w planach wynagrodzeń o zmiennej wysokości w celu obliczania dla nich nagród pieniężnych i niepieniężnych.</span><span class="sxs-lookup"><span data-stu-id="d6e80-104">The Compensation and Benefits manager can enrol employees in variable compensation plans to calculate cash and non-cash awards for employees.</span></span> <span data-ttu-id="d6e80-105">Ta procedura zakłada, że plan wynagrodzeń o zmiennej wysokości został utworzony z polem Włącz rejestrację ustawionym na wartość Tak, a dla tego planu utworzono reguły uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="d6e80-105">This procedure assumes that a variable compensation plan has been created with the Enable enrolment field set to Yes, and that eligibility rules have been created for that variable compensation plan.</span></span> <span data-ttu-id="d6e80-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d6e80-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d6e80-107">Aby rozpocząć procedurę, wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Pracownicy > Wynagrodzenie > Rejestracja w planie o zmiennej wysokości.</span><span class="sxs-lookup"><span data-stu-id="d6e80-107">To begin this procedure, go to Human resources > Workers > Employees > Compensation > Variable plan enrolment</span></span>

1. <span data-ttu-id="d6e80-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d6e80-108">Click New.</span></span>
2. <span data-ttu-id="d6e80-109">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d6e80-109">In the Plan field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d6e80-110">Wyszukiwanie planu zostanie wyfiltrowane w celu wyświetlenia tylko planów wynagrodzeń o zmiennej wysokości, do których pracownik jest uprawniony zgodnie z regułami uprawnień.</span><span class="sxs-lookup"><span data-stu-id="d6e80-110">The plan lookup will be filtered to only show the variable compensation plans that the employee is eligible for based on the eligibility rules.</span></span>  
3. <span data-ttu-id="d6e80-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d6e80-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d6e80-112">Przełącz rozwinięcie sekcji Ogólne.</span><span class="sxs-lookup"><span data-stu-id="d6e80-112">Toggle the expansion of the General section.</span></span>
5. <span data-ttu-id="d6e80-113">W polu Data obowiązywania wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="d6e80-113">In the Effective date field, enter a date.</span></span>
6. <span data-ttu-id="d6e80-114">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d6e80-114">Click Save.</span></span>
7. <span data-ttu-id="d6e80-115">Przełącz rozwinięcie sekcji Zastąpienia.</span><span class="sxs-lookup"><span data-stu-id="d6e80-115">Toggle the expansion of the Overrides section.</span></span>
    * <span data-ttu-id="d6e80-116">Opcjonalnie można ustawić datę reguły zatrudnienia, aby zastępować datę zatrudnienia pracownika, gdy regułą zatrudnienia określoną dla wybranego planu jest Procent.</span><span class="sxs-lookup"><span data-stu-id="d6e80-116">Optionally, a hire rule date can be set to override the hire date for an employee when the hire rule specified for the selected variable plan is Percent.</span></span>  
    * <span data-ttu-id="d6e80-117">Jeśli plan wynagrodzeń o zmiennej wysokości opiera się na procencie podstawy, można zastąpić wartość procentową nagrody dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="d6e80-117">If the variable plan is a percent of basis plan, the award percentage can be overridden for the employee.</span></span> <span data-ttu-id="d6e80-118">Jeśli plan wynagrodzeń o zmiennej wysokości opiera się na liczbie jednostek, można zastąpić liczbę jednostek dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="d6e80-118">If the variable compensation plan is a number of units plan, the number of units can be overridden for the employee.</span></span>  
    * <span data-ttu-id="d6e80-119">Jeśli pracownik powinien otrzymać stałą kwotę nagrody, kwotę można ustawić w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="d6e80-119">If the employee should be given a flat amount for their award, the amount can be set here.</span></span>  
8. <span data-ttu-id="d6e80-120">Przełącz rozwinięcie sekcji Zastąpienia na poziomie organizacji.</span><span class="sxs-lookup"><span data-stu-id="d6e80-120">Toggle the expansion of the Organizational overrides section.</span></span>
    * <span data-ttu-id="d6e80-121">Jeśli należy wziąć pod uwagę wyniki osiągane przez pracownika, różne działy lub dział inny niż przypisany w stanowisku pracownika, można zastąpić dział.</span><span class="sxs-lookup"><span data-stu-id="d6e80-121">If the employee's performance should take into consideration, the performance of different departments, or a department other than the one assigned on the employee's position, the department can be overridden.</span></span> <span data-ttu-id="d6e80-122">Wartość w kolumnie Procent musi mieć łącznie 100.</span><span class="sxs-lookup"><span data-stu-id="d6e80-122">The Percent column should total 100.</span></span>  


