---
title: Zestawy wymiarów finansowych
description: W tym temacie opisano zestawy wymiarów finansowych i przedstawiono kilka wskazówek dotyczących optymalizacji ich użycia.
author: yukonpeegs
manager: AnnBe
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b719d8eb868cb1722b470be4443d01181078ce21
ms.sourcegitcommit: 97ada5d52ed1829dcf030dad254096cd8df25da8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/06/2021
ms.locfileid: "5864419"
---
# <a name="financial-dimension-sets"></a><span data-ttu-id="20dde-103">Zestawy wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="20dde-103">Financial dimension sets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="20dde-104">W tym temacie opisano zestawy wymiarów finansowych i przedstawiono kilka wskazówek dotyczących optymalizacji ich użycia.</span><span class="sxs-lookup"><span data-stu-id="20dde-104">This topic describes financial dimension sets and provides some tips for optimizing their use.</span></span>

<span data-ttu-id="20dde-105">Zestaw wymiarów to uporządkowana lista wymiarów finansowych, której można użyć do podsumowania danych księgi głównej w sposób zdefiniowany przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="20dde-105">A dimension set is an ordered list of financial dimensions that can be used to summarize General ledger data in a user-defined way.</span></span> <span data-ttu-id="20dde-106">Podstawowym zastosowaniem zestawów wymiarów jest zdefiniowanie salda próbnego.</span><span class="sxs-lookup"><span data-stu-id="20dde-106">A primary use of dimension sets is to define a trial balance.</span></span>

<span data-ttu-id="20dde-107">Jedynym standardowym zestawem wymiarów jest zestaw wymiarów, który zawiera tylko konto główne.</span><span class="sxs-lookup"><span data-stu-id="20dde-107">The only standard dimension set is the dimension set that contains only the main account.</span></span>

<span data-ttu-id="20dde-108">Strona **Zestawy wymiarów finansowych** służy do tworzenia zestawów wymiarów finansowych i zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="20dde-108">You use the **Financial dimension sets** page to create and manage financial dimension sets.</span></span>

## <a name="dimension-set-balances"></a><span data-ttu-id="20dde-109">Salda zestawów wymiarów</span><span class="sxs-lookup"><span data-stu-id="20dde-109">Dimension set balances</span></span>

<span data-ttu-id="20dde-110">Zestaw wymiarów może mieć salda oparte na jego wymiarach finansowych.</span><span class="sxs-lookup"><span data-stu-id="20dde-110">A dimension set can have balances that are based on its financial dimensions.</span></span> <span data-ttu-id="20dde-111">Salda istnieją w księdze głównej i są oparte na definicji zestawu wymiarów.</span><span class="sxs-lookup"><span data-stu-id="20dde-111">The balances exist in General ledger and are based on the dimension set definition.</span></span> <span data-ttu-id="20dde-112">Salda są sumowane na podstawie danych księgi głównej, aby poprawić wydajność podczas ich pobierania (na przykład podczas generowania salda próbnego).</span><span class="sxs-lookup"><span data-stu-id="20dde-112">The balances are summarized from the General ledger data to help improve performance when they are retrieved (for example, when a trial balance is generated).</span></span>

## <a name="create-balances"></a><span data-ttu-id="20dde-113">Utwórz salda</span><span class="sxs-lookup"><span data-stu-id="20dde-113">Create balances</span></span>

<span data-ttu-id="20dde-114">Przycisk **Utwórz salda** służy do inicjowania sald dla zestawu wymiarów, który obecnie nie ma sald.</span><span class="sxs-lookup"><span data-stu-id="20dde-114">Use the **Create balances** button to initialize the balances for a dimension set that doesn't currently have balances.</span></span>

> [!NOTE]
> <span data-ttu-id="20dde-115">Zaleca się ograniczenie liczby zestawów wymiarów, które mają salda, ponieważ aktualizacje salda mają wpływ na wszystkie działania księgowania księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="20dde-115">We recommend that you limit the number of dimension sets that have balances, because balance updates affect all General ledger posting activities.</span></span>

## <a name="update-balances"></a><span data-ttu-id="20dde-116">Aktualizuj salda</span><span class="sxs-lookup"><span data-stu-id="20dde-116">Update balances</span></span>

