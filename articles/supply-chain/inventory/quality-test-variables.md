---
title: Zmienne testowe zarządzania jakością
description: W tym temacie opisano sposób tworzenia zmiennych testowych, których można używać w testach jakościowych w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5102d09f5762a390d6fd3aadafcb2ed23820982
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021715"
---
# <a name="quality-management-test-variables"></a><span data-ttu-id="f8a08-103">Zmienne testowe zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="f8a08-103">Quality management test variables</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8a08-104">W tym temacie opisano sposób tworzenia zmiennych testowych, których można używać w testach jakościowych w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f8a08-104">This topic describes how to create test variables that can be used for qualitative tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="f8a08-105">W każdym teście jakościowym zdefiniowanym na stronie **Testy** musisz zdefiniować zmienną testową i możliwe wyniki.</span><span class="sxs-lookup"><span data-stu-id="f8a08-105">For every qualitative test that is defined on the **Tests** page, you must define a test variable and its possible outcomes (results).</span></span> <span data-ttu-id="f8a08-106">(Dla testów jakościowych w polu **Typ** na stronie **Testy** ustawiono wartość *Opcja*).</span><span class="sxs-lookup"><span data-stu-id="f8a08-106">(For qualitative tests, the **Type** field on the **Tests** page is set to *Option*.)</span></span>

<span data-ttu-id="f8a08-107">Strona **Zmienne testowe** służy do konfigurowania, edytowania i wyświetlania możliwych wyników zmiennej testowej skojarzonej z testem jakościowym.</span><span class="sxs-lookup"><span data-stu-id="f8a08-107">You use the **Test variables** page to set up, edit, and view the possible outcomes for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="f8a08-108">Dla każdego wyniku przypisuje się stan wyniku *Zaliczony* lub *Niezaliczony*, aby określić, czy test został zaliczony czy niezaliczony, gdy ten wynik zostanie wybrany jako wynik testu.</span><span class="sxs-lookup"><span data-stu-id="f8a08-108">For each outcome, you assign an outcome status of either *Pass* or *Fail* to indicate whether the test is passed or failed when that outcome is selected as a test result.</span></span> <span data-ttu-id="f8a08-109">Strona **Grupy testów** służy do przypisywania zmiennej testowej i domyślnego wyniku do konkretnego testu.</span><span class="sxs-lookup"><span data-stu-id="f8a08-109">You use the **Test groups** page to assign a test variable and a default outcome for it to an individual qualitative test.</span></span>

<span data-ttu-id="f8a08-110">Zaleca się, aby dla każdej zmiennej testowej zdefiniować co najmniej dwa wyniki: jeden ze stanem wyniku *Zaliczony*, a drugi ze stanem wyniku *Niezaliczony*.</span><span class="sxs-lookup"><span data-stu-id="f8a08-110">For every test variable, we recommend that you define at least two outcomes: one that has an outcome status of *Pass* and one that has an outcome status of *Fail*.</span></span> <span data-ttu-id="f8a08-111">Nie ma ograniczeń co do łącznej liczby zmiennych lub wyników, które można zdefiniować.</span><span class="sxs-lookup"><span data-stu-id="f8a08-111">There is no limit on the total number of variables or outcomes that can be defined.</span></span> <span data-ttu-id="f8a08-112">Ponadto wiele testów może używać tych samych zmiennych testowych do rejestrowania wyników.</span><span class="sxs-lookup"><span data-stu-id="f8a08-112">Additionally, multiple tests can use the same test variables to record results.</span></span>

## <a name="examples-of-test-variables"></a><span data-ttu-id="f8a08-113">Przykłady zmiennych testowych</span><span class="sxs-lookup"><span data-stu-id="f8a08-113">Examples of test variables</span></span>

### <a name="example-1"></a><span data-ttu-id="f8a08-114">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="f8a08-114">Example 1</span></span>

<span data-ttu-id="f8a08-115">Firma produkcyjna wykonuje dwa testy na wyprodukowanych materiałach.</span><span class="sxs-lookup"><span data-stu-id="f8a08-115">A manufacturing company performs two tests on manufactured materials.</span></span> <span data-ttu-id="f8a08-116">W jednym teście poziom pH jest skojarzony z kolorowym paskiem testowym.</span><span class="sxs-lookup"><span data-stu-id="f8a08-116">In one test, the pH level is associated with a color strip.</span></span> <span data-ttu-id="f8a08-117">Dopuszczalne poziomy pH to jaśniejsze kolory, a nieakceptowalne poziomy pH mają ciemniejsze kolory.</span><span class="sxs-lookup"><span data-stu-id="f8a08-117">Acceptable pH levels are in lighter colors, and unacceptable pH levels are in darker colors.</span></span> <span data-ttu-id="f8a08-118">W innym teście jest wykonywanych wiele inspekcji wzrokowych, a pracownicy jakości według własnego uznania stwierdzają, czy towar przechodzi kontrolę wizualną czy nie.</span><span class="sxs-lookup"><span data-stu-id="f8a08-118">In another test, multiple visual inspections are performed, and quality workers use their judgement to determine whether the item passes or fails the visual inspection.</span></span>

