---
title: Testy zarządzania jakością
description: W tym temacie opisano sposób tworzenia testów, których można używać w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: b88011f486b6582db4727b85d021868899c6abe1
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956788"
---
# <a name="quality-management-tests"></a><span data-ttu-id="99516-103">Testy zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="99516-103">Quality management tests</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99516-104">W tym temacie opisano sposób tworzenia testów, których można używać w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="99516-104">This topic describes how to create tests that can be used for quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="99516-105">Strona **Testy** służy do definiowania i wyświetlania poszczególnych testów decydujących, czy produkty są zgodne ze specyfikacjami jakości.</span><span class="sxs-lookup"><span data-stu-id="99516-105">You use the **Tests** page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="99516-106">Do grupy testowej można przypisać jeden lub więcej testów.</span><span class="sxs-lookup"><span data-stu-id="99516-106">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="99516-107">W takim przypadku określa się również informacje właściwe dla danego testu, takie jak akceptowalne wartości pomiaru.</span><span class="sxs-lookup"><span data-stu-id="99516-107">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="99516-108">Wartości pomiarowe są używane w testach ilościowych.</span><span class="sxs-lookup"><span data-stu-id="99516-108">Measurement values are used for quantitative tests.</span></span> <span data-ttu-id="99516-109">W przypadku testów jakościowych są używane zmienne testowe.</span><span class="sxs-lookup"><span data-stu-id="99516-109">For qualitative tests, test variables are used.</span></span>

- <span data-ttu-id="99516-110">W przypadku testów ilościowych pole **Typ** ma wartość *Liczba całkowita* lub *Ułamek*.</span><span class="sxs-lookup"><span data-stu-id="99516-110">For quantitative tests, the **Type** field is set to *Integer* or *Fraction*.</span></span> <span data-ttu-id="99516-111">Jest również określona jednostka miary.</span><span class="sxs-lookup"><span data-stu-id="99516-111">A unit of measure is also specified.</span></span> <span data-ttu-id="99516-112">Specyfikacje jakości i wyniki testu są wyrażane jako liczby.</span><span class="sxs-lookup"><span data-stu-id="99516-112">Quality specifications and test results are expressed as numbers.</span></span>
- <span data-ttu-id="99516-113">W przypadku testów jakościowych w polu **Typ** jest ustawiona wartość *Opcja*.</span><span class="sxs-lookup"><span data-stu-id="99516-113">For qualitative tests, the **Type** field is set to *Option*.</span></span> <span data-ttu-id="99516-114">Testy jakości wymagają dodatkowych informacji konfiguracyjnych dotyczących zmiennej testowej i jej wyliczonych opcji.</span><span class="sxs-lookup"><span data-stu-id="99516-114">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="99516-115">Specyfikacje jakości i wyniki testu są wyrażane jako liczby.</span><span class="sxs-lookup"><span data-stu-id="99516-115">Quality specifications and test results are expressed according to an outcome.</span></span>

<span data-ttu-id="99516-116">Opcjonalnie można przypisać przyrząd testowy do testu.</span><span class="sxs-lookup"><span data-stu-id="99516-116">You can optionally assign a test instrument to a test.</span></span> <span data-ttu-id="99516-117">Jednak przyrządy testowe nie są wymagane do tworzenia i używania testów ze zleceniami kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="99516-117">However, test instruments aren't required to create and use tests with quality orders.</span></span> <span data-ttu-id="99516-118">Aby uzyskać więcej informacji, zobacz temat [Przyrządy testowe zarządzania kontrolą jakości](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="99516-118">For more information, see [Quality management test instruments](quality-test-instruments.md).</span></span>

<span data-ttu-id="99516-119">Opcjonalnie można także określić jednostkę dla testu, aby wskazać jednostkę miary, w której są rejestrowane wyniki testu.</span><span class="sxs-lookup"><span data-stu-id="99516-119">You can also optionally specify a unit for a test, to indicate the unit of measure that test results are recorded in.</span></span> <span data-ttu-id="99516-120">Na przykład test temperatury może zawierać jednostkę stopni Fahrenheita lub stopni Celsjusza.</span><span class="sxs-lookup"><span data-stu-id="99516-120">For example, a test for temperature might include a unit of either degrees Fahrenheit or degrees Celsius.</span></span>

## <a name="example-of-a-test"></a><span data-ttu-id="99516-121">Przykładowy test</span><span class="sxs-lookup"><span data-stu-id="99516-121">Example of a test</span></span>

