---
title: "Ponowne wykorzystywanie konfiguracji produktów"
description: "Możesz określić, że chcesz automatycznie ponownie używać istniejącej konfiguracji produktu. Wtedy gdy użytkownik zakończy sesję konfiguracji, system sprawdzi, czy już istnieje konfiguracja odpowiadająca opcjom wybranym przez użytkownika. Jeśli znajdzie pasującą konfigurację, ponownie wykorzysta identyfikator konfiguracji, odnośną listę składową (BOM) i marszrutę."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: c447440c33c1f80c6056974086b90d3b43e8499e
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---

# <a name="reuse-product-configurations"></a><span data-ttu-id="03301-105">Ponowne wykorzystywanie konfiguracji produktów</span><span class="sxs-lookup"><span data-stu-id="03301-105">Reuse product configurations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="03301-106">Możesz określić, że chcesz automatycznie ponownie używać istniejącej konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="03301-106">You can specify that you want to automatically reuse an existing configuration for a product.</span></span> <span data-ttu-id="03301-107">Wtedy gdy użytkownik zakończy sesję konfiguracji, system sprawdzi, czy już istnieje konfiguracja odpowiadająca opcjom wybranym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="03301-107">Then, when a user has completed a configuration session, the system verifies whether a configuration that matches the user’s selections already exists.</span></span> <span data-ttu-id="03301-108">Jeśli znajdzie pasującą konfigurację, ponownie wykorzysta identyfikator konfiguracji, odnośną listę składową (BOM) i marszrutę.</span><span class="sxs-lookup"><span data-stu-id="03301-108">If a matching configuration is found, the configuration ID, corresponding bill of materials (BOM), and route are reused.</span></span>

<a name="requirements-for-reusing-configurations"></a><span data-ttu-id="03301-109">Wymagania dotyczące ponownego wykorzystywania konfiguracji</span><span class="sxs-lookup"><span data-stu-id="03301-109">Requirements for reusing configurations</span></span>
---------------------------------------

<span data-ttu-id="03301-110">Aby umożliwić ponowne wykorzystywanie konfiguracji, należy określić następujące informacje dotyczące składników i atrybutów na stronie **Szczegóły modelu konfiguracji produktu**:</span><span class="sxs-lookup"><span data-stu-id="03301-110">To enable configurations to be reused, you must specify the following information for the components and attributes on the **Product configuration model details** page:</span></span>

-   <span data-ttu-id="03301-111">**Składniki i składniki podrzędne** — Na skróconej karcie **Ogólne** w polu **Użyj ponownie konfiguracji** zaznacz wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="03301-111">**Components and subcomponents** – On the **General** FastTab, in the **Reuse configurations** field, select **Yes**.</span></span>
-   <span data-ttu-id="03301-112">**Atrybuty** — Na skróconej karcie **Atrybuty** zaznacz opcję **Uwzględnij w ponownym użyciu**.</span><span class="sxs-lookup"><span data-stu-id="03301-112">**Attributes** – On the **Attributes** FastTab, select the **Include in reuse** option.</span></span> <span data-ttu-id="03301-113">Ta opcja jest wyświetlana tylko wtedy, gdy odnośny składnik jest włączony do ponownego wykorzystania.</span><span class="sxs-lookup"><span data-stu-id="03301-113">This option appears only when the related component is enabled for reuse.</span></span> <span data-ttu-id="03301-114">Jeśli nie wybierzesz żadnych atrybutów do ponownego wykorzystania, konfiguracja jest zawsze używana ponownie, niezależnie od opcji wybranych przez użytkownika podczas sesji konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="03301-114">If you don't select any attributes for reuse, the configuration is always reused, regardless of the user’s selections during a configuration session.</span></span> <span data-ttu-id="03301-115">Wartości atrybutów w istniejącej konfiguracji muszą odpowiadać opcjom wybranym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="03301-115">The attribute values in the existing configuration must match the user’s selections.</span></span> <span data-ttu-id="03301-116">Na przykład jeśli użytkownik wybierze **Niebieski** jako kolor w trakcie sesji konfiguracji, system zweryfikuje, czy istniejąca konfiguracja składnika ma kolor niebieski.</span><span class="sxs-lookup"><span data-stu-id="03301-116">For example, if the user selects **Blue** as the color during a configuration session, the system verifies whether an existing configuration of the component has the color blue.</span></span>

## <a name="resetting-configuration-reuse"></a><span data-ttu-id="03301-117">Resetowanie ponownego wykorzystywania konfiguracji</span><span class="sxs-lookup"><span data-stu-id="03301-117">Resetting configuration reuse</span></span>
<span data-ttu-id="03301-118">Po zresetowaniu funkcji ponownego wykorzystywania konfiguracji wcześniej utworzone konfiguracje nie są już brane pod uwagę.</span><span class="sxs-lookup"><span data-stu-id="03301-118">When you reset configuration reuse, previously created configurations are no longer considered.</span></span> <span data-ttu-id="03301-119">Funkcję można resetować na przykład w sytuacji, gdy zmieniła się specyfikacja BOM lub marszruta, ale powiązane atrybuty nie uległy zmianie.</span><span class="sxs-lookup"><span data-stu-id="03301-119">You might want to reset configuration reuse if the BOM or route was changed, but no related attributes were changed.</span></span> <span data-ttu-id="03301-120">Resetowanie ponownego używania konfiguracji odbywa się skróconej karcie **Ogólne** dla składnika.</span><span class="sxs-lookup"><span data-stu-id="03301-120">You reset configuration reuse on the **General** FastTab for the component.</span></span>