### <a name="example-2"></a><span data-ttu-id="f8a08-119">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="f8a08-119">Example 2</span></span>

<span data-ttu-id="f8a08-120">Firma produkująca ciasteczka przeprowadza testy kontrolne na gotowym produkcie.</span><span class="sxs-lookup"><span data-stu-id="f8a08-120">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="f8a08-121">Ten test inspekcji zawiera kilka zmiennych.</span><span class="sxs-lookup"><span data-stu-id="f8a08-121">This inspection test has several variables.</span></span> <span data-ttu-id="f8a08-122">Jedną ze zmiennych jest smak, a jej możliwe wyniki to dobry i zły.</span><span class="sxs-lookup"><span data-stu-id="f8a08-122">One variable is taste, and the possible outcomes for it are good and bad.</span></span> <span data-ttu-id="f8a08-123">Druga zmienna to kolor z wynikami zbyt ciemny, zbyt jasny i prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="f8a08-123">A second variable is color, and the possible outcomes for it are too dark, too light, and correct.</span></span>

## <a name="create-a-test-variable"></a><span data-ttu-id="f8a08-124">Tworzenie zmiennej testowej</span><span class="sxs-lookup"><span data-stu-id="f8a08-124">Create a test variable</span></span>

<span data-ttu-id="f8a08-125">Aby utworzyć zmienną testową, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f8a08-125">Follow these steps to create a test variable.</span></span>

1. <span data-ttu-id="f8a08-126">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Zmienne testowe**.</span><span class="sxs-lookup"><span data-stu-id="f8a08-126">Go to **Inventory management \> Setup \> Quality control \> Test variables**.</span></span>
1. <span data-ttu-id="f8a08-127">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="f8a08-127">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="f8a08-128">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="f8a08-128">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="f8a08-129">**Zmienna** — umożliwia wprowadzenie unikatowego identyfikatora lub nazwy zmiennej.</span><span class="sxs-lookup"><span data-stu-id="f8a08-129">**Variable** – Enter a unique ID or name for the variable.</span></span>
    - <span data-ttu-id="f8a08-130">**Opis** – wprowadź szczegółowy opis zmiennej.</span><span class="sxs-lookup"><span data-stu-id="f8a08-130">**Description** – Enter a detailed description of the variable.</span></span>

1. <span data-ttu-id="f8a08-131">Gdy nowy wiersz jest nadal zaznaczony, wybierz opcję **Wyniki** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="f8a08-131">While the new row is still selected, select **Outcomes** on the Action Pane.</span></span>
1. <span data-ttu-id="f8a08-132">Na stronie **Wyniki zmiennych testowych** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="f8a08-132">On the **Test variable outcomes** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="f8a08-133">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="f8a08-133">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="f8a08-134">**Wynik** — umożliwia wprowadzenie unikatowego identyfikatora lub nazwy wyniku.</span><span class="sxs-lookup"><span data-stu-id="f8a08-134">**Outcome** – Enter a unique ID or name for the outcome.</span></span>
    - <span data-ttu-id="f8a08-135">**Opis** – wprowadź szczegółowy opis wyniku.</span><span class="sxs-lookup"><span data-stu-id="f8a08-135">**Description** – Enter a detailed description of the outcome.</span></span>
    - <span data-ttu-id="f8a08-136">**Stan wyniku** — Dla każdego wyniku przypisuje się stan wyniku *Zaliczony* lub *Niezaliczony*, aby określić, czy test został zaliczony czy niezaliczony, gdy ten wynik zostanie wybrany jako wynik testu.</span><span class="sxs-lookup"><span data-stu-id="f8a08-136">**Outcome status** – Select either *Pass* or *Fail* to indicate whether the test is passed or failed when the outcome is selected as a test result.</span></span>

1. <span data-ttu-id="f8a08-137">Powtórz poprzedni krok dla każdego dodatkowego wyniku.</span><span class="sxs-lookup"><span data-stu-id="f8a08-137">Repeat the previous step for each additional outcome.</span></span> <span data-ttu-id="f8a08-138">Upewnij się, że co najmniej jeden wynik ma stan wyniku *Zaliczony* i co najmniej jeden ma stan wyniku *Niezaliczony*.</span><span class="sxs-lookup"><span data-stu-id="f8a08-138">Make sure that at least one outcome has an outcome status of *Pass* and at least one has an outcome status of *Fail*.</span></span>
1. <span data-ttu-id="f8a08-139">Zamknij strony.</span><span class="sxs-lookup"><span data-stu-id="f8a08-139">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f8a08-140">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f8a08-140">Additional resources</span></span>

- [<span data-ttu-id="f8a08-141">Przyrządy testowe zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="f8a08-141">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="f8a08-142">Testy zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="f8a08-142">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="f8a08-143">Grupy testowe zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="f8a08-143">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