<span data-ttu-id="20dde-117">Użyj przycisku **Aktualizuj salda**, aby uwzględnić w saldach najnowsze działanie księgowania księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="20dde-117">Use the **Update balances** button to include the latest General ledger posting activity in the balances.</span></span> <span data-ttu-id="20dde-118">Aktualizacje salda są lekkimi operacjami.</span><span class="sxs-lookup"><span data-stu-id="20dde-118">Balance updates are light operations.</span></span> <span data-ttu-id="20dde-119">Muszą przetwarzać tylko działanie księgowania księgi głównej, które wystąpiło od ostatniej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="20dde-119">They must process only the General ledger posting activity that has occurred since the last update.</span></span>

> [!NOTE]
> <span data-ttu-id="20dde-120">Wyświetlenie salda próbnego wymusza aktualizację, aby upewnić się, że pokazywane salda są aktualne.</span><span class="sxs-lookup"><span data-stu-id="20dde-120">Display of the trial balance forces an update, to ensure that the balances that are shown are current.</span></span> <span data-ttu-id="20dde-121">Rozważ użycie cyklicznego zadania wsadowego, aby aktualizacje najczęściej używanych zestawów wymiarów były szybkie.</span><span class="sxs-lookup"><span data-stu-id="20dde-121">Consider using a recurring batch job so that updates to your most frequently used dimension sets are quick.</span></span> <span data-ttu-id="20dde-122">W ten sposób pomagasz zminimalizować czas, jaki muszą czekać użytkownicy salda próbnego.</span><span class="sxs-lookup"><span data-stu-id="20dde-122">In this way, you help minimize the time that trial balance users must wait.</span></span>

## <a name="rebuild-balances"></a><span data-ttu-id="20dde-123">Odbuduj salda</span><span class="sxs-lookup"><span data-stu-id="20dde-123">Rebuild balances</span></span>

<span data-ttu-id="20dde-124">Przycisk **Odbuduj salda** umożliwia ponowne tworzenie sald od podstaw.</span><span class="sxs-lookup"><span data-stu-id="20dde-124">Use the **Rebuild balances** button to re-create the balances from scratch.</span></span> <span data-ttu-id="20dde-125">W ten sposób można zapewnić, że są one zgodne z danymi w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="20dde-125">In this way, you help ensure that they match the data in General ledger.</span></span> <span data-ttu-id="20dde-126">Przebudowa sald wymaga dużo przetwarzania i zwykle nie powinna być wymagana.</span><span class="sxs-lookup"><span data-stu-id="20dde-126">A rebuild of balances requires lots of processing and should not usually be required.</span></span>

> [!NOTE]
> <span data-ttu-id="20dde-127">Jeśli masz scenariusz, który regularnie wymaga przebudowy sald, zaleca się skontaktować się z obsługą klienta.</span><span class="sxs-lookup"><span data-stu-id="20dde-127">If you have a scenario that regularly requires a rebuild of balances, we recommend that you contact customer support.</span></span> <span data-ttu-id="20dde-128">Obsługa klienta może pomóc w określeniu, dlaczego salda nie są zgodne z danymi w księdze głównej.</span><span class="sxs-lookup"><span data-stu-id="20dde-128">Customer support can help you determine why balances don't match the data in General ledger.</span></span>

## <a name="clear-balances"></a><span data-ttu-id="20dde-129">Uzgodnij salda</span><span class="sxs-lookup"><span data-stu-id="20dde-129">Clear balances</span></span>

<span data-ttu-id="20dde-130">Użyj przycisku **Wyczyść salda**, aby usunąć salda i zatrzymać dalsze aktualizacje.</span><span class="sxs-lookup"><span data-stu-id="20dde-130">Use the **Clear balances** button to remove the balances and stop any further updates.</span></span> <span data-ttu-id="20dde-131">Zestaw wymiarów nie będzie już miał wpływu na działania księgowania księgi głównej.</span><span class="sxs-lookup"><span data-stu-id="20dde-131">The dimension set will no longer have an impact on General ledger posting activities.</span></span>

<span data-ttu-id="20dde-132">Aby uzyskać więcej informacji, zobacz [Wymiary finansowe](financial-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="20dde-132">For more information, see [Financial dimensions](financial-dimensions.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