<span data-ttu-id="99516-122">Firma produkcyjna wykonuje dwa testy na zakupionym materiale, w tym test ilości dotyczący jakości materiału i test jakości dotyczący uszkodzenia opakowania.</span><span class="sxs-lookup"><span data-stu-id="99516-122">A manufacturing company performs two tests on purchased material: a quantitative test for material quality and a qualitative test for packaging damage.</span></span> <span data-ttu-id="99516-123">Firma definiuje dodatkowe informacje na temat testu jakości w celu określenia zmiennej testowej (na przykład uszkodzone opakowanie) i jej wartości wynikowe.</span><span class="sxs-lookup"><span data-stu-id="99516-123">The company specifies additional information about the qualitative test to define the test variable (for example, damaged packaging) and its outcomes.</span></span> <span data-ttu-id="99516-124">Firma używa strony **Grupy testowe** do przypisania dwóch testów do grupy testowej i do określenia informacji specyficznych dla testu.</span><span class="sxs-lookup"><span data-stu-id="99516-124">The company uses the **Test groups** page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="99516-125">Grupa testów jest przypisywana do zlecenia kontroli jakości, dzięki czemu firma może raportować wyniki testu dla dwóch testów.</span><span class="sxs-lookup"><span data-stu-id="99516-125">The test group is assigned to a quality order so that the company can report test results for the two tests.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="99516-126">Tworzenie testu</span><span class="sxs-lookup"><span data-stu-id="99516-126">Create a test</span></span>

<span data-ttu-id="99516-127">Wykonaj poniższe kroki, aby utworzyć test.</span><span class="sxs-lookup"><span data-stu-id="99516-127">Follow these steps to create a test.</span></span>

1. <span data-ttu-id="99516-128">Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Testy**.</span><span class="sxs-lookup"><span data-stu-id="99516-128">Go to **Inventory management \> Setup \> Quality control \> Tests**.</span></span>
1. <span data-ttu-id="99516-129">W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki.</span><span class="sxs-lookup"><span data-stu-id="99516-129">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="99516-130">Następnie ustaw następujące pola dla nowego wiersza:</span><span class="sxs-lookup"><span data-stu-id="99516-130">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="99516-131">**Test** – wpisz unikatowy identyfikator lub nazwę testu.</span><span class="sxs-lookup"><span data-stu-id="99516-131">**Test** – Enter a unique ID or name for the test.</span></span>
    - <span data-ttu-id="99516-132">**Opis** – wprowadź szczegółowy opis testu.</span><span class="sxs-lookup"><span data-stu-id="99516-132">**Description** – Enter a detailed description of the test.</span></span>
    - <span data-ttu-id="99516-133">**Typ** — Umożliwia wybór typu wyników testu.</span><span class="sxs-lookup"><span data-stu-id="99516-133">**Type** – Select the type of results that the test produces.</span></span> <span data-ttu-id="99516-134">W przypadku testów ilościowych wybierz wartość *Ułamek* lub *Liczba całkowita*.</span><span class="sxs-lookup"><span data-stu-id="99516-134">For quantitative tests, select *Fraction* or *Integer*.</span></span> <span data-ttu-id="99516-135">W przypadku testów jakościowych wybierz opcję *Opcja*.</span><span class="sxs-lookup"><span data-stu-id="99516-135">For qualitative tests, select *Option*.</span></span>
    - <span data-ttu-id="99516-136">**Przyrząd testowy** — należy wybrać [przyrząd testowy](quality-test-instruments.md), który ma być używane w teście.</span><span class="sxs-lookup"><span data-stu-id="99516-136">**Test instrument** – Select a [test instrument](quality-test-instruments.md) that should be used for the test.</span></span>
    - <span data-ttu-id="99516-137">**Jednostka** — w przypadku wybrania w polu **Typ** wartości *Ułamek* lub *Liczba całkowita* (to jest, jeśli test jest testem ilościowym) należy wybrać jednostkę miary, w której mają być rejestrowane wyniki testu.</span><span class="sxs-lookup"><span data-stu-id="99516-137">**Unit** – If you selected *Fraction* or *Integer* in the **Type** field (that is, if the test is a quantitative test), select the unit of measure that test results should be recorded in.</span></span>

1. <span data-ttu-id="99516-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="99516-138">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="99516-139">Po zapisaniu testu nie można już edytować pola **Typ** w siatce.</span><span class="sxs-lookup"><span data-stu-id="99516-139">After you save a test, you can no longer edit the **Type** field in the grid.</span></span> <span data-ttu-id="99516-140">Jeśli trzeba zmienić typ wyników testu, które będą rejestrowane dla testu, wybierz opcję **Zmień typ testu jakości** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="99516-140">If you must change the type of test results that will be recorded for a test, select **Change quality test type** on the Action Pane.</span></span> <span data-ttu-id="99516-141">W oknie dialogowym **Zmień typ testu jakości** ustaw żądany typ w polu **Nowy typ**, a następnie wybierz przycisk **OK**, aby zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="99516-141">In the **Change quality test type** dialog box, set the **New type** field to the desired type, and then select **OK** to close the dialog box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="99516-142">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="99516-142">Additional resources</span></span>

- [<span data-ttu-id="99516-143">Przyrządy testowe zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="99516-143">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="99516-144">Grupy testowe zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="99516-144">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="99516-145">Zmienne testu zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="99516-145">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="99516-146">Powiązania jakości</span><span class="sxs-lookup"><span data-stu-id="99516-146">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
