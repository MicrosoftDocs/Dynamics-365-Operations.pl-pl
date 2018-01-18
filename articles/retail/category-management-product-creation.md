---
title: "Tworzenie kategorii produktu i zarządzanie nimi"
description: "W tym temacie opisano ulepszenia wprowadzone w zarządzaniu dla kategorii produktów detalicznych. Te ulepszenia umożliwiają menedżerom ds. merchandisingu powiązanie hierarchii produktów detalicznych i informacji o zwolnionych produktach."
author: ashishmsft
manager: AnnBe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
ms.search.form: RetailCategoryAndProductWorkspace, RetailCategory
audience: Application User
ms.search.scope: Core, Retail
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: e269f6c3815cea55b69b7eb6a9a65bf7c9e15378
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---

# <a name="product-category-management-and-creation"></a><span data-ttu-id="4f501-104">Tworzenie kategorii produktu i zarządzanie nimi</span><span class="sxs-lookup"><span data-stu-id="4f501-104">Product category management and creation</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="4f501-105">Ulepszenia wprowadzone w zarządzaniu dla kategorii produktów detalicznych umożliwiają menedżerom ds. merchandisingu powiązanie hierarchii produktów detalicznych i informacji o zwolnionych produktach.</span><span class="sxs-lookup"><span data-stu-id="4f501-105">Enhancements that have been made to the management experience for Retail product categories let merchandising managers have a correlation between Retail product hierarchy and released product details.</span></span> <span data-ttu-id="4f501-106">Aby wyświetlić te ulepszenia, w obszarze roboczym **Zarządzanie kategoriami i produktami** wybierz opcję **Hierarchia produktów sieci sprzedaży**, aby otworzyć stronę **Nowa struktura kategorii produktów sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="4f501-106">To view these enhancements, in the **Category & product management**  workspace, select **Retail product hierarchy** to open the **New structure of Retail product category** page.</span></span> 

<span data-ttu-id="4f501-107">W poprzednich wersjach właściwości produktów były podzielone na podstawowe właściwości produktów i właściwości produktów sieci sprzedaży na podstawie zakresu ich zastosowania.</span><span class="sxs-lookup"><span data-stu-id="4f501-107">In previous releases, product properties were divided into Basic product properties and Retail product properties, based on the scope of their applicability.</span></span> <span data-ttu-id="4f501-108">Właściwości produktów sieci sprzedaży były *globalne*.</span><span class="sxs-lookup"><span data-stu-id="4f501-108">Retail product properties were *global*.</span></span> <span data-ttu-id="4f501-109">Inaczej mówią, dla właściwości danego produktu ta sama wartość jest współdzielona we wszystkich firmach.</span><span class="sxs-lookup"><span data-stu-id="4f501-109">In other words, for a given product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="4f501-110">Podstawowe właściwości produktów były *specyficzne dla firmy*.</span><span class="sxs-lookup"><span data-stu-id="4f501-110">Basic product properties were *legal entity–specific*.</span></span> <span data-ttu-id="4f501-111">Inaczej mówiąc, dana właściwość produktu może różnić się w zależności od firmy w zależności od wymagań biznesowych.</span><span class="sxs-lookup"><span data-stu-id="4f501-111">In other words, a given product property might differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="4f501-112">Dzięki tym ulepszeniom, w przypadku właściwości produktu w kategorii produktów sieci sprzedaży, będziemy nadal rozdzielać pola na podstawie ich zastosowania w grupie, aby uwzględnić strukturę szczegółów zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="4f501-112">With these enhancements, for product properties in the Retail product category, we continue to separate the fields, based on their applicability within a group, to reflect the released product details form structure.</span></span>

<span data-ttu-id="4f501-113">Można przełączyć się między zarządzaniem właściwościami specyficznymi dla firmy we wszystkich firmach i zarządzaniem nimi dla określonej firmy.</span><span class="sxs-lookup"><span data-stu-id="4f501-113">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="4f501-114">Wybierz opcję **Wyświetl/edytuj dla wszystkich firm** lub **Wyświetl/edytuj dla określonej firmy** według potrzeb.</span><span class="sxs-lookup"><span data-stu-id="4f501-114">Just select **View/Edit for all legal entities** or **View/Edit for a specific legal entity** as you require.</span></span>

<span data-ttu-id="4f501-115">Menedżerowie ds. merchandisingu mogą także zdefiniować wartości domyślne dla dodatkowego zestawu właściwości produktu na poziomie danej kategorii.</span><span class="sxs-lookup"><span data-stu-id="4f501-115">Merchandising managers can also define default values for an additional set of product properties at the level of an individual category.</span></span> <span data-ttu-id="4f501-116">Te wartości właściwości są dziedziczone przez produkt na podstawie ich skojarzenia z kategorią w momencie tworzenia produktu.</span><span class="sxs-lookup"><span data-stu-id="4f501-116">These property values are inherited by a product, based on their association with a category at the time of product creation.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="4f501-117">Wybieranie właściwości do aktualizacji produktu z formularza kategorii produktów sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="4f501-117">Select properties to update products from the Retail product category form</span></span>

<span data-ttu-id="4f501-118">Można użyć właściwości grupowania logicznego, aby wybrać, które zaktualizowane właściwości produktu powinny być przesyłane do powiązanych produktów.</span><span class="sxs-lookup"><span data-stu-id="4f501-118">You can use logical grouping properties to select which updated product properties should be pushed to associated products.</span></span>

<span data-ttu-id="4f501-119">Menedżerowie ds. merchandisingu mogą zmodyfikować odziedziczone właściwości produktów dla każdego produktu, aby spełnić indywidualne wymagania biznesowe.</span><span class="sxs-lookup"><span data-stu-id="4f501-119">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>

