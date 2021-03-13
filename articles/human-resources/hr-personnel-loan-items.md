---
title: Zarządzanie przedmiotami wypożyczanymi pracownikom
description: Przedmioty pożyczek są rekordami, które pomagają kierownikom śledzić fizyczne przedmioty, które firma pożycza pracownikom.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmLoanItem, HcmLoanType, HcmPersonLoan, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3581
ms.assetid: b14bdddb-f10e-4619-9f91-8c88439da862
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: d34551e4a3cc08ce3fe47e8f8fd2c3cc68c0daf7
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130140"
---
# <a name="manage-items-that-are-lent-to-workers"></a><span data-ttu-id="daa4d-103">Zarządzanie przedmiotami wypożyczanymi pracownikom</span><span class="sxs-lookup"><span data-stu-id="daa4d-103">Manage items that are lent to workers</span></span>

<span data-ttu-id="daa4d-104">Przedmioty pożyczek są rekordami, które pomagają kierownikom śledzić fizyczne przedmioty, które firma pożycza pracownikom.</span><span class="sxs-lookup"><span data-stu-id="daa4d-104">Loan items are records that help managers track the physical items that your company lends to its workers.</span></span> 

<span data-ttu-id="daa4d-105">Poniżej przedstawiono listę przykładowych towarów, które firma może wypożyczyć pracownikom:</span><span class="sxs-lookup"><span data-stu-id="daa4d-105">The following points list examples of items that a company might lend to workers:</span></span>
-   <span data-ttu-id="daa4d-106">telefony komórkowe;</span><span class="sxs-lookup"><span data-stu-id="daa4d-106">Mobile telephones</span></span>
-   <span data-ttu-id="daa4d-107">samochody;</span><span class="sxs-lookup"><span data-stu-id="daa4d-107">Automobiles</span></span>
-   <span data-ttu-id="daa4d-108">Sprzęt komputerowy</span><span class="sxs-lookup"><span data-stu-id="daa4d-108">Computer equipment</span></span>

<span data-ttu-id="daa4d-109">Każdy przedmiot fizyczny musi mieć odpowiadający mu przedmiot pożyczki.</span><span class="sxs-lookup"><span data-stu-id="daa4d-109">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="daa4d-110">Każdy rekord przedmiotu pożyczki powinien opisywać wypożyczany przedmiot, osobę odpowiedzialną za wypożyczenie oraz możliwą liczbę dni wypożyczenia przedmiotu.</span><span class="sxs-lookup"><span data-stu-id="daa4d-110">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can loaned to a worker.</span></span> <span data-ttu-id="daa4d-111">Można utworzyć wiele przedmiotów pożyczki, takich jak klucze, karty dostępu lub mundury, w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="daa4d-111">You can create multiple loan items, for items such as keys, access cards or uniforms, at the same time.</span></span> 

<span data-ttu-id="daa4d-112">W przypadku pożyczania przedmiotu należy wprowadzić datę wypożyczenia przedmiotu oraz planowaną datę zwrócenia.</span><span class="sxs-lookup"><span data-stu-id="daa4d-112">When loaning an item, enter the date that the item was loaned, and the planned return date.</span></span> <span data-ttu-id="daa4d-113">W przypadku zwrócenia przedmiotu należy wprowadzić rzeczywistą datę zwrócenia.</span><span class="sxs-lookup"><span data-stu-id="daa4d-113">When the item is returned, enter the actual return date.</span></span>

<span data-ttu-id="daa4d-114">Pracownicy mogą wyświetlać rekordy wypożyczonych pozycji w obszarze roboczym Samoobsługa pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="daa4d-114">Employees can view the records of the items that have been loaned to them using the Employee self-service workspace.</span></span> <span data-ttu-id="daa4d-115">Mogą również edytować istniejące rekordy lub wprowadzać nowe wypożyczone przedmioty, jeśli otrzymali kolejne towary fizyczne.</span><span class="sxs-lookup"><span data-stu-id="daa4d-115">They can also edit the existing records or enter new loan items, if they've received additional physical items.</span></span>  <span data-ttu-id="daa4d-116">Przepływ pracy można ustawić tak, aby kierował zmiany do nowych lub istniejących wypożyczanych przedmiotów poprzez proces zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="daa4d-116">Workflow can be set up to route changes to new or existing loan items through an approval process.</span></span> 

<span data-ttu-id="daa4d-117">Menedżerowie mogą wyświetlać towar wypożyczony przez ich bezpośrednich podwładnych.</span><span class="sxs-lookup"><span data-stu-id="daa4d-117">Managers can view loaned items for their direct reports.</span></span> <span data-ttu-id="daa4d-118">Mogą także dostać uprawnienia dodawania nowych przedmiotów pożyczki w imieniu swoich pracowników.</span><span class="sxs-lookup"><span data-stu-id="daa4d-118">They can also be granted permission to add new loan items on behalf of their employees.</span></span>

 <a name="account-for-lost-or-misplaced-loan-items"></a><span data-ttu-id="daa4d-119"> Rozliczanie zgubionych lub przestawionych przedmiotów pożyczki</span><span class="sxs-lookup"><span data-stu-id="daa4d-119">Account for lost or misplaced loan items</span></span>
-----------------------------------------

<span data-ttu-id="daa4d-120">Jeśli przedmiot został uszkodzony lub przestawiony, należy zarejestrować fikcyjny zwrot.</span><span class="sxs-lookup"><span data-stu-id="daa4d-120">If an item becomes damaged or misplaced, enter a fictitious return record.</span></span> <span data-ttu-id="daa4d-121">Następnie należy usunąć przedmiot lub zachować go w zestawieniu i zmienić opis, aby wskazać, że przedmiot jest niedostępny.</span><span class="sxs-lookup"><span data-stu-id="daa4d-121">Then either delete the item or keep it in the overview and change the description to indicate that the item is not available.</span></span>


<a name="additional-resources"></a><span data-ttu-id="daa4d-122">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="daa4d-122">Additional resources</span></span>
--------

[<span data-ttu-id="daa4d-123">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="daa4d-123">Human resources</span></span>](index.md)



