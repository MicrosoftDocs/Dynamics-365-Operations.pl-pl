---
title: Widok składnika majątku
description: W tym temacie opisano widok składnika majątku w Zarządzaniu składniami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14dc2cd95a47931ae4941b87205f2104891af404
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208232"
---
# <a name="asset-view"></a><span data-ttu-id="a2015-103">Widok składnika majątku</span><span class="sxs-lookup"><span data-stu-id="a2015-103">Asset view</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a2015-104">W tym temacie opisano widok składnika majątku w Zarządzaniu składniami majątku.</span><span class="sxs-lookup"><span data-stu-id="a2015-104">This topic describes the asset view in Asset Management.</span></span> <span data-ttu-id="a2015-105">Strona **Widok składnika majątku** zawiera aktywne składniki majątku i lokalizacje czynności konserwacyjnych w widoku drzewa.</span><span class="sxs-lookup"><span data-stu-id="a2015-105">The **Asset view** page shows active assets and functional locations in a tree view.</span></span> <span data-ttu-id="a2015-106">W związku z tym można łatwo uzyskać przegląd relacji składników majątku do lokalizacji czynności konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="a2015-106">Therefore, you can easily get an overview of asset relations to functional locations.</span></span> <span data-ttu-id="a2015-107">Ponadto można wyświetlić szczegółowe informacje o lokalizacjach czynności konserwacyjnych, składnikach majątku i powiązanych listach składowych (BOM).</span><span class="sxs-lookup"><span data-stu-id="a2015-107">Additionally, you can view detailed information about functional locations, assets, and related bills of materials (BOMs).</span></span> <span data-ttu-id="a2015-108">Można również uzyskać szybki przegląd aktywnych żądań konserwacji i zleceń pracy, które są związane ze składnikiem majątku.</span><span class="sxs-lookup"><span data-stu-id="a2015-108">You can also get a quick overview of active maintenance requests and work orders that are related to an asset.</span></span>

1. <span data-ttu-id="a2015-109">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Widok składników majątku**.</span><span class="sxs-lookup"><span data-stu-id="a2015-109">Select **Asset management** \> **Common** \> **Assets** \> **Asset view**.</span></span>
2. <span data-ttu-id="a2015-110">Aby zmienić widok wyświetlany na stronie, wybierz nową wartość w polu **Widok.**</span><span class="sxs-lookup"><span data-stu-id="a2015-110">To change the view that is shown on the page, select a new value in the **View** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a2015-111">Domyślny widok wyświetlany po otwarciu strony **Widoku składników majątku** zależy od wartości wybranej w polu **Widok** na karcie **Składniki majątku** strony **Parametry zarządzania składnikami majątku** (**Zarządzanie składnikami majątku** \> **Ustawienia** \> **Parametry zarządzania składnikami majątku**).</span><span class="sxs-lookup"><span data-stu-id="a2015-111">The default view that is shown when you open the **Asset view** page depends on the value that is selected in the **View** field on the **Assets** tab of the **Asset management parameters** page (**Asset management** \> **Setup** \> **Asset management parameters**).</span></span>

<span data-ttu-id="a2015-112">Na skróconej karcie po prawej stronie będą widoczne szczegóły wybranego widoku.</span><span class="sxs-lookup"><span data-stu-id="a2015-112">On the right side of the page, FastTabs shows details of the selected view.</span></span>

<span data-ttu-id="a2015-113">Szlak nawigacyjny widoczny powyżej widoku drzewa pokazuje aktualne zaznaczenie w widoku drzewa.</span><span class="sxs-lookup"><span data-stu-id="a2015-113">The breadcrumb trail that appears above the tree view shows the current selection in the tree view.</span></span> <span data-ttu-id="a2015-114">Ten szlak nawigacyjny używa następującego formatu:</span><span class="sxs-lookup"><span data-stu-id="a2015-114">This breadcrumb trail uses the following format:</span></span>

<span data-ttu-id="a2015-115">Identyfikator lokalizacji czynności konserwacyjnych / Identyfikator lokalizacji czynności konserwacyjnych (jeśli jest więcej niż jedna lokalizacja czynności konserwacyjnych) \> Identyfikator składnika majątku / Identyfikator składnika majątku (jeśli jest więcej niż jeden składnik majątku) — numer elementu.</span><span class="sxs-lookup"><span data-stu-id="a2015-115">Functional location ID / Functional location ID (if there is more than one functional location) \> Asset ID / Asset ID (if there is more than one asset) - Item number.</span></span>

<span data-ttu-id="a2015-116">Jeśli masz wybrany składnik majątku w widoku drzewa, możesz wybrać **Aktywne żądania** lub **Aktywne zlecenia pracy**, aby wyświetlić żądania konserwacji lub zlecenia pracy, które są związane ze składnikiem majątku.</span><span class="sxs-lookup"><span data-stu-id="a2015-116">If you've selected an asset in the tree view, you can select **Active requests** or **Active work orders** to view the maintenance requests or work orders that are related to the asset.</span></span> <span data-ttu-id="a2015-117">Można również wybrać opcję **Otwórz** \> **Lokalizacja czynności konserwacyjnych**, **Składnik majątku** lub **BOM składnika majątku**, aby otworzyć powiązany widok.</span><span class="sxs-lookup"><span data-stu-id="a2015-117">You can also select **Open** \> **Functional location**, **Asset**, or **Asset BOM** to open the related view.</span></span>

<span data-ttu-id="a2015-118">Opcja **Lokalizacje czynności konserwacyjnych składnika majątku**, którą można wybrać w polu **Widok** jest również dostępna w dowolnym wyszukiwaniu składników majątku, w którym można wybrać składnik majątku.</span><span class="sxs-lookup"><span data-stu-id="a2015-118">The **Asset functional locations** option that you can select in the **View** field is also available in any asset lookup where you can select an asset.</span></span> <span data-ttu-id="a2015-119">Widok drzewa jest wyświetlany na karcie **Widok składników majątku** na przykład podczas tworzenia [składnika majątku](../objects/create-an-object.md), żądania konserwacji lub zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="a2015-119">The tree view is shown on an **Asset view** tab, for example, where you [create an asset](../objects/create-an-object.md), create a maintenance request, or create a work order.</span></span>
