---
title: Konfigurowanie urzędów skarbowych
description: Urzędy skarbowe to jednostki, do których należy zgłaszać i przekazywać zebrane podatki.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb0b30be91e33cb50af0ae5c2e4dcd75bd12599b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846326"
---
# <a name="set-up-sales-tax-authorities"></a><span data-ttu-id="c681d-103">Konfigurowanie urzędów skarbowych</span><span class="sxs-lookup"><span data-stu-id="c681d-103">Set up sales tax authorities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c681d-104">Urzędy skarbowe to jednostki, do których należy zgłaszać i przekazywać zebrane podatki.</span><span class="sxs-lookup"><span data-stu-id="c681d-104">Sales tax authorities are entities to which collected sales tax needs to be reported and paid.</span></span> <span data-ttu-id="c681d-105">Można płacić podatki urzędowi skarbowemu bezpośrednio lub za pośrednictwem konta dostawcy, które należy utworzyć dla urzędu skarbowego.</span><span class="sxs-lookup"><span data-stu-id="c681d-105">You can pay sales taxes to the authority directly or through a vendor account that you create for the sales tax authority.</span></span> <span data-ttu-id="c681d-106">W takim przypadku firma może używać swoich zwykłych procedur płatności, aby płacić podatki na czas.</span><span class="sxs-lookup"><span data-stu-id="c681d-106">If you do this, the company can use its usual payment routines to pay the sales tax authority on time.</span></span> <span data-ttu-id="c681d-107">Jeśli nie skonfigurujesz urzędu skarbowego jako dostawcy, ktoś musi przygotować ręczną płatność na rzecz urzędu skarbowego w odpowiednim terminie.</span><span class="sxs-lookup"><span data-stu-id="c681d-107">If you do not set up the tax authority as a vendor, someone must prepare a manual payment to the tax authority on the appropriate due date.</span></span> <span data-ttu-id="c681d-108">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="c681d-108">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="c681d-109">Wybierz kolejno opcje Podatek > Podatki pośrednie > Podatek > Urzędy skarbowe.</span><span class="sxs-lookup"><span data-stu-id="c681d-109">Go to Tax > Indirect taxes > Sales tax > Sales tax authorities.</span></span>
2. <span data-ttu-id="c681d-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c681d-110">Click New.</span></span>
3. <span data-ttu-id="c681d-111">W polu Organ wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c681d-111">In the Authority field, type a value.</span></span>
4. <span data-ttu-id="c681d-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c681d-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="c681d-113">W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c681d-113">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="c681d-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c681d-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="c681d-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c681d-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="c681d-116">Wybierz układ raportu dla swojego kraju/regionu, jeśli taki układ jest dostępny.</span><span class="sxs-lookup"><span data-stu-id="c681d-116">Select the report layout for your country/region, if one is available.</span></span> <span data-ttu-id="c681d-117">Jeśli układy raportów nie odpowiadają wymaganiom urzędu skarbowego, użyj domyślnego układu.</span><span class="sxs-lookup"><span data-stu-id="c681d-117">If the report layouts do not correspond to the requirements of the sales tax authority, use default layout.</span></span>
9. <span data-ttu-id="c681d-118">Wprowadź wartości w formularzu Zaokrąglanie i polach Zaokrąglenie, aby określić sposób zaokrąglania łącznej kwoty podatku do zapłaty.</span><span class="sxs-lookup"><span data-stu-id="c681d-118">Enter values in the Rounding form and the Round-off fields to specify how the tax total amount to be paid should be rounded.</span></span> <span data-ttu-id="c681d-119">Wszelkie różnice zaokrąglania będą księgowana na kontach transakcji automatycznych skonfigurowanych w Księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="c681d-119">Any rounding differences will be posted to Accounts for automatic transactions set up in General ledger.</span></span>
10. <span data-ttu-id="c681d-120">W polu Zaokrąglenie wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="c681d-120">In the Round-off field, enter a number.</span></span>
11. <span data-ttu-id="c681d-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c681d-121">Click Save.</span></span>

