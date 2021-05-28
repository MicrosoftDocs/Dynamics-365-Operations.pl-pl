---
title: Nie można zastosować szablonu do zwolnionego produktu
description: Nie można zastosować szablonu do zwolnionego produktu.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026806"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a><span data-ttu-id="7d91c-103">Nie możesz zastosować szablonu, aby utworzyć zwolniony produkt</span><span class="sxs-lookup"><span data-stu-id="7d91c-103">You can't apply a template to create a released product</span></span>

<span data-ttu-id="7d91c-104">Numer artykułu z bazy wiedzy: 4612097</span><span class="sxs-lookup"><span data-stu-id="7d91c-104">KB number: 4612097</span></span>

## <a name="symptoms"></a><span data-ttu-id="7d91c-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="7d91c-105">Symptoms</span></span>

<span data-ttu-id="7d91c-106">Podczas tworzenia nowego zwolnionego produktu przy użyciu okna dialogowego **Nowy zwolniony produkt** można wybrać szablon.</span><span class="sxs-lookup"><span data-stu-id="7d91c-106">When you create a new released product by using the **New released product** dialog box, you can select a template.</span></span> <span data-ttu-id="7d91c-107">Szablon powinien dostarczać domyślne ustawienia wielu pól nowego zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="7d91c-107">The template is supposed to provide default settings for many fields of the new released product.</span></span> <span data-ttu-id="7d91c-108">Jednak niektóre lub wszystkie pola nie są ustawiane po wybraniu szablonu.</span><span class="sxs-lookup"><span data-stu-id="7d91c-108">However, some or all of the fields aren't set after you select the template.</span></span>

## <a name="cause"></a><span data-ttu-id="7d91c-109">Powód</span><span class="sxs-lookup"><span data-stu-id="7d91c-109">Cause</span></span>

<span data-ttu-id="7d91c-110">Wiele stron w firmie Microsoft Dynamics 365 Supply Chain Management umożliwia utworzenie szablonu, który określa początkowe ustawienia rekordów wyświetlanych na tych stronach.</span><span class="sxs-lookup"><span data-stu-id="7d91c-110">Many pages in Microsoft Dynamics 365 Supply Chain Management let you create a template that establishes initial settings for the records that are shown on those pages.</span></span> <span data-ttu-id="7d91c-111">Można utworzyć jeden z tych szablonów, wybierając pozycję **Informacje o rekordzie** na karcie **Opcje** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="7d91c-111">You can create one of these templates by selecting **Record info** on the **Options** tab of the Action Pane.</span></span> <span data-ttu-id="7d91c-112">Jednak zwolnione produkty są o wiele bardziej złożone niż większość innych typów rekordów.</span><span class="sxs-lookup"><span data-stu-id="7d91c-112">However, released products are much more complex than most other types of records.</span></span> <span data-ttu-id="7d91c-113">Chociaż można wybrać **informacje o rekordzie** na stronie **Zwolnione produkty**, aby utworzyć szablon, i chociaż można wybrać ten szablon podczas tworzenia zwolnionego produktu, szablon nie będzie dostarczał oczekiwanych wartości pól dla nowego zwolnionego produktu.</span><span class="sxs-lookup"><span data-stu-id="7d91c-113">Although you can select **Record info** on the **Released products** page to create a template, and although you can select that template when you create a released product, the template won't provide the expected field values for the new released product.</span></span> <span data-ttu-id="7d91c-114">W związku z tym nie można używać szablonów „informacji o rekordzie” dla zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="7d91c-114">Therefore, you can't use "record info" templates for released products.</span></span> <span data-ttu-id="7d91c-115">Zamiast tego trzeba utworzyć dedykowane szablony produktów.</span><span class="sxs-lookup"><span data-stu-id="7d91c-115">Instead, you must create dedicated product templates.</span></span>

## <a name="resolution"></a><span data-ttu-id="7d91c-116">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="7d91c-116">Resolution</span></span>

<span data-ttu-id="7d91c-117">Aby utworzyć szablon produktu, należy użyć menu **Szablon** na karcie **Produkt** w okienku akcji, a nie przycisku **Informacje o rekordzie** na karcie **Opcje**.</span><span class="sxs-lookup"><span data-stu-id="7d91c-117">To create a product template, use the **Template** menu on the **Product** tab of the Action Pane, not the **Record info** button on the **Options** tab.</span></span>

1. <span data-ttu-id="7d91c-118">Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.</span><span class="sxs-lookup"><span data-stu-id="7d91c-118">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="7d91c-119">W okienku akcji, na karcie **Produkt** w grupie **Nowy** wybierz pozycję **Szablon**, a następnie wybierz opcję **Utwórz szablon osobisty** lub **Utwórz szablon udostępniony** zgodnie z potrzebą.</span><span class="sxs-lookup"><span data-stu-id="7d91c-119">On the Action Pane, on the **Product** tab, in the **New** group, select **Template**, and then select either **Create personal template** or **Create shared template**, as appropriate.</span></span>
